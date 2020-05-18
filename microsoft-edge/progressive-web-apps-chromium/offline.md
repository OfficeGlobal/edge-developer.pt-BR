---
title: Suporte a conectividade offline e de rede em aplicativos Web progressivos
description: Saiba como usar tecnologias de suporte para criar experiências resilientes para atender às diferentes condições da rede.
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/15/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: pwa
keywords: aplicativos Web progressivos, PWA, Edge, JavaScript, Windows, UWP, Microsoft Store
ms.openlocfilehash: 58ffb8e9ae596dec4b99143a3061995a6598ce44
ms.sourcegitcommit: d9cc829deb709b0866f6b43a5f4733682ddae5ca
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2020
ms.locfileid: "10659304"
---
# <span data-ttu-id="f5c8d-104">Suporte a conectividade offline e de rede em aplicativos Web progressivos</span><span class="sxs-lookup"><span data-stu-id="f5c8d-104">Offline and network connectivity support in Progressive Web Apps</span></span>

<span data-ttu-id="f5c8d-105">Por muitos anos, as organizações se relutam em investir muito em software baseado na Web em um software nativo porque os aplicativos da Web dependem de conexões de rede estáveis.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-105">For many years organizations were reluctant to invest heavily in web-based software over native software because web applications depended on stable network connections.</span></span> <span data-ttu-id="f5c8d-106">Hoje, a plataforma da Web agora oferece opções robustas que permitem aos usuários continuarem a trabalhar, mesmo se a conexão de rede ficar instável ou ficar completamente offline.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-106">Today, the web platform now offers robust options that enable users to continue working, even if the network connection becomes unstable or goes completely offline.</span></span>

## <span data-ttu-id="f5c8d-107">Usar o cache para melhorar o desempenho do PWAs</span><span class="sxs-lookup"><span data-stu-id="f5c8d-107">Use the caching to improve performance of PWAs</span></span>

<span data-ttu-id="f5c8d-108">Com a introdução de [trabalhadores de serviço][MDNServiceWorker], a plataforma da Web adicionou a `Cache` API para fornecer acesso a recursos gerenciados em cache.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-108">With the introduction of [Service Workers][MDNServiceWorker], the web platform added the `Cache` API to provide access to managed cached resources.</span></span> <span data-ttu-id="f5c8d-109">Essa API baseada em promessa permite que os desenvolvedores armazenem e recuperem muitos recursos da Web, HTML, CSS, JavaScript, imagens, JSON e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-109">This Promise-based API allows developers to store and retrieve many web resources—HTML, CSS, JavaScript, images, JSON, and so on.</span></span> <span data-ttu-id="f5c8d-110">Geralmente, a API do cache é usada dentro do contexto de um trabalhador de serviço, mas também está disponível no thread principal do `window` objeto.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-110">Usually, the Cache API is used within the context of a Service Worker, but it is also available in the main thread on the `window` object.</span></span>

<span data-ttu-id="f5c8d-111">Um uso comum para a `Cache` API é armazenar previamente em cache recursos críticos quando um trabalhador de serviço é instalado, conforme mostrado no trecho de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-111">One common use for the `Cache` API is to pre-cache critical resources when a Service Worker is installed, as shown in the following code snippet.</span></span>  

```javascript
self.addEventListener( "install", function( event ){
    event.waitUntil(
        caches.open( "static-cache" )
              .then(function( cache ){
            return cache.addAll([
                "/css/main.css",
                "/js/main.js",
                "/img/favicon.png",
                "/offline/"
            ]);
        })
    );
});
```  

<span data-ttu-id="f5c8d-112">Esse código, executado durante o evento ciclo de vida do trabalhador do serviço `install` , abre um cache chamado `static-cache` e, quando ele tem um ponteiro para o cache, adiciona quatro recursos a ele usando o `addAll()` método.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-112">This code, which runs during the Service Worker `install` life cycle event, opens a cache named `static-cache` and then, when it has a pointer to the cache, adds four resources to it using the `addAll()` method.</span></span>  <span data-ttu-id="f5c8d-113">Geralmente, a abordagem é combinada com a recuperação do cache durante um `fetch` evento</span><span class="sxs-lookup"><span data-stu-id="f5c8d-113">Often the approach is coupled with cache retrieval during a `fetch` event</span></span>   

```javascript
self.addEventListener( "fetch", event => {
    const request = event.request,
                    url = request.url;
    
    // If we are requesting an HTML page.
    if ( request.headers.get("Accept").includes("text/html") ) {
        event.respondWith(
            // Check the cache first to see if the asset exists, and if it does, return the cached asset.
            caches.match( request )
                  .then( cached_result => {
                if ( cached_result ) {
                    return cached_result;
                }
                // If the asset is not in the cache, fallback to a network request for the asset, and proceed to cache the result.
                return fetch( request )
                       .then( response => {
                    const copy = response.clone();
                    // Wait until the response we received is added to the cache.
                    event.waitUntil(
                        caches.open( "pages" )
                              .then( cache => {
                            return cache.put( request, response );
                        });
                    );
                    return response;
                })
                // If the network is unavailable to make a request, pull the offline page out of the cache.
                .catch(() => caches.match( "/offline/" ));
            })
        ); // end respondWith
    } // end if HTML
});
```  

<span data-ttu-id="f5c8d-114">O trecho de código é executado no trabalho do serviço sempre que o navegador faz uma `fetch` solicitação para esse site.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-114">The code snippet runs within the Service Worker whenever the browser makes a `fetch` request for this site.</span></span> <span data-ttu-id="f5c8d-115">Nesse evento, há uma instrução condicional que é executada se a solicitação for para um arquivo HTML.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-115">Within that event, there is a conditional statement that runs if the request is for an HTML file.</span></span> <span data-ttu-id="f5c8d-116">O trabalhador do serviço verifica se o arquivo já existe em qualquer cache \ (usando o `match()` método \).</span><span class="sxs-lookup"><span data-stu-id="f5c8d-116">The Service Worker checks to see if the file already exists in any cache \(using the `match()` method\).</span></span> <span data-ttu-id="f5c8d-117">Se a solicitação existir no cache, esse resultado será retornado em cache.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-117">If the request exists in the cache, that cached result is returned.</span></span> <span data-ttu-id="f5c8d-118">Caso contrário, um novo `fetch` para esse recurso é executado, uma cópia da resposta é armazenada em cache para mais tarde, e a resposta é retornada.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-118">If not, a new `fetch` for that resource is run, a copy of the response is cached for later, and the response is returned.</span></span> <span data-ttu-id="f5c8d-119">Se a `fetch` rede falhar porque a rede está indisponível, a página offline será retornada do cache.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-119">If the `fetch` fails because the network is unavailable, the offline page is returned from the cache.</span></span>

<span data-ttu-id="f5c8d-120">Esta introdução simples mostra como usar o cache em seu aplicativo Web progressivo (PWA).</span><span class="sxs-lookup"><span data-stu-id="f5c8d-120">This simple introduction shows how to use caching in your progressive web app (PWA).</span></span> <span data-ttu-id="f5c8d-121">Cada PWA é diferente e pode usar estratégias de cache diferentes.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-121">Each PWA is different and may use different caching strategies.</span></span> <span data-ttu-id="f5c8d-122">Seu código pode parecer diferente, e você pode usar estratégias de cache diferentes para rotas diferentes no mesmo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-122">Your code may look different, and you may use different caching strategies for different routes within the same application.</span></span>

## <span data-ttu-id="f5c8d-123">Use o IndexedDB no seu PWA para armazenar dados estruturados</span><span class="sxs-lookup"><span data-stu-id="f5c8d-123">Use IndexedDB in your PWA to store structured data</span></span>

`IndexedDB` <span data-ttu-id="f5c8d-124">é uma API para armazenar dados estruturados.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-124">is an API for storing structured data.</span></span> <span data-ttu-id="f5c8d-125">Semelhante à `Cache` API, ele também é assíncrono, o que significa que você pode usá-lo no thread principal ou em funcionários da Web, como funcionários de serviço.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-125">Similar to the `Cache` API, it is also asynchronous, which means you may use it in the main thread or with Web Workers such as Service Workers.</span></span> <span data-ttu-id="f5c8d-126">Use a `IndexedDB` API para armazenar uma quantidade significativa de dados estruturados no cliente ou dados binários, como objetos de mídia criptografados.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-126">Use the `IndexedDB` API for storing a significant amount of structured data on the client, or binary data, such as encrypted media objects.</span></span> <span data-ttu-id="f5c8d-127">Para obter mais informações, consulte [MDN Primer on using IndexedDB][MDNIndexeddbApiUsing].</span><span class="sxs-lookup"><span data-stu-id="f5c8d-127">For more information, see [MDN primer on using IndexedDB][MDNIndexeddbApiUsing].</span></span>

## <span data-ttu-id="f5c8d-128">Entender as opções de armazenamento para PWAs</span><span class="sxs-lookup"><span data-stu-id="f5c8d-128">Understand storage options for PWAs</span></span>

<span data-ttu-id="f5c8d-129">Às vezes, você pode precisar armazenar pequenas quantidades de dados para fornecer uma melhor experiência offline para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-129">Sometimes you may need to store small amounts of data in order to provide a better offline experience for your users.</span></span> <span data-ttu-id="f5c8d-130">Se esse for o caso, você pode encontrar a simplicidade do sistema de par de valor chave do armazenamento na Web para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-130">If that is the case, you may find the simplicity of the key-value pair system of web storage meets your needs.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="f5c8d-131">O armazenamento da Web é um processo síncrono e não está disponível para uso em threads de trabalho, como funcionários de serviço.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-131">Web Storage is a synchronous process and is not available for use within worker threads such as Service Workers.</span></span> <span data-ttu-id="f5c8d-132">Uso pesado pode criar problemas de desempenho para seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-132">Heavy usage may create performance issues for your application.</span></span> 


<span data-ttu-id="f5c8d-133">Há dois tipos de armazenamento na Web: `localStorage` e `sessionStorage` .</span><span class="sxs-lookup"><span data-stu-id="f5c8d-133">There are 2 types of Web Storage: `localStorage` and `sessionStorage`.</span></span> <span data-ttu-id="f5c8d-134">Cada um é mantido como um repositório de dados separado isolado para o domínio que o criou.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-134">Each is maintained as a separate data store isolated to the domain that created it.</span></span> `sessionStorage` <span data-ttu-id="f5c8d-135">persiste apenas pela duração da sessão de navegação (por exemplo, enquanto o navegador está aberto, o que inclui atualização e restaurações).</span><span class="sxs-lookup"><span data-stu-id="f5c8d-135">persists only for the duration of the browsing session (for example, while the browser is open, which includes refresh and restores).</span></span> `localStorage` <span data-ttu-id="f5c8d-136">persiste até que os dados sejam removidos pelo código, pelo usuário ou pelo navegador (por exemplo, quando houver armazenamento limitado disponível).</span><span class="sxs-lookup"><span data-stu-id="f5c8d-136">persists until the data is removed by the code, the user, or the browser (for example, when there is limited storage available).</span></span> <span data-ttu-id="f5c8d-137">O trecho de código a seguir mostra como usar `localStorage` , o que é semelhante ao `sessionStorage` usado.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-137">The following code snippet shows how to use `localStorage`, which is similar to how `sessionStorage` is used.</span></span>

```javascript
var data = {
    title: document.querySelector("[property='og:title']").getAttribute("content"),
    description: document.querySelector( "meta[name='description']" ).getAttribute("content")
};
localStorage.setItem( window.location, JSON.stringify(data) );
```  

<span data-ttu-id="f5c8d-138">Este trecho de código captura metadados sobre a página atual e armazena-os em um objeto JavaScript.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-138">This code snippet grabs metadata about the current page and stores it in a JavaScript object.</span></span> <span data-ttu-id="f5c8d-139">Em seguida, ele armazena esse valor como JSON em `localStorage` uso do `setItem()` método e atribui uma chave igual à `window.location` URL atual.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-139">Then it stores that value as JSON in `localStorage` using the `setItem()` method, and assigns a key equal to the current `window.location` URL.</span></span> <span data-ttu-id="f5c8d-140">Você pode recuperar as informações `localStorage` usando o `getItem()` método.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-140">You may retrieve the information from `localStorage` using the `getItem()` method.</span></span> 

<span data-ttu-id="f5c8d-141">O trecho de código a seguir mostra como usar o armazenamento em cache `localstorage` para enumerar páginas armazenadas em cache e extrair metadados para executar uma tarefa, como criar uma lista de links.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-141">The following code snippet shows how to use caching with `localstorage` to enumerate cached pages and extract metadata to perform a task, such as building a list of links.</span></span>

```javascript
caches.open( "pages" )
      .then( cache => {
    cache.keys()
         .then( keys => {
        if ( keys.length )
        {
            keys.forEach( insertOfflineLink );
        }
    })
});

function insertOfflineLink( request ) {
    var data = JSON.parse( localStorage.getItem( request.url ) );
    // If data exists and this page is not an offline page, assuming that offline pages have the word offline in the URL.
    if ( data && request.url.indexOf('offline') < 0  )
    {
        // Build a link and insert it into the page.
    }
}
```  

<span data-ttu-id="f5c8d-142">O `insertOfflineLink()` método passa a URL da solicitação para o `localStorage.getItem()` método para recuperar os metadados armazenados.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-142">The `insertOfflineLink()` method passes the URL of the request into the `localStorage.getItem()` method to retrieve any stored metadata.</span></span> <span data-ttu-id="f5c8d-143">Os dados recuperados são verificados para ver se ele existe e, em caso afirmativo, uma ação pode ser tomada nos dados, como a criação e a inserção da marcação para exibi-la.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-143">The retrieved data is checked to see if it exists, and if it does, an action can be taken on the data, such as building and inserting the markup to display it.</span></span>

## <span data-ttu-id="f5c8d-144">Testar conexões de rede no PWA</span><span class="sxs-lookup"><span data-stu-id="f5c8d-144">Test for network connections in your PWA</span></span>

<span data-ttu-id="f5c8d-145">Além de armazenar informações para uso offline, é útil saber quando uma conexão de rede está disponível para sincronizar dados ou informar aos usuários que o status da rede foi alterado.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-145">In addition to storing information for offline use, it is helpful to know when a network connection is available in order to synchronize data or inform users that the network status has changed.</span></span> <span data-ttu-id="f5c8d-146">Use as opções a seguir para testar a conectividade de rede.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-146">Use the following options to test for network connectivity.</span></span>

### <span data-ttu-id="f5c8d-147">Navigator. onLine</span><span class="sxs-lookup"><span data-stu-id="f5c8d-147">navigator.onLine</span></span>  

<span data-ttu-id="f5c8d-148">A `navigator.onLine` propriedade é um booliano que permite que você saiba o status atual da rede.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-148">The `navigator.onLine` property is a boolean that lets you know the current status of the network.</span></span> <span data-ttu-id="f5c8d-149">Se o valor for `true` , o usuário estará online, caso contrário, o usuário estará offline.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-149">If the value is `true`, the user is online, otherwise the user is offline.</span></span>

### <span data-ttu-id="f5c8d-150">Eventos online e offline</span><span class="sxs-lookup"><span data-stu-id="f5c8d-150">Online and Offline Events</span></span>  

<span data-ttu-id="f5c8d-151">Saber se a rede está disponível é útil, mas você pode querer fazer uma ação quando a conectividade da rede mudar.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-151">Knowing whether the network is available is helpful, but you may want to take action  when your network connectivity changes.</span></span> <span data-ttu-id="f5c8d-152">Nessa situação, talvez você queira ouvir e executar ações em resposta a eventos de rede.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-152">In this situation, you may want to listen and take action in response to network events.</span></span> <span data-ttu-id="f5c8d-153">Os eventos estão disponíveis nos `window` elementos, `document` e `document.body` como exibidos no trecho de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-153">The events are available on the `window`, `document`, and `document.body` elements as displayed in the following code snippet.</span></span>

```javascript
window.addEventListener("online",  function(){
    console.log("You are online!");
});
window.addEventListener("offline", function(){
    console.log("Oh no, you lost your network connection.");
});
```  

## <span data-ttu-id="f5c8d-154">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f5c8d-154">See also</span></span>  

<span data-ttu-id="f5c8d-155">Para saber mais sobre como gerenciar cenários offline, consulte as páginas a seguir.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-155">To learn more about managing offline scenarios, see the following pages.</span></span>  

*   [<span data-ttu-id="f5c8d-156">Cache</span><span class="sxs-lookup"><span data-stu-id="f5c8d-156">Cache</span></span>][MDNCache]  
*   [<span data-ttu-id="f5c8d-157">IndexedDB</span><span class="sxs-lookup"><span data-stu-id="f5c8d-157">IndexedDB</span></span>][MDNIndexeddbApi]  
*   [<span data-ttu-id="f5c8d-158">Trabalhador do serviço</span><span class="sxs-lookup"><span data-stu-id="f5c8d-158">Service Worker</span></span>][MDNServiceWorker]  
*   [<span data-ttu-id="f5c8d-159">Armazenamento na Web</span><span class="sxs-lookup"><span data-stu-id="f5c8d-159">Web Storage</span></span>][MDNWebStorageApi]  
*   [<span data-ttu-id="f5c8d-160">Navigator. onLine</span><span class="sxs-lookup"><span data-stu-id="f5c8d-160">navigator.onLine</span></span>][MDNNavigatoronline]  
*   [<span data-ttu-id="f5c8d-161">Eventos online e offline</span><span class="sxs-lookup"><span data-stu-id="f5c8d-161">Online and Offline Events</span></span>][MDNNavigatoronlineOfflineEvents]  
*   [<span data-ttu-id="f5c8d-162">Solicitação com intuito: estratégias de cache na época de PWAs</span><span class="sxs-lookup"><span data-stu-id="f5c8d-162">Request with Intent: Caching Strategies in the Age of PWAs</span></span>][AlistapartRequestIntentCachingStrategiesAgePwas]

<!-- links -->  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "Cache | MDN"  
[MDNIndexeddbApi]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API "API IndexedDB | MDN"  
[MDNIndexeddbApiUsing]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB "Usando a API IndexDb-IndexDB | MDN"  
[MDNServiceWorker]: https://developer.mozilla.org/docs/Web/API/ServiceWorker "Serviço de serviço | MDN"  
[MDNWebStorageApi]: https://developer.mozilla.org/docs/Web/API/Web_Storage_API "API de armazenamento da Web | MDN"  
[MDNNavigatoronline]: https://developer.mozilla.org/docs/Web/API/NavigatorOnLine "NavigatorOnLine | MDN"  
[MDNNavigatoronlineOfflineEvents]: https://developer.mozilla.org/docs/Web/API/NavigatorOnLine/Online_and_offline_events "Eventos online e offline-NavigatorOnLine | MDN"  

[AbookapartGoingOffline]: https://abookapart.com/products/going-offline "Como ficar offline por Jeremy Keith | Um livro distante"  

[AlistapartRequestIntentCachingStrategiesAgePwas]: https://alistapart.com/article/request-with-intent-caching-strategies-in-the-age-of-pwas "Solicitação com intuito: estratégias de cache na época de PWAs por Aaron Gustafson | Uma lista separada"  