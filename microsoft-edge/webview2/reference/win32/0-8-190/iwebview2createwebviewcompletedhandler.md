---
description: Hospedar conteúdo da Web em seu aplicativo Win32 com o controle WebView2 do Microsoft Edge
title: Microsoft Edge WebView2 para aplicativos Win32
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, webview2, WebView, aplicativos Win32, Win32, Edge
ms.openlocfilehash: 2788a18898da1f878520f4c4eb072c1a8b43375b
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652365"
---
# <span data-ttu-id="6fc8c-104">interface IWebView2CreateWebViewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="6fc8c-104">interface IWebView2CreateWebViewCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="6fc8c-105">Essa interface pode ser alterada ou indisponível para versões posteriores SDK da versão 0.8.355.</span><span class="sxs-lookup"><span data-stu-id="6fc8c-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="6fc8c-106">Consulte a [referência](../../../webview2-api-reference.md) para obter a referência da API mais recente.</span><span class="sxs-lookup"><span data-stu-id="6fc8c-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2CreateWebViewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="6fc8c-107">O chamador implementa essa interface para receber a WebView criada via WebView.</span><span class="sxs-lookup"><span data-stu-id="6fc8c-107">The caller implements this interface to receive the WebView created via CreateWebView.</span></span>

## <span data-ttu-id="6fc8c-108">Resumo</span><span class="sxs-lookup"><span data-stu-id="6fc8c-108">Summary</span></span>

 <span data-ttu-id="6fc8c-109">Parte</span><span class="sxs-lookup"><span data-stu-id="6fc8c-109">Members</span></span>                        | <span data-ttu-id="6fc8c-110">Descrições</span><span class="sxs-lookup"><span data-stu-id="6fc8c-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6fc8c-111">Invocar</span><span class="sxs-lookup"><span data-stu-id="6fc8c-111">Invoke</span></span>](#invoke) | <span data-ttu-id="6fc8c-112">Chamado para fornecer o implementador com o status de conclusão e o resultado da chamada de método assíncrono correspondente.</span><span class="sxs-lookup"><span data-stu-id="6fc8c-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="6fc8c-113">Parte</span><span class="sxs-lookup"><span data-stu-id="6fc8c-113">Members</span></span>

#### <span data-ttu-id="6fc8c-114">Invocar</span><span class="sxs-lookup"><span data-stu-id="6fc8c-114">Invoke</span></span> 

<span data-ttu-id="6fc8c-115">Chamado para fornecer o implementador com o status de conclusão e o resultado da chamada de método assíncrono correspondente.</span><span class="sxs-lookup"><span data-stu-id="6fc8c-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="6fc8c-116">[chamada](#invoke)a Public HRESULT (resultado HRESULT,[IWebView2WebView](IWebView2WebView.md) \* WebView)</span><span class="sxs-lookup"><span data-stu-id="6fc8c-116">public HRESULT [Invoke](#invoke)(HRESULT result,[IWebView2WebView](IWebView2WebView.md) \* webView)</span></span>
