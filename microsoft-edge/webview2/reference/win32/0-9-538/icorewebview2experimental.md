---
description: Inserir tecnologias da Web (HTML, CSS e JavaScript) em seus aplicativos nativos com o controle WebView2 do Microsoft Edge
title: WebView2 Win32 C++ ICoreWebView2Experimental
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, webview2, WebView, aplicativos Win32, Win32, Edge, ICoreWebView2, ICoreWebView2Controller, controle do navegador, HTML Edge, ICoreWebView2Experimental
ms.openlocfilehash: 98f13193e73781f9f7371db05ed3ca99ca93c128
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886506"
---
# interface ICoreWebView2Experimental 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2Experimental
  : public IUnknown
```

## Resumo

 Parte                        | Descrições
--------------------------------|---------------------------------------------
[add_WebResourceResponseReceived](#add_webresourceresponsereceived) | Adicione um manipulador de eventos para o evento WebResourceResponseReceived.
[remove_WebResourceResponseReceived](#remove_webresourceresponsereceived) | Remove o manipulador de eventos WebResourceResponseReceived anteriormente adicionado com add_WebResourceResponseReceived.

## Parte

#### add_WebResourceResponseReceived 

Adicione um manipulador de eventos para o evento WebResourceResponseReceived.

> Public HRESULT [add_WebResourceResponseReceived](#add_webresourceresponsereceived)([ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler](icorewebview2experimentalwebresourceresponsereceivedeventhandler.md) * EventHandler, EventRegistrationToken * token)

O evento WebResourceResponseReceived é acionado depois que a WebView recebeu e processou a resposta de uma solicitação WebResource. Os args de evento incluem o WebResourceRequest como enviado pelo fio e WebResourceResponse recebidos, incluindo outros cabeçalhos adicionais adicionados pela pilha de rede que não foram incluídos como parte do evento WebResourceRequested associado, como cabeçalhos de autenticação. 
```cpp
    wil::com_ptr<ICoreWebView2Experimental> webviewExperimental;
    CHECK_FAILURE(m_appWindow->GetWebView()->QueryInterface(IID_PPV_ARGS(&webviewExperimental)));
    CHECK_FAILURE(webviewExperimental->add_WebResourceResponseReceived(
        Callback<ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler>(
            [this](
                ICoreWebView2Experimental* sender,
                ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs* args) {           
                wil::com_ptr<ICoreWebView2WebResourceRequest> request;
                CHECK_FAILURE(args->get_Request(&request));
                wil::unique_cotaskmem_string uri;
                CHECK_FAILURE(request->get_Uri(&uri));
                if (wcscmp(uri.get(), L"https://authenticationtest.com/HTTPAuth/") == 0)
                {
                    wil::com_ptr<ICoreWebView2HttpRequestHeaders> requestHeaders;
                    CHECK_FAILURE(request->get_Headers(&requestHeaders));

                    wil::unique_cotaskmem_string authHeaderValue;
                    if (requestHeaders->GetHeader(L"Authorization", &authHeaderValue) == S_OK)
                    {
                        std::wstring message(L"Authorization: ");
                        message += authHeaderValue.get();
                        MessageBox(nullptr, message.c_str(), nullptr, MB_OK);
                        m_appWindow->DeleteComponent(this);
                    }
                }
                
                return S_OK;
            })
            .Get(),
        &m_webResourceResponseReceivedToken));
```

#### remove_WebResourceResponseReceived 

Remove o manipulador de eventos WebResourceResponseReceived anteriormente adicionado com add_WebResourceResponseReceived.

> [remove_WebResourceResponseReceived](#remove_webresourceresponsereceived)público HRESULT (token EventRegistrationToken)
