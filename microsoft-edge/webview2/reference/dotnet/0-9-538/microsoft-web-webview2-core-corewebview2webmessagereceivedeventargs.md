---
description: Hospedar conteúdo da Web em seu aplicativo Win32 com o controle WebView2 do Microsoft Edge
title: Microsoft Edge WebView2 para aplicativos Win32
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, webview2, WebView, aplicativos Win32, Win32, Edge, ICoreWebView2, ICoreWebView2Controller, controle do navegador, HTML Edge
ms.openlocfilehash: 9babcaff5b90e22ea6bac5d5703a54caef6d349d
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698402"
---
# Classe Microsoft. Web. WebView2. Core. CoreWebView2WebMessageReceivedEventArgs 

Namespace: Microsoft. Web. WebView2. Core \
Assembly: Microsoft. Web. WebView2. Core. dll

Args de evento para o evento WebMessageReceived.

## Resumo

 Parte                        | Descrições
--------------------------------|---------------------------------------------
[Origem](#source) | O URI do documento que enviou esta mensagem da Web.
[WebMessageAsJson](#webmessageasjson) | A mensagem postada do conteúdo da WebView para o host convertido em uma cadeia de caracteres JSON.
[TryGetWebMessageAsString](#trygetwebmessageasstring) | Se a mensagem postada do conteúdo WebView para o host for um tipo de cadeia de caracteres, esse método retornará o valor dessa cadeia de caracteres.

## Parte

#### Origem 

O URI do documento que enviou esta mensagem da Web.

> [fonte](#source) de cadeia de caracteres pública

#### WebMessageAsJson 

A mensagem postada do conteúdo da WebView para o host convertido em uma cadeia de caracteres JSON.

> Cadeia de caracteres pública [WebMessageAsJson](#webmessageasjson)

Use isso para se comunicar por objetos JavaScript.

Por exemplo, as seguintes chamadas de mensagens de mensagens resultam nos seguintes valores de WebMessageAsJson:

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### TryGetWebMessageAsString 

Se a mensagem postada do conteúdo WebView para o host for um tipo de cadeia de caracteres, esse método retornará o valor dessa cadeia de caracteres.

> [TryGetWebMessageAsString](#trygetwebmessageasstring)de cadeia de caracteres pública ()

Se a mensagem publicada for outro tipo de tipo JavaScript, esse método falhará com E_INVALIDARG. Use isso para se comunicar por meio de cadeias de caracteres simples.

Por exemplo, as seguintes chamadas de mensagens de mensagens resultam nos seguintes valores de WebMessageAsString:

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```
