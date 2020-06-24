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
ms.openlocfilehash: 7072a25636efb638fcb42c593aa6cc77e990965a
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698319"
---
# interface ICoreWebView2WebResourceResponse 

```
interface ICoreWebView2WebResourceResponse
  : public IUnknown
```

Uma resposta HTTP usada com o evento WebResourceRequested.

## Resumo

 Parte                        | Descrições
--------------------------------|---------------------------------------------
[get_Content](#get_content) | Conteúdo da resposta HTTP como Stream.
[get_Headers](#get_headers) | Cabeçalhos de resposta HTTP substituídos.
[get_ReasonPhrase](#get_reasonphrase) | A frase de motivo da resposta HTTP.
[get_StatusCode](#get_statuscode) | O código de status de resposta HTTP.
[put_Content](#put_content) | Defina a propriedade Content.
[put_ReasonPhrase](#put_reasonphrase) | Defina a propriedade ReasonPhrase.
[put_StatusCode](#put_statuscode) | Defina a propriedade StatusCode.

## Parte

#### get_Content 

Conteúdo da resposta HTTP como Stream.

> [get_Content](#get_content)público HRESULT (conteúdo IStream * *)

Stream deve ter todos os dados de conteúdo disponíveis no momento em que o adiamento do evento WebResourceRequested da resposta é concluído. Stream deve ser ágil ou ser criado a partir de um thread de segundo plano para evitar o impacto de desempenho no thread da interface do usuário. NULL significa sem dados de conteúdo. Semântica de IStream se aplica (retornar S_OK para ler chamadas até que todos os dados tenham esgotado)

#### get_Headers 

Cabeçalhos de resposta HTTP substituídos.

> público HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) * * cabeçalhos)

#### get_ReasonPhrase 

A frase de motivo da resposta HTTP.

> público HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR * ReasonPhrase)

#### get_StatusCode 

O código de status de resposta HTTP.

> [get_StatusCode](#get_statuscode)público HRESULT (int * StatusCode)

#### put_Content 

Defina a propriedade Content.

> [put_Content](#put_content)público HRESULT (conteúdo IStream *)

#### put_ReasonPhrase 

Defina a propriedade ReasonPhrase.

> Public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR ReasonPhrase)

#### put_StatusCode 

Defina a propriedade StatusCode.

> [put_StatusCode](#put_statuscode)público HRESULT (int StatusCode)
