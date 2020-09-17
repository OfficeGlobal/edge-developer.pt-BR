---
description: Inserir tecnologias da Web (HTML, CSS e JavaScript) em seus aplicativos nativos com o controle WebView2 do Microsoft Edge
title: WebView2 Win32 C++ ICoreWebView2DevToolsProtocolEventReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, webview2, WebView, aplicativos Win32, Win32, Edge, ICoreWebView2, ICoreWebView2Controller, controle do navegador, HTML Edge, ICoreWebView2DevToolsProtocolEventReceivedEventArgs
ms.openlocfilehash: 079b7840689fbeb2931a22f72ad78c1ce0f590b8
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011599"
---
# <span data-ttu-id="10c95-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="10c95-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="10c95-105">Args de evento para o evento DevToolsProtocolEventReceived.</span><span class="sxs-lookup"><span data-stu-id="10c95-105">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="10c95-106">Resumo</span><span class="sxs-lookup"><span data-stu-id="10c95-106">Summary</span></span>

 <span data-ttu-id="10c95-107">Parte</span><span class="sxs-lookup"><span data-stu-id="10c95-107">Members</span></span>                        | <span data-ttu-id="10c95-108">Descrições</span><span class="sxs-lookup"><span data-stu-id="10c95-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="10c95-109">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="10c95-109">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="10c95-110">O objeto de parâmetro do evento DevToolsProtocol correspondente representado como uma cadeia de caracteres JSON.</span><span class="sxs-lookup"><span data-stu-id="10c95-110">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="10c95-111">Parte</span><span class="sxs-lookup"><span data-stu-id="10c95-111">Members</span></span>

#### <span data-ttu-id="10c95-112">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="10c95-112">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="10c95-113">O objeto de parâmetro do evento DevToolsProtocol correspondente representado como uma cadeia de caracteres JSON.</span><span class="sxs-lookup"><span data-stu-id="10c95-113">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="10c95-114">público HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* ParameterObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="10c95-114">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>
