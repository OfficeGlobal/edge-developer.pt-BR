---
description: Saiba como usar JavaScript em cenários complexos em aplicativos do WebView2
title: Usar JavaScript em aplicativos do WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/14/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, webview2, WebView, aplicativos Win32, Win32, Edge, ICoreWebView2, ICoreWebView2Host, controle do navegador, HTML Edge
ms.openlocfilehash: f6e59acb0c4bf8ad5357aba87e0359d3b103ed63
ms.sourcegitcommit: 61cc15d2fc89aee3e09cec48ef1e0e5bbf8d289a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2020
ms.locfileid: "11119063"
---
# <span data-ttu-id="28b89-104">Usar JavaScript em WebView para cenários estendidos</span><span class="sxs-lookup"><span data-stu-id="28b89-104">Use JavaScript in WebView for extended scenarios</span></span>  

<span data-ttu-id="28b89-105">Usar JavaScript nos controles WebView2 permite que você personalize aplicativos nativos para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="28b89-105">Using JavaScript in WebView2 controls allows you to customize native apps to meet your requirements.</span></span>  <span data-ttu-id="28b89-106">Este artigo explica como usar JavaScript no WebView2 e analisa como desenvolver usando recursos e funcionalidades avançados do WebView2.</span><span class="sxs-lookup"><span data-stu-id="28b89-106">This article explores how to use JavaScript in WebView2, and reviews how to develop using advanced WebView2 features and functionality.</span></span>  

## <span data-ttu-id="28b89-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="28b89-107">Before you begin</span></span>  

<span data-ttu-id="28b89-108">Este artigo pressupõe que você já tem um projeto em funcionamento.</span><span class="sxs-lookup"><span data-stu-id="28b89-108">This article assumes that you already have a working project.</span></span>  <span data-ttu-id="28b89-109">Se você não tiver um projeto e quiser acompanhar, navegue até o [Guia de introdução ao WebView2][Webview2GettingstartedWpf].</span><span class="sxs-lookup"><span data-stu-id="28b89-109">If you do not have a project and want to follow along, navigate to the [WebView2 Getting Started Guide][Webview2GettingstartedWpf].</span></span>  

## <span data-ttu-id="28b89-110">Funções básicas de WebView2</span><span class="sxs-lookup"><span data-stu-id="28b89-110">Basic WebView2 Functions</span></span>  

<span data-ttu-id="28b89-111">Use as funções a seguir para começar a inserir JavaScript em seu aplicativo WebView.</span><span class="sxs-lookup"><span data-stu-id="28b89-111">Use the following functions to begin embedding JavaScript in your WebView app.</span></span>  

| <span data-ttu-id="28b89-112">API</span><span class="sxs-lookup"><span data-stu-id="28b89-112">API</span></span>  | <span data-ttu-id="28b89-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="28b89-113">Description</span></span>  |
|:--- |:--- |  
| [<span data-ttu-id="28b89-114">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="28b89-114">ExecuteScriptAsync</span></span>][Webview2ReferenceWpf09515MicrosoftWebExecutescriptasync] | <span data-ttu-id="28b89-115">Executar JavaScript em um controle WebView.</span><span class="sxs-lookup"><span data-stu-id="28b89-115">Run JavaScript in a WebView control.</span></span> <span data-ttu-id="28b89-116">Para obter mais informações, navegue até o tutorial de introdução.</span><span class="sxs-lookup"><span data-stu-id="28b89-116">For more information, navigate to the Getting Started tutorial.</span></span> |
| [<span data-ttu-id="28b89-117">OnDocumentCreatedAsync</span><span class="sxs-lookup"><span data-stu-id="28b89-117">OnDocumentCreatedAsync</span></span>][Webview2ReferenceWin3209538Icorewebview2Addscripttoexecuteondocumentcreated] | <span data-ttu-id="28b89-118">É executado quando o modelo de objeto do documento (DOM \) é criado.</span><span class="sxs-lookup"><span data-stu-id="28b89-118">Runs when the Document Object Model \(DOM\) is created.</span></span> |
      
## <span data-ttu-id="28b89-119">Cenário: executando um arquivo de script dedicado</span><span class="sxs-lookup"><span data-stu-id="28b89-119">Scenario:  Running a dedicated script file</span></span>  

<span data-ttu-id="28b89-120">Nesta seção, acesse um arquivo JavaScript dedicado a partir de seu controle WebView2.</span><span class="sxs-lookup"><span data-stu-id="28b89-120">In this section, access a dedicated JavaScript file from your WebView2 control.</span></span>  

> [!NOTE]
> <span data-ttu-id="28b89-121">Embora escrever JavaScript inline possa ser eficiente para comandos JavaScript rápidos, você perde os temas de cor JavaScript e a formatação de linha que tornam difícil escrever seções grandes de código no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="28b89-121">Although writing JavaScript inline may be efficient for quick JavaScript commands, you lose JavaScript color themes and line formatting that makes it difficult to write large sections of code in Visual Studio.</span></span>  

<span data-ttu-id="28b89-122">Para solucionar o problema, crie um arquivo JavaScript separado com seu código e, em seguida, passe uma referência para esse arquivo usando os `ExecuteScriptAsync` parâmetros.</span><span class="sxs-lookup"><span data-stu-id="28b89-122">To solve the problem, create a separate JavaScript file with your code, and then pass a reference to that file using the `ExecuteScriptAsync` parameters.</span></span>  

1.  <span data-ttu-id="28b89-123">Crie um `.js` arquivo em seu projeto e adicione o código JavaScript que você deseja executar.</span><span class="sxs-lookup"><span data-stu-id="28b89-123">Create a `.js` file in your project, and add the JavaScript code that you want to run.</span></span>  <span data-ttu-id="28b89-124">Por exemplo, crie um arquivo chamado `script.js` .</span><span class="sxs-lookup"><span data-stu-id="28b89-124">For example, create a file called `script.js`.</span></span>  
1.  <span data-ttu-id="28b89-125">Converter o arquivo JavaScript em uma cadeia de caracteres que é passada para `ExecuteScriptAsync` .</span><span class="sxs-lookup"><span data-stu-id="28b89-125">Convert the JavaScript file to a string that is passed to `ExecuteScriptAsync`.</span></span>  
    1.  <span data-ttu-id="28b89-126">Para converter o arquivo JavaScript em uma cadeia de caracteres, copie o trecho de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="28b89-126">To convert your JavaScript file into a string, copy the following code snippet.</span></span>  
        
        ```csharp
        string text = System.IO.File.ReadAllText(@"C:\PATH_TO_YOUR_FILE\script.js");
        ```  
        
    1.  <span data-ttu-id="28b89-127">Cole o código em `MainWindow.xaml.cs` .</span><span class="sxs-lookup"><span data-stu-id="28b89-127">Paste the code into `MainWindow.xaml.cs`.</span></span>  
1.  <span data-ttu-id="28b89-128">Passe a variável de texto usando `ExecuteScriptAsync` .</span><span class="sxs-lookup"><span data-stu-id="28b89-128">Pass your text variable using `ExecuteScriptAsync`.</span></span>  
    
    ```csharp
    await webView.CoreWebView2.ExecuteScriptAsync(text);
    ```  

## <span data-ttu-id="28b89-129">Cenário: remover a funcionalidade de arrastar e soltar</span><span class="sxs-lookup"><span data-stu-id="28b89-129">Scenario:  Remove drag-and-drop functionality</span></span>  

<span data-ttu-id="28b89-130">Nesta seção, use JavaScript para remover a funcionalidade de arrastar e soltar do controle WebView2.</span><span class="sxs-lookup"><span data-stu-id="28b89-130">In this section, use JavaScript to remove the drag-and-drop functionality from your WebView2 control.</span></span>  

<span data-ttu-id="28b89-131">Para começar, explore a funcionalidade de arrastar e soltar atual.</span><span class="sxs-lookup"><span data-stu-id="28b89-131">To begin, explore the current drag-and-drop functionality.</span></span>  

1.  <span data-ttu-id="28b89-132">Crie um `.txt` arquivo para arrastar e soltar.</span><span class="sxs-lookup"><span data-stu-id="28b89-132">Create a `.txt` file in order to drag-and-drop.</span></span>  <span data-ttu-id="28b89-133">Por exemplo, crie um arquivo denominado `contoso.txt` e adicione texto a ele.</span><span class="sxs-lookup"><span data-stu-id="28b89-133">For example, create a file named `contoso.txt` and add text to it.</span></span>  
1.  <span data-ttu-id="28b89-134">Execute o projeto.</span><span class="sxs-lookup"><span data-stu-id="28b89-134">Run your project.</span></span>  
1.  <span data-ttu-id="28b89-135">Arraste e solte o arquivo no `contoso.txt` controle WebView.</span><span class="sxs-lookup"><span data-stu-id="28b89-135">Drag-and-drop the `contoso.txt` file onto the WebView control.</span></span>  <span data-ttu-id="28b89-136">Uma nova janela será aberta, que é o resultado do código em seu projeto de amostra.</span><span class="sxs-lookup"><span data-stu-id="28b89-136">A new window opens, which is the result of the code in your sample project.</span></span>  
    
    :::image type="complex" source="./media/dragtext.png" alt-text="Resultado de arrastar e soltar contoso.txt" lightbox="./media/dragtext.png":::
       <span data-ttu-id="28b89-138">Resultado de arrastar e soltar contoso.txt</span><span class="sxs-lookup"><span data-stu-id="28b89-138">Result of dragging and dropping contoso.txt</span></span>  
    :::image-end:::  

<span data-ttu-id="28b89-139">Agora, adicione código para remover a funcionalidade de arrastar e soltar do controle WebView2.</span><span class="sxs-lookup"><span data-stu-id="28b89-139">Now, add code to remove the drag-and-drop functionality from the WebView2 control.</span></span>  

1.  <span data-ttu-id="28b89-140">Copie e cole o trecho de código a seguir em `InitializeAsync()` `MainWindow.xaml.cs` .</span><span class="sxs-lookup"><span data-stu-id="28b89-140">Copy and paste the following code snippet into `InitializeAsync()` in `MainWindow.xaml.cs`.</span></span>   
            
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('dragover',function(e){e.preventDefault();},false);");
    
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('drop',function(e){" +
    "e.preventDefault();" +
    "console.log(e.dataTransfer);" +
    "console.log(e.dataTransfer.files[0])" +
    "}, false);");
    ```  
          
1.  <span data-ttu-id="28b89-141">Execute o projeto.</span><span class="sxs-lookup"><span data-stu-id="28b89-141">Run your project.</span></span>  
1.  <span data-ttu-id="28b89-142">Tente arrastar e soltar `contoso.txt` .</span><span class="sxs-lookup"><span data-stu-id="28b89-142">Try to drag-and-drop `contoso.txt`.</span></span>  <span data-ttu-id="28b89-143">Confirme que você não pode arrastar e soltar.</span><span class="sxs-lookup"><span data-stu-id="28b89-143">Confirm that you are not able to drag-and-drop.</span></span>  

## <span data-ttu-id="28b89-144">Cenário: removendo o menu de contexto</span><span class="sxs-lookup"><span data-stu-id="28b89-144">Scenario:  Removing the Context Menu</span></span>  

<span data-ttu-id="28b89-145">Nesta seção, remova o menu de contexto padrão do seu controle WebView2.</span><span class="sxs-lookup"><span data-stu-id="28b89-145">In this section, remove the default context menu from your WebView2 control.</span></span>  

<span data-ttu-id="28b89-146">Para começar, explore a funcionalidade do menu contextual atual.</span><span class="sxs-lookup"><span data-stu-id="28b89-146">To begin, explore the current contextual menu functionality.</span></span>  

1.  <span data-ttu-id="28b89-147">Execute o projeto.</span><span class="sxs-lookup"><span data-stu-id="28b89-147">Run your project.</span></span>  
1.  <span data-ttu-id="28b89-148">Passe o mouse em qualquer lugar do controle WebView2 e abra o menu de contexto \ (clique com o botão direito do mouse \).</span><span class="sxs-lookup"><span data-stu-id="28b89-148">Hover anywhere on the WebView2 control and open the context menu \(right-click\).</span></span>  <span data-ttu-id="28b89-149">O menu de contexto exibe as opções padrão.</span><span class="sxs-lookup"><span data-stu-id="28b89-149">The context menu displays the default choices.</span></span>  
    
    :::image type="complex" source="./media/contextmenu.png" alt-text="Resultado de arrastar e soltar contoso.txt" lightbox="./media/contextmenu.png":::
       <span data-ttu-id="28b89-151">O menu de contexto mostrando as opções padrão</span><span class="sxs-lookup"><span data-stu-id="28b89-151">The context menu showing the default choices</span></span>  
    :::image-end:::  
    
<span data-ttu-id="28b89-152">Agora, adicione código para remover a funcionalidade do menu contextual do controle WebView2.</span><span class="sxs-lookup"><span data-stu-id="28b89-152">Now add code to remove the contextual menu functionality from the WebView2 control.</span></span>  

1.  <span data-ttu-id="28b89-153">Copie e cole o trecho de código a seguir em `InitializeAsync()` `MainWindow.xaml.cs` .</span><span class="sxs-lookup"><span data-stu-id="28b89-153">Copy and paste the following code snippet into `InitializeAsync()` in `MainWindow.xaml.cs`.</span></span>    
        
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('contextmenu', window => {window.preventDefault();});");
    ```  

1.  <span data-ttu-id="28b89-154">Execute o código novamente.</span><span class="sxs-lookup"><span data-stu-id="28b89-154">Run the code again.</span></span>  <span data-ttu-id="28b89-155">Confirme que você não pode abrir um menu de contexto \ (clique com o botão direito do mouse \).</span><span class="sxs-lookup"><span data-stu-id="28b89-155">Confirm that you're not able to open a context menu \(right-click\).</span></span>  
   
## <span data-ttu-id="28b89-156">Consulte também</span><span class="sxs-lookup"><span data-stu-id="28b89-156">See also</span></span>  

*   <span data-ttu-id="28b89-157">Para obter mais informações sobre como começar a usar o WebView2, navegue até [WebView2 guias de introdução][Webview2MainGettingStarted].</span><span class="sxs-lookup"><span data-stu-id="28b89-157">For more information on getting started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="28b89-158">Para obter um exemplo abrangente de recursos do WebView2, navegue até o repositório do [WebView2Samples][GithubMicrosoftedgeWebview2samples] no github.</span><span class="sxs-lookup"><span data-stu-id="28b89-158">For a comprehensive example of WebView2 capabilities, navigate to the [WebView2Samples][GithubMicrosoftedgeWebview2samples] repo on GitHub.</span></span>  
*   <span data-ttu-id="28b89-159">Para obter informações detalhadas sobre APIs do WebView2, navegue até [referência da API][Webview2ApiReference].</span><span class="sxs-lookup"><span data-stu-id="28b89-159">For detailed information on WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>  
*   <span data-ttu-id="28b89-160">Para obter mais informações sobre o WebView2, navegue até [recursos do WebView2][Webview2MainNextSteps].</span><span class="sxs-lookup"><span data-stu-id="28b89-160">For more information on WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>  

## <span data-ttu-id="28b89-161">Entrar em contato com a equipe do Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="28b89-161">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Ferramentas de desenvolvedor do Microsoft Edge (Chromium) | Documentos da Microsoft"  


[Webview2ApiReference]: ../webview2-api-reference.md "Referência de API do Microsoft Edge WebView2 | Documentos da Microsoft"  
[Webview2GettingstartedWpf]: ../gettingstarted/wpf.md "Introdução ao WebView2 no WPF (visualização) | Documentos da Microsoft"  
[Webview2MainGettingStarted]: ../index.md#getting-started "Ponto de partida-introdução ao Microsoft Edge WebView2 (visualização) | Documentos da Microsoft"  
[Webview2MainNextSteps]: ../index.md#next-steps "Próximas etapas-introdução ao Microsoft Edge WebView2 (visualização) | Documentos da Microsoft"  
[Webview2ReferenceWin3209538Icorewebview2Addscripttoexecuteondocumentcreated]: ../reference/win32/0-9-538/icorewebview2.md#addscripttoexecuteondocumentcreated "AddScriptToExecuteOnDocumentCreated-0.9.579-interface ICoreWebView2 | Documentos da Microsoft"  
[Webview2ReferenceWpf09515MicrosoftWebExecutescriptasync]: ../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#executescriptasync "ExecuteScriptAsync-classe Microsoft. Web. WebView2. WPF. WebView2 | Documentos da Microsoft"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "Exemplos de WebView2-MicrosoftEdge/WebView2Samples | GitHub"  