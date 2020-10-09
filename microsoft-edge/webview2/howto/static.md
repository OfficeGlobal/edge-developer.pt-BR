---
description: Saiba como vincular estaticamente a biblioteca WebView2 Loader.
title: Como vincular estaticamente a biblioteca WebView2 Loader
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/01/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, webview2, WebView, aplicativos Win32, Win32, Edge, ICoreWebView2, ICoreWebView2Host, controle do navegador, HTML Edge
ms.openlocfilehash: b7e0ec70cb00f318d4eb67254f37fcec79a5fcf6
ms.sourcegitcommit: 903524ab85321ade278facd741d6487e8cabe33f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2020
ms.locfileid: "11100292"
---
# <span data-ttu-id="159d3-104">Como vincular estaticamente a biblioteca WebView2 Loader</span><span class="sxs-lookup"><span data-stu-id="159d3-104">How to Statically link the WebView2 loader library</span></span>  

## <span data-ttu-id="159d3-105">Contexto</span><span class="sxs-lookup"><span data-stu-id="159d3-105">Context</span></span>  

<span data-ttu-id="159d3-106">O que é o WebView2Loader.dll?</span><span class="sxs-lookup"><span data-stu-id="159d3-106">What is the WebView2Loader.dll?</span></span>  

*   <span data-ttu-id="159d3-107">O SDK do WebView2 contém um arquivo de cabeçalho, `WebView2Loader.dll.` e o `IDL` arquivo.</span><span class="sxs-lookup"><span data-stu-id="159d3-107">The WebView2 SDK contains a header file, `WebView2Loader.dll.`, and the `IDL` file.</span></span> `WebView2Loader.dll` <span data-ttu-id="159d3-108">é um componente pequeno que ajuda os aplicativos a localizar o tempo de execução do WebView2 (ou canais do Microsoft Edge não estáveis) no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="159d3-108">is a small component that helps apps locate the WebView2 Runtime (or non-stable Microsoft Edge channels) on the device.</span></span>  

<span data-ttu-id="159d3-109">Para aplicativos que têm um tempo de execução único e não querem enviar a `WebView2Loader.dll` , conclua as etapas do **procedimento** a seguir.</span><span class="sxs-lookup"><span data-stu-id="159d3-109">For apps that have a single runtime, and do not want to ship a `WebView2Loader.dll`, complete the following **Procedure** steps.</span></span>  

## <span data-ttu-id="159d3-110">Procedimento</span><span class="sxs-lookup"><span data-stu-id="159d3-110">Procedure</span></span>  

1.  <span data-ttu-id="159d3-111">Abra o `.vcxproj` arquivo de projeto para seu aplicativo em um editor de texto, como código do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="159d3-111">Open the `.vcxproj` project file for your app in a text editor, such as Visual Studio Code.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="159d3-112">O `.vcproj` arquivo de projeto pode ser um arquivo oculto, o que significa que ele não é exibido no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="159d3-112">The `.vcproj` project file may be a hidden file, meaning it does not display in Visual Studio.</span></span>  <span data-ttu-id="159d3-113">Use a linha de comando para localizar um arquivo oculto.</span><span class="sxs-lookup"><span data-stu-id="159d3-113">Use the command-line to find a hidden file.</span></span>  
    
1.  <span data-ttu-id="159d3-114">Localize a seção no código em que você inclui os arquivos de destino do pacote NuGet do WebView2.</span><span class="sxs-lookup"><span data-stu-id="159d3-114">Locate the section in the code where you include the WebView2 NuGet package target files.</span></span>  <span data-ttu-id="159d3-115">O local no código é realçado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="159d3-115">The location in the code is highlighted in the following figure.</span></span>  
    
    :::image type="complex" source="./media/inserthere.png" alt-text="Trecho de código de arquivos de projeto" lightbox="./media/inserthere.png"::: 
       <span data-ttu-id="159d3-117">Trecho de código de arquivos de projeto</span><span class="sxs-lookup"><span data-stu-id="159d3-117">Project Files code snippet</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="159d3-118">Copie o trecho de código a seguir e cole-o em qualquer lugar no qual o `Microsoft.Web.WebView2.targets` está incluído.</span><span class="sxs-lookup"><span data-stu-id="159d3-118">Copy the following code snippet and paste it everywhere the `Microsoft.Web.WebView2.targets` is included.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="159d3-119">Por exemplo, inclua-o após o seguinte bloco de código.</span><span class="sxs-lookup"><span data-stu-id="159d3-119">For example, include it after the following code block.</span></span>  
    > 
    > ```csharp
    > <Import Project="..\packages\Microsoft.Web.WebView2.0.9.579-prerelease\build\native\Microsoft.Web.WebView2.targets" Condition="Exists('..\packages\Microsoft.Web.WebView2.0.9.579-prerelease\build\native\Microsoft.Web.WebView2.targets')" />
    > ```  
    
    ```csharp
    <PropertyGroup> <WebView2LoaderPreference>Static</WebView2LoaderPreference> </PropertyGroup>
    ```
    
    :::image type="complex" source="./media/staticlib.png" alt-text="Trecho de código de arquivos de projeto" lightbox="./media/staticlib.png"::: 
       <span data-ttu-id="159d3-121">Trecho de código inserido</span><span class="sxs-lookup"><span data-stu-id="159d3-121">Inserted code snippet</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="159d3-122">Edite as dependências adicionais da configuração de compilação do seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="159d3-122">Edit the additional dependencies of the build configuration for your app.</span></span>  <span data-ttu-id="159d3-123">Para começar, localize todas as `<AdditionalDependencies>` marcas.</span><span class="sxs-lookup"><span data-stu-id="159d3-123">To begin, find all of the `<AdditionalDependencies>` tags.</span></span>  
1.  <span data-ttu-id="159d3-124">Adicione `version.lib` como uma dependência adicional a cada configuração de compilação diferente no `.vcxproj` arquivo do seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="159d3-124">Add `version.lib` as an additional dependency to every different build configuration in the `.vcxproj` file for your app.</span></span>  
    
    :::image type="complex" source="./media/versionlib.png" alt-text="Trecho de código de arquivos de projeto" lightbox="./media/versionlib.png"::: 
       <span data-ttu-id="159d3-126">Adicionar `version.lib` a</span><span class="sxs-lookup"><span data-stu-id="159d3-126">Adding `version.lib` to</span></span> `ItemDefinitionGroups`  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="159d3-127">A equipe WebView2 tem o objetivo de automatizar a etapa de dependência adicional em lançamentos futuros.</span><span class="sxs-lookup"><span data-stu-id="159d3-127">The WebView2 team aims to automate the additional dependency step in future releases.</span></span>  
    
<span data-ttu-id="159d3-128">Compile e implante seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="159d3-128">Compile and deploy your app.</span></span>  <span data-ttu-id="159d3-129">Cessões.</span><span class="sxs-lookup"><span data-stu-id="159d3-129">Success.</span></span>  

## <span data-ttu-id="159d3-130">Consulte também</span><span class="sxs-lookup"><span data-stu-id="159d3-130">See also</span></span>  

*   <span data-ttu-id="159d3-131">Para começar a usar o WebView2, navegue até [WebView2 guias de introdução][Webview2MainGettingStarted].</span><span class="sxs-lookup"><span data-stu-id="159d3-131">To get started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="159d3-132">Para obter um exemplo abrangente de recursos do WebView2, navegue até [WebView2Samples][GithubMicrosoftedgeWebview2samples] no github.</span><span class="sxs-lookup"><span data-stu-id="159d3-132">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples][GithubMicrosoftedgeWebview2samples] on GitHub.</span></span>
*   <span data-ttu-id="159d3-133">Para obter informações mais detalhadas sobre APIs do WebView2, navegue até [referência da API][Webview2ApiReference].</span><span class="sxs-lookup"><span data-stu-id="159d3-133">For more detailed information about WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="159d3-134">Para obter mais informações sobre o WebView2, navegue até [recursos do WebView2][Webview2MainNextSteps].</span><span class="sxs-lookup"><span data-stu-id="159d3-134">For more information about WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>

## <span data-ttu-id="159d3-135">Entrar em contato com a equipe do WebView2</span><span class="sxs-lookup"><span data-stu-id="159d3-135">Getting in touch with the WebView2 team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Ferramentas de desenvolvedor do Microsoft Edge (Chromium) | Documentos da Microsoft"  

[Webview2ReferenceDotnet09628MicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]: ../reference/dotnet/0-9-628/microsoft-web-webview2-core-corewebview2environmentoptions.md#additionalbrowserarguments "AdditionalBrowserArguments-0.9.515-a classe Microsoft. Web. WebView2. Core. CoreWebView2EnvironmentOptions | Documentos da Microsoft"  
[Webview2ReferenceWin3209622Webview2IdlParameters]: ../reference/win32/0-9-622/webview2-idl.md#createcorewebview2environment  "CreateCoreWebView2Environment-globais | Documentos da Microsoft"  
[Webview2ApiReference]: ../webview2-api-reference.md "Referência de API do Microsoft Edge WebView2 | Documentos da Microsoft"  
[Webview2MainNextSteps]: ../index.md#next-steps "Próximas etapas-introdução ao Microsoft Edge WebView2 (visualização) | Documentos da Microsoft"  
[Webview2MainGettingStarted]: ../index.md#getting-started "Ponto de partida-introdução ao Microsoft Edge WebView2 (visualização) | Documentos da Microsoft"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "Feedback da WebView-MicrosoftEdge/WebViewFeedback | GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "Exemplos de WebView2-MicrosoftEdge/WebView2Samples | GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "Quais são as novidades? -Depurador JavaScript para código do Visual Studio-Microsoft/vscode-js-depuração | GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Aplicativos WebView do Microsoft Edge (Chromium)-depurador de código do Visual Studio para Microsoft Edge-Microsoft/vscode-Edge-debug2 | GitHub"  