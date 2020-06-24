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
ms.openlocfilehash: b3d6cc14ccaa6a803e0e987b68a74851a6c5f2f9
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698372"
---
# Classe Microsoft. Web. WebView2. Core. CoreWebView2AcceleratorKeyPressedEventArgs 

Namespace: Microsoft. Web. WebView2. Core \
Assembly: Microsoft. Web. WebView2. Core. dll

Args de evento para o evento AcceleratorKeyPressed.

## Resumo

 Parte                        | Descrições
--------------------------------|---------------------------------------------
[Handled](#handled) | Durante a invocação do manipulador AcceleratorKeyPressedEvent, o WebView está bloqueado aguardando a decisão de se o acelerador será manipulado pelo host ou não.
[KeyEventKind](#keyeventkind) | O tipo de evento Key que causou o evento a ser disparado.
[KeyEventLParam](#keyeventlparam) | O valor de LPARAM que acompanha a mensagem da janela.
[PhysicalKeyStatus](#physicalkeystatus) | Uma estrutura que representa as informações passadas no LPARAM da mensagem da janela.
[VirtualKey](#virtualkey) | O código da chave virtual Win32 da chave que foi pressionada ou liberada.

## Parte

#### Handled 

Durante a invocação do manipulador AcceleratorKeyPressedEvent, o WebView está bloqueado aguardando a decisão de se o acelerador será manipulado pelo host ou não.

> bool público [manipulado](#handled)

Se a propriedade Handled estiver definida como TRUE, isso impedirá que o WebView execute a ação padrão para essa chave aceleradora. Caso contrário, o WebView executará a ação padrão para a tecla aceleradora.

#### KeyEventKind 

O tipo de evento Key que causou o evento a ser disparado.

> [CoreWebView2KeyEventKind](./namespace-microsoft-web-webview2-core.md) público [KeyEventKind](#keyeventkind)

#### KeyEventLParam 

O valor de LPARAM que acompanha a mensagem da janela.

> public int [KeyEventLParam](#keyeventlparam)

Consulte a documentação para as mensagens de WM_KEYDOWN e WM_KEYUP.

#### PhysicalKeyStatus 

Uma estrutura que representa as informações passadas no LPARAM da mensagem da janela.

> [CoreWebView2PhysicalKeyStatus](microsoft-web-webview2-core-corewebview2physicalkeystatus.md) público [PhysicalKeyStatus](#physicalkeystatus)

#### VirtualKey 

O código da chave virtual Win32 da chave que foi pressionada ou liberada.

> Public uint [VirtualKey](#virtualkey)

Isso será uma das constantes de chave virtual do Win32, como VK_RETURN ou um valor ASCII (maiúsculo) como ' A '. Você pode verificar se a tecla CTRL ou Alt está pressionada chamando GetKeyState (VK_CONTROL) ou GetKeyState (VK_MENU).
