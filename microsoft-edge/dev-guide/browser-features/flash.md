---
description: Oferecer uma experiência de usuário perfeita em sites que exijam Adobe Flash.
title: Guia de desenvolvimento-Flash
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: Edge, desenvolvimento da Web, Flash
ms.openlocfilehash: b3e2efe142142b7cdf233acfc4e915cd320b556d
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "10560566"
---
# Flash

O Adobe Flash tem sido uma parte integral da Web há décadas, permitindo conteúdo rico e animações em navegadores desde que o HTML5 foi introduzido. Em navegadores modernos, os padrões da Web pioneiras pela Microsoft, Adobe, Google, Apple, Mozilla e muitos outros já estão permitindo que os sites excedam essas experiências sem flash e com desempenho e segurança aprimorados. Trabalhando em parceria com outros fornecedores de navegador e com a Adobe, recomendamos que os desenvolvedores migrem para os padrões do HTML5, incluindo [extensões de mídia criptografadas](https://developer.microsoft.com/microsoft-edge/platform/status/encryptedmediaextensions), [extensões de origem de mídia](https://developer.microsoft.com/microsoft-edge/platform/status/mediasourceextensions), [tela](https://developer.microsoft.com/microsoft-edge/platform/status/canvas), [áudio da Web](https://developer.microsoft.com/microsoft-edge/platform/status/webaudioapi)e [comunicação em tempo real](https://developer.microsoft.com/microsoft-edge/platform/status/webrtcobjectrtcapi).

Com o lançamento de outubro de 2018 do Windows 10, o Microsoft Edge continua com o esforço de substituição do flash que [abordamos](https://blogs.windows.com/msedgedev/2017/07/25/flash-on-windows-timeline/#9mCF959eQEK0poo5.97) como parte do [lançamento do fim do suporte da Adobe](https://theblog.adobe.com/adobe-flash-update/) após o 2021. Na versão de outubro de 2018, os usuários terão que permitir explicitamente que o flash seja executado em um site durante o tempo de vida da guia. A opção persistente sempre permitir não estará mais disponível e um usuário não poderá gerenciar a permissão do flash por site que abranja sessões de guias.

Ao fazer a transição para os padrões do HTML5, existem algumas coisas simples que você pode fazer para garantir que seus usuários ainda tenham uma experiência positiva ao visitar seu site com o Microsoft Edge na atualização do Windows 10 para criadores. 

Se o Flash for usado na página, mas o usuário não o tiver habilitado, o Microsoft Edge normalmente mostrará um ícone de peça de quebra-cabeça na barra de endereços, conforme mostrado neste [blog](https://blogs.windows.com/msedgedev/2016/12/14/edge-flash-click-run/#41svu6EMwKIAaigx.97). Se você estiver adicionando dinamicamente o controle flash após a página ser carregada, este ícone de peça de quebra-cabeça não pode ser exibido – nesse caso, é melhor testar a presença do flash e fornecer um link conforme descrito abaixo.

Para garantir que todos os usuários tenham uma boa experiência, continue testando a presença do flash usando seus mecanismos padrão. Se o Microsoft Edge reportar que o flash não está disponível, apresente o [link de download flash](http://get.adobe.com/flashplayer) e a [imagem de download do flash](http://www.adobe.com/legal/permissions/icons-web-logos.html#flashplayer) para o usuário. Quando o usuário clica no link, o Microsoft Edge (bem como outros navegadores) apresentará os avisos necessários para habilitar o Flash Player para o site. O link deve aparecer no domínio primário em que você deseja que o flash seja habilitado. Ele não funcionará se você redirecionar usuários para páginas em outros domínios.  [Aqui está uma demonstração](https://microsoftedge.github.io/MicrosoftEdge-Documentation/flashclicktorun/) da experiência sugerida e do [código de exemplo](https://github.com/MicrosoftEdge/MicrosoftEdge-Documentation/tree/master/docs/flashclicktorun)correspondente.