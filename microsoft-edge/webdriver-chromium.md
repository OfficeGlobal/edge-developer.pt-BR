---
description: Saiba como testar seu site ou aplicativo no Microsoft Edge ou automatizar o navegador com o WebDriver.
title: WebDriver (Chromium)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: Microsoft Edge, desenvolvimento na Web, HTML, CSS, JavaScript, desenvolvedor, WebDriver, Selenium, testes, ferramentas, automação, teste
ms.openlocfilehash: 0cb135553b04cd0cf160755eacc0dbae245d13b7
ms.sourcegitcommit: 24430258f363b7dd85f7067afd4565bf102b4a1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "10645312"
---
# WebDriver (Chromium)  

A API do W3C [WebDriver][W3CWebdriver] é uma plataforma e uma interface neutra em linguagem e um protocolo de conexão, permitindo que programas ou scripts controlem o comportamento de um navegador da Web, como o Microsoft Edge \ (Chromium \).  

O WebDriver permite que os desenvolvedores criem testes automatizados que simulam a interação do usuário.  Testes e simulações do WebDriver diferem dos testes de unidade JavaScript porque o WebDriver tem acesso à funcionalidade e às informações que o JavaScript em execução no navegador não, e a unidade ia pode simular com mais precisão os eventos do usuário ou do nível do sistema operacional.  O WebDriver é capaz de gerenciar testes em várias janelas, guias e páginas da Web em uma única sessão de teste.  

Veja como começar a usar o WebDriver para Microsoft Edge \ (Chromium \).  

## Instalar o Microsoft Edge (Chromium)  

Se você ainda não tiver feito isso, [Instale o Microsoft Edge (Chromium)][MicrosoftEdge].  Se você estiver usando uma versão pré-instalada do Microsoft Edge em seu computador, verifique se você tem o Microsoft Edge \ (Chromium \) e não o Microsoft Edge \ (EdgeHTML \).  Uma maneira rápida de verificar é carregar `edge://settings/help` no navegador e confirmar se o número da versão é v75 ou posterior.  

## Baixar o driver Microsoft Edge  

O WebDriver requer um driver específico do navegador para automatizar cada navegador.  Para o Microsoft Edge \ (Chromium \), o WebDriver requer o [Driver da Microsoft Edge][MicrosoftDeveloperEdgeToolsWebdriver] apropriado para a compilação do Microsoft Edge que você deseja testar ou automatizar.  

Para encontrar o seu número de versão correto, use as etapas a seguir.  

1.  Iniciar o Microsoft Edge 
1.  Exiba a versão \ (Chromium \) do Microsoft Edge.  
    *   Navegue até `edge://settings/help`  
    *   Selecionar `...`  >  **configurações**  >   **sobre o Microsoft Edge**  
1.  Verifique se a versão correta do WebDriver para a sua compilação garante, para que ele seja executado corretamente.  

:::image type="complex" source="./media/webdriver-chromium/edge-version.png" alt-text="O número do Build para o Microsoft Edge Canárias em 14 de janeiro de 2020":::
   Figura 1.  O número do Build para o Microsoft Edge Canárias em 14 de janeiro de 2020  
:::image-end:::

<!--  
> ##### Figure 1  
> The build number for Microsoft Edge Canary on January 14, 2020
> ![The build number for Microsoft Edge Canary on January 14, 2020][ImageWebdriverChromiumEdgeVersion]  
-->  

Agora, [Baixe a versão correspondente do driver Microsoft Edge][MicrosoftDeveloperEdgeToolsWebdriverDownloads].  

:::image type="complex" source="./media/webdriver-chromium/edge-driver-install.png" alt-text="A seção downloads da página do driver Microsoft Edge":::
   Figura 2.  A seção downloads da página do [driver Microsoft Edge][MicrosoftDeveloperEdgeToolsWebdriverDownloads]  
:::image-end:::

<!--  
> ##### Figure 2
> The Downloads section of the [Microsoft Edge Driver page][MicrosoftDeveloperEdgeToolsWebdriverDownloads]
> ![The Downloads section of the Microsoft Edge Driver page][ImageWebdriverChromiumEdgeDriverInstall]  
-->  

> [!NOTE]
> O Microsoft Edge \ (EdgeHTML \) não funciona com [o Microsoft Edge driver][MicrosoftDeveloperEdgeToolsWebdriverDownloads].  Para automatizar o Microsoft Edge \ (EdgeHTML \), você deve baixar [o Microsoft WebDriver para Microsoft Edge \ (EdgeHTML \)][Webdriver].  

## Escolher uma associação de linguagem do WebDriver  

O último componente que você deve baixar é um driver de cliente específico do idioma.  A associação de linguagem traduz o código que você escreve em Python, Java, C \ #, Ruby e JavaScript em comandos que o driver Microsoft Edge que você baixou na [seção anterior](#download-microsoft-edge-driver) pode executar no Microsoft Edge \ (Chromium \).  

[Baixe a vinculação de linguagem do WebDriver de sua preferência][SeleniumDownloads].  A equipe do Microsoft Edge é altamente recomendável [Selenium 4, 0-alpha05][NugetPackagesSeleniumWebdriver400alpha05] ou posterior, pois ele tem suporte interno para o Microsoft Edge \ (Chromium \).  No entanto, você pode orientar o Microsoft Edge \ (Chromium \) em todas as versões mais antigas do Selenium, incluindo a versão atual de 3 estável do Selenium.  

> [!IMPORTANT]
> Se você já estava automatizando ou testando o Microsoft Edge \ (Chromium \) usando `ChromeDriver` e `ChromeOptions` , o código do seu WebDriver não é executado com êxito no Microsoft Edge V80 ou posterior.  Esta é uma alteração quebrada, e o Microsoft Edge \ (Chromium \) não aceita mais esses comandos.  Você deve alterar seus testes para usar o `EdgeOptions` Driver de classe e [Microsoft Edge][MicrosoftDeveloperEdgeToolsWebdriver].  

### Usando o Selenium 3  

O [Selenium 3][|::ref1::|] é a versão mais recente do Selenium estável.  Por padrão, o Selenium 3 impulsiona o antigo Microsoft Edge \ (EdgeHTML \) e não tem suporte interno para o Microsoft Edge \ (Chromium \).  Para usar o Selenium 3 com o Microsoft Edge \ (Chromium \), instale o pacote do [Selenium Tools para Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] .  As ferramentas Selenium para Microsoft Edge Extend Selenium 3 com um driver atualizado para ajudá-lo a escrever testes automatizados para os navegadores Microsoft Edge \ (EdgeHTML \) e New Microsoft Edge \ (Chromium \).  

O Selenium Tools para Microsoft Edge é uma solução para os desenvolvedores que preferem permanecer no Selenium 3 e nos desenvolvedores que têm testes de navegador existentes e querem adicionar cobertura para o novo navegador Microsoft Edge \ (Chromium \) sem alterar as versões do Selenium.  As `EdgeDriver` classes e as `EdgeDriverService` contidas nas ferramentas são totalmente compatíveis com os equivalentes internos no Selenium e executam o Microsoft Edge \ (EdgeHTML \) por padrão para que as ferramentas possam ser usadas como uma substituição automática para as classes de borda existentes no Selenium.  

[Instale o Selenium Tools para Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] para começar a usar o Microsoft Edge \ (Chromium \) com seu projeto do Selenium 3.  

## Usar o Microsoft Edge (Chromium) com o WebDriver

Os exemplos a seguir são executáveis usando o Selenium 3 ou 4.  Para usar com o Selenium 3, as [Ferramentas do Selenium para Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] devem estar instaladas.  

### Uso básico  

Para usar com o Microsoft Edge \ (EdgeHTML \), basta criar uma instância padrão da `EdgeDriver` classe.

#### [C#](#tab/c-sharp/)  

<a id="basic-usage-code" />  

```csharp
var driver = new EdgeDriver();
```  

#### [Python](#tab/python/)  

<a id="basic-usage-code" />  

```python
driver = Edge()
```  

* * *  

### Dirigir o Microsoft Edge (Chromium)  

Para usar com o Microsoft Edge \ (Chromium \) em vez disso, crie uma nova `EdgeDriver` classe e passe a ela o `EdgeOptions` objeto com a `UseChromium` propriedade definida como `true` .  

#### [C#](#tab/c-sharp/)  

<a id="diving-microsoft-edge-chromium-code" />  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [Python](#tab/python/)  

<a id="diving-microsoft-edge-chromium-code" />  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

* * *  

### Escolher binários específicos do navegador (somente Chromium)  

Use a `EdgeOptions` classe para escolher um binário específico.  Isso é útil para testar os [canais da visualização do Microsoft Edge][MicrosoftedgeinsiderDownload] , como o Microsoft Edge beta.  

#### [C#](#tab/c-sharp/)  

<a id="choosing-specific-browser-binaries-chrome-only-code" />  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [Python](#tab/python/)  

<a id="choosing-specific-browser-binaries-chrome-only-code" />  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

* * *  

### Personalizando o serviço de driver do Microsoft Edge  

#### [C#](#tab/c-sharp/)  

<a id="customizing-microsoft-edge-driver-services-code" />  

Quando uma `EdgeDriver` instância de classe é criada usando `EdgeOptions` classe, ela cria e abre automaticamente a `EdgeDriverService` classe apropriada para o Microsoft Edge \ (EdgeHTML \) ou o Microsoft Edge \ (Chromium \).  

Se você quiser criar um `EdgeDriverService` , crie um configurado para o Microsoft Edge \ (Chromium \) usando o `CreateChromiumService()` método.  Pode ser útil para personalizações adicionais, como habilitar a saída de log detalhada no código a seguir.  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE]
> Você não precisa fornecer o `EdgeOptions` objeto ao passar a `EdgeDriver` instância da classe a `EdgeDriverService` .  A `EdgeDriver` classe usa as opções padrão para o Microsoft Edge \ (EdgeHTML \) ou o Microsoft Edge \ (Chromium \), dependendo do tipo de serviço que você fornecer.  
> 
> No entanto, se você quiser fornecer uma `EdgeDriverService` classe and e `EdgeOptions` , você deve garantir que ambos estejam configurados para a mesma versão do Microsoft Edge.  Por exemplo, não é possível usar uma classe padrão do Microsoft Edge \ (EdgeHTML \) `EdgeDriverService` e as propriedades Chromium na `EdgeOptions` classe.  A `EdgeDriver` classe gera um erro para impedir o uso de versões diferentes.  

#### [Python](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code" />  

Ao usar Python, o `Edge` objeto cria e gerencia o `EdgeService` .  Para configurar o `EdgeService` , passe argumentos adicionais para o `Edge` objeto:

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

* * *  

### Usando opções específicas do Chromium  

Usar a `EdgeOptions` classe com a `UseChromium` propriedade definida como `true` fornece acesso a todos os mesmos métodos e propriedades que estão disponíveis na classe [chromeoptions][SeleniumWebDriverChromeoptionsClass] em Selenium.  Por exemplo, assim como outros navegadores do Chromium, use o `EdgeOptions.AddArguments()` método para executar o Microsoft Edge \ (Chromium \) no [modo sem periféricos][WikiHeadlessBrowser] no código a seguir.  

#### [C#](#tab/c-sharp/)  

<a id="using-chromium-specific-options-code" />  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [Python](#tab/python/)  

<a id="using-chromium-specific-options-code" />  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument('headless')
options.add_argument('disable-gpu')
```  

* * *  

> [!NOTE]
> Essas [Propriedades e métodos específicos do Chromium][SeleniumWebDriverChromeoptionsClass] estão sempre disponíveis, mas não têm efeito se a `UseChromium` propriedade não estiver definida como `true` .  Da mesma forma, propriedades e métodos existentes para Microsoft Edge \ (EdgeHTML \) não têm efeito se `UseChromium` a propriedade for definida como `true` .  

<!--  
### [C#](#tab/c-sharp/)  

<a id="selenium-usage" />  

#### Basic Usage  

To use with Microsoft Edge \(EdgeHTML\), simply create a default instance of the `EdgeDriver` class.

```csharp
var driver = new EdgeDriver();
```  

#### Driving Microsoft Edge (Chromium)  

To use with Microsoft Edge \(Chromium\) instead, create a new `EdgeDriver` class and pass it the `EdgeOptions` object with the `UseChromium` property set to `true`.  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### Choosing Specific Browser Binaries (Chromium-Only)  

Use the `EdgeOptions` class to choose a specific binary.  It is useful for testing [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### Customizing the Edge Driver Service  

When an `EdgeDriver` class instance is created using `EdgeOptions` class, it automatically creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).  

If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.  You may find it useful for additional customizations like enabling verbose log output in the following code.  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE]
> You do not need to provide the `EdgeOptions` object when passing the `EdgeDriver` class instance the `EdgeDriverService`.  The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) depending on what kind of service you provide.  
> 
> However, if you want to provide both an `EdgeDriverService` and `EdgeOptions` classes, you must ensure that both are configured for the same version of Microsoft Edge.  For example, it is not possible to use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.  The `EdgeDriver` class throws an error to prevent using different versions.  

#### Using Chromium-Specific Options  

Using the `EdgeOptions` class with the `UseChromium` property set to `true` gives you access to all of the same methods and properties that are available in the [ChromeOptions][SeleniumWebDriverChromeoptionsClass] class in Selenium.  For example, just like with other Chromium browsers, use the `EdgeOptions.AddArguments()` method to run Microsoft Edge \(Chromium\) in [headless mode][WikiHeadlessBrowser] in the following code.  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

> [!NOTE]
> These [Chromium-specific properties and methods][SeleniumWebDriverChromeoptionsClass] are always available but have no effect if the `UseChromium` property is not set to `true`.  Similarly, existing properties and methods meant for Microsoft Edge \(EdgeHTML\) have no effect if `UseChromium` property is set to `true`.  

### [Python](#tab/python/)  

<a id="selenium-usage" />  

#### Basic Usage  

To use with Microsoft Edge \(EdgeHTML\), simply create a default instance of the `EdgeDriver` class.

```python
driver = Edge()
```  

#### Driving Microsoft Edge (Chromium)  

To use with Microsoft Edge \(Chromium\) instead, create a new `EdgeDriver` class and pass it the `EdgeOptions` object with the `UseChromium` property set to `true`.  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

#### Choosing Specific Browser Binaries (Chromium-Only)  

Use the `EdgeOptions` class to choose a specific binary.  It is useful for testing [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

#### Customizing the Edge Driver Service  

When an `EdgeDriver` class instance is created using `EdgeOptions` class, it automatically creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).  

If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.  You may find it useful for additional customizations like enabling verbose log output in the following code.  

When using Python, the `Edge` object creates and manages the `EdgeService`.  To configure the `EdgeService`, pass additional arguments to the `Edge` object:

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### Using Chromium-Specific Options  

Using the `EdgeOptions` class with the `UseChromium` property set to `true` gives you access to all of the same methods and properties that are available in the [ChromeOptions][SeleniumWebDriverChromeoptionsClass] class in Selenium.  For example, just like with other Chromium browsers, use the `EdgeOptions.AddArguments()` method to run Microsoft Edge \(Chromium\) in [headless mode][WikiHeadlessBrowser] in the following code.  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument('headless')
options.add_argument('disable-gpu')
```  

> [!NOTE]
> These [Chromium-specific properties and methods][SeleniumWebDriverChromeoptionsClass] are always available but have no effect if the `UseChromium` property is not set to `true`.  Similarly, existing properties and methods meant for Microsoft Edge \(EdgeHTML\) have no effect if `UseChromium` property is set to `true`.  

* * *  

-->  

<!--  
### Basic Usage  

To use with Microsoft Edge \(EdgeHTML\), simply create a default instance of the `EdgeDriver` class.

#### C\#  

```csharp
var driver = new EdgeDriver();
```  

#### Python  

```python
driver = Edge()
```  

### Driving Microsoft Edge (Chromium)  

To use with Microsoft Edge \(Chromium\) instead, create a new `EdgeDriver` class and pass it the `EdgeOptions` object with the `UseChromium` property set to `true`.  

#### C\#  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### Python  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

### Choosing Specific Browser Binaries (Chromium-Only)  

Use the `EdgeOptions` class to choose a specific binary.  It is useful for testing [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.  

#### C\#  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### Python  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

### Customizing the Edge Driver Service  

#### C\#  

When an `EdgeDriver` class instance is created using `EdgeOptions` class, it automatically creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).  

If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.  You may find it useful for additional customizations like enabling verbose log output in the following code.  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE]
> You do not need to provide the `EdgeOptions` object when passing the `EdgeDriver` class instance the `EdgeDriverService`.  The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) depending on what kind of service you provide.  
> 
> However, if you want to provide both an `EdgeDriverService` and `EdgeOptions` classes, you must ensure that both are configured for the same version of Microsoft Edge.  For example, it is not possible to use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.  The `EdgeDriver` class throws an error to prevent using different versions.  

#### Python  

When using Python, the `Edge` object creates and manages the `EdgeService`.  To configure the `EdgeService`, pass additional arguments to the `Edge` object:

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

### Using Chromium-Specific Options  

Using the `EdgeOptions` class with the `UseChromium` property set to `true` gives you access to all of the same methods and properties that are available in the [ChromeOptions][SeleniumWebDriverChromeoptionsClass] class in Selenium.  For example, just like with other Chromium browsers, use the `EdgeOptions.AddArguments()` method to run Microsoft Edge \(Chromium\) in [headless mode][WikiHeadlessBrowser] in the following code.  

#### C\#  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### Python  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument('headless')
options.add_argument('disable-gpu')
```  

> [!NOTE]
> These [Chromium-specific properties and methods][SeleniumWebDriverChromeoptionsClass] are always available but have no effect if the `UseChromium` property is not set to `true`.  Similarly, existing properties and methods meant for Microsoft Edge \(EdgeHTML\) have no effect if `UseChromium` property is set to `true`.  
-->  

## Outras maneiras de configurar o WebDriver  

### Chocolate  

Se você estiver usando uma [chocolate][Chocolatey] como gerente de pacote, instale o driver Microsoft Edge executando o seguinte comando.  

```console
choco install selenium-chromium-edge-driver
```  

Para obter mais informações, consulte [Selenium Chromium Edge driver em leite][ChocolateyPackagesSeleniumChromiumEdgeDriver].  

### Docker  

Se você estiver usando o [Docker][DockerHub], Baixe uma imagem pré-configurada com o Microsoft Edge \ (Chromium \) e [o Microsoft Edge driver][MicrosoftDeveloperEdgeToolsWebdriver] já instalado executando o seguinte comando.  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

Para obter mais informações, consulte [contêiner no Dock Hub][DockerHubMsedgedriver].  

## Entrar em contato com a equipe do Microsoft Edge DevTools    

A equipe do Microsoft Edge está ansiosos para ouvir seus comentários sobre como usar o WebDriver, o Selenium e o Microsoft Edge!  Use o ícone de **comentários** no Microsoft Edge devtools ou tweet [@EdgeDevTools][TwitterTweetEdgeDevTools] para que a equipe saiba qual é a sua opinião.  


:::image type="complex" source="./devtools-guide-chromium/media/devtools-feedback.png" alt-text="O ícone de comentários no Microsoft Edge DevTools":::
   O ícone de **comentários** no Microsoft Edge devtools  
:::image-end:::

<!--  
> ##### Figure 3  
> The **Feedback** icon in the Microsoft Edge DevTools  
> ![The example.png file produced by example.js][ImageDevtoolsGuideChromiumMediaDevtoolsFeedback])  
-->  

<!-- image links -->  

<!--[ImageWebdriverChromiumEdgeVersion]: ./media/webdriver-chromium/edge-version.png "Figure 1: The build number for Microsoft Edge Canary on January 14, 2020"  -->  
<!--[ImageWebdriverChromiumEdgeDriverInstall]: ./media/webdriver-chromium/edge-driver-install.png "Figure 2: The Downloads section of the Microsoft Edge Driver page"  -->
<!--[ImageDevtoolsGuideChromiumMediaDevtoolsFeedback]: ./devtools-guide-chromium/media/devtools-feedback.png "Figure 3: The example.png file produced by example.js"  -->  

<!-- links -->  

[Webdriver]: ./webdriver.md "WebDriver (EdgeHTML) | Documentos da Microsoft"  

[Chocolatey]: https://chocolatey.org "Chocolate | Software de chocolate"  
[ChocolateyPackagesSeleniumChromiumEdgeDriver]: https://chocolatey.org/packages/selenium-chromium-edge-driver "Selenium Chromium Edge driver | Chocolate"  

[DockerHub]: https://hub.docker.com "Hub do Docker"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver | Hub do Docker"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "Microsoft/Edge-Selenium-ferramentas | GitHub"  
[GithubSeleniumHq]: https://github.com/SeleniumHQ/selenium "SeleniumHQ/Selenium | GitHub"  

[MicrosoftDeveloperEdgeToolsWebdriver]: https://developer.microsoft.com/microsoft-edge/tools/webdriver "WebDriver | Desenvolvedor da Microsoft"
[MicrosoftDeveloperEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver/#downloads "Downloads-WebDriver | Desenvolvedor da Microsoft"  

[MicrosoftEdge]: https://www.microsoft.com/edge "Baixar novo navegador Microsoft Edge"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Baixar canais do Microsoft Edge Insider"  

[NugetPackagesMicrosoftEdgeSeleniumtools]: https://www.nuget.org/packages/Microsoft.Edge.SeleniumTools "Microsoft. Edge. SeleniumTools | Galeria do NuGet"  
[NugetPackagesSeleniumWebdriver31410]: https://www.nuget.org/packages/Selenium.WebDriver/3.141.0 "Selenium. WebDriver 3.141.0 | Galeria do NuGet"  
[NugetPackagesSeleniumWebdriver400alpha05]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha05 "Selenium. WebDriver 4.0.0-alpha05 | Galeria do NuGet"  

[SeleniumHQ]: https://www.selenium.dev "SeleniumHQ"  
[SeleniumDownloads]: https://selenium.dev/downloads "Downloads | Selenium"  
[SeleniumWebDriverChromeoptionsClass]: https://www.selenium.dev/selenium/docs/api/dotnet/?topic=html/T_OpenQA_Selenium_Chrome_ChromeOptions.htm "Chromeoptions Class-WebDriver | Selenium"  

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | Postar um tweet"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "Navegador sem periféricos | Wikipédia"