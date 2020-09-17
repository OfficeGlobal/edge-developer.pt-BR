---
description: Inserir tecnologias da Web (HTML, CSS e JavaScript) em seus aplicativos nativos com o controle WebView2 do Microsoft Edge
title: WebView2 Win32 C++ ICoreWebView2DevToolsProtocolEventReceiver
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, webview2, WebView, aplicativos Win32, Win32, Edge, ICoreWebView2, ICoreWebView2Controller, controle do navegador, HTML Edge, ICoreWebView2DevToolsProtocolEventReceiver
ms.openlocfilehash: 6b3d6170d84f5e968121f90e1eebe5daf532f03d
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011430"
---
# <span data-ttu-id="74785-104">interface ICoreWebView2DevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="74785-104">interface ICoreWebView2DevToolsProtocolEventReceiver</span></span> 

```
interface ICoreWebView2DevToolsProtocolEventReceiver
  : public IUnknown
```

<span data-ttu-id="74785-105">Um receptor é criado para um determinado evento de protocolo DevTools e permite que você assine e cancele a assinatura desse evento.</span><span class="sxs-lookup"><span data-stu-id="74785-105">A Receiver is created for a particular DevTools Protocol event and allows you to subscribe and unsubscribe from that event.</span></span>

## <span data-ttu-id="74785-106">Resumo</span><span class="sxs-lookup"><span data-stu-id="74785-106">Summary</span></span>

 <span data-ttu-id="74785-107">Parte</span><span class="sxs-lookup"><span data-stu-id="74785-107">Members</span></span>                        | <span data-ttu-id="74785-108">Descrições</span><span class="sxs-lookup"><span data-stu-id="74785-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="74785-109">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="74785-109">add_DevToolsProtocolEventReceived</span></span>](#add_devtoolsprotocoleventreceived) | <span data-ttu-id="74785-110">Assine um evento DevToolsProtocol.</span><span class="sxs-lookup"><span data-stu-id="74785-110">Subscribe to a DevToolsProtocol event.</span></span>
[<span data-ttu-id="74785-111">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="74785-111">remove_DevToolsProtocolEventReceived</span></span>](#remove_devtoolsprotocoleventreceived) | <span data-ttu-id="74785-112">Remover um manipulador de eventos adicionado anteriormente com add_DevToolsProtocolEventReceived.</span><span class="sxs-lookup"><span data-stu-id="74785-112">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>

<span data-ttu-id="74785-113">Obtido do objeto WebView via GetDevToolsProtocolEventReceiver.</span><span class="sxs-lookup"><span data-stu-id="74785-113">Obtained from the WebView object via GetDevToolsProtocolEventReceiver.</span></span>

## <span data-ttu-id="74785-114">Parte</span><span class="sxs-lookup"><span data-stu-id="74785-114">Members</span></span>

#### <span data-ttu-id="74785-115">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="74785-115">add_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="74785-116">Assine um evento DevToolsProtocol.</span><span class="sxs-lookup"><span data-stu-id="74785-116">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="74785-117">[add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)público HRESULT (manipulador[ICoreWebView2DevToolsProtocolEventReceivedEventHandler](icorewebview2devtoolsprotocoleventreceivedeventhandler.md) \*, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="74785-117">public HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)([ICoreWebView2DevToolsProtocolEventReceivedEventHandler](icorewebview2devtoolsprotocoleventreceivedeventhandler.md) \* handler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="74785-118">O método Invoke do manipulador será chamado sempre que o evento DevToolsProtocol correspondente for acionado.</span><span class="sxs-lookup"><span data-stu-id="74785-118">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="74785-119">Invoke será chamado com um objeto args de evento que contém o objeto de parâmetro do evento de protocolo DevTools como uma cadeia de caracteres JSON.</span><span class="sxs-lookup"><span data-stu-id="74785-119">Invoke will be called with an event args object containing the DevTools Protocol event's parameter object as a JSON string.</span></span>

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

#### <span data-ttu-id="74785-120">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="74785-120">remove_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="74785-121">Remover um manipulador de eventos adicionado anteriormente com add_DevToolsProtocolEventReceived.</span><span class="sxs-lookup"><span data-stu-id="74785-121">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>

> <span data-ttu-id="74785-122">[remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="74785-122">public HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)(EventRegistrationToken token)</span></span>
