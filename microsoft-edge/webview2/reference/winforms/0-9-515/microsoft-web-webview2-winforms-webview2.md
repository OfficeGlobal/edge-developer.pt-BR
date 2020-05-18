---
description: Hospedar conteúdo da Web em seu aplicativo Win32 com o controle WebView2 do Microsoft Edge
title: Microsoft Edge WebView2 para aplicativos Win32
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, webview2, WebView, aplicativos Win32, Win32, Edge, ICoreWebView2, ICoreWebView2Controller, controle do navegador, HTML Edge
ms.openlocfilehash: 25ea8367aa9d64d0a1066cf8c1564f4d9c9f05ed
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652352"
---
# <span data-ttu-id="50e20-104">Classe Microsoft. Web. WebView2. WinForms. WebView2</span><span class="sxs-lookup"><span data-stu-id="50e20-104">Microsoft.Web.WebView2.WinForms.WebView2 class</span></span> 

<span data-ttu-id="50e20-105">Namespace: Microsoft. Web. WebView2. WinForms </span><span class="sxs-lookup"><span data-stu-id="50e20-105">Namespace: Microsoft.Web.WebView2.WinForms</span></span>\
<span data-ttu-id="50e20-106">Assembly: Microsoft. Web. WebView2. WinForms. dll</span><span class="sxs-lookup"><span data-stu-id="50e20-106">Assembly: Microsoft.Web.WebView2.WinForms.dll</span></span>

```
class Microsoft.Web.WebView2.WinForms.WebView2
  : public Control
```

<span data-ttu-id="50e20-107">Controle para inserir WebView2 em WinForms.</span><span class="sxs-lookup"><span data-stu-id="50e20-107">Control to embed WebView2 in WinForms.</span></span>

## <span data-ttu-id="50e20-108">Resumo</span><span class="sxs-lookup"><span data-stu-id="50e20-108">Summary</span></span>

 <span data-ttu-id="50e20-109">Parte</span><span class="sxs-lookup"><span data-stu-id="50e20-109">Members</span></span>                        | <span data-ttu-id="50e20-110">Descrições</span><span class="sxs-lookup"><span data-stu-id="50e20-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="50e20-111">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="50e20-111">ContentLoading</span></span>](#contentloading) | <span data-ttu-id="50e20-112">ContentLoading despachos quando uma navegação começa a ser um novo URI e o conteúdo desse URI começa a ser renderizado.</span><span class="sxs-lookup"><span data-stu-id="50e20-112">ContentLoading dispatches after a navigation begins to a new URI and the content of that URI begins to render.</span></span>
[<span data-ttu-id="50e20-113">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="50e20-113">CoreWebView2Ready</span></span>](#corewebview2ready) | <span data-ttu-id="50e20-114">Esse evento é acionado quando o [CoreWebView2](#corewebview2) do controle termina de ser inicializado (independentemente de como a inicialização foi disparada), mas antes de ser usado para qualquer coisa.</span><span class="sxs-lookup"><span data-stu-id="50e20-114">This event is triggered when the control's [CoreWebView2](#corewebview2) has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>
[<span data-ttu-id="50e20-115">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="50e20-115">NavigationCompleted</span></span>](#navigationcompleted) | <span data-ttu-id="50e20-116">O NavigationCompleted despacha após uma navegação do documento de nível superior executa a renderização com êxito ou não.</span><span class="sxs-lookup"><span data-stu-id="50e20-116">NavigationCompleted dispatches after a navigate of the top level document completes rendering either successfully or not.</span></span>
[<span data-ttu-id="50e20-117">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="50e20-117">NavigationStarting</span></span>](#navigationstarting) | <span data-ttu-id="50e20-118">O NavigationStarting despacha antes de uma nova navegação começar para o documento de nível superior do WebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-118">NavigationStarting dispatches before a new navigate starts for the top level document of the WebView2.</span></span>
[<span data-ttu-id="50e20-119">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="50e20-119">SourceChanged</span></span>](#sourcechanged) | <span data-ttu-id="50e20-120">Os despachos SourceChanged após a alteração da propriedade de origem.</span><span class="sxs-lookup"><span data-stu-id="50e20-120">SourceChanged dispatches after the Source property changes.</span></span>
[<span data-ttu-id="50e20-121">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="50e20-121">WebMessageReceived</span></span>](#webmessagereceived) | <span data-ttu-id="50e20-122">WebMessageReceived despachos após conteúdo da Web envia uma mensagem para o host do aplicativo via `chrome.webview.postMessage` .</span><span class="sxs-lookup"><span data-stu-id="50e20-122">WebMessageReceived dispatches after web content sends a message to the app host via `chrome.webview.postMessage`.</span></span>
[<span data-ttu-id="50e20-123">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="50e20-123">CoreWebView2</span></span>](#corewebview2) | <span data-ttu-id="50e20-124">O CoreWebView2 subjacente.</span><span class="sxs-lookup"><span data-stu-id="50e20-124">The underlying CoreWebView2.</span></span>
[<span data-ttu-id="50e20-125">Origem</span><span class="sxs-lookup"><span data-stu-id="50e20-125">Source</span></span>](#source) | <span data-ttu-id="50e20-126">A propriedade Source é o URI do documento de nível superior do WebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-126">The Source property is the URI of the top level document of the WebView2.</span></span>
[<span data-ttu-id="50e20-127">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="50e20-127">ZoomFactor</span></span>](#zoomfactor) | <span data-ttu-id="50e20-128">O fator de zoom para o WebView.</span><span class="sxs-lookup"><span data-stu-id="50e20-128">The zoom factor for the WebView.</span></span>
[<span data-ttu-id="50e20-129">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="50e20-129">CanGoBack</span></span>](#cangoback) | <span data-ttu-id="50e20-130">Retorna verdadeiro se a WebView pode navegar para uma página anterior no histórico de navegação por meio do método GoBack.</span><span class="sxs-lookup"><span data-stu-id="50e20-130">Returns true if the webview can navigate to a previous page in the navigation history via the GoBack method.</span></span>
[<span data-ttu-id="50e20-131">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="50e20-131">CanGoForward</span></span>](#cangoforward) | <span data-ttu-id="50e20-132">Retorna verdadeiro se a WebView pode navegar para uma próxima página no histórico de navegação por meio do método GoForward.</span><span class="sxs-lookup"><span data-stu-id="50e20-132">Returns true if the webview can navigate to a next page in the navigation history via the GoForward method.</span></span>
[<span data-ttu-id="50e20-133">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="50e20-133">EnsureCoreWebView2Async</span></span>](#ensurecorewebview2async) | <span data-ttu-id="50e20-134">Disparar explicitamente a inicialização do [CoreWebView2](#corewebview2)do controle.</span><span class="sxs-lookup"><span data-stu-id="50e20-134">Explicitly trigger initialization of the control's [CoreWebView2](#corewebview2).</span></span>
[<span data-ttu-id="50e20-135">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="50e20-135">ExecuteScriptAsync</span></span>](#executescriptasync) | <span data-ttu-id="50e20-136">Executa o script fornecido no documento de nível superior do WebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-136">Executes the provided script in the top level document of the WebView2.</span></span>
[<span data-ttu-id="50e20-137">GoBack</span><span class="sxs-lookup"><span data-stu-id="50e20-137">GoBack</span></span>](#goback) | <span data-ttu-id="50e20-138">Navegar para a página anterior no histórico de navegação.</span><span class="sxs-lookup"><span data-stu-id="50e20-138">Navigate to the previous page in navigation history.</span></span>
[<span data-ttu-id="50e20-139">GoForward</span><span class="sxs-lookup"><span data-stu-id="50e20-139">GoForward</span></span>](#goforward) | <span data-ttu-id="50e20-140">Navegar para a próxima página no histórico de navegação.</span><span class="sxs-lookup"><span data-stu-id="50e20-140">Navigate to the next page in navigation history.</span></span>
[<span data-ttu-id="50e20-141">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="50e20-141">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="50e20-142">Renderize o HTML fornecido como o documento de nível superior do WebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-142">Render the provided HTML as the top level document of the WebView2.</span></span>
[<span data-ttu-id="50e20-143">Recarregar</span><span class="sxs-lookup"><span data-stu-id="50e20-143">Reload</span></span>](#reload) | <span data-ttu-id="50e20-144">Recarregue o documento de nível superior da WebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-144">Reload the top level document of the WebView2.</span></span>
[<span data-ttu-id="50e20-145">Parar</span><span class="sxs-lookup"><span data-stu-id="50e20-145">Stop</span></span>](#stop) | <span data-ttu-id="50e20-146">Parar a navegação em andamento no WebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-146">Stop any in progress navigation in the WebView2.</span></span>
[<span data-ttu-id="50e20-147">WebView2</span><span class="sxs-lookup"><span data-stu-id="50e20-147">WebView2</span></span>](#webview2) | <span data-ttu-id="50e20-148">Crie um novo controle WinForms do WebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-148">Create a new WebView2 WinForms control.</span></span>
[<span data-ttu-id="50e20-149">OnEnter</span><span class="sxs-lookup"><span data-stu-id="50e20-149">OnEnter</span></span>](#onenter) | <span data-ttu-id="50e20-150">Manipulador de foco protegido.</span><span class="sxs-lookup"><span data-stu-id="50e20-150">Protected focus handler.</span></span>
[<span data-ttu-id="50e20-151">OnSizeChanged</span><span class="sxs-lookup"><span data-stu-id="50e20-151">OnSizeChanged</span></span>](#onsizechanged) | <span data-ttu-id="50e20-152">Manipulador SizeChanged protegido.</span><span class="sxs-lookup"><span data-stu-id="50e20-152">Protected SizeChanged handler.</span></span>
[<span data-ttu-id="50e20-153">OnVisibleChanged</span><span class="sxs-lookup"><span data-stu-id="50e20-153">OnVisibleChanged</span></span>](#onvisiblechanged) | <span data-ttu-id="50e20-154">Manipulador de Visibilidadechanged protegido.</span><span class="sxs-lookup"><span data-stu-id="50e20-154">Protected VisibilityChanged handler.</span></span>

## <span data-ttu-id="50e20-155">Parte</span><span class="sxs-lookup"><span data-stu-id="50e20-155">Members</span></span>

#### <span data-ttu-id="50e20-156">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="50e20-156">ContentLoading</span></span> 

<span data-ttu-id="50e20-157">ContentLoading despachos quando uma navegação começa a ser um novo URI e o conteúdo desse URI começa a ser renderizado.</span><span class="sxs-lookup"><span data-stu-id="50e20-157">ContentLoading dispatches after a navigation begins to a new URI and the content of that URI begins to render.</span></span>

> <span data-ttu-id="50e20-158">< do evento público EventHandler CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)</span><span class="sxs-lookup"><span data-stu-id="50e20-158">public event EventHandler< CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)</span></span>

<span data-ttu-id="50e20-159">Isso equivale ao evento ContentLoading no CoreWebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-159">This is equivalent to the ContentLoading event on the CoreWebView2.</span></span> <span data-ttu-id="50e20-160">Consulte a documentação do CoreWebView2. ContentLoading para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50e20-160">See CoreWebView2.ContentLoading documentation for more information.</span></span>

#### <span data-ttu-id="50e20-161">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="50e20-161">CoreWebView2Ready</span></span> 

<span data-ttu-id="50e20-162">Esse evento é acionado quando o [CoreWebView2](#corewebview2) do controle termina de ser inicializado (independentemente de como a inicialização foi disparada), mas antes de ser usado para qualquer coisa.</span><span class="sxs-lookup"><span data-stu-id="50e20-162">This event is triggered when the control's [CoreWebView2](#corewebview2) has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>

> <span data-ttu-id="50e20-163">evento público EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span><span class="sxs-lookup"><span data-stu-id="50e20-163">public event EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span></span>

<span data-ttu-id="50e20-164">Você deve tratar esse evento se precisar executar operações de configuração únicas no CoreWebView2 que você deseja afetar todos os seus usos (por exemplo, adicionar manipuladores de eventos, definir configurações, instalar scripts de criação de documentos, adicionar objetos host).</span><span class="sxs-lookup"><span data-stu-id="50e20-164">You should handle this event if you need to perform one time setup operations on the CoreWebView2 which you want to affect all of its usages (e.g. adding event handlers, configuring settings, installing document creation scripts, adding host objects).</span></span>

<span data-ttu-id="50e20-165">Esse evento não fornece argumentos, e o remetente será o controle WebView2, cuja propriedade CoreWebView2 agora será válida (ou seja, não nula) pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="50e20-165">This event doesn't provide any arguments, and the sender will be the WebView2 control, whose CoreWebView2 property will now be valid (i.e. non-null) for the first time.</span></span>

#### <span data-ttu-id="50e20-166">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="50e20-166">NavigationCompleted</span></span> 

<span data-ttu-id="50e20-167">O NavigationCompleted despacha após uma navegação do documento de nível superior executa a renderização com êxito ou não.</span><span class="sxs-lookup"><span data-stu-id="50e20-167">NavigationCompleted dispatches after a navigate of the top level document completes rendering either successfully or not.</span></span>

> <span data-ttu-id="50e20-168">< do evento público EventHandler CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)</span><span class="sxs-lookup"><span data-stu-id="50e20-168">public event EventHandler< CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)</span></span>

<span data-ttu-id="50e20-169">Isso equivale ao evento NavigationCompleted no CoreWebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-169">This is equivalent to the NavigationCompleted event on the CoreWebView2.</span></span> <span data-ttu-id="50e20-170">Consulte a documentação do CoreWebView2. NavigationCompleted para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50e20-170">See CoreWebView2.NavigationCompleted documentation for more information.</span></span>

#### <span data-ttu-id="50e20-171">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="50e20-171">NavigationStarting</span></span> 

<span data-ttu-id="50e20-172">O NavigationStarting despacha antes de uma nova navegação começar para o documento de nível superior do WebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-172">NavigationStarting dispatches before a new navigate starts for the top level document of the WebView2.</span></span>

> <span data-ttu-id="50e20-173">< do evento público EventHandler CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)</span><span class="sxs-lookup"><span data-stu-id="50e20-173">public event EventHandler< CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)</span></span>

<span data-ttu-id="50e20-174">Isso equivale ao evento NavigationStarting no CoreWebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-174">This is equivalent to the NavigationStarting event on the CoreWebView2.</span></span> <span data-ttu-id="50e20-175">Consulte a documentação do CoreWebView2. NavigationStarting para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50e20-175">See CoreWebView2.NavigationStarting documentation for more information.</span></span>

#### <span data-ttu-id="50e20-176">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="50e20-176">SourceChanged</span></span> 

<span data-ttu-id="50e20-177">Os despachos SourceChanged após a alteração da propriedade de origem.</span><span class="sxs-lookup"><span data-stu-id="50e20-177">SourceChanged dispatches after the Source property changes.</span></span>

> <span data-ttu-id="50e20-178">evento público EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)</span><span class="sxs-lookup"><span data-stu-id="50e20-178">public event EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)</span></span>

<span data-ttu-id="50e20-179">Isso pode ocorrer durante uma navegação ou, caso contrário, o script na página alterará o URI do documento.</span><span class="sxs-lookup"><span data-stu-id="50e20-179">This may happen during a navigation or if otherwise the script in the page changes the URI of the document.</span></span> <span data-ttu-id="50e20-180">Isso equivale ao evento SourceChanged no CoreWebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-180">This is equivalent to the SourceChanged event on the CoreWebView2.</span></span> <span data-ttu-id="50e20-181">Consulte documentação da CoreWebView2. SourceChanged para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50e20-181">See CoreWebView2.SourceChanged documentation for more information.</span></span>

#### <span data-ttu-id="50e20-182">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="50e20-182">WebMessageReceived</span></span> 

<span data-ttu-id="50e20-183">WebMessageReceived despachos após conteúdo da Web envia uma mensagem para o host do aplicativo via `chrome.webview.postMessage` .</span><span class="sxs-lookup"><span data-stu-id="50e20-183">WebMessageReceived dispatches after web content sends a message to the app host via `chrome.webview.postMessage`.</span></span>

> <span data-ttu-id="50e20-184">< do evento público EventHandler CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span><span class="sxs-lookup"><span data-stu-id="50e20-184">public event EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span></span>

<span data-ttu-id="50e20-185">Isso equivale ao evento WebMessageReceived no CoreWebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-185">This is equivalent to the WebMessageReceived event on the CoreWebView2.</span></span> <span data-ttu-id="50e20-186">Consulte a documentação do CoreWebView2. WebMessageReceived para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50e20-186">See CoreWebView2.WebMessageReceived documentation for more information.</span></span>

#### <span data-ttu-id="50e20-187">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="50e20-187">CoreWebView2</span></span> 

<span data-ttu-id="50e20-188">O CoreWebView2 subjacente.</span><span class="sxs-lookup"><span data-stu-id="50e20-188">The underlying CoreWebView2.</span></span>

> <span data-ttu-id="50e20-189">CoreWebView2 público [CoreWebView2](#corewebview2)</span><span class="sxs-lookup"><span data-stu-id="50e20-189">public CoreWebView2 [CoreWebView2](#corewebview2)</span></span>

<span data-ttu-id="50e20-190">Use essa propriedade para executar mais operações no conteúdo do WebView2 do que é exposto no WebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-190">Use this property to perform more operations on the WebView2 content than is exposed on the WebView2.</span></span> <span data-ttu-id="50e20-191">Esse valor é nulo até ser inicializado.</span><span class="sxs-lookup"><span data-stu-id="50e20-191">This value is null until it is initialized.</span></span> <span data-ttu-id="50e20-192">Você pode forçar o CoreWebView2 subjacente a inicializar por meio do método InitializeAsync.</span><span class="sxs-lookup"><span data-stu-id="50e20-192">You can force the underlying CoreWebView2 to initialize via the InitializeAsync method.</span></span>

#### <span data-ttu-id="50e20-193">Origem</span><span class="sxs-lookup"><span data-stu-id="50e20-193">Source</span></span> 

<span data-ttu-id="50e20-194">A propriedade Source é o URI do documento de nível superior do WebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-194">The Source property is the URI of the top level document of the WebView2.</span></span>

> <span data-ttu-id="50e20-195">[fonte](#source) de URI público</span><span class="sxs-lookup"><span data-stu-id="50e20-195">public Uri [Source](#source)</span></span>

<span data-ttu-id="50e20-196">A configuração da fonte equivale a chamar CoreWebView2. Navigate.</span><span class="sxs-lookup"><span data-stu-id="50e20-196">Setting the Source is equivalent to calling CoreWebView2.Navigate.</span></span> <span data-ttu-id="50e20-197">Se a CoreWebView2 subjacente ainda não tiver sido inicializada, essa propriedade será "About: blank".</span><span class="sxs-lookup"><span data-stu-id="50e20-197">If the underlying CoreWebView2 is not yet initialized, this property is "about:blank".</span></span> <span data-ttu-id="50e20-198">Se a propriedade estiver definida como um URI não absoluto ou nulo, a propriedade permanecerá inalterada.</span><span class="sxs-lookup"><span data-stu-id="50e20-198">If the property is set to a non-absolute URI or null, the property remains unchanged.</span></span> <span data-ttu-id="50e20-199">Consulte CoreWebView2. Navegue na documentação para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50e20-199">See CoreWebView2.Navigate documentation for more information.</span></span>

#### <span data-ttu-id="50e20-200">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="50e20-200">ZoomFactor</span></span> 

<span data-ttu-id="50e20-201">O fator de zoom para o WebView.</span><span class="sxs-lookup"><span data-stu-id="50e20-201">The zoom factor for the WebView.</span></span>

> <span data-ttu-id="50e20-202">[ZoomFactors](#zoomfactor) duplos públicos</span><span class="sxs-lookup"><span data-stu-id="50e20-202">public double [ZoomFactor](#zoomfactor)</span></span>

#### <span data-ttu-id="50e20-203">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="50e20-203">CanGoBack</span></span> 

<span data-ttu-id="50e20-204">Retorna verdadeiro se a WebView pode navegar para uma página anterior no histórico de navegação por meio do método GoBack.</span><span class="sxs-lookup"><span data-stu-id="50e20-204">Returns true if the webview can navigate to a previous page in the navigation history via the GoBack method.</span></span>

> <span data-ttu-id="50e20-205">bool público [CanGoBack](#cangoback)</span><span class="sxs-lookup"><span data-stu-id="50e20-205">public bool [CanGoBack](#cangoback)</span></span>

<span data-ttu-id="50e20-206">Isso equivale à propriedade CanGoBack no CoreWebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-206">This is equivalent to the CanGoBack property on the CoreWebView2.</span></span> <span data-ttu-id="50e20-207">Se a CoreWebView2 subjacente ainda não tiver sido inicializada, essa propriedade será falsa.</span><span class="sxs-lookup"><span data-stu-id="50e20-207">If the underlying CoreWebView2 is not yet initialized, this property is false.</span></span> <span data-ttu-id="50e20-208">Consulte a documentação do CoreWebView2. CanGoBack para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50e20-208">See CoreWebView2.CanGoBack documentation for more information.</span></span>

#### <span data-ttu-id="50e20-209">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="50e20-209">CanGoForward</span></span> 

<span data-ttu-id="50e20-210">Retorna verdadeiro se a WebView pode navegar para uma próxima página no histórico de navegação por meio do método GoForward.</span><span class="sxs-lookup"><span data-stu-id="50e20-210">Returns true if the webview can navigate to a next page in the navigation history via the GoForward method.</span></span>

> <span data-ttu-id="50e20-211">Public bool [CanGoForward](#cangoforward)</span><span class="sxs-lookup"><span data-stu-id="50e20-211">public bool [CanGoForward](#cangoforward)</span></span>

<span data-ttu-id="50e20-212">Isso equivale à propriedade CanGoForward no CoreWebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-212">This is equivalent to the CanGoForward property on the CoreWebView2.</span></span> <span data-ttu-id="50e20-213">Se a CoreWebView2 subjacente ainda não tiver sido inicializada, essa propriedade será falsa.</span><span class="sxs-lookup"><span data-stu-id="50e20-213">If the underlying CoreWebView2 is not yet initialized, this property is false.</span></span> <span data-ttu-id="50e20-214">Consulte a documentação do CoreWebView2. CanGoForward para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50e20-214">See CoreWebView2.CanGoForward documentation for more information.</span></span>

#### <span data-ttu-id="50e20-215">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="50e20-215">EnsureCoreWebView2Async</span></span> 

<span data-ttu-id="50e20-216">Disparar explicitamente a inicialização do [CoreWebView2](#corewebview2)do controle.</span><span class="sxs-lookup"><span data-stu-id="50e20-216">Explicitly trigger initialization of the control's [CoreWebView2](#corewebview2).</span></span>

> <span data-ttu-id="50e20-217">[EnsureCoreWebView2Async](#ensurecorewebview2async)de tarefas públicas (ambiente CoreWebView2Environment)</span><span class="sxs-lookup"><span data-stu-id="50e20-217">public Task [EnsureCoreWebView2Async](#ensurecorewebview2async)(CoreWebView2Environment environment)</span></span>

##### <span data-ttu-id="50e20-218">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="50e20-218">Parameters</span></span>
* `environment` <span data-ttu-id="50e20-219">Um CoreWebView2Environment pré-criado que deve ser usado para criar o CoreWebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-219">A pre-created CoreWebView2Environment that should be used to create the CoreWebView2.</span></span> <span data-ttu-id="50e20-220">Criar seu próprio ambiente permite que você controle várias opções que afetam como a CoreWebView2 é inicializada.</span><span class="sxs-lookup"><span data-stu-id="50e20-220">Creating your own environment gives you control over several options that affect how the CoreWebView2 is initialized.</span></span> <span data-ttu-id="50e20-221">Se você passar NULL (o valor padrão), um ambiente padrão será criado e usado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="50e20-221">If you pass null (the default value) then a default environment will be created and used automatically.</span></span> 

##### <span data-ttu-id="50e20-222">Devolver</span><span class="sxs-lookup"><span data-stu-id="50e20-222">Returns</span></span>
<span data-ttu-id="50e20-223">Uma tarefa que representa o processo de inicialização em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="50e20-223">A Task that represents the background initialization process.</span></span> <span data-ttu-id="50e20-224">Quando a tarefa for concluída, a propriedade CoreWebView2 estará disponível para uso (ou seja, não nulo).</span><span class="sxs-lookup"><span data-stu-id="50e20-224">When the task completes then the CoreWebView2 property will be available for use (i.e. non-null).</span></span> <span data-ttu-id="50e20-225">Observe que o evento [CoreWebView2Ready](#corewebview2ready) do controle será invocado antes da conclusão da tarefa.</span><span class="sxs-lookup"><span data-stu-id="50e20-225">Note that the control's [CoreWebView2Ready](#corewebview2ready) event will be invoked before the task completes.</span></span> 

<span data-ttu-id="50e20-226">Chamar esse método momentos adicionais não terão efeito (qualquer ambiente especificado será ignorado) e retornará a mesma tarefa que a primeira chamada.</span><span class="sxs-lookup"><span data-stu-id="50e20-226">Calling this method additional times will have no effect (any specified environment is ignored) and return the same Task as the first call.</span></span> <span data-ttu-id="50e20-227">Chamar esse método após a inicialização foi disparada implicitamente, definindo a propriedade [Source](#source) não terá nenhum efeito (qualquer ambiente especificado é ignorado) e simplesmente retornar uma tarefa representando essa inicialização já em andamento.</span><span class="sxs-lookup"><span data-stu-id="50e20-227">Calling this method after initialization has been implicitly triggered by setting the [Source](#source) property will have no effect (any specified environment is ignored) and simply return a Task representing that initialization already in progress.</span></span> 

##### <span data-ttu-id="50e20-228">Exceções</span><span class="sxs-lookup"><span data-stu-id="50e20-228">Exceptions</span></span>
* `System.InvalidOperationException` <span data-ttu-id="50e20-229">Lançada quando invocada do thread que não é da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="50e20-229">Thrown when invoked from non-UI thread.</span></span>

#### <span data-ttu-id="50e20-230">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="50e20-230">ExecuteScriptAsync</span></span> 

<span data-ttu-id="50e20-231">Executa o script fornecido no documento de nível superior do WebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-231">Executes the provided script in the top level document of the WebView2.</span></span>

> <span data-ttu-id="50e20-232">Cadeia de caracteres de< de tarefa assíncrona pública > [ExecuteScriptAsync](#executescriptasync)(script de cadeia de caracteres)</span><span class="sxs-lookup"><span data-stu-id="50e20-232">public async Task< string > [ExecuteScriptAsync](#executescriptasync)(string script)</span></span>

<span data-ttu-id="50e20-233">Isso equivale ao método ExecuteScriptAsync no CoreWebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-233">This is equivalent to the ExecuteScriptAsync method on the CoreWebView2.</span></span> <span data-ttu-id="50e20-234">Se o CoreWebView2 subjacente ainda não tiver sido inicializado, esse método lançará um InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="50e20-234">If the underlying CoreWebView2 is not yet initialized, this method throws an InvalidOperationException.</span></span> <span data-ttu-id="50e20-235">Consulte a documentação do CoreWebView2. ExecuteScriptAsync para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50e20-235">See CoreWebView2.ExecuteScriptAsync documentation for more information.</span></span>

#### <span data-ttu-id="50e20-236">GoBack</span><span class="sxs-lookup"><span data-stu-id="50e20-236">GoBack</span></span> 

<span data-ttu-id="50e20-237">Navegar para a página anterior no histórico de navegação.</span><span class="sxs-lookup"><span data-stu-id="50e20-237">Navigate to the previous page in navigation history.</span></span>

> <span data-ttu-id="50e20-238">public void [(](#goback)) public void</span><span class="sxs-lookup"><span data-stu-id="50e20-238">public void [GoBack](#goback)()</span></span>

<span data-ttu-id="50e20-239">Isso equivale ao método GoBack no CoreWebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-239">This is equivalent to the GoBack method on the CoreWebView2.</span></span> <span data-ttu-id="50e20-240">Se o CoreWebView2 subjacente ainda não tiver sido inicializado, esse método não fará nada.</span><span class="sxs-lookup"><span data-stu-id="50e20-240">If the underlying CoreWebView2 is not yet initialized, this method does nothing.</span></span> <span data-ttu-id="50e20-241">Consulte a documentação do CoreWebView2. GoBack para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50e20-241">See CoreWebView2.GoBack documentation for more information.</span></span>

#### <span data-ttu-id="50e20-242">GoForward</span><span class="sxs-lookup"><span data-stu-id="50e20-242">GoForward</span></span> 

<span data-ttu-id="50e20-243">Navegar para a próxima página no histórico de navegação.</span><span class="sxs-lookup"><span data-stu-id="50e20-243">Navigate to the next page in navigation history.</span></span>

> <span data-ttu-id="50e20-244">public void [GoForward](#goforward)()</span><span class="sxs-lookup"><span data-stu-id="50e20-244">public void [GoForward](#goforward)()</span></span>

<span data-ttu-id="50e20-245">Isso equivale ao método GoForward no CoreWebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-245">This is equivalent to the GoForward method on the CoreWebView2.</span></span> <span data-ttu-id="50e20-246">Se o CoreWebView2 subjacente ainda não tiver sido inicializado, esse método não fará nada.</span><span class="sxs-lookup"><span data-stu-id="50e20-246">If the underlying CoreWebView2 is not yet initialized, this method does nothing.</span></span> <span data-ttu-id="50e20-247">Consulte a documentação do CoreWebView2. GoForward para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50e20-247">See CoreWebView2.GoForward documentation for more information.</span></span>

#### <span data-ttu-id="50e20-248">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="50e20-248">NavigateToString</span></span> 

<span data-ttu-id="50e20-249">Renderize o HTML fornecido como o documento de nível superior do WebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-249">Render the provided HTML as the top level document of the WebView2.</span></span>

> <span data-ttu-id="50e20-250">public void [NavigateToString](#navigatetostring)(cadeia de caracteres htmlContent)</span><span class="sxs-lookup"><span data-stu-id="50e20-250">public void [NavigateToString](#navigatetostring)(string htmlContent)</span></span>

<span data-ttu-id="50e20-251">Isso equivale ao método NavigateToString no CoreWebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-251">This is equivalent to the NavigateToString method on the CoreWebView2.</span></span> <span data-ttu-id="50e20-252">Se o CoreWebView2 subjacente ainda não tiver sido inicializado, esse método lançará um InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="50e20-252">If the underlying CoreWebView2 is not yet initialized, this method throws an InvalidOperationException.</span></span> <span data-ttu-id="50e20-253">Consulte a documentação do CoreWebView2. NavigateToString para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50e20-253">See CoreWebView2.NavigateToString documentation for more information.</span></span>

#### <span data-ttu-id="50e20-254">Recarregar</span><span class="sxs-lookup"><span data-stu-id="50e20-254">Reload</span></span> 

<span data-ttu-id="50e20-255">Recarregue o documento de nível superior da WebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-255">Reload the top level document of the WebView2.</span></span>

> <span data-ttu-id="50e20-256">recarregamento [Reload](#reload)nulo público ()</span><span class="sxs-lookup"><span data-stu-id="50e20-256">public void [Reload](#reload)()</span></span>

<span data-ttu-id="50e20-257">Isso equivale ao método reload no CoreWebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-257">This is equivalent to the Reload method on the CoreWebView2.</span></span> <span data-ttu-id="50e20-258">Se o CoreWebView2 subjacente ainda não tiver sido inicializado, esse método lançará um InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="50e20-258">If the underlying CoreWebView2 is not yet initialized, this method throws an InvalidOperationException.</span></span> <span data-ttu-id="50e20-259">Consulte CoreWebView2. recarregue a documentação para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50e20-259">See CoreWebView2.Reload documentation for more information.</span></span>

#### <span data-ttu-id="50e20-260">Parar</span><span class="sxs-lookup"><span data-stu-id="50e20-260">Stop</span></span> 

<span data-ttu-id="50e20-261">Parar a navegação em andamento no WebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-261">Stop any in progress navigation in the WebView2.</span></span>

> <span data-ttu-id="50e20-262">[Stop](#stop)void Public ()</span><span class="sxs-lookup"><span data-stu-id="50e20-262">public void [Stop](#stop)()</span></span>

<span data-ttu-id="50e20-263">Isso equivale ao método Stop no CoreWebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-263">This is equivalent to the Stop method on the CoreWebView2.</span></span> <span data-ttu-id="50e20-264">Se o CoreWebView2 subjacente ainda não tiver sido inicializado, esse método não fará nada.</span><span class="sxs-lookup"><span data-stu-id="50e20-264">If the underlying CoreWebView2 is not yet initialized, this method does nothing.</span></span> <span data-ttu-id="50e20-265">Consulte CoreWebView2. pare a documentação para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50e20-265">See CoreWebView2.Stop documentation for more information.</span></span>

#### <span data-ttu-id="50e20-266">WebView2</span><span class="sxs-lookup"><span data-stu-id="50e20-266">WebView2</span></span> 

<span data-ttu-id="50e20-267">Crie um novo controle WinForms do WebView2.</span><span class="sxs-lookup"><span data-stu-id="50e20-267">Create a new WebView2 WinForms control.</span></span>

> <span data-ttu-id="50e20-268">[WebView2](#webview2)público ()</span><span class="sxs-lookup"><span data-stu-id="50e20-268">public [WebView2](#webview2)()</span></span>

<span data-ttu-id="50e20-269">Após a construção, a propriedade CoreWebView2 é NULL.</span><span class="sxs-lookup"><span data-stu-id="50e20-269">After construction the CoreWebView2 property is null.</span></span> <span data-ttu-id="50e20-270">Chame [EnsureCoreWebView2Async](#ensurecorewebview2async) para inicializar o CoreWebView2 subjacente.</span><span class="sxs-lookup"><span data-stu-id="50e20-270">Call [EnsureCoreWebView2Async](#ensurecorewebview2async) to initialize the underlying CoreWebView2.</span></span>

#### <span data-ttu-id="50e20-271">OnEnter</span><span class="sxs-lookup"><span data-stu-id="50e20-271">OnEnter</span></span> 

<span data-ttu-id="50e20-272">Manipulador de foco protegido.</span><span class="sxs-lookup"><span data-stu-id="50e20-272">Protected focus handler.</span></span>

> <span data-ttu-id="50e20-273">Protected override void [OnEnter](#onenter)(EventArgs e)</span><span class="sxs-lookup"><span data-stu-id="50e20-273">protected override void [OnEnter](#onenter)(EventArgs e)</span></span>

#### <span data-ttu-id="50e20-274">OnSizeChanged</span><span class="sxs-lookup"><span data-stu-id="50e20-274">OnSizeChanged</span></span> 

<span data-ttu-id="50e20-275">Manipulador SizeChanged protegido.</span><span class="sxs-lookup"><span data-stu-id="50e20-275">Protected SizeChanged handler.</span></span>

> <span data-ttu-id="50e20-276">proteção contra substituição void [OnSizeChanged](#onsizechanged)(EventArgs e)</span><span class="sxs-lookup"><span data-stu-id="50e20-276">protected override void [OnSizeChanged](#onsizechanged)(EventArgs e)</span></span>

#### <span data-ttu-id="50e20-277">OnVisibleChanged</span><span class="sxs-lookup"><span data-stu-id="50e20-277">OnVisibleChanged</span></span> 

<span data-ttu-id="50e20-278">Manipulador de Visibilidadechanged protegido.</span><span class="sxs-lookup"><span data-stu-id="50e20-278">Protected VisibilityChanged handler.</span></span>

> <span data-ttu-id="50e20-279">proteção contra substituição nula [OnVisibleChanged](#onvisiblechanged)(EventArgs e)</span><span class="sxs-lookup"><span data-stu-id="50e20-279">protected override void [OnVisibleChanged](#onvisiblechanged)(EventArgs e)</span></span>
