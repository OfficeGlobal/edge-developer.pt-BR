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
ms.openlocfilehash: d43cbe741cc9cd8b027a21115133db9377a95658
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652536"
---
# <span data-ttu-id="007d9-104">interface IWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="007d9-104">interface IWebView2Deferral</span></span> 

> [!NOTE]
> <span data-ttu-id="007d9-105">Essa interface pode ser alterada ou indisponível para versões posteriores SDK da versão 0.8.355.</span><span class="sxs-lookup"><span data-stu-id="007d9-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="007d9-106">Consulte a [referência](../../../webview2-api-reference.md) para obter a referência da API mais recente.</span><span class="sxs-lookup"><span data-stu-id="007d9-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="007d9-107">Essa interface é usada para concluir adiamentos em argumentos de evento que dão suporte a obter adiamentos por meio do método.</span><span class="sxs-lookup"><span data-stu-id="007d9-107">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="007d9-108">Resumo</span><span class="sxs-lookup"><span data-stu-id="007d9-108">Summary</span></span>

 <span data-ttu-id="007d9-109">Parte</span><span class="sxs-lookup"><span data-stu-id="007d9-109">Members</span></span>                        | <span data-ttu-id="007d9-110">Descrições</span><span class="sxs-lookup"><span data-stu-id="007d9-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="007d9-111">Concluída</span><span class="sxs-lookup"><span data-stu-id="007d9-111">Complete</span></span>](#complete) | <span data-ttu-id="007d9-112">Conclui o evento adiado associado.</span><span class="sxs-lookup"><span data-stu-id="007d9-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="007d9-113">Parte</span><span class="sxs-lookup"><span data-stu-id="007d9-113">Members</span></span>

#### <span data-ttu-id="007d9-114">Concluída</span><span class="sxs-lookup"><span data-stu-id="007d9-114">Complete</span></span> 

<span data-ttu-id="007d9-115">Conclui o evento adiado associado.</span><span class="sxs-lookup"><span data-stu-id="007d9-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="007d9-116">público HRESULT [concluído](#complete)()</span><span class="sxs-lookup"><span data-stu-id="007d9-116">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="007d9-117">Concluir só deve ser chamado uma vez para cada adiamento tirado.</span><span class="sxs-lookup"><span data-stu-id="007d9-117">Complete should only be called once for each deferral taken.</span></span>
