---
description: Inserir tecnologias da Web (HTML, CSS e JavaScript) em seus aplicativos nativos com o controle WebView2 do Microsoft Edge
title: WebView2 Win32 C++ ICoreWebView2WebMessageReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, webview2, WebView, aplicativos Win32, Win32, Edge, ICoreWebView2, ICoreWebView2Controller, controle do navegador, HTML Edge, ICoreWebView2WebMessageReceivedEventArgs
ms.openlocfilehash: 1a541bc5c735f67013464347781de5163a7c01b2
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011593"
---
# <span data-ttu-id="e5f71-104">interface ICoreWebView2WebMessageReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="e5f71-104">interface ICoreWebView2WebMessageReceivedEventArgs</span></span> 

```
interface ICoreWebView2WebMessageReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="e5f71-105">Args de evento para o evento WebMessageReceived.</span><span class="sxs-lookup"><span data-stu-id="e5f71-105">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="e5f71-106">Resumo</span><span class="sxs-lookup"><span data-stu-id="e5f71-106">Summary</span></span>

 <span data-ttu-id="e5f71-107">Parte</span><span class="sxs-lookup"><span data-stu-id="e5f71-107">Members</span></span>                        | <span data-ttu-id="e5f71-108">Descrições</span><span class="sxs-lookup"><span data-stu-id="e5f71-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e5f71-109">get_Source</span><span class="sxs-lookup"><span data-stu-id="e5f71-109">get_Source</span></span>](#get_source) | <span data-ttu-id="e5f71-110">O URI do documento que enviou esta mensagem da Web.</span><span class="sxs-lookup"><span data-stu-id="e5f71-110">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="e5f71-111">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="e5f71-111">get_WebMessageAsJson</span></span>](#get_webmessageasjson) | <span data-ttu-id="e5f71-112">A mensagem postada do conteúdo da WebView para o host convertido em uma cadeia de caracteres JSON.</span><span class="sxs-lookup"><span data-stu-id="e5f71-112">The message posted from the WebView content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="e5f71-113">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="e5f71-113">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="e5f71-114">Se a mensagem postada do conteúdo WebView para o host for um tipo de cadeia de caracteres, esse método retornará o valor dessa cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e5f71-114">If the message posted from the WebView content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="e5f71-115">Parte</span><span class="sxs-lookup"><span data-stu-id="e5f71-115">Members</span></span>

#### <span data-ttu-id="e5f71-116">get_Source</span><span class="sxs-lookup"><span data-stu-id="e5f71-116">get_Source</span></span> 

<span data-ttu-id="e5f71-117">O URI do documento que enviou esta mensagem da Web.</span><span class="sxs-lookup"><span data-stu-id="e5f71-117">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="e5f71-118">[get_Source](#get_source)público HRESULT (fonte LPWSTR \*)</span><span class="sxs-lookup"><span data-stu-id="e5f71-118">public HRESULT [get_Source](#get_source)(LPWSTR \* source)</span></span>

#### <span data-ttu-id="e5f71-119">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="e5f71-119">get_WebMessageAsJson</span></span> 

<span data-ttu-id="e5f71-120">A mensagem postada do conteúdo da WebView para o host convertido em uma cadeia de caracteres JSON.</span><span class="sxs-lookup"><span data-stu-id="e5f71-120">The message posted from the WebView content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="e5f71-121">público HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR \* WebMessageAsJson)</span><span class="sxs-lookup"><span data-stu-id="e5f71-121">public HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR \* webMessageAsJson)</span></span>

<span data-ttu-id="e5f71-122">Use isso para se comunicar por objetos JavaScript.</span><span class="sxs-lookup"><span data-stu-id="e5f71-122">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="e5f71-123">Por exemplo, as seguintes chamadas de mensagens de mensagens resultam nos seguintes valores de WebMessageAsJson:</span><span class="sxs-lookup"><span data-stu-id="e5f71-123">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="e5f71-124">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="e5f71-124">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="e5f71-125">Se a mensagem postada do conteúdo WebView para o host for um tipo de cadeia de caracteres, esse método retornará o valor dessa cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e5f71-125">If the message posted from the WebView content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="e5f71-126">Public HRESULT [TryGetWebMessageAsString](#trygetwebmessageasstring)(LPWSTR \* webMessageAsString)</span><span class="sxs-lookup"><span data-stu-id="e5f71-126">public HRESULT [TryGetWebMessageAsString](#trygetwebmessageasstring)(LPWSTR \* webMessageAsString)</span></span>

<span data-ttu-id="e5f71-127">Se a mensagem publicada for outro tipo de tipo JavaScript, esse método falhará com E_INVALIDARG.</span><span class="sxs-lookup"><span data-stu-id="e5f71-127">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="e5f71-128">Use isso para se comunicar por meio de cadeias de caracteres simples.</span><span class="sxs-lookup"><span data-stu-id="e5f71-128">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="e5f71-129">Por exemplo, as seguintes chamadas de mensagens de mensagens resultam nos seguintes valores de WebMessageAsString:</span><span class="sxs-lookup"><span data-stu-id="e5f71-129">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```
