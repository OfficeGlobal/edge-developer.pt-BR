---
description: Hospedar conteúdo da Web em seu aplicativo Win32 com o controle WebView2 do Microsoft Edge
title: Microsoft Edge WebView2 para aplicativos Win32
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, webview2, WebView, aplicativos Win32, Win32, Edge, ICoreWebView2, ICoreWebView2Host, controle do navegador, HTML Edge
ms.openlocfilehash: 1d2956aee178c2bdc581d51a93006e14cfb539e3
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652511"
---
# <span data-ttu-id="27f58-104">interface ICoreWebView2CreateCoreWebView2HostCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="27f58-104">interface ICoreWebView2CreateCoreWebView2HostCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="27f58-105">Essa interface pode ser alterada ou indisponível para versões posteriores SDK da versão 0.9.430.</span><span class="sxs-lookup"><span data-stu-id="27f58-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="27f58-106">Consulte a [referência](../../../webview2-api-reference.md) para obter a referência da API mais recente.</span><span class="sxs-lookup"><span data-stu-id="27f58-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2CreateCoreWebView2HostCompletedHandler
  : public IUnknown
```

<span data-ttu-id="27f58-107">O chamador implementa essa interface para receber a CoreWebView2Host criada via CreateCoreWebView2Host.</span><span class="sxs-lookup"><span data-stu-id="27f58-107">The caller implements this interface to receive the CoreWebView2Host created via CreateCoreWebView2Host.</span></span>

## <span data-ttu-id="27f58-108">Resumo</span><span class="sxs-lookup"><span data-stu-id="27f58-108">Summary</span></span>

 <span data-ttu-id="27f58-109">Parte</span><span class="sxs-lookup"><span data-stu-id="27f58-109">Members</span></span>                        | <span data-ttu-id="27f58-110">Descrições</span><span class="sxs-lookup"><span data-stu-id="27f58-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="27f58-111">Invocar</span><span class="sxs-lookup"><span data-stu-id="27f58-111">Invoke</span></span>](#invoke) | <span data-ttu-id="27f58-112">Chamado para fornecer o implementador com o status de conclusão e o resultado da chamada de método assíncrono correspondente.</span><span class="sxs-lookup"><span data-stu-id="27f58-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="27f58-113">Parte</span><span class="sxs-lookup"><span data-stu-id="27f58-113">Members</span></span>

#### <span data-ttu-id="27f58-114">Invocar</span><span class="sxs-lookup"><span data-stu-id="27f58-114">Invoke</span></span> 

<span data-ttu-id="27f58-115">Chamado para fornecer o implementador com o status de conclusão e o resultado da chamada de método assíncrono correspondente.</span><span class="sxs-lookup"><span data-stu-id="27f58-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="27f58-116">[chamada](#invoke)a Public HRESULT (resultado HRESULT,[ICoreWebView2Host](ICoreWebView2Host.md) \* created_host)</span><span class="sxs-lookup"><span data-stu-id="27f58-116">public HRESULT [Invoke](#invoke)(HRESULT result,[ICoreWebView2Host](ICoreWebView2Host.md) \* created_host)</span></span>
