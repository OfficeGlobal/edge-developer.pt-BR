---
description: Descubra os novos fluxos de trabalho de depuração nesta referência abrangente de recursos de depuração do Microsoft Edge DevTools.
title: Referências de Depuração de JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, desenvolvimento na Web, ferramentas F12, devtools
ms.openlocfilehash: c1d6b9d301ff2bc696900b48d80a3d5352f8fd58
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124800"
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

# Referências de depuração de JavaScript  

Descubra os novos fluxos de trabalho de depuração com a seguinte referência abrangente de recursos de depuração do Microsoft Edge DevTools.  

Consulte [introdução à depuração de JavaScript no Microsoft Edge devtools][DevToolsJavascriptGetStarted] para aprender as noções básicas de depuração.  

## Pausar código com pontos de interrupção  

Defina um ponto de interrupção para que você possa pausar seu código no meio do tempo de execução.  

Consulte [Pausar um código com pontos de interrupção][DevToolsJavascriptBreakpoints] para saber como definir pontos de interrupção.  

## Depurar o código  

Depois que o seu código for pausado, percorra-o, uma linha por vez, investigando o fluxo de controle e os valores de propriedade ao longo do caminho.  

### Etapa sobre linha de código  

Quando pausado em uma linha de código contendo uma função que não é relevante para o problema que você está Depurando, clique no botão de **etapa sobre** \ ( ![ etapa sobre ][ImageStepOverIcon] \) para executar a função sem fazer a depuração.  

:::image type="complex" source="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png":::
   Escolha passar **sobre**  
:::image-end:::  

Por exemplo, suponha que você esteja Depurando o trecho de código a seguir.  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName(); // A
    updateName(name); // D
}
function getName() {
    var name = app.first + ' ' + app.last; // B
    return name; // C
}
```  

Você está pausado `A` .  Pressionando a **etapa**, o devtools executa todo o código na função que você está Depurando, que é `B` e `C` .  DevTools, em seguida, faz uma pausa `D` .  

### Etapa na linha de código  

Quando pausado em uma linha de código contendo uma chamada de função que está relacionada ao problema que você está Depurando, clique no botão **Step Into** \ ( ![ Step Into ][ImageStepIntoIcon] \) para investigar essa função ainda mais.  

:::image type="complex" source="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png":::
   Escolha **passar em**  
:::image-end:::  

Por exemplo, suponha que você esteja Depurando o trecho de código a seguir.  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName(); // A
    updateName(name);
}
function getName() {
    var name = app.first + ' ' + app.last; // B
    return name;
}
```  

Você está pausado `A` .  Ao pressionar **Step Into**, o devtools executa essa linha de código e, em seguida, pausa em `B` .  

### Etapa da linha de código  

Quando pausado dentro de uma função que não está relacionada ao problema que você está Depurando, clique no botão **Step Out** \ ( ![ Step Out ][ImageStepOutIcon] \) para executar o restante do código da função.  

:::image type="complex" source="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png":::
   Escolha **depurar**  
:::image-end:::  

Por exemplo, suponha que você esteja Depurando o trecho de código a seguir.  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName();
    updateName(name); // C
}
function getName() {
    var name = app.first + ' ' + app.last; // A
    return name; // B
}
```  

Você está pausado `A` .  Ao pressionar a **etapa**, o devtools executa o restante do código `getName()` , que está apenas `B` neste exemplo e, em seguida, pausa em `C` .  

### Executar todo o código em uma linha específica  

Durante a depuração de uma função longa, pode haver muitos códigos que não estão relacionados ao problema que você está depurando.  

Você pode optar por percorrer todas as linhas, mas isso é entediante.  Você pode optar por definir um ponto de interrupção de linha de código na linha na qual está interessado e clicar no botão **continuar execução do script** \ ( ![ retomar execução do script ][ImageResumeScriptExecutionIcon] \), mas há uma maneira mais rápida.  

Clique com o botão direito do mouse na linha de código na qual você está interessado e escolha **continuar até aqui**.  O DevTools executa todo o código até esse ponto e, em seguida, faz uma pausa nessa linha.  

:::image type="complex" source="../media/javascript-source-page-continue-to-here.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-source-page-continue-to-here.msft.png":::
   Escolha **continuar até aqui**  
:::image-end:::  

### Reinicie a função superior da pilha de chamadas  

Enquanto pausado em uma linha de código, clique com o botão direito do mouse em qualquer lugar no painel de **pilha de chamadas** e escolha **reiniciar quadro** para pausar na primeira linha da função superior na pilha de chamadas.  A função Top é a última função que foi executada.  

O trecho de código a seguir é um exemplo para percorrer.  

```javascript
function factorial(n) {
    var product = 0; // B
    for (var i = 1; i <= n; i++) {
      product += i;
    }
    return product; // A
}
```  

Você está pausado `A` .  Depois de escolher **reiniciar o quadro**, você deve pausar `B` , sem precisar definir um ponto de interrupção ou escolher **retomar a execução do script**.  

:::image type="complex" source="../media/javascript-source-page-debugger-restart-frame.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-source-page-debugger-restart-frame.msft.png":::
   Escolha **reiniciar quadro**  
:::image-end:::  

### Retomar o tempo de execução do script  

Para continuar o tempo de execução após uma pausa do seu script, escolha o botão **continuar execução do script** \ ( ![ continuar execução do script ][ImageResumeScriptExecutionIcon] \).  DevTools executa o script até o próximo ponto de interrupção, se houver.  

:::image type="complex" source="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png":::
   Escolha **retomar execução do script**  
:::image-end:::  

#### Forçar tempo de execução de script  

Para ignorar todos os pontos de interrupção e forçar o reinício do script, escolha e segure o botão **continuar execução do script** \ ( ![ retomar execução do script ][ImageResumeScriptExecutionIcon] \) e, em seguida, escolha o botão **forçar execução de script** \ ( ![ forçar execução de script ][ImageForceScriptExecutionIcon] \).  

:::image type="complex" source="../media/javascript-sources-get-started-js-force-script-runtime.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-sources-get-started-js-force-script-runtime.msft.png":::
   Escolha **forçar execução de script**  
:::image-end:::  

### Alterar o contexto do thread  

Ao trabalhar com trabalhadores da Web ou funcionários do serviço, escolha em um contexto listado no painel **threads** para alternar para esse contexto.  O ícone de seta azul representa qual contexto está selecionado no momento.  

:::image type="complex" source="../media/javascript-sources-main-min-js-threads.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-sources-main-min-js-threads.msft.png":::
   O painel **threads**  
:::image-end:::  

Por exemplo, suponha que você está pausado em um ponto de interrupção no script principal e no seu roteiro de trabalho do serviço.  Você deseja exibir as propriedades locais e globais do contexto do trabalho do serviço, mas o painel **fontes** está mostrando o contexto do script principal.  Selecionando a entrada de trabalho do serviço no painel **threads** , você deve ser capaz de alternar para esse contexto.  

## Exibir e editar propriedades locais, de fechamento e globais  

Enquanto pausado em uma linha de código, use o painel **escopo** para exibir e editar os valores de propriedades e variáveis nos escopos local, fechamento e global.  

*   Clique duas vezes em um valor de propriedade para alterá-lo.  
*   As propriedades não enumeráveis ficam acinzentadas.  

:::image type="complex" source="../media/javascript-sources-get-started-js-scope.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-sources-get-started-js-scope.msft.png":::
   O painel **escopo**  
:::image-end:::  

## Exibir a pilha de chamadas atual  

Enquanto pausado em uma linha de código, use o painel de **pilha de chamadas** para ver a pilha de chamadas que você recebeu para este ponto.  

<!--If you are working with async code, check the **Async** checkbox to enable async call stacks.  -->  

Escolha em uma entrada para saltar para a linha de código em que essa função foi chamada.  O ícone de seta azul representa qual função DevTools está realçando no momento.  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png":::
   O painel **pilha de chamadas**  
:::image-end:::  

> [!NOTE]
> Quando não pausa em uma linha de código, o painel **pilha de chamadas** está vazio.  

### Copiar rastreamento de pilha  

<!--
This should be moved to an "Export debug data" H2 section when there is enough content for that, but there is not right now, so it is here.
-->

Clique com o botão direito do mouse em qualquer lugar no painel de **pilha de chamadas** e escolha **copiar rastreamento de pilha** para copiar a pilha de chamadas atual para a área de transferência.  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png":::
   Escolha **copiar rastreamento de pilha**  
:::image-end:::  

O trecho de código a seguir é um exemplo da saída.  

```javascript
getNumber1 (get-started.js:35)
inputsAreEmpty (get-started.js:22)
onClick (get-started.js:15)
```  

## Ignorar um script ou um padrão de scripts  

Marque um script como código da biblioteca quando quiser ignorar esse script durante a depuração.  Quando marcado como código de biblioteca, um script fica obscurecido no painel de **pilha de chamadas** , e você nunca percorre as funções do script quando percorre o código.  

O trecho de código a seguir é um exemplo para percorrer.  

```javascript
function animate() {
    prepare();
    lib.doFancyStuff(); // A
    render();
}
```  

`A` é uma biblioteca de terceiros em que você confia.  Se você tiver certeza de que o problema que está depurando não está relacionado à biblioteca de terceiros, faça sentido marcar o script como código de **biblioteca**.  

### Marcar um script como código da biblioteca no painel do editor  

Conclua as ações a seguir para marcar um script como **código de biblioteca** no painel do **Editor** .  

1.  Abra o arquivo.  
1.  Clique com o botão direito do mouse em qualquer lugar.  
1.  Escolha **Marcar como código da biblioteca**.  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png":::
       Marcar um script como **código da biblioteca** no painel do **Editor**  
    :::image-end:::  
    
### Marcar um script como código da biblioteca no painel pilha de chamadas  

Compelte folliwng XX XX XX XX XX XX XX **Library code** XX XX XX XX **Call Stack** .  

1.  Clique com o botão direito do mouse em uma função do script.  
1.  Escolha **Marcar como código da biblioteca**.  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png":::
       Marcar um script como **código da biblioteca** no painel **pilha de chamadas**  
    :::image-end:::  
    
### Marcar um script como código de biblioteca em configurações  

Conclua as ações a seguir para marcar um único script ou um padrão de scripts em **configurações**.  

1.  Abrir [as configurações][DevToolsCustomize].  
1.  Vá para a guia **código da biblioteca** .  
1.  Escolha **Adicionar padrão**.  
1.  Digite o nome do script ou um padrão de Regex de nomes de script para marcar como **código de biblioteca**.  
1.  Escolha **Adicionar**.  
    
    :::image type="complex" source="../media/javascript-framework-library-code.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-framework-library-code.msft.png":::
       Marcar um script como **código de biblioteca** em **configurações**  
    :::image-end:::  
    
## Executar trechos de código de depuração de qualquer página  

Se você estiver executando o mesmo código de depuração no console repetidamente, considere os trechos de código.  Trechos de código são scripts de tempo de execução que você cria, armazena e executa dentro do DevTools.  

Consulte [executar trechos de código em qualquer página][DevToolsJavascriptSnippets] para saber mais.  

## Assista aos valores de expressões JavaScript personalizadas  

Use o painel de **inspeção** para ver os valores de expressões personalizadas.  Você pode assistir a uma expressão JavaScript válida.  

:::image type="complex" source="../media/javascript-sources-get-started-js-watch.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-sources-get-started-js-watch.msft.png":::
   O painel de **inspeção**  
:::image-end:::  

*   Escolha o botão **Adicionar expressão** \ ( ![ Adicionar expressão ][ImageAddExpressionIcon] \) para criar uma nova expressão de inspeção.  
*   Escolha o botão **Atualizar** \ ( ![ Atualizar ][ImageRefreshIcon] \) para atualizar os valores de todas as expressões existentes.  Valores são atualizados automaticamente durante a depuração do código.  
*   Passe o mouse sobre uma expressão e escolha o botão **excluir expressão** \ ( ![ excluir expressão ][ImageDeleteExpressionIcon] \) para excluí-la.  

## Torne um arquivo do minified legível  

Escolha o botão **formato** \ ( ![ formato ][ImageFormatIcon] \) para fazer com que um arquivo minified seja legível pelo homem.  

:::image type="complex" source="../media/javascript-sources-html-non-minified.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-sources-html-non-minified.msft.png":::
   O botão **Formatar**  
:::image-end:::  

## Editar um script  

Ao corrigir um bug, você muitas vezes deseja testar algumas alterações no código JavaScript.  Você não precisa fazer as alterações em um editor externo ou IDE e, em seguida, recarregar a página.  Você pode editar o script no DevTools.  

Conclua as ações a seguir para editar um script.  

1.  Abra o arquivo no painel **Editor** do painel **fontes** .  
1.  Faça suas alterações no painel do **Editor** .  
1.  Selecione `Ctrl` + `S` \ (Windows, Linux \) ou `Command` + `S` \ (MacOS \) para salvar.  O DevTools patches de todo o arquivo JS para o mecanismo JavaScript do Microsoft Edge.  
    
    :::image type="complex" source="../media/javascript-sources-html-minified.msft.png" alt-text="Selecione passar sobre" lightbox="../media/javascript-sources-html-minified.msft.png":::
       Painel do **Editor**  
    :::image-end:::  
     
## Desabilitar o JavaScript  

Navegue até [desabilitar JavaScript com o Microsoft Edge devtools][DevToolsJavascriptDisable].  

## Entrar em contato com a equipe Microsoft Edge DevTools  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageStepOverIcon]: ../media/step-over-icon.msft.png  
[ImageStepIntoIcon]: ../media/step-into-icon.msft.png  
[ImageStepOutIcon]: ../media/step-out-icon.msft.png  
[ImageResumeScriptExecutionIcon]: ../media/resume-script-run-icon.msft.png  
[ImageForceScriptExecutionIcon]: ../media/force-script-run-icon.msft.png  
[ImageAddExpressionIcon]: ../media/add-expression-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  
[ImageDeleteExpressionIcon]: ../media/delete-expression-icon.msft.png  
[ImageFormatIcon]: ../media/format-icon.msft.png  

<!-- links -->  

[DevToolsJavascriptBreakpoints]: ./breakpoints.md "Como pausar um código com pontos de interrupção no Microsoft Edge DevTools | Documentos da Microsoft"  
[DevToolsJavascriptDisable]: ./disable.md "Desabilitar JavaScript com o Microsoft Edge DevTools | Documentos da Microsoft"  
[DevToolsJavascriptGetStarted]: ./index.md "Introdução à depuração JavaScript no Microsoft Edge DevTools | Documentos da Microsoft"  
[DevToolsJavascriptSnippets]: ./snippets.md "Executar trechos de JavaScript em qualquer página com o Microsoft Edge DevTools | Documentos da Microsoft"  
[DevToolsCustomize]: ../customize/index.md "Personalizar o Microsoft Edge DevTools | Documentos da Microsoft"  

> [!NOTE]
> Partes desta página são modificações com base no trabalho criado e [compartilhado pelo Google][GoogleSitePolicies] e usados de acordo com os termos descritos na [licença internacional Creative Commons][CCA4IL]rereference 4,0 International.  
> A página original é encontrada [aqui](https://developers.google.com/web/tools/chrome-devtools/javascript/reference) e é criada por [Kayce Basques][KayceBasques] \ (redator técnico, Chrome devtools \ & Lighthouse \).  

[![Licença Creative Commons][CCby4Image]][CCA4IL]  
Esse trabalho é licenciado sob uma [Licença Attribution 4.0 International (CC BY 4.0) da Creative Commons][CCA4IL].  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
