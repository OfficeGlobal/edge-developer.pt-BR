---
description: Como exibir dados do SQL da Web no painel de aplicativos do Microsoft Edge DevTools.
title: Exibir dados do SQL da Web com o Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, desenvolvimento na Web, ferramentas F12, devtools
ms.openlocfilehash: 0396a00ec354fdd707bc4d484242d4cf844db5f9
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125465"
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

# Exibir dados do SQL da Web com o Microsoft Edge DevTools  

> [!WARNING]
> A especificação SQL da Web [não está sendo mantida][W3CWebSQLStatus].  

Este guia mostra como usar [o Microsoft Edge devtools][MicrosoftEdgeDevTools] para inspecionar dados SQL da Web.  

## Exibir dados do SQL Web  

1.  Selecione a guia **fontes** para abrir o painel **fontes** .  O painel de **manifesto** geralmente abre por padrão.  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="Painel de manifesto" lightbox="../media/storage-application-manifest.msft.png":::
       Painel de **manifesto**  
    :::image-end:::  
    
1.  Expanda a seção **SQL Web** para exibir bancos de dados e tabelas.  Na figura a seguir, abaixo de **html5meetup** é um banco de dados e **salas** é uma tabela.  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql.msft.png" alt-text="Painel de manifesto" lightbox="../media/storage-application-storage-web-sql.msft.png":::
       O painel **SQL Web**  
    :::image-end:::  
    
1.  Selecione uma tabela para exibir os dados dessa tabela.  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png" alt-text="Painel de manifesto" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png":::
       Exibir os dados de uma tabela SQL da Web  
    :::image-end:::  
    
## Editar dados do SQL da Web  

Você não pode editar dados SQL da Web ao exibir uma tabela SQL da Web, como na **Figura 3** acima.  Mas você pode executar instruções a partir do console SQL Web que edita ou exclui tabelas.  Consulte [executar consultas do SQL Web](#run-web-sql-queries).  

## Executar consultas do SQL da Web  

1.  Selecione um banco de dados para abrir um console para esse banco de dados.  
1.  Digite uma instrução SQL da Web e selecione `Enter` para executá-la.  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png" alt-text="Painel de manifesto" lightbox="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png":::
       Usar o console do SQL Web para excluir uma linha de uma tabela  
    :::image-end:::  
    
## Atualizar uma tabela SQL da Web  

O DevTools não atualiza tabelas em tempo real.  Para atualizar os dados em uma tabela:  

1.  [Exiba os dados em uma tabela SQL da Web](#view-web-sql-data).  
1.  Escolha **Atualizar** \ ( ![ Atualizar ][ImageRefreshIcon] \).  
    
## Filtrar colunas em uma tabela SQL da Web  

1.  [Exiba os dados em uma tabela SQL da Web](#view-web-sql-data).  
1.  Use a caixa de texto **colunas visíveis** para especificar quais colunas você deseja mostrar.  Forneça os nomes de coluna como uma lista de CSV.  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png" alt-text="Painel de manifesto" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png":::
       Use a caixa de texto **colunas visíveis** para reduzir o número de colunas exibidas  
    :::image-end:::  
    
## Excluir todos os dados SQL da Web  

1.  Abrir o painel **limpar armazenamento** .  
1.  Verifique se a caixa de seleção **SQL da Web** está habilitada.  
    
    :::image type="complex" source="../media/storage-application-clear-storage-web-sql.msft.png" alt-text="Painel de manifesto" lightbox="../media/storage-application-clear-storage-web-sql.msft.png":::
       A caixa de seleção **SQL da Web**  
    :::image-end:::  
    
1.  Escolha **limpar dados do site**.  
    
    :::image type="complex" source="../media/storage-application-clear-storage-clear-site-data-button.msft.png" alt-text="Painel de manifesto" lightbox="../media/storage-application-clear-storage-clear-site-data-button.msft.png":::
       O botão **limpar dados do site**  
    :::image-end:::  
    
## Entrar em contato com a equipe Microsoft Edge DevTools  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Ferramentas de desenvolvedor do Microsoft Edge (Chromium) | Documentos da Microsoft"  

[W3CWebSQLStatus]: https://w3.org/TR/webdatabase/#status-of-this-document "Banco de dados SQL Web | W3C"  

> [!NOTE]
> Partes desta página são modificações com base no trabalho criado e [compartilhado pelo Google][GoogleSitePolicies] e usados de acordo com os termos descritos na [licença internacional Creative Commons][CCA4IL]rereference 4,0 International.  
> A página original é encontrada [aqui](https://developers.google.com/web/tools/chrome-devtools/storage/websql) e é criada por [Kayce Basques][KayceBasques] \ (redator técnico, Chrome devtools \ & Lighthouse \).  

[![Licença Creative Commons][CCby4Image]][CCA4IL]  
Esse trabalho é licenciado sob uma [Licença Attribution 4.0 International (CC BY 4.0) da Creative Commons][CCA4IL].  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
