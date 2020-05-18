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
ms.openlocfilehash: 4c2c859525753a386134b2ae0145f4fdca4c37ae
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652423"
---
# <span data-ttu-id="8925d-104">interface ICoreWebView2DevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="8925d-104">interface ICoreWebView2DevToolsProtocolEventReceiver</span></span> 

> [!NOTE]
> <span data-ttu-id="8925d-105">Essa interface pode ser alterada ou indisponível para versões posteriores SDK da versão 0.9.430.</span><span class="sxs-lookup"><span data-stu-id="8925d-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="8925d-106">Consulte a [referência](../../../webview2-api-reference.md) para obter a referência da API mais recente.</span><span class="sxs-lookup"><span data-stu-id="8925d-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2DevToolsProtocolEventReceiver
  : public IUnknown
```

<span data-ttu-id="8925d-107">Um receptor é criado para um determinado evento de protocolo DevTools e permite que você assine e UNSUBSRIBE desse evento.</span><span class="sxs-lookup"><span data-stu-id="8925d-107">A Receiver is created for a particular DevTools Protocol event and allows you to subscribe and unsubsribe from that event.</span></span>

## <span data-ttu-id="8925d-108">Resumo</span><span class="sxs-lookup"><span data-stu-id="8925d-108">Summary</span></span>

 <span data-ttu-id="8925d-109">Parte</span><span class="sxs-lookup"><span data-stu-id="8925d-109">Members</span></span>                        | <span data-ttu-id="8925d-110">Descrições</span><span class="sxs-lookup"><span data-stu-id="8925d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8925d-111">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="8925d-111">add_DevToolsProtocolEventReceived</span></span>](#add_devtoolsprotocoleventreceived) | <span data-ttu-id="8925d-112">Assine um evento DevToolsProtocol.</span><span class="sxs-lookup"><span data-stu-id="8925d-112">Subscribe to a DevToolsProtocol event.</span></span>
[<span data-ttu-id="8925d-113">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="8925d-113">remove_DevToolsProtocolEventReceived</span></span>](#remove_devtoolsprotocoleventreceived) | <span data-ttu-id="8925d-114">Remover um manipulador de eventos adicionado anteriormente com add_DevToolsProtocolEventReceived.</span><span class="sxs-lookup"><span data-stu-id="8925d-114">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>

<span data-ttu-id="8925d-115">Obtido do objeto WebView via GetDevToolsProtocolEventReceiver.</span><span class="sxs-lookup"><span data-stu-id="8925d-115">Obtained from the WebView object via GetDevToolsProtocolEventReceiver.</span></span>

## <span data-ttu-id="8925d-116">Parte</span><span class="sxs-lookup"><span data-stu-id="8925d-116">Members</span></span>

#### <span data-ttu-id="8925d-117">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="8925d-117">add_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="8925d-118">Assine um evento DevToolsProtocol.</span><span class="sxs-lookup"><span data-stu-id="8925d-118">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="8925d-119">[add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)público HRESULT (manipulador[ICoreWebView2DevToolsProtocolEventReceivedEventHandler](ICoreWebView2DevToolsProtocolEventReceivedEventHandler.md) \*, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="8925d-119">public HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)([ICoreWebView2DevToolsProtocolEventReceivedEventHandler](ICoreWebView2DevToolsProtocolEventReceivedEventHandler.md) \* handler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="8925d-120">O método Invoke do manipulador será chamado sempre que o evento DevToolsProtocol correspondente for acionado.</span><span class="sxs-lookup"><span data-stu-id="8925d-120">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="8925d-121">Invoke será chamado com o objeto do evento args que contém o objeto de parâmetro do evento de protocolo DevTools como uma cadeia de caracteres JSON.</span><span class="sxs-lookup"><span data-stu-id="8925d-121">Invoke will be called with the an event args object containing the DevTools Protocol event's parameter object as a JSON string.</span></span>

```cpp
// Prompt the user to name a CDP event, and then subscribe to that event.
void ScriptComponent::SubscribeToCdpEvent()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Subscribe to CDP Event",
        L"CDP event name:",
        L"Enter the name of the CDP event to subscribe to.\r\n"
            L"You may also have to call the \"enable\" method of the\r\n"
            L"event's domain to receive events (for example \"Log.enable\").\r\n",
        L"Log.entryAdded");
    if (dialog.confirmed)
    {
        std::wstring eventName = dialog.input;
        wil::com_ptr<ICoreWebView2DevToolsProtocolEventReceiver> receiver;
        CHECK_FAILURE(
            m_webView->GetDevToolsProtocolEventReceiver(eventName.c_str(), &receiver));

        // If we are already subscribed to this event, unsubscribe first.
        auto preexistingToken = m_devToolsProtocolEventReceivedTokenMap.find(eventName);
        if (preexistingToken != m_devToolsProtocolEventReceivedTokenMap.end())
        {
            CHECK_FAILURE(receiver->remove_DevToolsProtocolEventReceived(
                preexistingToken->second));
        }

        CHECK_FAILURE(receiver->add_DevToolsProtocolEventReceived(
            Callback<ICoreWebView2DevToolsProtocolEventReceivedEventHandler>(
                [eventName](
                    ICoreWebView2* sender,
                    ICoreWebView2DevToolsProtocolEventReceivedEventArgs* args) -> HRESULT {
                    wil::unique_cotaskmem_string parameterObjectAsJson;
                    CHECK_FAILURE(args->get_ParameterObjectAsJson(&parameterObjectAsJson));
                    MessageBox(
                        nullptr, parameterObjectAsJson.get(),
                        (L"CDP Event Fired: " + eventName).c_str(), MB_OK);
                    return S_OK;
                })
                .Get(),
            &m_devToolsProtocolEventReceivedTokenMap[eventName]));
    }
}
```

#### <span data-ttu-id="8925d-122">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="8925d-122">remove_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="8925d-123">Remover um manipulador de eventos adicionado anteriormente com add_DevToolsProtocolEventReceived.</span><span class="sxs-lookup"><span data-stu-id="8925d-123">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>

> <span data-ttu-id="8925d-124">[remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="8925d-124">public HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)(EventRegistrationToken token)</span></span>
