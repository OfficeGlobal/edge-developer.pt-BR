---
description: Inserir tecnologias da Web (HTML, CSS e JavaScript) em seus aplicativos nativos com o controle WebView2 do Microsoft Edge
title: Microsoft. Web. WebView2. Core. CoreWebView2WebMessageReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: Microsoft. Web. WebView2, Core, WebView2, WebView, dotnet, WPF, WinForms, app, Edge, CoreWebView2, CoreWebView2Controller, controle do navegador, Edge HTML, Microsoft. Web. WebView2. Core. CoreWebView2WebMessageReceivedEventArgs
ms.openlocfilehash: ab273337307eeef6e8842d337296756877939aff
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011464"
---
# <span data-ttu-id="7b7d4-104">Classe Microsoft. Web. WebView2. Core. CoreWebView2WebMessageReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="7b7d4-104">Microsoft.Web.WebView2.Core.CoreWebView2WebMessageReceivedEventArgs class</span></span> 

<span data-ttu-id="7b7d4-105">Namespace: Microsoft. Web. WebView2. Core </span><span class="sxs-lookup"><span data-stu-id="7b7d4-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="7b7d4-106">Assembly: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="7b7d4-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="7b7d4-107">Args de evento para o evento WebMessageReceived.</span><span class="sxs-lookup"><span data-stu-id="7b7d4-107">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="7b7d4-108">Resumo</span><span class="sxs-lookup"><span data-stu-id="7b7d4-108">Summary</span></span>

 <span data-ttu-id="7b7d4-109">Parte</span><span class="sxs-lookup"><span data-stu-id="7b7d4-109">Members</span></span>                        | <span data-ttu-id="7b7d4-110">Descrições</span><span class="sxs-lookup"><span data-stu-id="7b7d4-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7b7d4-111">Origem</span><span class="sxs-lookup"><span data-stu-id="7b7d4-111">Source</span></span>](#source) | <span data-ttu-id="7b7d4-112">O URI do documento que enviou esta mensagem da Web.</span><span class="sxs-lookup"><span data-stu-id="7b7d4-112">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="7b7d4-113">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="7b7d4-113">WebMessageAsJson</span></span>](#webmessageasjson) | <span data-ttu-id="7b7d4-114">A mensagem postada do conteúdo da WebView para o host convertido em uma cadeia de caracteres JSON.</span><span class="sxs-lookup"><span data-stu-id="7b7d4-114">The message posted from the WebView content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="7b7d4-115">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="7b7d4-115">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="7b7d4-116">Se a mensagem postada do conteúdo WebView para o host for um tipo de cadeia de caracteres, esse método retornará o valor dessa cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7b7d4-116">If the message posted from the WebView content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="7b7d4-117">Parte</span><span class="sxs-lookup"><span data-stu-id="7b7d4-117">Members</span></span>

#### <span data-ttu-id="7b7d4-118">Origem</span><span class="sxs-lookup"><span data-stu-id="7b7d4-118">Source</span></span> 

<span data-ttu-id="7b7d4-119">O URI do documento que enviou esta mensagem da Web.</span><span class="sxs-lookup"><span data-stu-id="7b7d4-119">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="7b7d4-120">[fonte](#source) de cadeia de caracteres pública</span><span class="sxs-lookup"><span data-stu-id="7b7d4-120">public string [Source](#source)</span></span>

#### <span data-ttu-id="7b7d4-121">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="7b7d4-121">WebMessageAsJson</span></span> 

<span data-ttu-id="7b7d4-122">A mensagem postada do conteúdo da WebView para o host convertido em uma cadeia de caracteres JSON.</span><span class="sxs-lookup"><span data-stu-id="7b7d4-122">The message posted from the WebView content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="7b7d4-123">Cadeia de caracteres pública [WebMessageAsJson](#webmessageasjson)</span><span class="sxs-lookup"><span data-stu-id="7b7d4-123">public string [WebMessageAsJson](#webmessageasjson)</span></span>

<span data-ttu-id="7b7d4-124">Use isso para se comunicar por objetos JavaScript.</span><span class="sxs-lookup"><span data-stu-id="7b7d4-124">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="7b7d4-125">Por exemplo, as seguintes chamadas de mensagens de mensagens resultam nos seguintes valores de WebMessageAsJson:</span><span class="sxs-lookup"><span data-stu-id="7b7d4-125">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="7b7d4-126">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="7b7d4-126">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="7b7d4-127">Se a mensagem postada do conteúdo WebView para o host for um tipo de cadeia de caracteres, esse método retornará o valor dessa cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7b7d4-127">If the message posted from the WebView content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="7b7d4-128">[TryGetWebMessageAsString](#trygetwebmessageasstring)de cadeia de caracteres pública ()</span><span class="sxs-lookup"><span data-stu-id="7b7d4-128">public string [TryGetWebMessageAsString](#trygetwebmessageasstring)()</span></span>

<span data-ttu-id="7b7d4-129">Se a mensagem publicada for outro tipo de tipo JavaScript, esse método falhará com E_INVALIDARG.</span><span class="sxs-lookup"><span data-stu-id="7b7d4-129">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="7b7d4-130">Use isso para se comunicar por meio de cadeias de caracteres simples.</span><span class="sxs-lookup"><span data-stu-id="7b7d4-130">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="7b7d4-131">Por exemplo, as seguintes chamadas de mensagens de mensagens resultam nos seguintes valores de WebMessageAsString:</span><span class="sxs-lookup"><span data-stu-id="7b7d4-131">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```
