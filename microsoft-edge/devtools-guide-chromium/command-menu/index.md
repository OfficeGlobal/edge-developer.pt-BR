---
description: Um guia sobre como abrir o menu de comando, executar comandos, revisar outras ações e muito mais.
title: Executar comandos com o menu de comando do Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, desenvolvimento na Web, ferramentas F12, devtools
ms.openlocfilehash: 2f13461fdf04e034b324db63c6ec6d9090f80f50
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125276"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# Executar comandos com o menu de comando do Microsoft Edge DevTools  

  

O menu de comando fornece uma maneira rápida de navegar na interface do usuário do Microsoft Edge DevTools e realizar tarefas comuns, como [desabilitar o JavaScript][JavascriptDisable].  Você pode estar familiarizado com um recurso semelhante no código do Visual Studio chamado de [paleta de comandos][VisualStudioCodeUICommandPalette], que era a inspiração original para o menu de comando.  

:::image type="complex" source="../media/command-menu-run-command-java.msft.png" alt-text="Usar o menu de comandos para desativar o JavaScript" lightbox="../media/command-menu-run-command-java.msft.png":::
   Usar o menu de comandos para desativar o JavaScript  
:::image-end:::  

## Abrir o menu de comandos  

Selecione `Control` + `Shift` + `P` \ (Windows, Linux \) ou `Command` + `Shift` + `P` \ (MacOS \). Ou escolha **Personalizar e controlar devtools** `...` e, em seguida, escolha **executar comando**.  

:::image type="complex" source="../media/command-menu-options-run-command.msft.png" alt-text="Usar o menu de comandos para desativar o JavaScript" lightbox="../media/command-menu-options-run-command.msft.png":::
   Comando executar  
:::image-end:::  

## Ver outras ações disponíveis  

Se você usar o fluxo de trabalho descrito em [abrir o menu de comando](#open-the-command-menu), o menu de comandos será aberto com um `>` caractere semipendente na caixa de texto do menu de comandos.  

:::image type="complex" source="../media/command-menu-run-command.msft.png" alt-text="Usar o menu de comandos para desativar o JavaScript" lightbox="../media/command-menu-run-command.msft.png":::
   O caractere de comando  
:::image-end:::  

Exclua o `>` caractere e digite `?` para ver outras ações que estão disponíveis no menu de comando.  

:::image type="complex" source="../media/command-menu-help.msft.png" alt-text="Usar o menu de comandos para desativar o JavaScript" lightbox="../media/command-menu-help.msft.png":::
   Outras ações disponíveis  
:::image-end:::  

## Entrar em contato com a equipe Microsoft Edge DevTools  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[JavascriptDisable]: ../javascript/disable.md "Desabilitar JavaScript com o Microsoft Edge DevTools | Documentos da Microsoft"  

[VisualStudioCodeUICommandPalette]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette "Paleta de comandos-UI de código do Visual Studio"  

> [!NOTE]
> Partes desta página são modificações com base no trabalho criado e [compartilhado pelo Google][GoogleSitePolicies] e usados de acordo com os termos descritos na [licença internacional Creative Commons][CCA4IL]rereference 4,0 International.  
> A página original é encontrada [aqui](https://developers.google.com/web/tools/chrome-devtools/command-menu/index) e é criada por [Kayce Basques][KayceBasques] \ (redator técnico, Chrome devtools \ & Lighthouse \).  

[![Licença Creative Commons][CCby4Image]][CCA4IL]  
Esse trabalho é licenciado sob uma [Licença Attribution 4.0 International (CC BY 4.0) da Creative Commons][CCA4IL].  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
