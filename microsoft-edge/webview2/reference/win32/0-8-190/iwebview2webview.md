---
description: Hospedar conteúdo da Web em seu aplicativo Win32 com o controle WebView2 do Microsoft Edge
title: Microsoft Edge WebView2 para aplicativos Win32
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, webview2, WebView, aplicativos Win32, Win32, Edge
ms.openlocfilehash: 5c84cfb703c8901560307b7bba8bc7887cb19377
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652354"
---
# <span data-ttu-id="0d3b5-104">interface IWebView2WebView</span><span class="sxs-lookup"><span data-stu-id="0d3b5-104">interface IWebView2WebView</span></span> 

> [!NOTE]
> <span data-ttu-id="0d3b5-105">Essa interface pode ser alterada ou indisponível para versões posteriores SDK da versão 0.8.355.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="0d3b5-106">Consulte a [referência](../../../webview2-api-reference.md) para obter a referência da API mais recente.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebView
  : public IUnknown
```

<span data-ttu-id="0d3b5-107">O WebView2 permite que você hospede conteúdo da Web usando a tecnologia de navegador da Web mais recente do Edge.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-107">WebView2 enables you to host web content using the latest Edge web browser technology.</span></span>

## <span data-ttu-id="0d3b5-108">Resumo</span><span class="sxs-lookup"><span data-stu-id="0d3b5-108">Summary</span></span>

 <span data-ttu-id="0d3b5-109">Parte</span><span class="sxs-lookup"><span data-stu-id="0d3b5-109">Members</span></span>                        | <span data-ttu-id="0d3b5-110">Descrições</span><span class="sxs-lookup"><span data-stu-id="0d3b5-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0d3b5-111">get_Settings</span><span class="sxs-lookup"><span data-stu-id="0d3b5-111">get_Settings</span></span>](#get_settings) | <span data-ttu-id="0d3b5-112">O objeto [IWebView2Settings](IWebView2Settings.md) contém várias configurações modificáveis para a execução do WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-112">The [IWebView2Settings](IWebView2Settings.md) object contains various modifiable settings for the running WebView.</span></span>
[<span data-ttu-id="0d3b5-113">get_Source</span><span class="sxs-lookup"><span data-stu-id="0d3b5-113">get_Source</span></span>](#get_source) | <span data-ttu-id="0d3b5-114">O URI do documento de nível superior atual.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-114">The URI of the current top level document.</span></span>
[<span data-ttu-id="0d3b5-115">Navegar</span><span class="sxs-lookup"><span data-stu-id="0d3b5-115">Navigate</span></span>](#navigate) | <span data-ttu-id="0d3b5-116">Fazer uma navegação do documento de nível superior para o URI especificado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-116">Cause a navigation of the top level document to the specified URI.</span></span>
[<span data-ttu-id="0d3b5-117">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="0d3b5-117">MoveFocus</span></span>](#movefocus) | <span data-ttu-id="0d3b5-118">Mover o foco para o WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-118">Move focus into WebView.</span></span>
[<span data-ttu-id="0d3b5-119">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="0d3b5-119">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="0d3b5-120">Inicia uma navegação para htmlContent como código-fonte HTML de um novo documento.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-120">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="0d3b5-121">add_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="0d3b5-121">add_NavigationStarting</span></span>](#add_navigationstarting) | <span data-ttu-id="0d3b5-122">Adicione um manipulador de eventos para o evento NavigationStarting.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-122">Add an event handler for the NavigationStarting event.</span></span>
[<span data-ttu-id="0d3b5-123">remove_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="0d3b5-123">remove_NavigationStarting</span></span>](#remove_navigationstarting) | <span data-ttu-id="0d3b5-124">Remover um manipulador de eventos adicionado anteriormente com add_NavigationStarting.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-124">Remove an event handler previously added with add_NavigationStarting.</span></span>
[<span data-ttu-id="0d3b5-125">add_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="0d3b5-125">add_DocumentStateChanged</span></span>](#add_documentstatechanged) | <span data-ttu-id="0d3b5-126">Adicione um manipulador de eventos para o evento DocumentStateChanged.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-126">Add an event handler for the DocumentStateChanged event.</span></span>
[<span data-ttu-id="0d3b5-127">remove_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="0d3b5-127">remove_DocumentStateChanged</span></span>](#remove_documentstatechanged) | <span data-ttu-id="0d3b5-128">Remover um manipulador de eventos adicionado anteriormente com add_DocumentStateChanged.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-128">Remove an event handler previously added with add_DocumentStateChanged.</span></span>
[<span data-ttu-id="0d3b5-129">add_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="0d3b5-129">add_NavigationCompleted</span></span>](#add_navigationcompleted) | <span data-ttu-id="0d3b5-130">Adicione um manipulador de eventos para o evento NavigationCompleted.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-130">Add an event handler for the NavigationCompleted event.</span></span>
[<span data-ttu-id="0d3b5-131">remove_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="0d3b5-131">remove_NavigationCompleted</span></span>](#remove_navigationcompleted) | <span data-ttu-id="0d3b5-132">Remover um manipulador de eventos adicionado anteriormente com add_NavigationCompleted.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-132">Remove an event handler previously added with add_NavigationCompleted.</span></span>
[<span data-ttu-id="0d3b5-133">add_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="0d3b5-133">add_FrameNavigationStarting</span></span>](#add_framenavigationstarting) | <span data-ttu-id="0d3b5-134">Adicione um manipulador de eventos para o evento FrameNavigationStarting.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-134">Add an event handler for the FrameNavigationStarting event.</span></span>
[<span data-ttu-id="0d3b5-135">remove_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="0d3b5-135">remove_FrameNavigationStarting</span></span>](#remove_framenavigationstarting) | <span data-ttu-id="0d3b5-136">Remover um manipulador de eventos adicionado anteriormente com add_FrameNavigationStarting.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-136">Remove an event handler previously added with add_FrameNavigationStarting.</span></span>
[<span data-ttu-id="0d3b5-137">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="0d3b5-137">add_MoveFocusRequested</span></span>](#add_movefocusrequested) | <span data-ttu-id="0d3b5-138">Adicione um manipulador de eventos para o evento MoveFocusRequested.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-138">Add an event handler for the MoveFocusRequested event.</span></span>
[<span data-ttu-id="0d3b5-139">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="0d3b5-139">remove_MoveFocusRequested</span></span>](#remove_movefocusrequested) | <span data-ttu-id="0d3b5-140">Remover um manipulador de eventos adicionado anteriormente com add_MoveFocusRequested.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-140">Remove an event handler previously added with add_MoveFocusRequested.</span></span>
[<span data-ttu-id="0d3b5-141">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="0d3b5-141">add_GotFocus</span></span>](#add_gotfocus) | <span data-ttu-id="0d3b5-142">Adicione um manipulador de eventos para o evento GotFocus.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-142">Add an event handler for the GotFocus event.</span></span>
[<span data-ttu-id="0d3b5-143">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="0d3b5-143">remove_GotFocus</span></span>](#remove_gotfocus) | <span data-ttu-id="0d3b5-144">Remover um manipulador de eventos adicionado anteriormente com add_GotFocus.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-144">Remove an event handler previously added with add_GotFocus.</span></span>
[<span data-ttu-id="0d3b5-145">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="0d3b5-145">add_LostFocus</span></span>](#add_lostfocus) | <span data-ttu-id="0d3b5-146">Adicione um manipulador de eventos para o evento LostFocus.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-146">Add an event handler for the LostFocus event.</span></span>
[<span data-ttu-id="0d3b5-147">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="0d3b5-147">remove_LostFocus</span></span>](#remove_lostfocus) | <span data-ttu-id="0d3b5-148">Remover um manipulador de eventos adicionado anteriormente com add_LostFocus.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-148">Remove an event handler previously added with add_LostFocus.</span></span>
[<span data-ttu-id="0d3b5-149">add_WebResourceRequested_deprecated</span><span class="sxs-lookup"><span data-stu-id="0d3b5-149">add_WebResourceRequested_deprecated</span></span>](#add_webresourcerequested_deprecated) | <span data-ttu-id="0d3b5-150">Esta API será preterida, use a nova API de add_WebResourceRequested.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-150">This API will be deprecated, please use the new add_WebResourceRequested API.</span></span>
[<span data-ttu-id="0d3b5-151">remove_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="0d3b5-151">remove_WebResourceRequested</span></span>](#remove_webresourcerequested) | <span data-ttu-id="0d3b5-152">Remover um manipulador de eventos adicionado anteriormente com add_WebResourceRequested.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-152">Remove an event handler previously added with add_WebResourceRequested.</span></span>
[<span data-ttu-id="0d3b5-153">add_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="0d3b5-153">add_ScriptDialogOpening</span></span>](#add_scriptdialogopening) | <span data-ttu-id="0d3b5-154">Adicione um manipulador de eventos para o evento ScriptDialogOpening.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-154">Add an event handler for the ScriptDialogOpening event.</span></span>
[<span data-ttu-id="0d3b5-155">remove_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="0d3b5-155">remove_ScriptDialogOpening</span></span>](#remove_scriptdialogopening) | <span data-ttu-id="0d3b5-156">Remover um manipulador de eventos adicionado anteriormente com add_ScriptDialogOpening.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-156">Remove an event handler previously added with add_ScriptDialogOpening.</span></span>
[<span data-ttu-id="0d3b5-157">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="0d3b5-157">add_ZoomFactorChanged</span></span>](#add_zoomfactorchanged) | <span data-ttu-id="0d3b5-158">Adicione um manipulador de eventos para o evento ZoomFactorChanged.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-158">Add an event handler for the ZoomFactorChanged event.</span></span>
[<span data-ttu-id="0d3b5-159">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="0d3b5-159">remove_ZoomFactorChanged</span></span>](#remove_zoomfactorchanged) | <span data-ttu-id="0d3b5-160">Remover um manipulador de eventos adicionado anteriormente com add_ZoomFactorChanged.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-160">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>
[<span data-ttu-id="0d3b5-161">add_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="0d3b5-161">add_PermissionRequested</span></span>](#add_permissionrequested) | <span data-ttu-id="0d3b5-162">Adicione um manipulador de eventos para o evento PermissionRequested.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-162">Add an event handler for the PermissionRequested event.</span></span>
[<span data-ttu-id="0d3b5-163">remove_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="0d3b5-163">remove_PermissionRequested</span></span>](#remove_permissionrequested) | <span data-ttu-id="0d3b5-164">Remover um manipulador de eventos adicionado anteriormente com add_PermissionRequested.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-164">Remove an event handler previously added with add_PermissionRequested.</span></span>
[<span data-ttu-id="0d3b5-165">add_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="0d3b5-165">add_ProcessFailed</span></span>](#add_processfailed) | <span data-ttu-id="0d3b5-166">Adicione um manipulador de eventos para o evento ProcessFailed.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-166">Add an event handler for the ProcessFailed event.</span></span>
[<span data-ttu-id="0d3b5-167">remove_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="0d3b5-167">remove_ProcessFailed</span></span>](#remove_processfailed) | <span data-ttu-id="0d3b5-168">Remover um manipulador de eventos adicionado anteriormente com add_ProcessFailed.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-168">Remove an event handler previously added with add_ProcessFailed.</span></span>
[<span data-ttu-id="0d3b5-169">AddScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="0d3b5-169">AddScriptToExecuteOnDocumentCreated</span></span>](#addscripttoexecuteondocumentcreated) | <span data-ttu-id="0d3b5-170">Adicione o JavaScript fornecido a uma lista de scripts que devem ser executados após a criação do objeto global, mas antes de o documento HTML ter sido analisado e antes de qualquer outro script incluído no documento HTML ser executado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-170">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>
[<span data-ttu-id="0d3b5-171">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="0d3b5-171">RemoveScriptToExecuteOnDocumentCreated</span></span>](#removescripttoexecuteondocumentcreated) | <span data-ttu-id="0d3b5-172">Remova o JavaScript correspondente adicionado via AddScriptToExecuteOnDocumentCreated.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-172">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated.</span></span>
[<span data-ttu-id="0d3b5-173">ExecuteScript</span><span class="sxs-lookup"><span data-stu-id="0d3b5-173">ExecuteScript</span></span>](#executescript) | <span data-ttu-id="0d3b5-174">Execute o código JavaScript do parâmetro JavaScript no documento de nível superior atual renderizado no WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-174">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="0d3b5-175">CapturePreview</span><span class="sxs-lookup"><span data-stu-id="0d3b5-175">CapturePreview</span></span>](#capturepreview) | <span data-ttu-id="0d3b5-176">Capture uma imagem do que o WebView está exibindo.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-176">Capture an image of what WebView is displaying.</span></span>
[<span data-ttu-id="0d3b5-177">Recarregar</span><span class="sxs-lookup"><span data-stu-id="0d3b5-177">Reload</span></span>](#reload) | <span data-ttu-id="0d3b5-178">Recarregar a página atual.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-178">Reload the current page.</span></span>
[<span data-ttu-id="0d3b5-179">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="0d3b5-179">get_Bounds</span></span>](#get_bounds) | <span data-ttu-id="0d3b5-180">Os limites da WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-180">The webview bounds.</span></span>
[<span data-ttu-id="0d3b5-181">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="0d3b5-181">put_Bounds</span></span>](#put_bounds) | <span data-ttu-id="0d3b5-182">Defina a propriedade Bounds.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-182">Set the Bounds property.</span></span>
[<span data-ttu-id="0d3b5-183">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="0d3b5-183">get_ZoomFactor</span></span>](#get_zoomfactor) | <span data-ttu-id="0d3b5-184">O fator de zoom para a página atual no WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-184">The zoom factor for the current page in the WebView.</span></span>
[<span data-ttu-id="0d3b5-185">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="0d3b5-185">put_ZoomFactor</span></span>](#put_zoomfactor) | <span data-ttu-id="0d3b5-186">Defina a propriedade ZoomFactor.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-186">Set the ZoomFactor property.</span></span>
[<span data-ttu-id="0d3b5-187">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="0d3b5-187">get_IsVisible</span></span>](#get_isvisible) | <span data-ttu-id="0d3b5-188">A propriedade IsVisible Determina se deseja mostrar ou ocultar o WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-188">The IsVisible property determines whether to show or hide the webview.</span></span>
[<span data-ttu-id="0d3b5-189">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="0d3b5-189">put_IsVisible</span></span>](#put_isvisible) | <span data-ttu-id="0d3b5-190">Defina a propriedade IsVisible.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-190">Set the IsVisible property.</span></span>
[<span data-ttu-id="0d3b5-191">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="0d3b5-191">PostWebMessageAsJson</span></span>](#postwebmessageasjson) | <span data-ttu-id="0d3b5-192">Poste a WebMessage especificada no documento de nível superior neste [IWebView2WebView]().</span><span class="sxs-lookup"><span data-stu-id="0d3b5-192">Post the specified webMessage to the top level document in this [IWebView2WebView]().</span></span>
[<span data-ttu-id="0d3b5-193">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="0d3b5-193">PostWebMessageAsString</span></span>](#postwebmessageasstring) | <span data-ttu-id="0d3b5-194">Isso é um auxiliar para postar uma mensagem que é uma cadeia de caracteres simples em vez de uma representação JSON de cadeia de caracteres de um objeto JavaScript.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-194">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>
[<span data-ttu-id="0d3b5-195">add_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="0d3b5-195">add_WebMessageReceived</span></span>](#add_webmessagereceived) | <span data-ttu-id="0d3b5-196">Esse evento é acionado quando a configuração IsWebMessageEnabled é definida e o documento de nível superior das chamadas WebView `window.chrome.webview.postMessage` .</span><span class="sxs-lookup"><span data-stu-id="0d3b5-196">This event fires when the IsWebMessageEnabled setting is set and the top level document of the webview calls `window.chrome.webview.postMessage`.</span></span>
[<span data-ttu-id="0d3b5-197">remove_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="0d3b5-197">remove_WebMessageReceived</span></span>](#remove_webmessagereceived) | <span data-ttu-id="0d3b5-198">Remover um manipulador de eventos adicionado anteriormente com add_WebMessageReceived.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-198">Remove an event handler previously added with add_WebMessageReceived.</span></span>
[<span data-ttu-id="0d3b5-199">Fechar</span><span class="sxs-lookup"><span data-stu-id="0d3b5-199">Close</span></span>](#close) | <span data-ttu-id="0d3b5-200">Fecha a WebView e limpa a instância do navegador subjacente.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-200">Closes the webview and cleans up the underlying browser instance.</span></span>
[<span data-ttu-id="0d3b5-201">CallDevToolsProtocolMethod</span><span class="sxs-lookup"><span data-stu-id="0d3b5-201">CallDevToolsProtocolMethod</span></span>](#calldevtoolsprotocolmethod) | <span data-ttu-id="0d3b5-202">Chame um método DevToolsProtocol assíncrono.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-202">Call an asynchronous DevToolsProtocol method.</span></span>
[<span data-ttu-id="0d3b5-203">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="0d3b5-203">add_DevToolsProtocolEventReceived</span></span>](#add_devtoolsprotocoleventreceived) | <span data-ttu-id="0d3b5-204">Assine um evento DevToolsProtocol.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-204">Subscribe to a DevToolsProtocol event.</span></span>
[<span data-ttu-id="0d3b5-205">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="0d3b5-205">remove_DevToolsProtocolEventReceived</span></span>](#remove_devtoolsprotocoleventreceived) | <span data-ttu-id="0d3b5-206">Remover um manipulador de eventos adicionado anteriormente com add_DevToolsProtocolEventReceived.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-206">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>
[<span data-ttu-id="0d3b5-207">get_BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="0d3b5-207">get_BrowserProcessId</span></span>](#get_browserprocessid) | <span data-ttu-id="0d3b5-208">A ID do processo do navegador que hospeda o WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-208">The process id of the browser process that hosts the WebView.</span></span>
[<span data-ttu-id="0d3b5-209">get_CanGoBack</span><span class="sxs-lookup"><span data-stu-id="0d3b5-209">get_CanGoBack</span></span>](#get_cangoback) | <span data-ttu-id="0d3b5-210">Pode navegar pelo WebView para a página anterior no histórico de navegação.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-210">Can navigate the webview to the previous page in the navigation history.</span></span>
[<span data-ttu-id="0d3b5-211">get_CanGoForward</span><span class="sxs-lookup"><span data-stu-id="0d3b5-211">get_CanGoForward</span></span>](#get_cangoforward) | <span data-ttu-id="0d3b5-212">Pode navegar pelo WebView para a próxima página no histórico de navegação.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-212">Can navigate the webview to the next page in the navigation history.</span></span>
[<span data-ttu-id="0d3b5-213">GoBack</span><span class="sxs-lookup"><span data-stu-id="0d3b5-213">GoBack</span></span>](#goback) | <span data-ttu-id="0d3b5-214">Navega o WebView para a página anterior no histórico de navegação.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-214">Navigates the webview to the previous page in the navigation history.</span></span>
[<span data-ttu-id="0d3b5-215">GoForward</span><span class="sxs-lookup"><span data-stu-id="0d3b5-215">GoForward</span></span>](#goforward) | <span data-ttu-id="0d3b5-216">Navega o WebView para a próxima página no histórico de navegação.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-216">Navigates the webview to the next page in the navigation history.</span></span>
[<span data-ttu-id="0d3b5-217">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span><span class="sxs-lookup"><span data-stu-id="0d3b5-217">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span></span>](#webview2_capture_preview_image_format) | <span data-ttu-id="0d3b5-218">Formato de imagem usado pelo método [IWebView2WebView:: CapturePreview](#capturepreview) .</span><span class="sxs-lookup"><span data-stu-id="0d3b5-218">Image format used by the [IWebView2WebView::CapturePreview](#capturepreview) method.</span></span>
[<span data-ttu-id="0d3b5-219">WEBVIEW2_SCRIPT_DIALOG_KIND</span><span class="sxs-lookup"><span data-stu-id="0d3b5-219">WEBVIEW2_SCRIPT_DIALOG_KIND</span></span>](#webview2_script_dialog_kind) | <span data-ttu-id="0d3b5-220">Tipo de caixa de diálogo JavaScript usada na interface [IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) .</span><span class="sxs-lookup"><span data-stu-id="0d3b5-220">Kind of JavaScript dialog used in the [IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) interface.</span></span>
[<span data-ttu-id="0d3b5-221">WEBVIEW2_PROCESS_FAILED_KIND</span><span class="sxs-lookup"><span data-stu-id="0d3b5-221">WEBVIEW2_PROCESS_FAILED_KIND</span></span>](#webview2_process_failed_kind) | <span data-ttu-id="0d3b5-222">Tipo de falha de processo usada na interface [IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) .</span><span class="sxs-lookup"><span data-stu-id="0d3b5-222">Kind of process failure used in the [IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) interface.</span></span>
[<span data-ttu-id="0d3b5-223">WEBVIEW2_PERMISSION_TYPE</span><span class="sxs-lookup"><span data-stu-id="0d3b5-223">WEBVIEW2_PERMISSION_TYPE</span></span>](#webview2_permission_type) | <span data-ttu-id="0d3b5-224">O tipo de uma solicitação de permissão.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-224">The type of a permission request.</span></span>
[<span data-ttu-id="0d3b5-225">WEBVIEW2_PERMISSION_STATE</span><span class="sxs-lookup"><span data-stu-id="0d3b5-225">WEBVIEW2_PERMISSION_STATE</span></span>](#webview2_permission_state) | <span data-ttu-id="0d3b5-226">Resposta a uma solicitação de permissão.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-226">Response to a permission request.</span></span>
[<span data-ttu-id="0d3b5-227">WEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="0d3b5-227">WEBVIEW2_MOVE_FOCUS_REASON</span></span>](#webview2_move_focus_reason) | <span data-ttu-id="0d3b5-228">Motivo para mover o foco.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-228">Reason for moving focus.</span></span>
[<span data-ttu-id="0d3b5-229">WEBVIEW2_WEB_ERROR_STATUS</span><span class="sxs-lookup"><span data-stu-id="0d3b5-229">WEBVIEW2_WEB_ERROR_STATUS</span></span>](#webview2_web_error_status) | <span data-ttu-id="0d3b5-230">Valores de status de erro para navegações na Web.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-230">Error status values for web navigations.</span></span>
[<span data-ttu-id="0d3b5-231">WEBVIEW2_WEB_RESOURCE_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="0d3b5-231">WEBVIEW2_WEB_RESOURCE_CONTEXT</span></span>](#webview2_web_resource_context) | <span data-ttu-id="0d3b5-232">Enumeração para contextos de solicitação de recurso da Web.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-232">Enum for web resource request contexts.</span></span>

## <span data-ttu-id="0d3b5-233">Eventos de navegação</span><span class="sxs-lookup"><span data-stu-id="0d3b5-233">Navigation events</span></span>

<span data-ttu-id="0d3b5-234">A sequência normal de eventos de navegação é NavigationStarting, DocumentStateChanged e NavigationCompleted.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-234">The normal sequence of navigation events is NavigationStarting, DocumentStateChanged and then NavigationCompleted.</span></span>

![Dot-inline-dotgraph-1. png](media/dot-inline-dotgraph-1.png)

<span data-ttu-id="0d3b5-236">Observe que isso se destina a eventos de navegação com o mesmo evento Navigationid ARG.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-236">Note that this is for navigation events with the same NavigationId event arg.</span></span> <span data-ttu-id="0d3b5-237">Navegação eventos com diferentes args de eventos Navigationid podem sobrepor-se.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-237">Navigations events with different NavigationId event args may overlap.</span></span> <span data-ttu-id="0d3b5-238">Por exemplo, se você iniciar um evento de navegação e, em seguida, iniciar uma outra navegação, verá o NavigationStarting para a primeira navegação acompanhada pela NavigationStarting da segunda navegação, seguida da NavigationCompleted para a primeira navegação e, em seguida, todos os demais eventos de navegação apropriados para a segunda navegação.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-238">For instance, if you start a navigation wait for its NavigationStarting event and then start another navigation you'll see the NavigationStarting for the first navigate followed by the NavigationStarting of the second navigate, followed by the NavigationCompleted for the first navigation and then all the rest of the appropriate navigation events for the second navigation.</span></span> <span data-ttu-id="0d3b5-239">Em casos de erro, pode ou não ser um evento DocumentStateChanged dependendo se a navegação é continuada para uma página de erro.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-239">In error cases there may or may not be a DocumentStateChanged event depending on whether the navigation is continued to an error page.</span></span> <span data-ttu-id="0d3b5-240">No caso de um redirecionamento HTTP, haverá vários eventos NavigationStarting em uma linha, com os seguintes, o sinalizador isredirect definido.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-240">In case of an HTTP redirect, there will be multiple NavigationStarting events in a row, with ones following the first will have their IsRedirect flag set.</span></span>

<span data-ttu-id="0d3b5-241">Para subquadros dentro do WebView, o único evento de navegação acionado é o evento NavigationStarting que fornece ao host a capacidade de bloquear as navegações do subquadro.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-241">For subframes inside WebView, the only navigation event fired is the NavigationStarting event which gives host the ability to block subframe navigations.</span></span>

## <span data-ttu-id="0d3b5-242">Modelo de processo</span><span class="sxs-lookup"><span data-stu-id="0d3b5-242">Process model</span></span>

<span data-ttu-id="0d3b5-243">O WebView2 usa o mesmo modelo de processo que o navegador da Web Edge.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-243">WebView2 uses the same process model as the Edge web browser.</span></span> <span data-ttu-id="0d3b5-244">Há um processo do navegador Edge por diretório de dados do usuário especificado em uma sessão do usuário que servirá qualquer processo de chamadas do WebView2 que especifique esse diretório de dados do usuário.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-244">There is one Edge browser process per specified user data directory in a user session that will serve any WebView2 calling process that specifies that user data directory.</span></span> <span data-ttu-id="0d3b5-245">Isso significa que um processo do navegador Edge pode estar servindo vários processos de chamadas e um processo de chamada pode estar usando vários processos do navegador do Edge.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-245">This means one Edge browser process may be serving multiple calling processes and one calling process may be using multiple Edge browser processes.</span></span>

![Dot-inline-dotgraph-2. png](media/dot-inline-dotgraph-2.png)

<span data-ttu-id="0d3b5-247">Fora de um processo de navegador, haverá alguns processos de processamento.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-247">Off of a browser process there will be some number of renderer processes.</span></span> <span data-ttu-id="0d3b5-248">Elas são criadas, conforme necessário, para atender a vários quadros potencialmente em diferentes modos de exibição.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-248">These are created as necessary to service potentially multiple frames in different WebViews.</span></span> <span data-ttu-id="0d3b5-249">O número de processos de renderização varia de acordo com o recurso de navegador de isolamento de site e o número de origens discadas discadas renderizadas em webviews associadas.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-249">The number of renderer processes varies based on the site isolation browser feature and the number of distinct disconnected origins rendered in associated WebViews.</span></span>

![Dot-inline-dotgraph-3. png](media/dot-inline-dotgraph-3.png)

<span data-ttu-id="0d3b5-251">Você pode reagir a falhas e travamentos nesses processos do navegador e do renderizador usando o evento ProcessFailure.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-251">You can react to crashes and hangs in these browser and renderer processes using the ProcessFailure event.</span></span>

<span data-ttu-id="0d3b5-252">Você pode desligar com segurança os processos do navegador e do renderizador associados usando o método Close.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-252">You can safely shutdown associated browser and renderer processes using the Close method.</span></span>

## <span data-ttu-id="0d3b5-253">Modelo de Threading</span><span class="sxs-lookup"><span data-stu-id="0d3b5-253">Threading model</span></span>

<span data-ttu-id="0d3b5-254">O WebView2 deve ser criado em um thread de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-254">The WebView2 must be created on a UI thread.</span></span> <span data-ttu-id="0d3b5-255">Especificamente um thread com um bombeamento de mensagem.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-255">Specifically a thread with a message pump.</span></span> <span data-ttu-id="0d3b5-256">Todos os retornos de chamada ocorrerão nesse thread e as chamadas para o WebView deverão ser feitas nesse thread.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-256">All callbacks will occur on that thread and calls into the WebView must be done on that thread.</span></span> <span data-ttu-id="0d3b5-257">Não é seguro usar a WebView a partir de outro thread.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-257">It is not safe to use the WebView from another thread.</span></span>

<span data-ttu-id="0d3b5-258">Os retornos de chamada, incluindo manipuladores de eventos e manipuladores de conclusão, são executados em série.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-258">Callbacks including event handlers and completion handlers execute serially.</span></span> <span data-ttu-id="0d3b5-259">Ou seja, se você tiver um manipulador de eventos em execução e iniciar um loop de mensagem, nenhum outro manipulador de eventos ou chamadas de retorno de conclusão começarão a ser executados de forma reentrada.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-259">That is, if you have an event handler running and begin a message loop no other event handlers or completion callbacks will begin executing reentrantly.</span></span>

## <span data-ttu-id="0d3b5-260">Segurança</span><span class="sxs-lookup"><span data-stu-id="0d3b5-260">Security</span></span>

<span data-ttu-id="0d3b5-261">Sempre verifique a propriedade Source da WebView antes de usar ExecuteScript, PostWebMessageAsJson, PostWebMessageAsString ou qualquer outro método para enviar informações para o WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-261">Always check the Source property of the WebView before using ExecuteScript, PostWebMessageAsJson, PostWebMessageAsString, or any other method to send information into the WebView.</span></span> <span data-ttu-id="0d3b5-262">A WebView pode ter navegado para outra página por meio do usuário final interagindo com a página ou o script na página que está causando a navegação.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-262">The WebView may have navigated to another page via the end user interacting with the page or script in the page causing navigation.</span></span> <span data-ttu-id="0d3b5-263">Da mesma forma, tenha muito cuidado com o AddScriptToExecuteOnDocumentCreated.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-263">Similarly, be very careful with AddScriptToExecuteOnDocumentCreated.</span></span> <span data-ttu-id="0d3b5-264">Todas as navegações futuras executarão esse script e, se ele fornecer acesso às informações destinadas apenas a determinada origem, qualquer documento HTML poderá ter acesso.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-264">All future navigations will run this script and if it provides access to information intended only for a certain origin, any HTML document may have access.</span></span>

<span data-ttu-id="0d3b5-265">Ao examinar o resultado de uma chamada de método ExecuteScript, um evento WebMessageReceived, sempre verifique a fonte do remetente ou qualquer outro mecanismo de recebimento de informações de um documento HTML em uma WebView validar o URI do documento HTML é o que você espera.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-265">When examining the result of an ExecuteScript method call, a WebMessageReceived event, always check the Source of the sender, or any other mechanism of receiving information from an HTML document in a WebView validate the URI of the HTML document is what you expect.</span></span>

<span data-ttu-id="0d3b5-266">Ao construir uma mensagem para enviar para um WebView, prefira usar PostWebMessageAsJson e construir o parâmetro de cadeia de caracteres JSON usando uma biblioteca JSON.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-266">When constructing a message to send into a WebView, prefer using PostWebMessageAsJson and construct the JSON string parameter using a JSON library.</span></span> <span data-ttu-id="0d3b5-267">Isso evitará possíveis acidentes de codificar informações em uma cadeia de caracteres ou script JSON e garantir que nenhuma entrada controlada pelo invasor possa modificar o restante da mensagem JSON ou executar um script arbitrário.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-267">This will avoid any potential accidents of encoding information into a JSON string or script and ensure no attacker controlled input can modify the rest of the JSON message or run arbitrary script.</span></span>

## <span data-ttu-id="0d3b5-268">Tipos de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="0d3b5-268">String types</span></span>

<span data-ttu-id="0d3b5-269">Parâmetros de cadeia de caracteres de saída são cadeias de caracteres de terminação NULL</span><span class="sxs-lookup"><span data-stu-id="0d3b5-269">String out parameters are LPWSTR null terminated strings.</span></span> <span data-ttu-id="0d3b5-270">O chamado aloca a cadeia de caracteres usando CoTaskMemAlloc.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-270">The callee allocates the string using CoTaskMemAlloc.</span></span> <span data-ttu-id="0d3b5-271">A propriedade é transferida para o chamador e fica até o chamador liberar a memória usando o CoTaskMemFree.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-271">Ownership is transferred to the caller and it is up to the caller to free the memory using CoTaskMemFree.</span></span>

<span data-ttu-id="0d3b5-272">Cadeias de caracteres em parâmetros são cadeias de caracteres terminadas LPCWSTR nulas.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-272">String in parameters are LPCWSTR null terminated strings.</span></span> <span data-ttu-id="0d3b5-273">O chamador garante que a cadeia de caracteres é válida para a duração da chamada de função síncrona.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-273">The caller ensures the string is valid for the duration of the synchronous function call.</span></span> <span data-ttu-id="0d3b5-274">Se o chamador precisa reter esse valor para algum ponto após a conclusão da chamada de função, o Calle deve alocar sua própria cópia do valor da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-274">If the callee needs to retain that value to some point after the function call completes, the callee must allocate its own copy of the string value.</span></span>

## <span data-ttu-id="0d3b5-275">Análise de URI e JSON</span><span class="sxs-lookup"><span data-stu-id="0d3b5-275">URI and JSON parsing</span></span>

<span data-ttu-id="0d3b5-276">Vários métodos fornecem ou aceitam URIs e JSON como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-276">Various methods provide or accept URIs and JSON as strings.</span></span> <span data-ttu-id="0d3b5-277">Use sua própria biblioteca preferida para analisar e gerar essas cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-277">Please use your own preferred library for parsing and generating these strings.</span></span>

<span data-ttu-id="0d3b5-278">Se o WinRT estiver disponível para seu aplicativo, você pode usar `RuntimeClass_Windows_Data_Json_JsonObject` e `IJsonObjectStatics` analisar ou produzir cadeias de caracteres JSON ou `RuntimeClass_Windows_Foundation_Uri` `IUriRuntimeClassFactory` analisar e produzir URIs.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-278">If WinRT is available for your app you can use `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` to parse or produce JSON strings or `RuntimeClass_Windows_Foundation_Uri` and `IUriRuntimeClassFactory` to parse and produce URIs.</span></span> <span data-ttu-id="0d3b5-279">Ambos trabalham em aplicativos Win32.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-279">Both of these work in Win32 apps.</span></span>

<span data-ttu-id="0d3b5-280">Se você usar o IUri e o CreateUri para analisar URIs, talvez queira usar os seguintes sinalizadores de criação de URI para que o comportamento de CreateUri corresponda melhor à análise de URI no WebView:</span><span class="sxs-lookup"><span data-stu-id="0d3b5-280">If you use IUri and CreateUri to parse URIs you may want to use the following URI creation flags to have CreateUri behavior more closely match the URI parsing in the WebView:</span></span> `Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO`

## <span data-ttu-id="0d3b5-281">Depuração</span><span class="sxs-lookup"><span data-stu-id="0d3b5-281">Debugging</span></span>

<span data-ttu-id="0d3b5-282">Abra o DevTools com os atalhos normais: `F12` ou `Ctrl+Shift+I` .</span><span class="sxs-lookup"><span data-stu-id="0d3b5-282">Open DevTools with the normal shortcuts: `F12` or `Ctrl+Shift+I`.</span></span> <span data-ttu-id="0d3b5-283">Você pode usar o `--auto-open-devtools-for-tabs` argumento de comando switch para que a janela do devtools seja aberta imediatamente ao criar a primeira vez uma WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-283">You can use the `--auto-open-devtools-for-tabs` command argument switch to have the DevTools window open immediately when first creating a WebView.</span></span> <span data-ttu-id="0d3b5-284">Consulte a documentação de WebView para obter mais argumentos de linha de comando para o processo do navegador.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-284">See CreateWebView documentation for how to provide additional command line arguments to the browser process.</span></span> <span data-ttu-id="0d3b5-285">Confira a chave do registro LoaderOverride para experimentar versões diferentes do WebView2 sem modificar seu aplicativo na documentação da WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-285">Check out the LoaderOverride registry key for trying out different builds of WebView2 without modifying your application in the CreateWebView documentation.</span></span>

## <span data-ttu-id="0d3b5-286">Controle de versão</span><span class="sxs-lookup"><span data-stu-id="0d3b5-286">Versioning</span></span>

<span data-ttu-id="0d3b5-287">Depois de usar uma versão específica do SDK para criar seu aplicativo, seu aplicativo pode acabar sendo executado com uma versão mais antiga ou mais recente dos binários instalados do navegador.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-287">After you've used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.</span></span> <span data-ttu-id="0d3b5-288">Até a versão 1.0.0.0 do WebView2, pode haver alterações significativas durante as atualizações que impedem que o SDK funcione com versões diferentes dos binários instalados do navegador.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-288">Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that will prevent your SDK from working with different versions of installed browser binaries.</span></span> <span data-ttu-id="0d3b5-289">Após a versão 1.0.0.0 versões diferentes do SDK podem funcionar com versões diferentes do navegador instalado seguindo estas práticas recomendadas:</span><span class="sxs-lookup"><span data-stu-id="0d3b5-289">After version 1.0.0.0 different versions of the SDK can work with different versions of the installed browser by following these best practices:</span></span>

<span data-ttu-id="0d3b5-290">Para fazer a conta de alterações significativas na API, verifique se há uma falha ao chamar a DLL de exportação CreateWebView2Environment e ao chamar QueryInterface em qualquer objeto WebView2.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-290">To account for breaking changes to the API be sure to check for failure when calling the DLL export CreateWebView2Environment and when calling QueryInterface on any WebView2 object.</span></span> <span data-ttu-id="0d3b5-291">Um valor de retorno de E_NOINTERFACE pode indicar que o SDK não é compatível com os binários do navegador Edge.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-291">A return value of E_NOINTERFACE can indicate the SDK is not compatible with the Edge browser binaries.</span></span>

<span data-ttu-id="0d3b5-292">Verificar a falha de QueryInterface também contará em casos em que o SDK é mais recente do que a versão do navegador Edge e seu aplicativo tenta usar uma interface do qual o navegador Edge não reconhece.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-292">Checking for failure from QueryInterface will also account for cases where the SDK is newer than the version of the Edge browser and your app attempts to use an interface of which the Edge browser is unaware.</span></span>

<span data-ttu-id="0d3b5-293">Quando uma interface não está disponível, você pode considerar a possibilidade de desabilitar o recurso associado, se possível, ou informar ao usuário final que ele precisa atualizar o navegador.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-293">When an interface is unavailable, you can consider disabling the associated feature if possible, or otherwise informing the end user they need to update their browser.</span></span>

## <span data-ttu-id="0d3b5-294">Parte</span><span class="sxs-lookup"><span data-stu-id="0d3b5-294">Members</span></span>

#### <span data-ttu-id="0d3b5-295">get_Settings</span><span class="sxs-lookup"><span data-stu-id="0d3b5-295">get_Settings</span></span> 

<span data-ttu-id="0d3b5-296">O objeto [IWebView2Settings](IWebView2Settings.md) contém várias configurações modificáveis para a execução do WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-296">The [IWebView2Settings](IWebView2Settings.md) object contains various modifiable settings for the running WebView.</span></span>

> <span data-ttu-id="0d3b5-297">público HRESULT [get_Settings](#get_settings)(configurações[IWebView2Settings](IWebView2Settings.md) \* \*)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-297">public HRESULT [get_Settings](#get_settings)([IWebView2Settings](IWebView2Settings.md) \*\* settings)</span></span>

#### <span data-ttu-id="0d3b5-298">get_Source</span><span class="sxs-lookup"><span data-stu-id="0d3b5-298">get_Source</span></span> 

<span data-ttu-id="0d3b5-299">O URI do documento de nível superior atual.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-299">The URI of the current top level document.</span></span>

> <span data-ttu-id="0d3b5-300">[get_Source](#get_source)público HRESULT (URI LPWSTR \*)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-300">public HRESULT [get_Source](#get_source)(LPWSTR \* uri)</span></span>

<span data-ttu-id="0d3b5-301">Esse valor potencialmente muda como parte do acionamento do evento DocumentStateChanged para alguns casos, como navegar para diferentes navegações em sites ou fragmentadores.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-301">This value potentially changes as a part of the DocumentStateChanged event firing for some cases such as navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="0d3b5-302">Ele permanecerá o mesmo para outros tipos de navegação, como recarregamentos de página ou historystate com a mesma URL que a página atual.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-302">It will remain the same for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span>

```cpp
    // Register a handler for the DocumentStateChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_DocumentStateChanged(
        Callback<IWebView2DocumentStateChangedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2DocumentStateChangedEventArgs* args)
                -> HRESULT {
                wil::unique_cotaskmem_string uri;
                sender->get_Source(&uri);
                if (wcscmp(uri.get(), L"about:blank") == 0)
                {
                    uri = wil::make_cotaskmem_string(L"");
                }
                SetWindowText(m_toolbar->addressBarWindow, uri.get());

                return S_OK;
            })
            .Get(),
        &m_documentStateChangedToken));
```

#### <span data-ttu-id="0d3b5-303">Navegar</span><span class="sxs-lookup"><span data-stu-id="0d3b5-303">Navigate</span></span> 

<span data-ttu-id="0d3b5-304">Fazer uma navegação do documento de nível superior para o URI especificado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-304">Cause a navigation of the top level document to the specified URI.</span></span>

> <span data-ttu-id="0d3b5-305">público- [navegação](#navigate)HRESULT (URI LPCWSTR)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-305">public HRESULT [Navigate](#navigate)(LPCWSTR uri)</span></span>

<span data-ttu-id="0d3b5-306">Consulte os eventos de navegação para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-306">See the navigation events for more information.</span></span> <span data-ttu-id="0d3b5-307">Observe que isso iniciará uma navegação e o evento NavigationStarting correspondente será acionado algum tempo após a conclusão dessa chamada de navegação.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-307">Note that this starts a navigation and the corresponding NavigationStarting event will fire sometime after this Navigate call completes.</span></span>

```cpp
void ControlComponent::NavigateToAddressBar()
{
    WCHAR uri[2048] = L"";
    GetWindowText(m_toolbar->addressBarWindow, uri, ARRAYSIZE(uri));
    CHECK_FAILURE(m_webView->Navigate(uri));
}
```

#### <span data-ttu-id="0d3b5-308">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="0d3b5-308">MoveFocus</span></span> 

<span data-ttu-id="0d3b5-309">Mover o foco para o WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-309">Move focus into WebView.</span></span>

> <span data-ttu-id="0d3b5-310">Public HRESULT [MoveFocus](#movefocus)(motivo[WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason) )</span><span class="sxs-lookup"><span data-stu-id="0d3b5-310">public HRESULT [MoveFocus](#movefocus)([WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason) reason)</span></span>

<span data-ttu-id="0d3b5-311">O WebView receberá o foco e o foco será definido como elemento correspondente na página hospedada na WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-311">WebView will get focus and focus will be set to correspondent element in the page hosted in the WebView.</span></span> <span data-ttu-id="0d3b5-312">Para motivo programático, o foco é definido como elemento prefoco anteriormente ou o elemento padrão se não houver nenhum elemento focalizado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-312">For Programmatic reason, focus is set to previously focused element or the default element if there is no previously focused element.</span></span> <span data-ttu-id="0d3b5-313">Para o próximo motivo, o foco é definido como o primeiro elemento.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-313">For Next reason, focus is set to the first element.</span></span> <span data-ttu-id="0d3b5-314">Para o motivo anterior, o foco é definido como o último elemento.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-314">For Previous reason, focus is set to the last element.</span></span> <span data-ttu-id="0d3b5-315">A WebView também pode ter o foco por meio da interação do usuário, como clicar em um WebView ou Tab.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-315">WebView can also got focus through user interaction like clicking into WebView or Tab into it.</span></span> <span data-ttu-id="0d3b5-316">Para tabulação, o aplicativo pode chamar MoveFocus com o próximo ou o anterior para alinhar-se com Tab e Shift + Tab, respectivamente, quando decide que o WebView é o próximo elemento que pode ser tabulado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-316">For tabbing, the app can call MoveFocus with Next or Previous to align with tab and shift+tab respectively when it decides the WebView is the next tabbable element.</span></span> <span data-ttu-id="0d3b5-317">Ou, o aplicativo pode chamar IsDialogMessage como parte de seu loop de mensagem para permitir que a plataforma manipule a Tabulação automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-317">Or, the app can call IsDialogMessage as part of its message loop to allow the platform to auto handle tabbing.</span></span> <span data-ttu-id="0d3b5-318">A plataforma irá girar por todas as janelas com WS_TABSTOP.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-318">The platform will rotate through all windows with WS_TABSTOP.</span></span> <span data-ttu-id="0d3b5-319">Quando a WebView se concentrar no IsDialogMessage, o foco será inserido internamente no primeiro ou último elemento para Tab e Shift + Tab respectivamente.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-319">When the WebView gets focus from IsDialogMessage, it will internally put the focus on the first or last element for tab and shift+tab respectively.</span></span>

```cpp
    while (GetMessage(&msg, nullptr, 0, 0))
    {
        if (!TranslateAccelerator(msg.hwnd, hAccelTable, &msg))
        {
            // Calling IsDialogMessage handles Tab traversal automatically. If the
            // app wants the platform to auto handle tab, then call IsDialogMessage
            // before calling TranslateMessage/DispatchMessage. If the app wants to
            // handle tabbing itself, then skip calling IsDialogMessage and call
            // TranslateMessage/DispatchMessage directly.
            if (!g_autoTabHandle || !IsDialogMessage(GetAncestor(msg.hwnd, GA_ROOT), &msg))
            {
                TranslateMessage(&msg);
                DispatchMessage(&msg);
            }
        }
    }
```

```cpp
        if (wParam == VK_TAB)
        {
            // Find out if the window is one we've customized for tab handling
            for (int i = 0; i < m_tabbableWindows.size(); i++)
            {
                if (m_tabbableWindows[i].first == hWnd)
                {
                    if (GetKeyState(VK_SHIFT) < 0)
                    {
                        TabBackwards(i);
                    }
                    else
                    {
                        TabForwards(i);
                    }
                    return true;
                }
            }
        }
```

```cpp
void ControlComponent::TabForwards(int currentIndex)
{
    // Find first enabled window after the active one
    for (int i = currentIndex + 1; i < m_tabbableWindows.size(); i++)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    m_webView->MoveFocus(WEBVIEW2_MOVE_FOCUS_REASON_NEXT);
}

void ControlComponent::TabBackwards(int currentIndex)
{
    // Find first enabled window before the active one
    for (int i = currentIndex - 1; i >= 0; i--)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    CHECK_FAILURE(m_webView->MoveFocus(WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS));
}
```

#### <span data-ttu-id="0d3b5-320">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="0d3b5-320">NavigateToString</span></span> 

<span data-ttu-id="0d3b5-321">Inicia uma navegação para htmlContent como código-fonte HTML de um novo documento.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-321">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="0d3b5-322">Public HRESULT [NavigateToString](#navigatetostring)(LPCWSTR htmlContent)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-322">public HRESULT [NavigateToString](#navigatetostring)(LPCWSTR htmlContent)</span></span>

<span data-ttu-id="0d3b5-323">O parâmetro htmlContent não pode ter mais de 2 MB de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-323">The htmlContent parameter may not be larger than 2 MB of characters.</span></span> <span data-ttu-id="0d3b5-324">A origem da nova página será: em branco.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-324">The origin of the new page will be about:blank.</span></span>

```cpp
                static const PCWSTR htmlContent =
                    L"<h1>Domain Blocked</h1>"
                    L"<p>You've attempted to navigate to a domain in the blocked "
                    L"sites list. Press back to return to the previous page.</p>";
                CHECK_FAILURE(sender->NavigateToString(htmlContent));
```

#### <span data-ttu-id="0d3b5-325">add_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="0d3b5-325">add_NavigationStarting</span></span> 

<span data-ttu-id="0d3b5-326">Adicione um manipulador de eventos para o evento NavigationStarting.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-326">Add an event handler for the NavigationStarting event.</span></span>

> <span data-ttu-id="0d3b5-327">Public HRESULT [add_NavigationStarting](#add_navigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-327">public HRESULT [add_NavigationStarting](#add_navigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0d3b5-328">NavigationStarting é acionado quando o quadro principal do WebView está solicitando permissão para navegar para um URI diferente.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-328">NavigationStarting fires when the WebView main frame is requesting permission to navigate to a different URI.</span></span> <span data-ttu-id="0d3b5-329">Isso também será acionado para redirecionamentos.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-329">This will fire for redirects as well.</span></span>

```cpp
    // Register a handler for the NavigationStarting event.
    // This handler will check the domain being navigated to, and if the domain
    // matches a list of blocked sites, it will cancel the navigation and
    // possibly display a warning page.  It will also disable JavaScript on
    // selected websites.
    CHECK_FAILURE(m_webView->add_NavigationStarting(
        Callback<IWebView2NavigationStartingEventHandler>(
            [this](IWebView2WebView* sender,
                   IWebView2NavigationStartingEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Uri(&uri));

        if (ShouldBlockUri(uri.get()))
        {
            CHECK_FAILURE(args->put_Cancel(true));

            // If the user clicked a link to navigate, show a warning page.
            BOOL userInitiated;
            CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));
            if (userInitiated)
            {
                static const PCWSTR htmlContent =
                    L"<h1>Domain Blocked</h1>"
                    L"<p>You've attempted to navigate to a domain in the blocked "
                    L"sites list. Press back to return to the previous page.</p>";
                CHECK_FAILURE(sender->NavigateToString(htmlContent));
            }
        }
        // Changes to settings will apply at the next navigation, which includes the
        // navigation after a NavigationStarting event.  We can use this to change
        // settings according to what site we're visiting.
        if (ShouldBlockScriptForUri(uri.get()))
        {
            m_settings->put_IsScriptEnabled(FALSE);
        }
        else
        {
            m_settings->put_IsScriptEnabled(m_isScriptEnabled);
        }
        return S_OK;
    }).Get(), &m_navigationStartingToken));
```

#### <span data-ttu-id="0d3b5-330">remove_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="0d3b5-330">remove_NavigationStarting</span></span> 

<span data-ttu-id="0d3b5-331">Remover um manipulador de eventos adicionado anteriormente com add_NavigationStarting.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-331">Remove an event handler previously added with add_NavigationStarting.</span></span>

> <span data-ttu-id="0d3b5-332">[remove_NavigationStarting](#remove_navigationstarting)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-332">public HRESULT [remove_NavigationStarting](#remove_navigationstarting)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0d3b5-333">add_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="0d3b5-333">add_DocumentStateChanged</span></span> 

<span data-ttu-id="0d3b5-334">Adicione um manipulador de eventos para o evento DocumentStateChanged.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-334">Add an event handler for the DocumentStateChanged event.</span></span>

> <span data-ttu-id="0d3b5-335">Public HRESULT [add_DocumentStateChanged](#add_documentstatechanged)([IWebView2DocumentStateChangedEventHandler](IWebView2DocumentStateChangedEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-335">public HRESULT [add_DocumentStateChanged](#add_documentstatechanged)([IWebView2DocumentStateChangedEventHandler](IWebView2DocumentStateChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0d3b5-336">DocumentStateChanged é acionado quando o novo conteúdo começa a ser carregado no quadro principal do WebView ou se ocorre uma mesma navegação de página (por exemplo, por meio de navegações de fragmento ou de histórico. pushstate).</span><span class="sxs-lookup"><span data-stu-id="0d3b5-336">DocumentStateChanged fires when new content has started loading on the webview's main frame or if a same page navigation occurs (such as through fragment navigations or history.pushState navigations).</span></span> <span data-ttu-id="0d3b5-337">Isso segue o evento NavigationStarting e precede o evento NavigationCompleted.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-337">This follows the NavigationStarting event and precedes the NavigationCompleted event.</span></span>

```cpp
    // Register a handler for the DocumentStateChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_DocumentStateChanged(
        Callback<IWebView2DocumentStateChangedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2DocumentStateChangedEventArgs* args)
                -> HRESULT {
                wil::unique_cotaskmem_string uri;
                sender->get_Source(&uri);
                if (wcscmp(uri.get(), L"about:blank") == 0)
                {
                    uri = wil::make_cotaskmem_string(L"");
                }
                SetWindowText(m_toolbar->addressBarWindow, uri.get());

                return S_OK;
            })
            .Get(),
        &m_documentStateChangedToken));
```

#### <span data-ttu-id="0d3b5-338">remove_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="0d3b5-338">remove_DocumentStateChanged</span></span> 

<span data-ttu-id="0d3b5-339">Remover um manipulador de eventos adicionado anteriormente com add_DocumentStateChanged.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-339">Remove an event handler previously added with add_DocumentStateChanged.</span></span>

> <span data-ttu-id="0d3b5-340">[remove_DocumentStateChanged](#remove_documentstatechanged)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-340">public HRESULT [remove_DocumentStateChanged](#remove_documentstatechanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0d3b5-341">add_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="0d3b5-341">add_NavigationCompleted</span></span> 

<span data-ttu-id="0d3b5-342">Adicione um manipulador de eventos para o evento NavigationCompleted.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-342">Add an event handler for the NavigationCompleted event.</span></span>

> <span data-ttu-id="0d3b5-343">Public HRESULT [add_NavigationCompleted](#add_navigationcompleted)([IWebView2NavigationCompletedEventHandler](IWebView2NavigationCompletedEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-343">public HRESULT [add_NavigationCompleted](#add_navigationcompleted)([IWebView2NavigationCompletedEventHandler](IWebView2NavigationCompletedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0d3b5-344">O evento NavigationCompleted é acionado quando o WebView foi completamente carregado (Body. OnLoad foi acionado) ou o carregamento parou com o erro.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-344">NavigationCompleted event fires when the WebView has completely loaded (body.onload has fired) or loading stopped with error.</span></span>

```cpp
    // Register a handler for the NavigationCompleted event.
    // Check whether the navigation succeeded, and if not, do something.
    // Also update the Back, Forward, and Cancel buttons.
    CHECK_FAILURE(m_webView->add_NavigationCompleted(
        Callback<IWebView2NavigationCompletedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2NavigationCompletedEventArgs* args)
                -> HRESULT {
                BOOL success;
                CHECK_FAILURE(args->get_IsSuccess(&success));
                if (!success)
                {
                    WEBVIEW2_WEB_ERROR_STATUS webErrorStatus;
                    CHECK_FAILURE(args->get_WebErrorStatus(&webErrorStatus));
                    if (webErrorStatus == WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED)
                    {
                        // Do something here if you want to handle a specific error case.
                        // In most cases this isn't necessary, because the WebView will
                        // display its own error page automatically.
                    }
                }

                BOOL canGoBack;
                BOOL canGoForward;
                sender->get_CanGoBack(&canGoBack);
                sender->get_CanGoForward(&canGoForward);
                EnableWindow(m_toolbar->backWindow, canGoBack);
                EnableWindow(m_toolbar->forwardWindow, canGoForward);
                EnableWindow(m_toolbar->cancelWindow, FALSE);
                return S_OK;
            })
            .Get(),
        &m_navigationCompletedToken));
```

#### <span data-ttu-id="0d3b5-345">remove_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="0d3b5-345">remove_NavigationCompleted</span></span> 

<span data-ttu-id="0d3b5-346">Remover um manipulador de eventos adicionado anteriormente com add_NavigationCompleted.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-346">Remove an event handler previously added with add_NavigationCompleted.</span></span>

> <span data-ttu-id="0d3b5-347">[remove_NavigationCompleted](#remove_navigationcompleted)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-347">public HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0d3b5-348">add_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="0d3b5-348">add_FrameNavigationStarting</span></span> 

<span data-ttu-id="0d3b5-349">Adicione um manipulador de eventos para o evento FrameNavigationStarting.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-349">Add an event handler for the FrameNavigationStarting event.</span></span>

> <span data-ttu-id="0d3b5-350">Public HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-350">public HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0d3b5-351">FrameNavigationStarting é acionado quando um quadro filho na WebView solicita permissão para navegar para um URI diferente.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-351">FrameNavigationStarting fires when a child frame in the WebView requesting permission to navigate to a different URI.</span></span> <span data-ttu-id="0d3b5-352">Isso também será acionado para redirecionamentos.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-352">This will fire for redirects as well.</span></span>

```cpp
    // Register a handler for the FrameNavigationStarting event.
    // This handler will prevent a frame from navigating to a blocked domain.
    CHECK_FAILURE(m_webView->add_FrameNavigationStarting(
        Callback<IWebView2NavigationStartingEventHandler>(
            [this](IWebView2WebView* sender,
                   IWebView2NavigationStartingEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Uri(&uri));

        if (ShouldBlockUri(uri.get()))
        {
            CHECK_FAILURE(args->put_Cancel(true));
        }
        return S_OK;
    }).Get(), &m_frameNavigationStartingToken));
```

#### <span data-ttu-id="0d3b5-353">remove_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="0d3b5-353">remove_FrameNavigationStarting</span></span> 

<span data-ttu-id="0d3b5-354">Remover um manipulador de eventos adicionado anteriormente com add_FrameNavigationStarting.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-354">Remove an event handler previously added with add_FrameNavigationStarting.</span></span>

> <span data-ttu-id="0d3b5-355">[remove_FrameNavigationStarting](#remove_framenavigationstarting)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-355">public HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0d3b5-356">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="0d3b5-356">add_MoveFocusRequested</span></span> 

<span data-ttu-id="0d3b5-357">Adicione um manipulador de eventos para o evento MoveFocusRequested.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-357">Add an event handler for the MoveFocusRequested event.</span></span>

> <span data-ttu-id="0d3b5-358">Public HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([IWebView2MoveFocusRequestedEventHandler](IWebView2MoveFocusRequestedEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-358">public HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([IWebView2MoveFocusRequestedEventHandler](IWebView2MoveFocusRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0d3b5-359">MoveFocusRequested é acionado quando o usuário tenta Tab no WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-359">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span> <span data-ttu-id="0d3b5-360">O foco da WebView não mudou quando esse evento é acionado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-360">The WebView's focus has not changed when this event is fired.</span></span>

```cpp
    // Register a handler for the MoveFocusRequested event.
    // This event will be fired when the user tabs out of the webview.
    // The handler will focus another window in the app, depending on which
    // direction the focus is being shifted.
    CHECK_FAILURE(m_webView->add_MoveFocusRequested(
        Callback<IWebView2MoveFocusRequestedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2MoveFocusRequestedEventArgs* args)
                -> HRESULT {
                if (!g_autoTabHandle)
                {
                    WEBVIEW2_MOVE_FOCUS_REASON reason;
                    CHECK_FAILURE(args->get_Reason(&reason));

                    if (reason == WEBVIEW2_MOVE_FOCUS_REASON_NEXT)
                    {
                        TabForwards(-1);
                    }
                    else if (reason == WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS)
                    {
                        TabBackwards(int(m_tabbableWindows.size()));
                    }
                    CHECK_FAILURE(args->put_Handled(TRUE));
                }
                return S_OK;
            })
            .Get(),
        &m_moveFocusRequestedToken));
```

#### <span data-ttu-id="0d3b5-361">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="0d3b5-361">remove_MoveFocusRequested</span></span> 

<span data-ttu-id="0d3b5-362">Remover um manipulador de eventos adicionado anteriormente com add_MoveFocusRequested.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-362">Remove an event handler previously added with add_MoveFocusRequested.</span></span>

> <span data-ttu-id="0d3b5-363">[remove_MoveFocusRequested](#remove_movefocusrequested)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-363">public HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0d3b5-364">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="0d3b5-364">add_GotFocus</span></span> 

<span data-ttu-id="0d3b5-365">Adicione um manipulador de eventos para o evento GotFocus.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-365">Add an event handler for the GotFocus event.</span></span>

> <span data-ttu-id="0d3b5-366">Public HRESULT [add_GotFocus](#add_gotfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-366">public HRESULT [add_GotFocus](#add_gotfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0d3b5-367">GotFocus é acionado quando o WebView tem foco.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-367">GotFocus fires when WebView got focus.</span></span>

#### <span data-ttu-id="0d3b5-368">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="0d3b5-368">remove_GotFocus</span></span> 

<span data-ttu-id="0d3b5-369">Remover um manipulador de eventos adicionado anteriormente com add_GotFocus.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-369">Remove an event handler previously added with add_GotFocus.</span></span>

> <span data-ttu-id="0d3b5-370">[remove_GotFocus](#remove_gotfocus)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-370">public HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0d3b5-371">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="0d3b5-371">add_LostFocus</span></span> 

<span data-ttu-id="0d3b5-372">Adicione um manipulador de eventos para o evento LostFocus.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-372">Add an event handler for the LostFocus event.</span></span>

> <span data-ttu-id="0d3b5-373">Public HRESULT [add_LostFocus](#add_lostfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-373">public HRESULT [add_LostFocus](#add_lostfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0d3b5-374">LostFocus é acionado quando o WebView perdeu o foco.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-374">LostFocus fires when WebView lost focus.</span></span> <span data-ttu-id="0d3b5-375">No caso em que o evento MoveFocusRequested é acionado, o foco continua no WebView quando o evento MoveFocusRequested é acionado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-375">In the case where MoveFocusRequested event is fired, the focus is still on WebView when MoveFocusRequested event fires.</span></span> <span data-ttu-id="0d3b5-376">O foco perdido só será acionado depois que o código do aplicativo ou a ação padrão do conjunto de eventos MoveFocusRequested se concentrar em uma exibição de exibição ausente.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-376">Lost focus only fires afterwards when app's code or default action of MoveFocusRequested event set focus away from WebView.</span></span>

#### <span data-ttu-id="0d3b5-377">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="0d3b5-377">remove_LostFocus</span></span> 

<span data-ttu-id="0d3b5-378">Remover um manipulador de eventos adicionado anteriormente com add_LostFocus.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-378">Remove an event handler previously added with add_LostFocus.</span></span>

> <span data-ttu-id="0d3b5-379">[remove_LostFocus](#remove_lostfocus)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-379">public HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0d3b5-380">add_WebResourceRequested_deprecated</span><span class="sxs-lookup"><span data-stu-id="0d3b5-380">add_WebResourceRequested_deprecated</span></span> 

<span data-ttu-id="0d3b5-381">Esta API será preterida, use a nova API de add_WebResourceRequested.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-381">This API will be deprecated, please use the new add_WebResourceRequested API.</span></span>

> <span data-ttu-id="0d3b5-382">Public HRESULT [add_WebResourceRequested_deprecated](#add_webresourcerequested_deprecated)(LPCWSTR \* const urlFilter,[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context) \* const resourceContextFilter, size_t filterLength,[IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-382">public HRESULT [add_WebResourceRequested_deprecated](#add_webresourcerequested_deprecated)(LPCWSTR \*const urlFilter,[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context) \*const resourceContextFilter,SIZE_T filterLength,[IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0d3b5-383">Adicione um manipulador de eventos para o evento WebResourceRequested.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-383">Add an event handler for the WebResourceRequested event.</span></span> <span data-ttu-id="0d3b5-384">Acionado quando o WebView executa qualquer solicitação HTTP.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-384">Fires when the WebView has performs any HTTP request.</span></span> <span data-ttu-id="0d3b5-385">Use urlFilter para passar uma lista com tamanho filterLength de URLs a serem escutadas.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-385">Use urlFilter to pass in a list with size filterLength of urls to listen for.</span></span> <span data-ttu-id="0d3b5-386">Cada entrada de URL também dá suporte a caracteres curinga: ' \* ' corresponde a zero ou mais caracteres e '? ' corresponde exatamente a um caractere.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-386">Each url entry also supports wildcards: '\*' matches zero or more characters, and '?' matches exactly one character.</span></span> <span data-ttu-id="0d3b5-387">Para cada entrada urlFilter, forneça um resourceContextFilter correspondente que representa os tipos de recursos para os quais o WebResourceRequested deve ser acionado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-387">For each urlFilter entry, provide a matching resourceContextFilter representing the types of resources for which WebResourceRequested should fire.</span></span> <span data-ttu-id="0d3b5-388">Se filterLength for 0, o evento será acionado para todas as solicitações de rede.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-388">If filterLength is 0, the event will fire for all network requests.</span></span> <span data-ttu-id="0d3b5-389">Os contextos de recursos com suporte são: Document, StyleSheet, Image, Media, Font, script, XHR, Fetch.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-389">The supported resource contexts are: Document, Stylesheet, Image, Media, Font, Script, XHR, Fetch.</span></span>

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<IWebView2WebResourceRequestedEventHandler>(
                    [this](
                        IWebView2WebView* sender,
                        IWebView2WebResourceRequestedEventArgs* args) {
                        wil::com_ptr<IWebView2WebResourceRequestedEventArgs2>
                            webResourceEventArgs2;
                        args->QueryInterface(IID_PPV_ARGS(&webResourceEventArgs2));
                        WEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            webResourceEventArgs2->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
                        {
                            return E_INVALIDARG;
                        }
                        // Override the response with an empty one to block the image.
                        // If put_Response is not called, the request will continue as normal.
                        wil::com_ptr<IWebView2WebResourceResponse> response;
                        CHECK_FAILURE(m_webViewEnvironment->CreateWebResourceResponse(
                            nullptr, 403 /*NoContent*/, L"Blocked", L"", &response));
                        CHECK_FAILURE(args->put_Response(response.get()));
                        return S_OK;
                    })
                    .Get(),
                &m_webResourceRequestedTokenForImageBlocking));
        }
        else
        {
            CHECK_FAILURE(m_webView->remove_WebResourceRequested(
                m_webResourceRequestedTokenForImageBlocking));
        }
```

#### <span data-ttu-id="0d3b5-390">remove_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="0d3b5-390">remove_WebResourceRequested</span></span> 

<span data-ttu-id="0d3b5-391">Remover um manipulador de eventos adicionado anteriormente com add_WebResourceRequested.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-391">Remove an event handler previously added with add_WebResourceRequested.</span></span>

> <span data-ttu-id="0d3b5-392">[remove_WebResourceRequested](#remove_webresourcerequested)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-392">public HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0d3b5-393">add_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="0d3b5-393">add_ScriptDialogOpening</span></span> 

<span data-ttu-id="0d3b5-394">Adicione um manipulador de eventos para o evento ScriptDialogOpening.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-394">Add an event handler for the ScriptDialogOpening event.</span></span>

> <span data-ttu-id="0d3b5-395">Public HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)([IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-395">public HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)([IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0d3b5-396">O evento é acionado quando uma caixa de diálogo JavaScript (alerta, confirmação ou prompt) aparecerá para o WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-396">The event fires when a JavaScript dialog (alert, confirm, or prompt) will show for the webview.</span></span> <span data-ttu-id="0d3b5-397">Esse evento só será acionado se a propriedade IWebView2Settings:: AreDefaultScriptDialogsEnabled estiver definida como false.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-397">This event only fires if the IWebView2Settings::AreDefaultScriptDialogsEnabled property is set to false.</span></span>

```cpp
    // Register a handler for the ScriptDialogOpening event.
    // This handler will set up a custom prompt dialog for the user,
    // and may defer the event if the setting to defer dialogs is enabled.
    CHECK_FAILURE(m_webView->add_ScriptDialogOpening(
        Callback<IWebView2ScriptDialogOpeningEventHandler>(
            [this](
                IWebView2WebView* sender,
                IWebView2ScriptDialogOpeningEventArgs* args) -> HRESULT
    {
        wil::com_ptr<IWebView2ScriptDialogOpeningEventArgs> eventArgs = args;
        auto showDialog = [this, eventArgs]
        {
            wil::unique_cotaskmem_string uri;
            WEBVIEW2_SCRIPT_DIALOG_KIND type;
            wil::unique_cotaskmem_string message;
            wil::unique_cotaskmem_string defaultText;

            CHECK_FAILURE(eventArgs->get_Uri(&uri));
            CHECK_FAILURE(eventArgs->get_Kind(&type));
            CHECK_FAILURE(eventArgs->get_Message(&message));
            CHECK_FAILURE(eventArgs->get_DefaultText(&defaultText));

            std::wstring promptString = std::wstring(L"The page at '")
                + uri.get() + L"' says:";
            TextInputDialog dialog(
                m_appWindow->GetMainWindow(),
                L"Script Dialog",
                promptString.c_str(),
                message.get(),
                defaultText.get(),
                /* readonly */ type != WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT);
            if (dialog.confirmed)
            {
                CHECK_FAILURE(eventArgs->put_ResultText(dialog.input.c_str()));
                CHECK_FAILURE(eventArgs->Accept());
            }
        };

        if (m_deferScriptDialogs)
        {
            wil::com_ptr<IWebView2Deferral> deferral;
            CHECK_FAILURE(args->GetDeferral(&deferral));
            m_completeDeferredDialog = [showDialog, deferral]
            {
                showDialog();
                CHECK_FAILURE(deferral->Complete());
            };
        }
        else
        {
            showDialog();
        }

        return S_OK;
    }).Get(), &m_scriptDialogOpeningToken));
```

#### <span data-ttu-id="0d3b5-398">remove_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="0d3b5-398">remove_ScriptDialogOpening</span></span> 

<span data-ttu-id="0d3b5-399">Remover um manipulador de eventos adicionado anteriormente com add_ScriptDialogOpening.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-399">Remove an event handler previously added with add_ScriptDialogOpening.</span></span>

> <span data-ttu-id="0d3b5-400">[remove_ScriptDialogOpening](#remove_scriptdialogopening)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-400">public HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0d3b5-401">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="0d3b5-401">add_ZoomFactorChanged</span></span> 

<span data-ttu-id="0d3b5-402">Adicione um manipulador de eventos para o evento ZoomFactorChanged.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-402">Add an event handler for the ZoomFactorChanged event.</span></span>

> <span data-ttu-id="0d3b5-403">Public HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([IWebView2ZoomFactorChangedEventHandler](IWebView2ZoomFactorChangedEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-403">public HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([IWebView2ZoomFactorChangedEventHandler](IWebView2ZoomFactorChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0d3b5-404">O evento é acionado quando a propriedade ZoomFactor da WebView é alterada.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-404">The event fires when the ZoomFactor property of the WebView changes.</span></span> <span data-ttu-id="0d3b5-405">O evento pode ser acionado porque o chamador modificou a propriedade ZoomFactor ou porque o usuário modificou manualmente o zoom.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-405">The event could fire because the caller modified the ZoomFactor property, or due to the user manually modifying the zoom.</span></span> <span data-ttu-id="0d3b5-406">Quando ela é modificada pelo chamador por meio da propriedade ZoomFactor, o fator de zoom interno é atualizado imediatamente e não haverá um evento ZoomFactorChanged.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-406">When it is modified by the caller via the ZoomFactor property, the internal zoom factor is updated immediately and there will be no ZoomFactorChanged event.</span></span> <span data-ttu-id="0d3b5-407">O WebView associa o último fator de zoom usado para cada site.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-407">WebView associates the last used zoom factor for each site.</span></span> <span data-ttu-id="0d3b5-408">Portanto, é possível que o fator de zoom mude ao navegar para uma página diferente.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-408">Therefore, it is possible for the zoom factor to change when navigating to a different page.</span></span> <span data-ttu-id="0d3b5-409">Quando o fator de zoom muda devido a isso, o evento ZoomFactorChanged é acionado logo após o evento DocumentStateChanged.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-409">When the zoom factor changes due to this, the ZoomFactorChanged event fires right after the DocumentStateChanged event.</span></span>

```cpp
    // Register a handler for the ZoomFactorChanged event.
    // This handler just announces the new level of zoom on the window's title bar.
    CHECK_FAILURE(m_webView->add_ZoomFactorChanged(
        Callback<IWebView2ZoomFactorChangedEventHandler>(
            [this](IWebView2WebView* sender, IUnknown* args) -> HRESULT {
                double zoomFactor;
                CHECK_FAILURE(sender->get_ZoomFactor(&zoomFactor));

                std::wstring message = L"WebView2APISample (Zoom: " +
                                       std::to_wstring(int(zoomFactor * 100)) + L"%)";
                SetWindowText(m_appWindow->GetMainWindow(), message.c_str());
                return S_OK;
            })
            .Get(),
        &m_zoomFactorChangedToken));
```

#### <span data-ttu-id="0d3b5-410">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="0d3b5-410">remove_ZoomFactorChanged</span></span> 

<span data-ttu-id="0d3b5-411">Remover um manipulador de eventos adicionado anteriormente com add_ZoomFactorChanged.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-411">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>

> <span data-ttu-id="0d3b5-412">[remove_ZoomFactorChanged](#remove_zoomfactorchanged)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-412">public HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0d3b5-413">add_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="0d3b5-413">add_PermissionRequested</span></span> 

<span data-ttu-id="0d3b5-414">Adicione um manipulador de eventos para o evento PermissionRequested.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-414">Add an event handler for the PermissionRequested event.</span></span>

> <span data-ttu-id="0d3b5-415">Public HRESULT [add_PermissionRequested](#add_permissionrequested)([IWebView2PermissionRequestedEventHandler](IWebView2PermissionRequestedEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-415">public HRESULT [add_PermissionRequested](#add_permissionrequested)([IWebView2PermissionRequestedEventHandler](IWebView2PermissionRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0d3b5-416">Acionado quando o conteúdo de uma WebView solicita permissão para acessar alguns recursos privilegiados.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-416">Fires when content in a WebView requests permission to access some privileged resources.</span></span>

```cpp
    // Register a handler for the PermissionRequested event.
    // This handler prompts the user to allow or deny the request.
    CHECK_FAILURE(m_webView->add_PermissionRequested(
        Callback<IWebView2PermissionRequestedEventHandler>(
            [this](
                IWebView2WebView* sender,
                IWebView2PermissionRequestedEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        WEBVIEW2_PERMISSION_TYPE type = WEBVIEW2_PERMISSION_TYPE_UNKNOWN_PERMISSION;
        BOOL userInitiated = FALSE;

        CHECK_FAILURE(args->get_Uri(&uri));
        CHECK_FAILURE(args->get_PermissionType(&type));
        CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));

        std::wstring message = L"Do you want to grant permission for ";
        message += NameOfPermissionType(type);
        message += L" to the website at ";
        message += uri.get();
        message += L"?\n\n";
        message += (userInitiated
            ? L"This request came from a user gesture."
            : L"This request did not come from a user gesture.");

        int response = MessageBox(nullptr, message.c_str(), L"Permission Request",
                                   MB_YESNOCANCEL | MB_ICONWARNING);

        WEBVIEW2_PERMISSION_STATE state =
              response == IDYES ? WEBVIEW2_PERMISSION_STATE_ALLOW
            : response == IDNO  ? WEBVIEW2_PERMISSION_STATE_DENY
            :                     WEBVIEW2_PERMISSION_STATE_DEFAULT;
        CHECK_FAILURE(args->put_State(state));

        return S_OK;
    }).Get(), &m_permissionRequestedToken));
```

#### <span data-ttu-id="0d3b5-417">remove_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="0d3b5-417">remove_PermissionRequested</span></span> 

<span data-ttu-id="0d3b5-418">Remover um manipulador de eventos adicionado anteriormente com add_PermissionRequested.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-418">Remove an event handler previously added with add_PermissionRequested.</span></span>

> <span data-ttu-id="0d3b5-419">[remove_PermissionRequested](#remove_permissionrequested)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-419">public HRESULT [remove_PermissionRequested](#remove_permissionrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0d3b5-420">add_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="0d3b5-420">add_ProcessFailed</span></span> 

<span data-ttu-id="0d3b5-421">Adicione um manipulador de eventos para o evento ProcessFailed.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-421">Add an event handler for the ProcessFailed event.</span></span>

> <span data-ttu-id="0d3b5-422">Public HRESULT [add_ProcessFailed](#add_processfailed)([IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-422">public HRESULT [add_ProcessFailed](#add_processfailed)([IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0d3b5-423">Acionado quando um processo da WebView termina inesperadamente ou não responde.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-423">Fires when a WebView process terminated unexpectedly or become unresponsive.</span></span>

```cpp
    // Register a handler for the ProcessFailed event.
    // This handler checks if the browser process failed, and asks the user if
    // they want to recreate the webview.
    CHECK_FAILURE(m_webView->add_ProcessFailed(
        Callback<IWebView2ProcessFailedEventHandler>(
            [this](IWebView2WebView* sender,
                IWebView2ProcessFailedEventArgs* args) -> HRESULT
    {
        WEBVIEW2_PROCESS_FAILED_KIND failureType;
        CHECK_FAILURE(args->get_ProcessFailedKind(&failureType));
        if (failureType == WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED)
        {
            int button = MessageBox(
                m_appWindow->GetMainWindow(),
                L"Browser process exited unexpectedly.  Recreate webview?",
                L"Browser process exited",
                MB_YESNO);
            if (button == IDYES)
            {
                m_appWindow->ReinitializeWebView();
            }
        }
        return S_OK;
    }).Get(), &m_processFailedToken));
```

#### <span data-ttu-id="0d3b5-424">remove_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="0d3b5-424">remove_ProcessFailed</span></span> 

<span data-ttu-id="0d3b5-425">Remover um manipulador de eventos adicionado anteriormente com add_ProcessFailed.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-425">Remove an event handler previously added with add_ProcessFailed.</span></span>

> <span data-ttu-id="0d3b5-426">[remove_ProcessFailed](#remove_processfailed)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-426">public HRESULT [remove_ProcessFailed](#remove_processfailed)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0d3b5-427">AddScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="0d3b5-427">AddScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="0d3b5-428">Adicione o JavaScript fornecido a uma lista de scripts que devem ser executados após a criação do objeto global, mas antes de o documento HTML ter sido analisado e antes de qualquer outro script incluído no documento HTML ser executado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-428">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>

> <span data-ttu-id="0d3b5-429">Public HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)(LPCWSTR JavaScript,[IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler.md) \* Handler)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-429">public HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)(LPCWSTR javaScript,[IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="0d3b5-430">O script injetado se aplicará a todas as futuras navegações de documento de nível superior e quadro filho até que sejam removidas com o RemoveScriptToExecuteOnDocumentCreated.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-430">The injected script will apply to all future top level document and child frame navigations until removed with RemoveScriptToExecuteOnDocumentCreated.</span></span> <span data-ttu-id="0d3b5-431">Isso é aplicado de forma assíncrona e você deve aguardar até que o manipulador de conclusão seja executado antes de poder ter certeza de que o script está pronto para ser executado em navegações futuras.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-431">This is applied asynchronously and you must wait for the completion handler to run before you can be sure that the script is ready to execute on future navigations.</span></span>

<span data-ttu-id="0d3b5-432">Observe que, se um documento HTML tiver uma área restrita de algum tipo via propriedades de [área restrita](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox) ou o [cabeçalho HTTP de política de segurança de conteúdo](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy) , isso afetará o script ser executado aqui.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-432">Note that if an HTML document has sandboxing of some kind via [sandbox](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox) properties or the [Content-Security-Policy HTTP header](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy) this will affect the script run here.</span></span> <span data-ttu-id="0d3b5-433">Portanto, por exemplo, se a palavra-chave ' allow-janelarestritas ' não estiver definida, as chamadas para a `alert` função serão ignoradas.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-433">So, for example, if the 'allow-modals' keyword is not set then calls to the `alert` function will be ignored.</span></span>

```cpp
// Prompt the user for some script and register it to execute whenever a new page loads.
void ScriptComponent::AddInitializeScript()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Add Initialize Script",
        L"Initialization Script:",
        L"Enter the JavaScript code to run as the initialization script that "
            L"runs before any script in the HTML document.",
    // This example script stops child frames from opening new windows.  Because
    // the initialization script runs before any script in the HTML document, we
    // can trust the results of our checks on window.parent and window.top.
        L"if (window.parent !== window.top) {\r\n"
        L"    delete window.open;\r\n"
        L"}");
    if (dialog.confirmed)
    {
        m_webView->AddScriptToExecuteOnDocumentCreated(
            dialog.input.c_str(),
            Callback<IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler>(
                [this](HRESULT error, PCWSTR id) -> HRESULT
        {
            m_lastInitializeScriptId = id;
            MessageBox(nullptr, id, L"AddScriptToExecuteOnDocumentCreated Id", MB_OK);
            return S_OK;
        }).Get());

    }
}
```

#### <span data-ttu-id="0d3b5-434">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="0d3b5-434">RemoveScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="0d3b5-435">Remova o JavaScript correspondente adicionado via AddScriptToExecuteOnDocumentCreated.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-435">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated.</span></span>

> <span data-ttu-id="0d3b5-436">Public HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(ID LPCWSTR)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-436">public HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(LPCWSTR id)</span></span>

#### <span data-ttu-id="0d3b5-437">ExecuteScript</span><span class="sxs-lookup"><span data-stu-id="0d3b5-437">ExecuteScript</span></span> 

<span data-ttu-id="0d3b5-438">Execute o código JavaScript do parâmetro JavaScript no documento de nível superior atual renderizado no WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-438">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="0d3b5-439">Public HRESULT [ExecuteScript](#executescript)(LPCWSTR JavaScript,[IWebView2ExecuteScriptCompletedHandler](IWebView2ExecuteScriptCompletedHandler.md) \* Handler)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-439">public HRESULT [ExecuteScript](#executescript)(LPCWSTR javaScript,[IWebView2ExecuteScriptCompletedHandler](IWebView2ExecuteScriptCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="0d3b5-440">Isso será executado de forma assíncrona e, quando concluída, se um manipulador for fornecido no parâmetro ExecuteScriptCompletedHandler, seu método Invoke será chamado com o resultado da avaliação do JavaScript fornecido.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-440">This will execute asynchronously and when complete, if a handler is provided in the ExecuteScriptCompletedHandler parameter, its Invoke method will be called with the result of evaluating the provided JavaScript.</span></span> <span data-ttu-id="0d3b5-441">O valor do resultado é uma cadeia de caracteres codificada JSON.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-441">The result value is a JSON encoded string.</span></span> <span data-ttu-id="0d3b5-442">Se o resultado for indefinido, contiver um ciclo de referência ou não puder ser codificado em JSON, o valor NULL JSON será retornado como a cadeia de caracteres ' NULL '.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-442">If the result is undefined, contains a reference cycle, or otherwise cannot be encoded into JSON, the JSON null value will be returned as the string 'null'.</span></span> <span data-ttu-id="0d3b5-443">Observe que uma função sem valor de retorno explícito retorna indefinida.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-443">Note that a function that has no explicit return value returns undefined.</span></span> <span data-ttu-id="0d3b5-444">Se o script executado lançar uma exceção não tratada, o resultado também será ' nulo '.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-444">If the executed script throws an unhandled exception, then the result is also 'null'.</span></span> <span data-ttu-id="0d3b5-445">Esse método é aplicado de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-445">This method is applied asynchronously.</span></span> <span data-ttu-id="0d3b5-446">Se a chamada for feita enquanto o WebView estiver em um documento e ocorrer uma navegação após a chamada ser feita, mas antes que o JavaScript seja executado, o script não será executado e o manipulador será chamado com E_FAIL para o parâmetro errorCode.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-446">If the call is made while the webview is on one document, and a navigation occurs after the call is made but before the JavaScript is executed, then the script will not be executed and the handler will be called with E_FAIL for its errorCode parameter.</span></span> <span data-ttu-id="0d3b5-447">ExecuteScript funcionará mesmo se IsScriptEnabled estiver definido como FALSE.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-447">ExecuteScript will work even if IsScriptEnabled is set to FALSE.</span></span>

```cpp
// Prompt the user for some script and then execute it.
void ScriptComponent::InjectScript()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Inject Script",
        L"Enter script code:",
        L"Enter the JavaScript code to run in the webview.",
        L"window.getComputedStyle(document.body).backgroundColor");
    if (dialog.confirmed)
    {
        m_webView->ExecuteScript(dialog.input.c_str(),
            Callback<IWebView2ExecuteScriptCompletedHandler>(
                [](HRESULT error, PCWSTR result) -> HRESULT
        {
            if (error != S_OK) {
                ShowFailure(error, L"ExecuteScript failed");
            }
            MessageBox(nullptr, result, L"ExecuteScript Result", MB_OK);
            return S_OK;
        }).Get());
    }
}
```

#### <span data-ttu-id="0d3b5-448">CapturePreview</span><span class="sxs-lookup"><span data-stu-id="0d3b5-448">CapturePreview</span></span> 

<span data-ttu-id="0d3b5-449">Capture uma imagem do que o WebView está exibindo.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-449">Capture an image of what WebView is displaying.</span></span>

> <span data-ttu-id="0d3b5-450">Public HRESULT [CapturePreview](#capturepreview)([WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format) ImageFormat, IStream \* imageStream,[IWebView2CapturePreviewCompletedHandler](IWebView2CapturePreviewCompletedHandler.md) \* Handler)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-450">public HRESULT [CapturePreview](#capturepreview)([WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format) imageFormat,IStream \* imageStream,[IWebView2CapturePreviewCompletedHandler](IWebView2CapturePreviewCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="0d3b5-451">Especifique o formato da imagem com o parâmetro imageFormat.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-451">Specify the format of the image with the imageFormat parameter.</span></span> <span data-ttu-id="0d3b5-452">Os dados binários da imagem resultante são gravados no parâmetro imageStream fornecido.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-452">The resulting image binary data is written to the provided imageStream parameter.</span></span> <span data-ttu-id="0d3b5-453">Quando o CapturePreview termina de gravar no fluxo, o método Invoke no parâmetro do manipulador fornecido é chamado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-453">When CapturePreview finishes writing to the stream, the Invoke method on the provided handler parameter is called.</span></span>

```cpp
// Show the user a file selection dialog, then save a screenshot of the WebView
// to the selected file.
void FileComponent::SaveScreenshot()
{
    OPENFILENAME openFileName = {};
    openFileName.lStructSize = sizeof(openFileName);
    openFileName.hwndOwner = nullptr;
    openFileName.hInstance = nullptr;
    WCHAR fileName[MAX_PATH] = L"WebView2_Screenshot.png";
    openFileName.lpstrFile = fileName;
    openFileName.lpstrFilter = L"PNG File\0*.png\0";
    openFileName.nMaxFile = ARRAYSIZE(fileName);
    openFileName.Flags = OFN_OVERWRITEPROMPT;

    if (GetSaveFileName(&openFileName))
    {
        wil::com_ptr<IStream> stream;
        CHECK_FAILURE(SHCreateStreamOnFileEx(
            fileName, STGM_READWRITE | STGM_CREATE, FILE_ATTRIBUTE_NORMAL, TRUE, nullptr,
            &stream));

        HWND mainWindow = m_appWindow->GetMainWindow();

        CHECK_FAILURE(m_webView->CapturePreview(
            WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG, stream.get(),
            Callback<IWebView2CapturePreviewCompletedHandler>(
                [mainWindow](HRESULT error_code) -> HRESULT {
                    CHECK_FAILURE(error_code);

                    MessageBox(mainWindow, L"Preview Captured", L"Preview Captured", MB_OK);
                    return S_OK;
                })
                .Get()));
    }
}
```

#### <span data-ttu-id="0d3b5-454">Recarregar</span><span class="sxs-lookup"><span data-stu-id="0d3b5-454">Reload</span></span> 

<span data-ttu-id="0d3b5-455">Recarregar a página atual.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-455">Reload the current page.</span></span>

> <span data-ttu-id="0d3b5-456">HRESULT ( [recarregamento](#reload)) público</span><span class="sxs-lookup"><span data-stu-id="0d3b5-456">public HRESULT [Reload](#reload)()</span></span>

<span data-ttu-id="0d3b5-457">Isso é semelhante a navegar para o URI do documento de nível superior atual, incluindo todos os eventos de navegação que estão sendo acionados e como respeitar as entradas no cache HTTP.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-457">This is similar to navigating to the URI of current top level document including all navigation events firing and respecting any entries in the HTTP cache.</span></span> <span data-ttu-id="0d3b5-458">Mas o histórico de back/forward não será modificado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-458">But, the back/forward history will not be modified.</span></span>

#### <span data-ttu-id="0d3b5-459">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="0d3b5-459">get_Bounds</span></span> 

<span data-ttu-id="0d3b5-460">Os limites da WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-460">The webview bounds.</span></span>

> <span data-ttu-id="0d3b5-461">Associação Pública HRESULT [get_Bounds](#get_bounds)(Rect \*)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-461">public HRESULT [get_Bounds](#get_bounds)(RECT \* bounds)</span></span>

<span data-ttu-id="0d3b5-462">Os limites são relativos ao HWND pai.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-462">Bounds are relative to the parent HWND.</span></span> <span data-ttu-id="0d3b5-463">O aplicativo tem duas maneiras de posicionar um WebView:</span><span class="sxs-lookup"><span data-stu-id="0d3b5-463">The app has two ways it can position a WebView:</span></span>

1. <span data-ttu-id="0d3b5-464">Crie um HWND filho que seja o HWND pai do WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-464">Create a child HWND that is the WebView parent HWND.</span></span> <span data-ttu-id="0d3b5-465">Posicione esta janela onde o WebView deve estar.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-465">Position this window where the WebView should be.</span></span> <span data-ttu-id="0d3b5-466">Nesse caso, use (0, 0) para o canto superior esquerdo Bound's do WebView (o deslocamento).</span><span class="sxs-lookup"><span data-stu-id="0d3b5-466">In this case, use (0, 0) for the WebView's Bound's top left corner (the offset).</span></span>

1. <span data-ttu-id="0d3b5-467">Use a janela mais superior do aplicativo como o HWND pai do WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-467">Use the app's top most window as the WebView parent HWND.</span></span> <span data-ttu-id="0d3b5-468">Defina o Bound's canto superior esquerdo da WebView para que o WebView esteja posicionado corretamente no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-468">Set the WebView's Bound's top left corner so that the WebView is positioned correctly in the app.</span></span> <span data-ttu-id="0d3b5-469">Os valores do limite estão no espaço de coordenadas do host.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-469">The Bound's values are in the host's coordinate space.</span></span>

#### <span data-ttu-id="0d3b5-470">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="0d3b5-470">put_Bounds</span></span> 

<span data-ttu-id="0d3b5-471">Defina a propriedade Bounds.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-471">Set the Bounds property.</span></span>

> <span data-ttu-id="0d3b5-472">[put_Bounds](#put_bounds)público HRESULT (limites Rect)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-472">public HRESULT [put_Bounds](#put_bounds)(RECT bounds)</span></span>

```cpp
// Update the bounds of the WebView window to fit available space.
void ViewComponent::ResizeWebView()
{
    RECT desiredBounds = m_webViewBounds;
    desiredBounds.bottom = LONG(
        (m_webViewBounds.bottom - m_webViewBounds.top) * m_webViewRatio + m_webViewBounds.top);
    desiredBounds.right = LONG(
        (m_webViewBounds.right - m_webViewBounds.left) * m_webViewRatio + m_webViewBounds.left);

    m_webView->put_Bounds(desiredBounds);
}
```

#### <span data-ttu-id="0d3b5-473">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="0d3b5-473">get_ZoomFactor</span></span> 

<span data-ttu-id="0d3b5-474">O fator de zoom para a página atual no WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-474">The zoom factor for the current page in the WebView.</span></span>

> <span data-ttu-id="0d3b5-475">público HRESULT [get_ZoomFactor](#get_zoomfactor)(duplo \* ZoomFactor)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-475">public HRESULT [get_ZoomFactor](#get_zoomfactor)(double \* zoomFactor)</span></span>

<span data-ttu-id="0d3b5-476">O fator de zoom é mantido por site.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-476">The zoom factor is persisted per site.</span></span> <span data-ttu-id="0d3b5-477">Observe que a alteração do fator de zoom pode fazer com que o `window.innerWidth/innerHeight` layout da página seja alterado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-477">Note that changing zoom factor could cause `window.innerWidth/innerHeight` and page layout to change.</span></span> <span data-ttu-id="0d3b5-478">Quando a WebView navegar para uma página de um site diferente, o fator de zoom definido para a página anterior não será aplicado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-478">When WebView navigates to a page from a different site, the zoom factor set for the previous page will not be applied.</span></span> <span data-ttu-id="0d3b5-479">Se o aplicativo quiser definir o fator de zoom para uma determinada página, o primeiro local para fazer isso é no manipulador de eventos DocumentStateChanged.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-479">If the app wants to set the zoom factor for a certain page, the earliest place to do it is in the DocumentStateChanged event handler.</span></span> <span data-ttu-id="0d3b5-480">Observe que, se isso for o caso, poderá receber um evento ZoomFactorChanged para o fator de zoom persistente antes de receber o evento ZoomFactorChanged do fator de zoom especificado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-480">Note that if it does that, it might receive a ZoomFactorChanged event for the persisted zoom factor before receiving the ZoomFactorChanged event for the specified zoom factor.</span></span> <span data-ttu-id="0d3b5-481">Não é permitido especificar um zoomFactor menor ou igual a 0.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-481">Specifying a zoomFactor less than or equal to 0 is not allowed.</span></span> <span data-ttu-id="0d3b5-482">WebView também tem um intervalo de fator de zoom interno com suporte.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-482">WebView also has an internal supported zoom factor range.</span></span> <span data-ttu-id="0d3b5-483">Quando um fator de zoom especificado estiver fora desse intervalo, ele será normalizado para estar dentro do intervalo, e um evento ZoomFactorChanged será acionado para o fator de zoom aplicado real.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-483">When a specified zoom factor is out of that range, it will be normalized to be within the range, and a ZoomFactorChanged event will be fired for the real applied zoom factor.</span></span> <span data-ttu-id="0d3b5-484">Quando essa faixa de normalização acontece, a propriedade ZoomFactor relata o fator de zoom especificado durante a modificação anterior da propriedade ZoomFactor até que o evento ZoomFactorChanged seja recebido após o WebView se aplicar o fator de zoom normalizado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-484">When this range normalization happens, the ZoomFactor property will report the zoom factor specified during the previous modification of the ZoomFactor property until the ZoomFactorChanged event is received after webview applies the normalized zoom factor.</span></span>

#### <span data-ttu-id="0d3b5-485">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="0d3b5-485">put_ZoomFactor</span></span> 

<span data-ttu-id="0d3b5-486">Defina a propriedade ZoomFactor.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-486">Set the ZoomFactor property.</span></span>

> <span data-ttu-id="0d3b5-487">público HRESULT [put_ZoomFactor](#put_zoomfactor)(ZoomFactor duplo)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-487">public HRESULT [put_ZoomFactor](#put_zoomfactor)(double zoomFactor)</span></span>

#### <span data-ttu-id="0d3b5-488">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="0d3b5-488">get_IsVisible</span></span> 

<span data-ttu-id="0d3b5-489">A propriedade IsVisible Determina se deseja mostrar ou ocultar o WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-489">The IsVisible property determines whether to show or hide the webview.</span></span>

> <span data-ttu-id="0d3b5-490">[get_IsVisible](#get_isvisible)público HRESULT (bool \* IsVisible)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-490">public HRESULT [get_IsVisible](#get_isvisible)(BOOL \* isVisible)</span></span>

<span data-ttu-id="0d3b5-491">Se IsVisible estiver definido como false, o WebView será transparente e não será renderizado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-491">If IsVisible is set to false, the webview will be transparent and will not be rendered.</span></span> <span data-ttu-id="0d3b5-492">No entanto, isso não afetará a janela que contém o WebView (o parâmetro hWnd que foi passado para WebView).</span><span class="sxs-lookup"><span data-stu-id="0d3b5-492">However, this will not affect the window containing the webview (the HWND parameter that was passed to CreateWebView).</span></span> <span data-ttu-id="0d3b5-493">Se você quiser que essa janela desapareça também, chame o recurso de janela diretamente, além de modificar a propriedade IsVisible.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-493">If you want that window to disappear too, call ShowWindow on it directly in addition to modifying the IsVisible property.</span></span> <span data-ttu-id="0d3b5-494">A WebView como uma janela filho não obterá mensagens de janela quando a janela superior for minimizada ou restaurada.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-494">WebView as a child window won't get window messages when the top window is minimized or restored.</span></span> <span data-ttu-id="0d3b5-495">Por motivo de desempenho, o desenvolvedor deve definir a propriedade IsVisible do WebView como false quando a janela do aplicativo é minimizada e retomada como true quando a janela do aplicativo for restaurada.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-495">For performance reason, developer should set IsVisible property of the WebView to false when the app window is minimized and back to true when app window is restored.</span></span> <span data-ttu-id="0d3b5-496">A janela do aplicativo pode fazer isso ao manipular SC_MINIMIZE e SC_RESTORE comando ao receber WM_SYSCOMMAND mensagem.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-496">App window can do this by handling SC_MINIMIZE and SC_RESTORE command upon receiving WM_SYSCOMMAND message.</span></span>

```cpp
void ViewComponent::ToggleVisibility()
{
    BOOL visible;
    m_webView->get_IsVisible(&visible);
    m_isVisible = !visible;
    m_webView->put_IsVisible(m_isVisible);
}
```

#### <span data-ttu-id="0d3b5-497">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="0d3b5-497">put_IsVisible</span></span> 

<span data-ttu-id="0d3b5-498">Defina a propriedade IsVisible.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-498">Set the IsVisible property.</span></span>

> <span data-ttu-id="0d3b5-499">público HRESULT [put_IsVisible](#put_isvisible)(bool IsVisible)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-499">public HRESULT [put_IsVisible](#put_isvisible)(BOOL isVisible)</span></span>

```cpp
    if (message == WM_SYSCOMMAND)
    {
        if (wParam == SC_MINIMIZE)
        {
            // Hide the webview when the app window is minimized.
            m_webView->put_IsVisible(FALSE);
        }
        else if (wParam == SC_RESTORE)
        {
            // When the app window is restored, show the webview
            // (unless the user has toggle visibility off).
            if (m_isVisible)
            {
                m_webView->put_IsVisible(TRUE);
            }
        }
    }
```

#### <span data-ttu-id="0d3b5-500">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="0d3b5-500">PostWebMessageAsJson</span></span> 

<span data-ttu-id="0d3b5-501">Poste a WebMessage especificada no documento de nível superior neste [IWebView2WebView]().</span><span class="sxs-lookup"><span data-stu-id="0d3b5-501">Post the specified webMessage to the top level document in this [IWebView2WebView]().</span></span>

> <span data-ttu-id="0d3b5-502">Public HRESULT [PostWebMessageAsJson](#postwebmessageasjson)(LPCWSTR webMessageAsJson)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-502">public HRESULT [PostWebMessageAsJson](#postwebmessageasjson)(LPCWSTR webMessageAsJson)</span></span>

<span data-ttu-id="0d3b5-503">O evento Message da janela do documento de nível superior. Chrome. WebView será acionado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-503">The top level document's window.chrome.webview's message event fires.</span></span> <span data-ttu-id="0d3b5-504">O JavaScript nesse documento pode assinar e cancelar a assinatura do evento por meio do seguinte:</span><span class="sxs-lookup"><span data-stu-id="0d3b5-504">JavaScript in that document may subscribe and unsubscribe to the event via the following:</span></span> 

```cpp
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

 <span data-ttu-id="0d3b5-505">Os argumentos do evento é uma instância de `MessageEvent` .</span><span class="sxs-lookup"><span data-stu-id="0d3b5-505">The event args is an instance of `MessageEvent`.</span></span> <span data-ttu-id="0d3b5-506">A configuração IWebView2Settings:: IsWebMessageEnabled deve ser true ou esse método irá falhar com E_INVALIDARG.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-506">The IWebView2Settings::IsWebMessageEnabled setting must be true or this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="0d3b5-507">A propriedade data do ARG do evento é o parâmetro da cadeia de caracteres WebMessage analisado como uma cadeia de caracteres JSON em um objeto JavaScript.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-507">The event arg's data property is the webMessage string parameter parsed as a JSON string into a JavaScript object.</span></span> <span data-ttu-id="0d3b5-508">A propriedade de origem do ARG do evento é uma referência ao `window.chrome.webview` objeto.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-508">The event arg's source property is a reference to the `window.chrome.webview` object.</span></span> <span data-ttu-id="0d3b5-509">Consulte SetWebMessageReceivedEventHandler para obter informações sobre como enviar mensagens do documento HTML no WebView para o host.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-509">See SetWebMessageReceivedEventHandler for information on sending messages from the HTML document in the webview to the host.</span></span> <span data-ttu-id="0d3b5-510">Esta mensagem é enviada de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-510">This message is sent asynchronously.</span></span> <span data-ttu-id="0d3b5-511">Se ocorrer uma navegação antes que a mensagem seja postada na página, a mensagem não será enviada.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-511">If a navigation occurs before the message is posted to the page, then the message will not be sent.</span></span>

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<IWebView2WebMessageReceivedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->get_WebMessageAsString(&messageRaw));
        std::wstring message = messageRaw.get();

        if (message.compare(0, 13, L"SetTitleText ") == 0)
        {
            m_appWindow->SetTitleText(message.substr(13).c_str());
        }
        else if (message.compare(L"GetWindowBounds") == 0)
        {
            RECT bounds = m_appWindow->GetWindowBounds();
            std::wstring reply =
                L"{\"WindowBounds\":\"Left:" + std::to_wstring(bounds.left)
                + L"\\nTop:" + std::to_wstring(bounds.top)
                + L"\\nRight:" + std::to_wstring(bounds.right)
                + L"\\nBottom:" + std::to_wstring(bounds.bottom)
                + L"\"}";
            CHECK_FAILURE(sender->PostWebMessageAsJson(reply.c_str()));
        }
        return S_OK;
    }).Get(), &m_webMessageReceivedToken));
```

#### <span data-ttu-id="0d3b5-512">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="0d3b5-512">PostWebMessageAsString</span></span> 

<span data-ttu-id="0d3b5-513">Isso é um auxiliar para postar uma mensagem que é uma cadeia de caracteres simples em vez de uma representação JSON de cadeia de caracteres de um objeto JavaScript.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-513">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>

> <span data-ttu-id="0d3b5-514">Public HRESULT [PostWebMessageAsString](#postwebmessageasstring)(LPCWSTR webMessageAsString)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-514">public HRESULT [PostWebMessageAsString](#postwebmessageasstring)(LPCWSTR webMessageAsString)</span></span>

<span data-ttu-id="0d3b5-515">Isso se comporta exatamente da mesma maneira que PostWebMessageAsJson, mas a `window.chrome.webview` propriedade data do ARG (evento de mensagem) será uma cadeia de caracteres com o mesmo valor de webMessageAsString.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-515">This behaves in exactly the same manner as PostWebMessageAsJson but the `window.chrome.webview` message event arg's data property will be a string with the same value as webMessageAsString.</span></span> <span data-ttu-id="0d3b5-516">Use isso em vez de PostWebMessageAsJson se você quiser se comunicar por cadeias de caracteres simples em vez de objetos JSON.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-516">Use this instead of PostWebMessageAsJson if you want to communicate via simple strings rather than JSON objects.</span></span>

#### <span data-ttu-id="0d3b5-517">add_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="0d3b5-517">add_WebMessageReceived</span></span> 

<span data-ttu-id="0d3b5-518">Esse evento é acionado quando a configuração IsWebMessageEnabled é definida e o documento de nível superior das chamadas WebView `window.chrome.webview.postMessage` .</span><span class="sxs-lookup"><span data-stu-id="0d3b5-518">This event fires when the IsWebMessageEnabled setting is set and the top level document of the webview calls `window.chrome.webview.postMessage`.</span></span>

> <span data-ttu-id="0d3b5-519">[add_WebMessageReceived](#add_webmessagereceived)público HRESULT (manipulador[IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) \*, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-519">public HRESULT [add_WebMessageReceived](#add_webmessagereceived)([IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) \* handler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0d3b5-520">A função CreateMessage é `void postMessage(object)` onde o objeto é qualquer objeto compatível com a conversão JSON.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-520">The postMessage function is `void postMessage(object)` where object is any object supported by JSON conversion.</span></span>

```cpp
        window.chrome.webview.addEventListener('message', arg => {
            if ("SetColor" in arg.data) {
                document.getElementById("colorable").style.color = arg.data.SetColor;
            }
            if ("WindowBounds" in arg.data) {
                document.getElementById("window-bounds").value = arg.data.WindowBounds;
            }
        });

        function SetTitleText() {
            let titleText = document.getElementById("title-text");
            window.chrome.webview.postMessage(`SetTitleText ${titleText.value}`);
        }
        function GetWindowBounds() {
            window.chrome.webview.postMessage("GetWindowBounds");
        }
```

 <span data-ttu-id="0d3b5-521">Quando a "CreateMessage" é chamado, o conjunto de [IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) por meio desse método SetWebMessageReceivedEventHandler será invocado com o parâmetro de objeto da createmessagestring convertido em uma cadeia de caracteres JSON.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-521">When postMessage is called, the [IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) set via this SetWebMessageReceivedEventHandler method will be invoked with the postMessage's object parameter converted to a JSON string.</span></span>

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<IWebView2WebMessageReceivedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->get_WebMessageAsString(&messageRaw));
        std::wstring message = messageRaw.get();

        if (message.compare(0, 13, L"SetTitleText ") == 0)
        {
            m_appWindow->SetTitleText(message.substr(13).c_str());
        }
        else if (message.compare(L"GetWindowBounds") == 0)
        {
            RECT bounds = m_appWindow->GetWindowBounds();
            std::wstring reply =
                L"{\"WindowBounds\":\"Left:" + std::to_wstring(bounds.left)
                + L"\\nTop:" + std::to_wstring(bounds.top)
                + L"\\nRight:" + std::to_wstring(bounds.right)
                + L"\\nBottom:" + std::to_wstring(bounds.bottom)
                + L"\"}";
            CHECK_FAILURE(sender->PostWebMessageAsJson(reply.c_str()));
        }
        return S_OK;
    }).Get(), &m_webMessageReceivedToken));
```

#### <span data-ttu-id="0d3b5-522">remove_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="0d3b5-522">remove_WebMessageReceived</span></span> 

<span data-ttu-id="0d3b5-523">Remover um manipulador de eventos adicionado anteriormente com add_WebMessageReceived.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-523">Remove an event handler previously added with add_WebMessageReceived.</span></span>

> <span data-ttu-id="0d3b5-524">[remove_WebMessageReceived](#remove_webmessagereceived)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-524">public HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0d3b5-525">Fechar</span><span class="sxs-lookup"><span data-stu-id="0d3b5-525">Close</span></span> 

<span data-ttu-id="0d3b5-526">Fecha a WebView e limpa a instância do navegador subjacente.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-526">Closes the webview and cleans up the underlying browser instance.</span></span>

> <span data-ttu-id="0d3b5-527">público HRESULT [fechar](#close)()</span><span class="sxs-lookup"><span data-stu-id="0d3b5-527">public HRESULT [Close](#close)()</span></span>

<span data-ttu-id="0d3b5-528">A limpeza do navegador instace liberará os recursos que reabrirão o WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-528">Cleaning up the browser instace will release the resources powering the webview.</span></span> <span data-ttu-id="0d3b5-529">A instância do navegador será encerrada se não houver outros webviews que o usam.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-529">The browser instance will be shut down if there are no other webviews using it.</span></span>

<span data-ttu-id="0d3b5-530">Depois de chamar Close, todas as chamadas de método falharão e os manipuladores de eventos deixarão de ser acionados.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-530">After calling Close, all method calls will fail and event handlers will stop firing.</span></span> <span data-ttu-id="0d3b5-531">Especificamente, a WebView liberará suas referências a seus manipuladores de eventos quando Close for chamado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-531">Specifically, the WebView will release its references to its event handlers when Close is called.</span></span>

<span data-ttu-id="0d3b5-532">Fechar é chamado implicitamente quando o WebView perde sua referência final e é destruido.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-532">Close is implicitly called when the WebView loses its final reference and is destructed.</span></span> <span data-ttu-id="0d3b5-533">Mas é uma prática recomendada chamar o fechamento explicitamente para evitar qualquer ciclo acidental de referências entre o WebView e o código do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-533">But it is best practice to explicitly call Close to avoid any accidental cycle of references between the WebView and the app code.</span></span> <span data-ttu-id="0d3b5-534">Especificamente, se você capturar uma referência ao WebView em um manipulador de eventos, criará um ciclo de referência entre o WebView e o manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-534">Specifically, if you capture a reference to the WebView in an event handler you will create a reference cycle between the WebView and the event handler.</span></span> <span data-ttu-id="0d3b5-535">Fechar irá interromper esse ciclo liberando todos os manipuladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-535">Close will break this cycle by releasing all event handlers.</span></span> <span data-ttu-id="0d3b5-536">Mas para evitar essa situação, é recomendável fazer chamadas explícitas para fechar na WebView e não capturar uma referência para o WebView para garantir que o WebView possa ser limpo corretamente.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-536">But to avoid this situation it is best practice to both explicitly call Close on the WebView and to not capture a reference to the WebView to ensure the WebView can be cleaned up correctly.</span></span>

```cpp
// Close the WebView and deinitialize related state. This doesn't close the app window.
void AppWindow::CloseWebView()
{
    DeleteAllComponents();
    if (m_webView)
    {
        m_webView->Close();
        m_webView = nullptr;
    }
    m_webViewEnvironment = nullptr;
}
```

#### <span data-ttu-id="0d3b5-537">CallDevToolsProtocolMethod</span><span class="sxs-lookup"><span data-stu-id="0d3b5-537">CallDevToolsProtocolMethod</span></span> 

<span data-ttu-id="0d3b5-538">Chame um método DevToolsProtocol assíncrono.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-538">Call an asynchronous DevToolsProtocol method.</span></span>

> <span data-ttu-id="0d3b5-539">Public HRESULT [CallDevToolsProtocolMethod](#calldevtoolsprotocolmethod)(LPCWSTR METHODNAME, LPCWSTR ParametersAsJson,[IWebView2CallDevToolsProtocolMethodCompletedHandler](IWebView2CallDevToolsProtocolMethodCompletedHandler.md) \* Handler)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-539">public HRESULT [CallDevToolsProtocolMethod](#calldevtoolsprotocolmethod)(LPCWSTR methodName,LPCWSTR parametersAsJson,[IWebView2CallDevToolsProtocolMethodCompletedHandler](IWebView2CallDevToolsProtocolMethodCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="0d3b5-540">Consulte o [Visualizador de protocolo devtools](https://aka.ms/DevToolsProtocolDocs) para obter uma lista e a descrição dos métodos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-540">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available methods.</span></span> <span data-ttu-id="0d3b5-541">O parâmetro methodName é o nome completo do método no formato `{domain}.{method}` .</span><span class="sxs-lookup"><span data-stu-id="0d3b5-541">The methodName parameter is the full name of the method in the format `{domain}.{method}`.</span></span> <span data-ttu-id="0d3b5-542">O parâmetro parametersAsJson é uma cadeia de caracteres JSON formatada que contém os parâmetros para o método correspondente.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-542">The parametersAsJson parameter is a JSON formatted string containing the parameters for the corresponding method.</span></span> <span data-ttu-id="0d3b5-543">O método Invoke do manipulador será chamado quando o método for concluído de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-543">The handler's Invoke method will be called when the method asynchronously completes.</span></span> <span data-ttu-id="0d3b5-544">Invoke será chamado com o objeto Return do método como uma cadeia de caracteres JSON.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-544">Invoke will be called with the method's return object as a JSON string.</span></span>

```cpp
// Prompt the user for the name and parameters of a CDP method, then call it.
void ScriptComponent::CallCdpMethod()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Call CDP Method",
        L"CDP method name:",
        L"Enter the CDP method name to call, followed by a space,\r\n"
            L"followed by the parameters in JSON format.",
        L"Runtime.evaluate {\"expression\":\"alert(\\\"test\\\")\"}");
    if (dialog.confirmed)
    {
        size_t delimiterPos = dialog.input.find(L' ');
        std::wstring methodName = dialog.input.substr(0, delimiterPos);
        std::wstring methodParams =
            (delimiterPos < dialog.input.size()
                ? dialog.input.substr(delimiterPos + 1)
                : L"{}");

        m_webView->CallDevToolsProtocolMethod(
            methodName.c_str(),
            methodParams.c_str(),
            Callback<IWebView2CallDevToolsProtocolMethodCompletedHandler>(
                [](HRESULT error, PCWSTR resultJson) -> HRESULT
                {
                    MessageBox(nullptr, resultJson, L"CDP Method Result", MB_OK);
                    return S_OK;
                }).Get());
    }
}
```

#### <span data-ttu-id="0d3b5-545">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="0d3b5-545">add_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="0d3b5-546">Assine um evento DevToolsProtocol.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-546">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="0d3b5-547">Public HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)(LPCWSTR EventName,[IWebView2DevToolsProtocolEventReceivedEventHandler](IWebView2DevToolsProtocolEventReceivedEventHandler.md) \* Handler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-547">public HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)(LPCWSTR eventName,[IWebView2DevToolsProtocolEventReceivedEventHandler](IWebView2DevToolsProtocolEventReceivedEventHandler.md) \* handler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0d3b5-548">Consulte o [Visualizador de protocolo devtools](https://aka.ms/DevToolsProtocolDocs) para obter uma lista e a descrição de eventos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-548">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available events.</span></span> <span data-ttu-id="0d3b5-549">O parâmetro EventName é o nome completo do evento no formato `{domain}.{event}` .</span><span class="sxs-lookup"><span data-stu-id="0d3b5-549">The eventName parameter is the full name of the event in the format `{domain}.{event}`.</span></span> <span data-ttu-id="0d3b5-550">O método Invoke do manipulador será chamado sempre que o evento DevToolsProtocol correspondente for acionado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-550">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="0d3b5-551">Invoke será chamado com o objeto do evento args que contém o objeto Parameter do evento CDP como uma cadeia de caracteres JSON.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-551">Invoke will be called with the an event args object containing the CDP event's parameter object as a JSON string.</span></span>

```cpp
// Prompt the user to name a CDP event, and then subscribe to that event.
void ScriptComponent::SubscribeToCdpEvent()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Subscribe to CDP Event",
        L"CDP event name:",
        L"Enter the name of the CDP event to subscribe to.\r\n"
            L"You may also have to call the \"enable\" method of the\r\n"
            L"event's domain to receive events (for example \"Log.enable\").\r\n",
        L"Log.entryAdded");
    if (dialog.confirmed)
    {
        std::wstring eventName = dialog.input;
        // If we are already subscribed to this event, unsubscribe first.
        auto preexistingToken = m_devToolsProtocolEventReceivedTokenMap.find(eventName);
        if (preexistingToken != m_devToolsProtocolEventReceivedTokenMap.end())
        {
            CHECK_FAILURE(m_webView->remove_DevToolsProtocolEventReceived(
                eventName.c_str(),
                preexistingToken->second));
        }

        CHECK_FAILURE(m_webView->add_DevToolsProtocolEventReceived(
            eventName.c_str(),
            Callback<IWebView2DevToolsProtocolEventReceivedEventHandler>(
                [eventName](IWebView2WebView* sender,
                            IWebView2DevToolsProtocolEventReceivedEventArgs* args)
                -> HRESULT
        {
            wil::unique_cotaskmem_string parameterObjectAsJson;
            CHECK_FAILURE(args->get_ParameterObjectAsJson(&parameterObjectAsJson));
            MessageBox(nullptr, parameterObjectAsJson.get(),
                       (L"CDP Event Fired: " + eventName).c_str(), MB_OK);
            return S_OK;
        }).Get(), &m_devToolsProtocolEventReceivedTokenMap[eventName]));
    }
}
```

#### <span data-ttu-id="0d3b5-552">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="0d3b5-552">remove_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="0d3b5-553">Remover um manipulador de eventos adicionado anteriormente com add_DevToolsProtocolEventReceived.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-553">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>

> <span data-ttu-id="0d3b5-554">Public HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)(LPCWSTR EventName, EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-554">public HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)(LPCWSTR eventName,EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0d3b5-555">get_BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="0d3b5-555">get_BrowserProcessId</span></span> 

<span data-ttu-id="0d3b5-556">A ID do processo do navegador que hospeda o WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-556">The process id of the browser process that hosts the WebView.</span></span>

> <span data-ttu-id="0d3b5-557">[get_BrowserProcessId](#get_browserprocessid)público HRESULT (valor UINT32 \*)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-557">public HRESULT [get_BrowserProcessId](#get_browserprocessid)(UINT32 \* value)</span></span>

#### <span data-ttu-id="0d3b5-558">get_CanGoBack</span><span class="sxs-lookup"><span data-stu-id="0d3b5-558">get_CanGoBack</span></span> 

<span data-ttu-id="0d3b5-559">Pode navegar pelo WebView para a página anterior no histórico de navegação.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-559">Can navigate the webview to the previous page in the navigation history.</span></span>

> <span data-ttu-id="0d3b5-560">[get_CanGoBack](#get_cangoback)público HRESULT (bool \* CanGoBack)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-560">public HRESULT [get_CanGoBack](#get_cangoback)(BOOL \* canGoBack)</span></span>

<span data-ttu-id="0d3b5-561">get_CanGoBack alterar o valor com o evento DocumentStateChanged.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-561">get_CanGoBack change value with the DocumentStateChanged event.</span></span>

#### <span data-ttu-id="0d3b5-562">get_CanGoForward</span><span class="sxs-lookup"><span data-stu-id="0d3b5-562">get_CanGoForward</span></span> 

<span data-ttu-id="0d3b5-563">Pode navegar pelo WebView para a próxima página no histórico de navegação.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-563">Can navigate the webview to the next page in the navigation history.</span></span>

> <span data-ttu-id="0d3b5-564">[get_CanGoForward](#get_cangoforward)público HRESULT (bool \* CanGoForward)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-564">public HRESULT [get_CanGoForward](#get_cangoforward)(BOOL \* canGoForward)</span></span>

<span data-ttu-id="0d3b5-565">get_CanGoForward alterar o valor com o evento DocumentStateChanged.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-565">get_CanGoForward change value with the DocumentStateChanged event.</span></span>

#### <span data-ttu-id="0d3b5-566">GoBack</span><span class="sxs-lookup"><span data-stu-id="0d3b5-566">GoBack</span></span> 

<span data-ttu-id="0d3b5-567">Navega o WebView para a página anterior no histórico de navegação.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-567">Navigates the webview to the previous page in the navigation history.</span></span>

> <span data-ttu-id="0d3b5-568">público HRESULT [GoBack](#goback)()</span><span class="sxs-lookup"><span data-stu-id="0d3b5-568">public HRESULT [GoBack](#goback)()</span></span>

#### <span data-ttu-id="0d3b5-569">GoForward</span><span class="sxs-lookup"><span data-stu-id="0d3b5-569">GoForward</span></span> 

<span data-ttu-id="0d3b5-570">Navega o WebView para a próxima página no histórico de navegação.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-570">Navigates the webview to the next page in the navigation history.</span></span>

> <span data-ttu-id="0d3b5-571">Public HRESULT [GoForward](#goforward)()</span><span class="sxs-lookup"><span data-stu-id="0d3b5-571">public HRESULT [GoForward](#goforward)()</span></span>

#### <span data-ttu-id="0d3b5-572">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span><span class="sxs-lookup"><span data-stu-id="0d3b5-572">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span></span> 

<span data-ttu-id="0d3b5-573">Formato de imagem usado pelo método [IWebView2WebView:: CapturePreview](#capturepreview) .</span><span class="sxs-lookup"><span data-stu-id="0d3b5-573">Image format used by the [IWebView2WebView::CapturePreview](#capturepreview) method.</span></span>

> <span data-ttu-id="0d3b5-574">Enumeração [WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-574">enum [WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format)</span></span>

 <span data-ttu-id="0d3b5-575">Valores</span><span class="sxs-lookup"><span data-stu-id="0d3b5-575">Values</span></span>                         | <span data-ttu-id="0d3b5-576">Descrições</span><span class="sxs-lookup"><span data-stu-id="0d3b5-576">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="0d3b5-577">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG</span><span class="sxs-lookup"><span data-stu-id="0d3b5-577">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG</span></span>            | <span data-ttu-id="0d3b5-578">Formato de imagem PNG.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-578">PNG image format.</span></span>
<span data-ttu-id="0d3b5-579">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG</span><span class="sxs-lookup"><span data-stu-id="0d3b5-579">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG</span></span>            | <span data-ttu-id="0d3b5-580">Formato de imagem JPEG.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-580">JPEG image format.</span></span>

#### <span data-ttu-id="0d3b5-581">WEBVIEW2_SCRIPT_DIALOG_KIND</span><span class="sxs-lookup"><span data-stu-id="0d3b5-581">WEBVIEW2_SCRIPT_DIALOG_KIND</span></span> 

<span data-ttu-id="0d3b5-582">Tipo de caixa de diálogo JavaScript usada na interface [IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) .</span><span class="sxs-lookup"><span data-stu-id="0d3b5-582">Kind of JavaScript dialog used in the [IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) interface.</span></span>

> <span data-ttu-id="0d3b5-583">Enumeração [WEBVIEW2_SCRIPT_DIALOG_KIND](#webview2_script_dialog_kind)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-583">enum [WEBVIEW2_SCRIPT_DIALOG_KIND](#webview2_script_dialog_kind)</span></span>

 <span data-ttu-id="0d3b5-584">Valores</span><span class="sxs-lookup"><span data-stu-id="0d3b5-584">Values</span></span>                         | <span data-ttu-id="0d3b5-585">Descrições</span><span class="sxs-lookup"><span data-stu-id="0d3b5-585">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="0d3b5-586">WEBVIEW2_SCRIPT_DIALOG_KIND_ALERT</span><span class="sxs-lookup"><span data-stu-id="0d3b5-586">WEBVIEW2_SCRIPT_DIALOG_KIND_ALERT</span></span>            | <span data-ttu-id="0d3b5-587">Uma caixa de diálogo chamada por meio da função JavaScript Window. Alert.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-587">A dialog invoked via the window.alert JavaScript function.</span></span>
<span data-ttu-id="0d3b5-588">WEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM</span><span class="sxs-lookup"><span data-stu-id="0d3b5-588">WEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM</span></span>            | <span data-ttu-id="0d3b5-589">Uma caixa de diálogo invocada pela janela. confirmar a função JavaScript.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-589">A dialog invoked via the window.confirm JavaScript function.</span></span>
<span data-ttu-id="0d3b5-590">WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT</span><span class="sxs-lookup"><span data-stu-id="0d3b5-590">WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT</span></span>            | <span data-ttu-id="0d3b5-591">Uma caixa de diálogo chamada por meio da função de JavaScript Window. prompt.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-591">A dialog invoked via the window.prompt JavaScript function.</span></span>

#### <span data-ttu-id="0d3b5-592">WEBVIEW2_PROCESS_FAILED_KIND</span><span class="sxs-lookup"><span data-stu-id="0d3b5-592">WEBVIEW2_PROCESS_FAILED_KIND</span></span> 

<span data-ttu-id="0d3b5-593">Tipo de falha de processo usada na interface [IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) .</span><span class="sxs-lookup"><span data-stu-id="0d3b5-593">Kind of process failure used in the [IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) interface.</span></span>

> <span data-ttu-id="0d3b5-594">Enumeração [WEBVIEW2_PROCESS_FAILED_KIND](#webview2_process_failed_kind)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-594">enum [WEBVIEW2_PROCESS_FAILED_KIND](#webview2_process_failed_kind)</span></span>

 <span data-ttu-id="0d3b5-595">Valores</span><span class="sxs-lookup"><span data-stu-id="0d3b5-595">Values</span></span>                         | <span data-ttu-id="0d3b5-596">Descrições</span><span class="sxs-lookup"><span data-stu-id="0d3b5-596">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="0d3b5-597">WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED</span><span class="sxs-lookup"><span data-stu-id="0d3b5-597">WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED</span></span>            | <span data-ttu-id="0d3b5-598">Indica que o processo do navegador foi encerrado inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-598">Indicates the browser process terminated unexpectedly.</span></span>
<span data-ttu-id="0d3b5-599">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED</span><span class="sxs-lookup"><span data-stu-id="0d3b5-599">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED</span></span>            | <span data-ttu-id="0d3b5-600">Indica que o processo de renderização terminou inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-600">Indicates the render process terminated unexpectedly.</span></span>
<span data-ttu-id="0d3b5-601">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE</span><span class="sxs-lookup"><span data-stu-id="0d3b5-601">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE</span></span>            | <span data-ttu-id="0d3b5-602">Indica que o processo de renderização se torna não responsivo.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-602">Indicates the render process becomes unresponsive.</span></span>

#### <span data-ttu-id="0d3b5-603">WEBVIEW2_PERMISSION_TYPE</span><span class="sxs-lookup"><span data-stu-id="0d3b5-603">WEBVIEW2_PERMISSION_TYPE</span></span> 

<span data-ttu-id="0d3b5-604">O tipo de uma solicitação de permissão.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-604">The type of a permission request.</span></span>

> <span data-ttu-id="0d3b5-605">Enumeração [WEBVIEW2_PERMISSION_TYPE](#webview2_permission_type)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-605">enum [WEBVIEW2_PERMISSION_TYPE](#webview2_permission_type)</span></span>

 <span data-ttu-id="0d3b5-606">Valores</span><span class="sxs-lookup"><span data-stu-id="0d3b5-606">Values</span></span>                         | <span data-ttu-id="0d3b5-607">Descrições</span><span class="sxs-lookup"><span data-stu-id="0d3b5-607">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="0d3b5-608">WEBVIEW2_PERMISSION_TYPE_UNKNOWN_PERMISSION</span><span class="sxs-lookup"><span data-stu-id="0d3b5-608">WEBVIEW2_PERMISSION_TYPE_UNKNOWN_PERMISSION</span></span>            | <span data-ttu-id="0d3b5-609">Permissões desconhecidas.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-609">Unknown permission.</span></span>
<span data-ttu-id="0d3b5-610">WEBVIEW2_PERMISSION_TYPE_MICROPHONE</span><span class="sxs-lookup"><span data-stu-id="0d3b5-610">WEBVIEW2_PERMISSION_TYPE_MICROPHONE</span></span>            | <span data-ttu-id="0d3b5-611">Permissão para capturar o áudio.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-611">Permission to capture audio.</span></span>
<span data-ttu-id="0d3b5-612">WEBVIEW2_PERMISSION_TYPE_CAMERA</span><span class="sxs-lookup"><span data-stu-id="0d3b5-612">WEBVIEW2_PERMISSION_TYPE_CAMERA</span></span>            | <span data-ttu-id="0d3b5-613">Permissão para capturar vídeo.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-613">Permission to capture video.</span></span>
<span data-ttu-id="0d3b5-614">WEBVIEW2_PERMISSION_TYPE_GEOLOCATION</span><span class="sxs-lookup"><span data-stu-id="0d3b5-614">WEBVIEW2_PERMISSION_TYPE_GEOLOCATION</span></span>            | <span data-ttu-id="0d3b5-615">Permissão para acessar a localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-615">Permission to access geolocation.</span></span>
<span data-ttu-id="0d3b5-616">WEBVIEW2_PERMISSION_TYPE_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="0d3b5-616">WEBVIEW2_PERMISSION_TYPE_NOTIFICATIONS</span></span>            | <span data-ttu-id="0d3b5-617">Permissão para enviar notificações da Web.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-617">Permission to send web notifications.</span></span>
<span data-ttu-id="0d3b5-618">WEBVIEW2_PERMISSION_TYPE_OTHER_SENSORS</span><span class="sxs-lookup"><span data-stu-id="0d3b5-618">WEBVIEW2_PERMISSION_TYPE_OTHER_SENSORS</span></span>            | <span data-ttu-id="0d3b5-619">Permissão para acessar o sensor genérico.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-619">Permission to access generic sensor.</span></span>
<span data-ttu-id="0d3b5-620">WEBVIEW2_PERMISSION_TYPE_CLIPBOARD_READ</span><span class="sxs-lookup"><span data-stu-id="0d3b5-620">WEBVIEW2_PERMISSION_TYPE_CLIPBOARD_READ</span></span>            | <span data-ttu-id="0d3b5-621">Permissão para ler a área de transferência do sistema sem um gesto do usuário.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-621">Permission to read system clipboard without a user gesture.</span></span>

#### <span data-ttu-id="0d3b5-622">WEBVIEW2_PERMISSION_STATE</span><span class="sxs-lookup"><span data-stu-id="0d3b5-622">WEBVIEW2_PERMISSION_STATE</span></span> 

<span data-ttu-id="0d3b5-623">Resposta a uma solicitação de permissão.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-623">Response to a permission request.</span></span>

> <span data-ttu-id="0d3b5-624">Enumeração [WEBVIEW2_PERMISSION_STATE](#webview2_permission_state)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-624">enum [WEBVIEW2_PERMISSION_STATE](#webview2_permission_state)</span></span>

 <span data-ttu-id="0d3b5-625">Valores</span><span class="sxs-lookup"><span data-stu-id="0d3b5-625">Values</span></span>                         | <span data-ttu-id="0d3b5-626">Descrições</span><span class="sxs-lookup"><span data-stu-id="0d3b5-626">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="0d3b5-627">WEBVIEW2_PERMISSION_STATE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="0d3b5-627">WEBVIEW2_PERMISSION_STATE_DEFAULT</span></span>            | <span data-ttu-id="0d3b5-628">Use o comportamento padrão do navegador, que normalmente solicita aos usuários a decisão.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-628">Use default browser behavior, which normally prompt users for decision.</span></span>
<span data-ttu-id="0d3b5-629">WEBVIEW2_PERMISSION_STATE_ALLOW</span><span class="sxs-lookup"><span data-stu-id="0d3b5-629">WEBVIEW2_PERMISSION_STATE_ALLOW</span></span>            | <span data-ttu-id="0d3b5-630">Conceder a solicitação de permissão.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-630">Grant the permission request.</span></span>
<span data-ttu-id="0d3b5-631">WEBVIEW2_PERMISSION_STATE_DENY</span><span class="sxs-lookup"><span data-stu-id="0d3b5-631">WEBVIEW2_PERMISSION_STATE_DENY</span></span>            | <span data-ttu-id="0d3b5-632">Negue a solicitação de permissão.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-632">Deny the permission request.</span></span>

#### <span data-ttu-id="0d3b5-633">WEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="0d3b5-633">WEBVIEW2_MOVE_FOCUS_REASON</span></span> 

<span data-ttu-id="0d3b5-634">Motivo para mover o foco.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-634">Reason for moving focus.</span></span>

> <span data-ttu-id="0d3b5-635">Enumeração [WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-635">enum [WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason)</span></span>

 <span data-ttu-id="0d3b5-636">Valores</span><span class="sxs-lookup"><span data-stu-id="0d3b5-636">Values</span></span>                         | <span data-ttu-id="0d3b5-637">Descrições</span><span class="sxs-lookup"><span data-stu-id="0d3b5-637">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="0d3b5-638">WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span><span class="sxs-lookup"><span data-stu-id="0d3b5-638">WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span></span>            | <span data-ttu-id="0d3b5-639">Configuração de código focalizada no WebView.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-639">Code setting focus into WebView.</span></span>
<span data-ttu-id="0d3b5-640">WEBVIEW2_MOVE_FOCUS_REASON_NEXT</span><span class="sxs-lookup"><span data-stu-id="0d3b5-640">WEBVIEW2_MOVE_FOCUS_REASON_NEXT</span></span>            | <span data-ttu-id="0d3b5-641">Movendo o foco devido à guia passagem para frente.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-641">Moving focus due to Tab traversal forward.</span></span>
<span data-ttu-id="0d3b5-642">WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span><span class="sxs-lookup"><span data-stu-id="0d3b5-642">WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span></span>            | <span data-ttu-id="0d3b5-643">Movendo o foco devido a Tabulação de passagem para trás.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-643">Moving focus due to Tab traversal backward.</span></span>

#### <span data-ttu-id="0d3b5-644">WEBVIEW2_WEB_ERROR_STATUS</span><span class="sxs-lookup"><span data-stu-id="0d3b5-644">WEBVIEW2_WEB_ERROR_STATUS</span></span> 

<span data-ttu-id="0d3b5-645">Valores de status de erro para navegações na Web.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-645">Error status values for web navigations.</span></span>

> <span data-ttu-id="0d3b5-646">Enumeração [WEBVIEW2_WEB_ERROR_STATUS](#webview2_web_error_status)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-646">enum [WEBVIEW2_WEB_ERROR_STATUS](#webview2_web_error_status)</span></span>

 <span data-ttu-id="0d3b5-647">Valores</span><span class="sxs-lookup"><span data-stu-id="0d3b5-647">Values</span></span>                         | <span data-ttu-id="0d3b5-648">Descrições</span><span class="sxs-lookup"><span data-stu-id="0d3b5-648">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="0d3b5-649">WEBVIEW2_WEB_ERROR_STATUS_UNKNOWN</span><span class="sxs-lookup"><span data-stu-id="0d3b5-649">WEBVIEW2_WEB_ERROR_STATUS_UNKNOWN</span></span>            | <span data-ttu-id="0d3b5-650">Ocorreu um erro desconhecido.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-650">An unknown error occurred.</span></span>
<span data-ttu-id="0d3b5-651">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT</span><span class="sxs-lookup"><span data-stu-id="0d3b5-651">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT</span></span>            | <span data-ttu-id="0d3b5-652">O nome comum do certificado SSL não corresponde ao endereço Web.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-652">The SSL certificate common name does not match the web address.</span></span>
<span data-ttu-id="0d3b5-653">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="0d3b5-653">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED</span></span>            | <span data-ttu-id="0d3b5-654">O certificado SSL venceu.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-654">The SSL certificate has expired.</span></span>
<span data-ttu-id="0d3b5-655">WEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS</span><span class="sxs-lookup"><span data-stu-id="0d3b5-655">WEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS</span></span>            | <span data-ttu-id="0d3b5-656">O certificado do cliente SSL contém erros.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-656">The SSL client certificate contains errors.</span></span>
<span data-ttu-id="0d3b5-657">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED</span><span class="sxs-lookup"><span data-stu-id="0d3b5-657">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED</span></span>            | <span data-ttu-id="0d3b5-658">A revogação do certificado SSL foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-658">The SSL certificate has been revoked.</span></span>
<span data-ttu-id="0d3b5-659">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID</span><span class="sxs-lookup"><span data-stu-id="0d3b5-659">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID</span></span>            | <span data-ttu-id="0d3b5-660">O certificado SSL é inválido.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-660">The SSL certificate is invalid.</span></span>
<span data-ttu-id="0d3b5-661">WEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="0d3b5-661">WEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE</span></span>            | <span data-ttu-id="0d3b5-662">Não é possível acessar o host.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-662">The host is unreachable.</span></span>
<span data-ttu-id="0d3b5-663">WEBVIEW2_WEB_ERROR_STATUS_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0d3b5-663">WEBVIEW2_WEB_ERROR_STATUS_TIMEOUT</span></span>            | <span data-ttu-id="0d3b5-664">A conexão expirou.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-664">The connection has timed out.</span></span>
<span data-ttu-id="0d3b5-665">WEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE</span><span class="sxs-lookup"><span data-stu-id="0d3b5-665">WEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE</span></span>            | <span data-ttu-id="0d3b5-666">O servidor retornou uma resposta inválida ou não reconhecida.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-666">The server returned an invalid or unrecognized response.</span></span>
<span data-ttu-id="0d3b5-667">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED</span><span class="sxs-lookup"><span data-stu-id="0d3b5-667">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED</span></span>            | <span data-ttu-id="0d3b5-668">A conexão foi anulada.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-668">The connection was aborted.</span></span>
<span data-ttu-id="0d3b5-669">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET</span><span class="sxs-lookup"><span data-stu-id="0d3b5-669">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET</span></span>            | <span data-ttu-id="0d3b5-670">A conexão foi redefinida.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-670">The connection was reset.</span></span>
<span data-ttu-id="0d3b5-671">WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED</span><span class="sxs-lookup"><span data-stu-id="0d3b5-671">WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED</span></span>            | <span data-ttu-id="0d3b5-672">A conexão à Internet foi perdida.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-672">The Internet connection has been lost.</span></span>
<span data-ttu-id="0d3b5-673">WEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT</span><span class="sxs-lookup"><span data-stu-id="0d3b5-673">WEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT</span></span>            | <span data-ttu-id="0d3b5-674">Não é possível se conectar ao destino.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-674">Cannot connect to destination.</span></span>
<span data-ttu-id="0d3b5-675">WEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="0d3b5-675">WEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED</span></span>            | <span data-ttu-id="0d3b5-676">Não foi possível resolver o nome de host fornecido.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-676">Could not resolve provided host name.</span></span>
<span data-ttu-id="0d3b5-677">WEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED</span><span class="sxs-lookup"><span data-stu-id="0d3b5-677">WEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED</span></span>            | <span data-ttu-id="0d3b5-678">A operação foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-678">The operation was canceled.</span></span>
<span data-ttu-id="0d3b5-679">WEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED</span><span class="sxs-lookup"><span data-stu-id="0d3b5-679">WEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED</span></span>            | <span data-ttu-id="0d3b5-680">Falha no redirecionamento de solicitação.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-680">The request redirect failed.</span></span>
<span data-ttu-id="0d3b5-681">WEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR</span><span class="sxs-lookup"><span data-stu-id="0d3b5-681">WEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR</span></span>            | <span data-ttu-id="0d3b5-682">Ocorreu um erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-682">An unexpected error occurred.</span></span>

#### <span data-ttu-id="0d3b5-683">WEBVIEW2_WEB_RESOURCE_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="0d3b5-683">WEBVIEW2_WEB_RESOURCE_CONTEXT</span></span> 

<span data-ttu-id="0d3b5-684">Enumeração para contextos de solicitação de recurso da Web.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-684">Enum for web resource request contexts.</span></span>

> <span data-ttu-id="0d3b5-685">Enumeração [WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context)</span><span class="sxs-lookup"><span data-stu-id="0d3b5-685">enum [WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context)</span></span>

 <span data-ttu-id="0d3b5-686">Valores</span><span class="sxs-lookup"><span data-stu-id="0d3b5-686">Values</span></span>                         | <span data-ttu-id="0d3b5-687">Descrições</span><span class="sxs-lookup"><span data-stu-id="0d3b5-687">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="0d3b5-688">WEBVIEW2_WEB_RESOURCE_CONTEXT_ALL</span><span class="sxs-lookup"><span data-stu-id="0d3b5-688">WEBVIEW2_WEB_RESOURCE_CONTEXT_ALL</span></span>            | <span data-ttu-id="0d3b5-689">Todos os recursos.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-689">All resources.</span></span>
<span data-ttu-id="0d3b5-690">WEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT</span><span class="sxs-lookup"><span data-stu-id="0d3b5-690">WEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT</span></span>            | <span data-ttu-id="0d3b5-691">Recursos de documento.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-691">Document resources.</span></span>
<span data-ttu-id="0d3b5-692">WEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET</span><span class="sxs-lookup"><span data-stu-id="0d3b5-692">WEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET</span></span>            | <span data-ttu-id="0d3b5-693">Recursos CSS.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-693">CSS resources.</span></span>
<span data-ttu-id="0d3b5-694">WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE</span><span class="sxs-lookup"><span data-stu-id="0d3b5-694">WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE</span></span>            | <span data-ttu-id="0d3b5-695">Recursos de imagem.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-695">Image resources.</span></span>
<span data-ttu-id="0d3b5-696">WEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA</span><span class="sxs-lookup"><span data-stu-id="0d3b5-696">WEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA</span></span>            | <span data-ttu-id="0d3b5-697">Outros recursos de mídia, como vídeos.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-697">Other media resources such as videos.</span></span>
<span data-ttu-id="0d3b5-698">WEBVIEW2_WEB_RESOURCE_CONTEXT_FONT</span><span class="sxs-lookup"><span data-stu-id="0d3b5-698">WEBVIEW2_WEB_RESOURCE_CONTEXT_FONT</span></span>            | <span data-ttu-id="0d3b5-699">Recursos de fonte.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-699">Font resources.</span></span>
<span data-ttu-id="0d3b5-700">WEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT</span><span class="sxs-lookup"><span data-stu-id="0d3b5-700">WEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT</span></span>            | <span data-ttu-id="0d3b5-701">Recursos de script.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-701">Script resources.</span></span>
<span data-ttu-id="0d3b5-702">WEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST</span><span class="sxs-lookup"><span data-stu-id="0d3b5-702">WEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST</span></span>            | <span data-ttu-id="0d3b5-703">Solicitações HTTP XML.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-703">XML HTTP requests.</span></span>
<span data-ttu-id="0d3b5-704">WEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH</span><span class="sxs-lookup"><span data-stu-id="0d3b5-704">WEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH</span></span>            | <span data-ttu-id="0d3b5-705">Busque a comunicação da API.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-705">Fetch API communication.</span></span>
<span data-ttu-id="0d3b5-706">WEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK</span><span class="sxs-lookup"><span data-stu-id="0d3b5-706">WEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK</span></span>            | <span data-ttu-id="0d3b5-707">Recursos do texttrack.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-707">TextTrack resources.</span></span>
<span data-ttu-id="0d3b5-708">WEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE</span><span class="sxs-lookup"><span data-stu-id="0d3b5-708">WEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE</span></span>            | 
<span data-ttu-id="0d3b5-709">WEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET</span><span class="sxs-lookup"><span data-stu-id="0d3b5-709">WEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET</span></span>            | 
<span data-ttu-id="0d3b5-710">WEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST</span><span class="sxs-lookup"><span data-stu-id="0d3b5-710">WEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST</span></span>            | 
<span data-ttu-id="0d3b5-711">WEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE</span><span class="sxs-lookup"><span data-stu-id="0d3b5-711">WEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE</span></span>            | 
<span data-ttu-id="0d3b5-712">WEBVIEW2_WEB_RESOURCE_CONTEXT_PING</span><span class="sxs-lookup"><span data-stu-id="0d3b5-712">WEBVIEW2_WEB_RESOURCE_CONTEXT_PING</span></span>            | 
<span data-ttu-id="0d3b5-713">WEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT</span><span class="sxs-lookup"><span data-stu-id="0d3b5-713">WEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT</span></span>            | 
<span data-ttu-id="0d3b5-714">WEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER</span><span class="sxs-lookup"><span data-stu-id="0d3b5-714">WEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER</span></span>            | <span data-ttu-id="0d3b5-715">Outros recursos.</span><span class="sxs-lookup"><span data-stu-id="0d3b5-715">Other resources.</span></span>