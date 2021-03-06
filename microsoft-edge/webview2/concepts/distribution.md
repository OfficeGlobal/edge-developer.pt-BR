---
description: Opções de distribuição ao liberar um aplicativo usando o Microsoft Edge WebView2
title: Distribuição de aplicativos do Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, webview2, WebView, aplicativos WPF, WPF, Edge, ICoreWebView2, ICoreWebView2Host, controle do navegador, HTML Edge
ms.openlocfilehash: bf0a79d41d9eddf39a31426db79d502c09b782ad
ms.sourcegitcommit: af91bfc3e6d8afc51f0fbbc0fe392262f424225c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2020
ms.locfileid: "11120344"
---
# Distribuição de aplicativos usando o WebView2  

Ao distribuir seu aplicativo do WebView2, certifique-se de que a plataforma da Web de backup, o [tempo de execução do WebView2][Webview2Installer], esteja presente antes do início do aplicativo.  Este artigo descreve como você pode instalar o tempo de execução do  [WebView2 e usar](#evergreen-distribution-mode) os dois modos de distribuição para seu aplicativo do WebView2: versão do baixo e [fixo](#fixed-version-distribution-mode).  

## Modo de distribuição do verde  

> [!NOTE]
> O modo de distribuição de verde é recomendado para a maioria dos desenvolvedores.  

O modo de distribuição do verde garante que seu aplicativo Tire proveito dos recursos e das atualizações de segurança mais recentes.  Ele tem as características a seguir.  

*   A plataforma da Web subjacente \ (tempo de execução WebView2 \) é atualizada automaticamente sem esforço adicional.  
*   Todos os aplicativos que usam o modo de distribuição para o verde usam uma cópia compartilhada do tempo de execução do WebView2, que poupa espaço em disco.  
    
### Compreendendo o tempo de execução do WebView2  

O tempo de execução do WebView2 é um tempo de execução redistribuível e serve como a plataforma de backup para aplicativos do WebView2.  O conceito é semelhante ao Visual C++ ou ao .NET Runtime para aplicativos C++/.NET.  O tempo de execução contém binários do Microsoft Edge \ (Chromium \) modificados e testados para aplicativos.  O tempo de execução não aparece como um navegador visível ao usuário durante a instalação.  Por exemplo, um usuário não tem um atalho da área de trabalho do navegador ou uma entrada do menu iniciar.  

Durante o desenvolvimento e o teste, você pode usar como a plataforma da Web de backup.  

*   O tempo de execução do WebView2  
*   Qualquer canal do navegador Office Insider \ (não estável \) Microsoft Edge \ (Chromium \)  

Em ambientes de produção, você deve garantir que o tempo de execução esteja presente em dispositivos de usuário antes de o aplicativo iniciar.  O canal estável do Microsoft Edge não está disponível para uso do WebView2.  A decisão impede que os aplicativos tirem uma dependência do navegador na produção.

Não faça dependências no navegador porque:  

*   O Microsoft Edge \ (Chromium \) não está garantido para estar presente em todos os dispositivos do usuário.  Por exemplo, dispositivos desconectados do Windows Update ou não são gerenciados pela Microsoft diretamente \ (uma grande parte da empresa e o setor EDU) podem não ter o navegador.  Permitir que você distribua o tempo de execução WebView2 evita fazer uma dependência do navegador como pré-requisito para aplicativos.  
*   Navegadores e aplicativos têm casos de uso diferentes e, portanto, assumir uma dependência em um navegador pode ter efeitos colaterais indesejados nos seus aplicativos.  Por exemplo, os administradores de ti podem controlar a versão do navegador para compatibilidade de site interno.  O tempo de execução do WebView2 permite que os aplicativos permaneçam sempre à frente enquanto as atualizações do navegador são gerenciadas ativamente.  
*   Ao contrário do navegador, o tempo de execução é desenvolvido e testado para cenários de aplicativo e, em alguns casos, pode incluir correções de bugs que ainda não estão disponíveis no navegador.  
    
No futuro, o tempo de execução do WebView2 em verde será enviado em versões futuras do Windows.  Implante o tempo de execução com o aplicativo de produção até que o tempo de execução se torne mais universalmente disponível.  

### Implantando o tempo de execução do WebView2 verde  

Apenas uma instalação do WebView2 do tempo de execução do verde é necessária para todos os aplicativos no dispositivo.  Há várias ferramentas disponíveis na página de download do [tempo de execução do WebView2][Webview2Installer].  As ferramentas a seguir ajudam a implantar o tempo de execução de verde.  

*   O inicializador de tempo de execução do WebView2 é um instalador pequeno \ (aproximadamente 2 MB \).  O inicializador de tempo de execução do WebView2 baixa e instala o tempo de execução de verde dos servidores da Microsoft que corresponde à arquitetura de dispositivos do usuário.  
*   Use um link para baixar programaticamente o bootstrapper.  
*   O instalador autônomo do WebView2 Runtime é um instalador completo que pode instalar o tempo de execução do WebView2 verde em ambientes offline.  
    
Atualmente, tanto o bootstrapper quanto o instalador autônomo são compatíveis com instalações por máquina, o que requer elevação.  Se um instalador for executado sem elevação, o usuário será solicitado a elevar as permissões.  

Recomendamos os seguintes fluxos de trabalho para garantir que o tempo de execução já esteja instalado antes do aplicativo ser iniciado.  Você pode ajustar o fluxo de trabalho dependendo do cenário.  O exemplo de código está disponível no [repositório de exemplos][InstallerSample].  

#### Implantação somente online  

Se você tiver um cenário de implantação somente online em que os usuários finais presumiram ter acesso à Internet, conclua as etapas a seguir.  

1.  Durante a configuração do aplicativo, verifique se o tempo de execução já está instalado.  Para verificar, execute uma das seguintes ações.  
    *   Inspecione se a `pv (REG_SZ)` RegKey existe e não está `null` ou está vazia.  Localize  `pv (REG_SZ)` no local a seguir.  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```
          
    *   Execute o [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] e verifique se o `versionInfo` está `NULL` .  
1.  Se o tempo de execução não estiver instalado, use o link para baixar programaticamente o bootstrapper.  
1.  Invoque o bootstrapper de um processo elevado ou prompt de comando com `MicrosoftEdgeWebview2Setup.exe /silent /install` para a instalação silenciosa.  
    
O fluxo de trabalho anterior tem os seguintes benefícios.  

*   Instale o tempo de execução somente quando necessário ou quando não for necessário fazer pacotes para instaladores.  
*   O bootstrapper detecta automaticamente a arquitetura do dispositivo e instala o tempo de execução correspondente. 
*   Instale o tempo de execução silenciosamente.  
    
Você também pode optar por empacotar o bootstrapper com seu aplicativo em vez de baixá-lo programaticamente sob demanda.  

#### Implantação offline  

Se você tiver um cenário de implantação offline em que a implantação do aplicativo tem que funcionar completamente offline, conclua as etapas a seguir.  

1.  Baixe o [instalador autônomo][Webview2Installer].  
1.  Inclua o instalador em seu instalador de aplicativos ou atualizador.  
1.  Durante a configuração do aplicativo, verifique se o tempo de execução já está instalado.  Para verificar, execute uma das seguintes ações.  
    *   Inspecione se a `pv (REG_SZ)` RegKey existe e não está `null` ou está vazia.  Localize  `pv (REG_SZ)` no local a seguir.  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```
          
    *   Execute o [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] e verifique se o `versionInfo` está `NULL` .  
1.  Se o tempo de execução não estiver instalado, execute o instalador autônomo.  Se você quiser executar uma instalação silenciosa, execute o instalador a partir de um processo elevado ou copie e execute o seguinte comando.  
    
    ```shell
    MicrosoftEdgeWebView2RuntimeInstaller{X64/X86/ARM64}.exe /silent /install
    ```  
    
### Mantenha-se compatível com o modo verde

A Web está sempre em evolução. O tempo de execução do WebView2 está sempre atualizado para fornecer os recursos e correções de segurança mais recentes.  Para garantir que seu aplicativo permaneça compatível com a Web, recomendamos que você configure a infraestrutura de teste.

Canais não estáveis do Microsoft Edge \ (beta/dev/Canárias \) fornecem uma espiada no que está chegando em WebView2 tempo de execução.  Assim como o desenvolvimento de sites para Microsoft Edge, recomendamos que você teste seu aplicativo WebView2 regularmente.  Teste seu aplicativo WebView2 em um dos canais não estáveis e atualize seu aplicativo ou [informe problemas][GithubMicrosoftedgeWebviewfeedback] se surgirem problemas. Geralmente, o desenvolvimento e a versão beta são os canais recomendados.  Para ajudá-lo a decidir qual canal está correto, navegue até [visão geral dos canais Microsoft Edge][DeployEdgeMicrosoftEdgeChannels].  Você pode baixar o [canal Microsoft Edge não estável][DownloadNonstableEdge] em seu ambiente de teste e usar `regkey` ou variáveis de ambiente para indicar a preferência de canal para o aplicativo de teste.  Para obter mais informações, acesse [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions].  Você também pode usar o [WebDriver][HowtoWebdriver] para automatizar o teste do WebView2.

## Modo de distribuição de versão corrigido  

> [!NOTE]
> O modo de distribuição de versão fixa está em visualização pública.  

O modo de distribuição de versão fixa anteriormente tinha o nome de trazer para a sua conta.  

Para ambientes restritos com requisitos de compatibilidade estritos, considere o uso do modo de distribuição de versão fixa.  Selecione e empacote uma versão específica do tempo de execução do WebView2 usando o modo de distribuição de versão fixa.  Você pode especificar o intervalo de atualizações de tempo de execução para seu aplicativo.  O modo de distribuição de versão fixa não recebe atualizações automáticas. Você deve planejar a atualização do seu aplicativo e do tempo de execução.  

Para usar o modo de versão corrigido,  

*   [Baixe][Webview2Installer] o pacote de versão corrigido e descompacte o pacote.  
*   Inclua os binários de versão descompactada em seu projeto.  
*   Indique o caminho para os binários de versão fixa ao criar o ambiente WebView2.  
    *   Para o Win32 C/C++, você pode criar o ambiente usando a função [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions] .  Use o `browserExecutableFolder` parâmetro para indicar o caminho para os binários de versão corrigidos.  
    *   Para .NET, você pode executar uma das seguintes opções para especificar o ambiente.  
        
        > [!NOTE]
        > Você deve especificar o ambiente antes de a `Source` Propriedade WebView2 entrar em vigor.  
        
        *   Defina a `CreationProperties` Propriedade \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties] / [WinForms][ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]\) no elemento WebView2.  Use o `BrowserExecutableFolder` membro na `CoreWebView2CreationProperties` classe \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties] / [WinForms][ReferenceWinFormsMicrosoftWebWebview2WinForms]\) para indicar o caminho para os binários de versão corrigido.  
        *   Use `EnsureCoreWebView2Async` \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async] / [WinForms][ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]\) para especificar o ambiente.  Use o `browserExecutableFolder` parâmetro em [CoreWebView2Environment. createasync][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync] para indicar o caminho para os binários de versão corrigido.  
*   Empacote e envie os binários de versão corrigido com seu aplicativo.  Atualize os binários conforme apropriado.  
    
<!-- links -->  

[ConceptsVersioning]: ./versioning.md "Noções básicas sobre versões do navegador e WebView2 | Documentos da Microsoft"  

[HowtoWebdriver]: ../howto/webdriver.md "Automatizando e testando o WebView2 com o Microsoft Edge driver | Documentos da Microsoft"  

[DeployEdgeMicrosoftEdgeChannels]: /deployedge/microsoft-edge-channels "Visão geral dos canais Microsoft Edge | Documentos da Microsoft"  

[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.createasync "Classe createasync-Microsoft. Web. WebView2. Core. CoreWebView2Environment | Documentos da Microsoft"  

[ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async "EnsureCoreWebView2Async-classe Microsoft. Web. WebView2. WPF. WebView2 | Documentos da Microsoft"  

[ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.winforms.webview2.ensurecorewebview2async "EnsureCoreWebView2Async-classe Microsoft. Web. WebView2. WinForms. WebView2 | Documentos da Microsoft"  

[ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.corewebview2creationproperties "CoreWebView2CreationProperties-classe Microsoft. Web. WebView2. WPF. CoreWebView2CreationProperties | Documentos da Microsoft"  

[ReferenceWinFormsMicrosoftWebWebview2WinForms]: /dotnet/api/microsoft.web.webview2.winforms "Classe Microsoft. Web. WebView2. WinForms | Documentos da Microsoft"  

[ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.webview2.creationproperties "Creationproperties-Microsoft. Web. WebView2. WPF. WebView2 Class | Documentos da Microsoft"  

[ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]: /dotnet/api/microsoft.web.webview2.winforms.webview2 "Classe Microsoft. Web. WebView2. WinForms. WebView2 | Documentos da Microsoft"  

[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-globais | Documentos da Microsoft"  

[ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]: /microsoft-edge/webview2/reference/win32/webview2-idl#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString-globais | Documentos da Microsoft"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "Instalador do WebView2"  

[InstallerSample]: https://aka.ms/wv2installersample "Exemplo de instalador WebView2"  

[DownloadNonstableEdge]: https://www.microsoftedgeinsider.com/download "Baixar canais do Microsoft Edge Insider"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView feedback | GitHub"  
