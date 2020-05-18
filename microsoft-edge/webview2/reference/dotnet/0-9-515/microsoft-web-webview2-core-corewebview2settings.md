---
description: Hospedar conteúdo da Web em seu aplicativo Win32 com o controle WebView2 do Microsoft Edge
title: Microsoft Edge WebView2 para aplicativos Win32
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, webview2, WebView, aplicativos Win32, Win32, Edge, ICoreWebView2, ICoreWebView2Controller, controle do navegador, HTML Edge
ms.openlocfilehash: 519ef71db87d49aaf5a8a80970ff0cda61dfebbf
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652441"
---
# <span data-ttu-id="10f81-104">Classe Microsoft. Web. WebView2. Core. CoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="10f81-104">Microsoft.Web.WebView2.Core.CoreWebView2Settings class</span></span> 

<span data-ttu-id="10f81-105">Namespace: Microsoft. Web. WebView2. Core </span><span class="sxs-lookup"><span data-stu-id="10f81-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="10f81-106">Assembly: Microsoft. Web. WebView2. Core. dll</span><span class="sxs-lookup"><span data-stu-id="10f81-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="10f81-107">Define propriedades que habilitam, desabilitam ou modificam recursos do WebView.</span><span class="sxs-lookup"><span data-stu-id="10f81-107">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="10f81-108">Resumo</span><span class="sxs-lookup"><span data-stu-id="10f81-108">Summary</span></span>

 <span data-ttu-id="10f81-109">Parte</span><span class="sxs-lookup"><span data-stu-id="10f81-109">Members</span></span>                        | <span data-ttu-id="10f81-110">Descrições</span><span class="sxs-lookup"><span data-stu-id="10f81-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="10f81-111">AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-111">AreDefaultContextMenusEnabled</span></span>](#aredefaultcontextmenusenabled) | <span data-ttu-id="10f81-112">A propriedade AreDefaultContextMenusEnabled é usada para impedir que os menus de contexto padrão sejam mostrados para o usuário no WebView.</span><span class="sxs-lookup"><span data-stu-id="10f81-112">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="10f81-113">AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-113">AreDefaultScriptDialogsEnabled</span></span>](#aredefaultscriptdialogsenabled) | <span data-ttu-id="10f81-114">AreDefaultScriptDialogsEnabled é usado ao carregar um novo documento HTML.</span><span class="sxs-lookup"><span data-stu-id="10f81-114">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="10f81-115">AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-115">AreDevToolsEnabled</span></span>](#aredevtoolsenabled) | <span data-ttu-id="10f81-116">AreDevToolsEnabled controla se o usuário pode usar o menu de contexto ou os atalhos de teclado para abrir a janela do DevTools.</span><span class="sxs-lookup"><span data-stu-id="10f81-116">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="10f81-117">AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="10f81-117">AreRemoteObjectsAllowed</span></span>](#areremoteobjectsallowed) | <span data-ttu-id="10f81-118">A propriedade AreRemoteObjectsAllowed é usada para controlar se os objetos remotos podem ser acessados na página do WebView.</span><span class="sxs-lookup"><span data-stu-id="10f81-118">The AreRemoteObjectsAllowed property is used to control whether remote objects are accessible from the page in webview.</span></span>
[<span data-ttu-id="10f81-119">IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-119">IsBuiltInErrorPageEnabled</span></span>](#isbuiltinerrorpageenabled) | <span data-ttu-id="10f81-120">A propriedade IsBuiltInErrorPageEnabled é usada para desabilitar a página de erro interna para falha de navegação e falha no processo de renderização.</span><span class="sxs-lookup"><span data-stu-id="10f81-120">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>
[<span data-ttu-id="10f81-121">IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-121">IsScriptEnabled</span></span>](#isscriptenabled) | <span data-ttu-id="10f81-122">Controla se a execução JavaScript está habilitada em todas as navegações futuras no WebView.</span><span class="sxs-lookup"><span data-stu-id="10f81-122">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="10f81-123">IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-123">IsStatusBarEnabled</span></span>](#isstatusbarenabled) | <span data-ttu-id="10f81-124">IsStatusBarEnabled controla se a barra de status será exibida.</span><span class="sxs-lookup"><span data-stu-id="10f81-124">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="10f81-125">IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-125">IsWebMessageEnabled</span></span>](#iswebmessageenabled) | <span data-ttu-id="10f81-126">A propriedade IsWebMessageEnabled é usada ao carregar um novo documento HTML.</span><span class="sxs-lookup"><span data-stu-id="10f81-126">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="10f81-127">IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-127">IsZoomControlEnabled</span></span>](#iszoomcontrolenabled) | <span data-ttu-id="10f81-128">A propriedade IsZoomControlEnabled é usada para impedir que o usuário afete o zoom da WebView.</span><span class="sxs-lookup"><span data-stu-id="10f81-128">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

<span data-ttu-id="10f81-129">As alterações de configuração feitas após o evento NavigationStarting não serão aplicadas até a próxima navegação de nível superior.</span><span class="sxs-lookup"><span data-stu-id="10f81-129">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="10f81-130">Parte</span><span class="sxs-lookup"><span data-stu-id="10f81-130">Members</span></span>

#### <span data-ttu-id="10f81-131">AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-131">AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="10f81-132">A propriedade AreDefaultContextMenusEnabled é usada para impedir que os menus de contexto padrão sejam mostrados para o usuário no WebView.</span><span class="sxs-lookup"><span data-stu-id="10f81-132">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="10f81-133">Public bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)</span><span class="sxs-lookup"><span data-stu-id="10f81-133">public bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)</span></span>

<span data-ttu-id="10f81-134">O padrão é TRUE.</span><span class="sxs-lookup"><span data-stu-id="10f81-134">Defaults to TRUE.</span></span>

#### <span data-ttu-id="10f81-135">AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-135">AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="10f81-136">AreDefaultScriptDialogsEnabled é usado ao carregar um novo documento HTML.</span><span class="sxs-lookup"><span data-stu-id="10f81-136">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="10f81-137">Public bool [AreDefaultScriptDialogsEnabled](#aredefaultscriptdialogsenabled)</span><span class="sxs-lookup"><span data-stu-id="10f81-137">public bool [AreDefaultScriptDialogsEnabled](#aredefaultscriptdialogsenabled)</span></span>

<span data-ttu-id="10f81-138">Se definido como false, o WebView não renderizará a caixa de diálogo JavaScript padrão (especificamente as mostradas pelo alerta de JavaScript, confirme, funções de prompt e evento beforeunload).</span><span class="sxs-lookup"><span data-stu-id="10f81-138">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="10f81-139">Em vez disso, se um manipulador de eventos for definido por SetScriptDialogOpeningEventHandler, o WebView enviará um evento que conterá todas as informações da caixa de diálogo e permitirá que o aplicativo host mostre sua própria interface do usuário personalizada.</span><span class="sxs-lookup"><span data-stu-id="10f81-139">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="10f81-140">AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-140">AreDevToolsEnabled</span></span> 

<span data-ttu-id="10f81-141">AreDevToolsEnabled controla se o usuário pode usar o menu de contexto ou os atalhos de teclado para abrir a janela do DevTools.</span><span class="sxs-lookup"><span data-stu-id="10f81-141">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="10f81-142">Public bool [AreDevToolsEnabled](#aredevtoolsenabled)</span><span class="sxs-lookup"><span data-stu-id="10f81-142">public bool [AreDevToolsEnabled](#aredevtoolsenabled)</span></span>

<span data-ttu-id="10f81-143">É verdade por padrão.</span><span class="sxs-lookup"><span data-stu-id="10f81-143">It is true by default.</span></span>

#### <span data-ttu-id="10f81-144">AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="10f81-144">AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="10f81-145">A propriedade AreRemoteObjectsAllowed é usada para controlar se os objetos remotos podem ser acessados na página do WebView.</span><span class="sxs-lookup"><span data-stu-id="10f81-145">The AreRemoteObjectsAllowed property is used to control whether remote objects are accessible from the page in webview.</span></span>

> <span data-ttu-id="10f81-146">Public bool [AreRemoteObjectsAllowed](#areremoteobjectsallowed)</span><span class="sxs-lookup"><span data-stu-id="10f81-146">public bool [AreRemoteObjectsAllowed](#areremoteobjectsallowed)</span></span>

<span data-ttu-id="10f81-147">O padrão é TRUE.</span><span class="sxs-lookup"><span data-stu-id="10f81-147">Defaults to TRUE.</span></span>

#### <span data-ttu-id="10f81-148">IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-148">IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="10f81-149">A propriedade IsBuiltInErrorPageEnabled é usada para desabilitar a página de erro interna para falha de navegação e falha no processo de renderização.</span><span class="sxs-lookup"><span data-stu-id="10f81-149">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>

> <span data-ttu-id="10f81-150">Public bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)</span><span class="sxs-lookup"><span data-stu-id="10f81-150">public bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)</span></span>

<span data-ttu-id="10f81-151">O padrão é TRUE.</span><span class="sxs-lookup"><span data-stu-id="10f81-151">Defaults to TRUE.</span></span> <span data-ttu-id="10f81-152">Quando desativado, a página em branco será mostrada quando ocorrer um erro relacionado.</span><span class="sxs-lookup"><span data-stu-id="10f81-152">When disabled, blank page will be shown when related error happens.</span></span>

#### <span data-ttu-id="10f81-153">IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-153">IsScriptEnabled</span></span> 

<span data-ttu-id="10f81-154">Controla se a execução JavaScript está habilitada em todas as navegações futuras no WebView.</span><span class="sxs-lookup"><span data-stu-id="10f81-154">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="10f81-155">Public bool [IsScriptEnabled](#isscriptenabled)</span><span class="sxs-lookup"><span data-stu-id="10f81-155">public bool [IsScriptEnabled](#isscriptenabled)</span></span>

<span data-ttu-id="10f81-156">Isso afeta apenas scripts no documento; scripts injetados com ExecuteScript serão executados mesmo se o script estiver desabilitado.</span><span class="sxs-lookup"><span data-stu-id="10f81-156">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="10f81-157">É verdade por padrão.</span><span class="sxs-lookup"><span data-stu-id="10f81-157">It is true by default.</span></span>

#### <span data-ttu-id="10f81-158">IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-158">IsStatusBarEnabled</span></span> 

<span data-ttu-id="10f81-159">IsStatusBarEnabled controla se a barra de status será exibida.</span><span class="sxs-lookup"><span data-stu-id="10f81-159">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="10f81-160">Public bool [IsStatusBarEnabled](#isstatusbarenabled)</span><span class="sxs-lookup"><span data-stu-id="10f81-160">public bool [IsStatusBarEnabled](#isstatusbarenabled)</span></span>

<span data-ttu-id="10f81-161">A barra de status geralmente é exibida no canto inferior esquerdo da WebView e mostra itens como o URI de um link quando o usuário passa o mouse sobre ele e outras informações.</span><span class="sxs-lookup"><span data-stu-id="10f81-161">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="10f81-162">É verdade por padrão.</span><span class="sxs-lookup"><span data-stu-id="10f81-162">It is true by default.</span></span>

#### <span data-ttu-id="10f81-163">IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-163">IsWebMessageEnabled</span></span> 

<span data-ttu-id="10f81-164">A propriedade IsWebMessageEnabled é usada ao carregar um novo documento HTML.</span><span class="sxs-lookup"><span data-stu-id="10f81-164">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="10f81-165">Public bool [IsWebMessageEnabled](#iswebmessageenabled)</span><span class="sxs-lookup"><span data-stu-id="10f81-165">public bool [IsWebMessageEnabled](#iswebmessageenabled)</span></span>

<span data-ttu-id="10f81-166">Se definido como true, a comunicação do host com o documento HTML de nível superior da WebView é permitida por meio do evento de mensagem do PostWebMessageAsJson, do PostWebMessageAsString e do Window. Chrome. WebView (consulte a documentação do PostWebMessageAsJson para obter detalhes).</span><span class="sxs-lookup"><span data-stu-id="10f81-166">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="10f81-167">A comunicação do documento HTML de nível superior do WebView para o host é permitida por meio da função de SetWebMessageReceivedEventHandler do Window. Chrome. WebView e do método (consulte a documentação do SetWebMessageReceivedEventHandler para obter detalhes).</span><span class="sxs-lookup"><span data-stu-id="10f81-167">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="10f81-168">Se definido como false, a comunicação não será permitida.</span><span class="sxs-lookup"><span data-stu-id="10f81-168">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="10f81-169">PostWebMessageAsJson e PostWebMessageAsString falharão com E_ACCESSDENIED e Window. Chrome. WebView. CreateMessage irá falhar ao lançar uma instância de um objeto de erro.</span><span class="sxs-lookup"><span data-stu-id="10f81-169">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="10f81-170">É verdade por padrão.</span><span class="sxs-lookup"><span data-stu-id="10f81-170">It is true by default.</span></span>

#### <span data-ttu-id="10f81-171">IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="10f81-171">IsZoomControlEnabled</span></span> 

<span data-ttu-id="10f81-172">A propriedade IsZoomControlEnabled é usada para impedir que o usuário afete o zoom da WebView.</span><span class="sxs-lookup"><span data-stu-id="10f81-172">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="10f81-173">Public bool [IsZoomControlEnabled](#iszoomcontrolenabled)</span><span class="sxs-lookup"><span data-stu-id="10f81-173">public bool [IsZoomControlEnabled](#iszoomcontrolenabled)</span></span>

<span data-ttu-id="10f81-174">O padrão é TRUE.</span><span class="sxs-lookup"><span data-stu-id="10f81-174">Defaults to TRUE.</span></span> <span data-ttu-id="10f81-175">Quando desabilitado, o usuário não poderá aplicar zoom usando Ctrl +/ou CTRL + mouse wheel, mas o zoom poderá ser definido por meio da API ZoomFactor.</span><span class="sxs-lookup"><span data-stu-id="10f81-175">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via ZoomFactor API.</span></span>
