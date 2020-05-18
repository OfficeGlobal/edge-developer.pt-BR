---
description: Hospedar conteúdo da Web em seu aplicativo Win32 com o controle WebView2 do Microsoft Edge
title: Microsoft Edge WebView2 para aplicativos Win32
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, webview2, WebView, aplicativos Win32, Win32, Edge, ICoreWebView2, ICoreWebView2Host, controle do navegador, HTML Edge
ms.openlocfilehash: 4fe7d149aa422fb98ad3b63e63943533f00c84e5
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652505"
---
# <span data-ttu-id="75dfb-104">interface ICoreWebView2Host</span><span class="sxs-lookup"><span data-stu-id="75dfb-104">interface ICoreWebView2Host</span></span> 

> [!NOTE]
> <span data-ttu-id="75dfb-105">Essa interface pode ser alterada ou indisponível para versões posteriores SDK da versão 0.9.430.</span><span class="sxs-lookup"><span data-stu-id="75dfb-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="75dfb-106">Consulte a [referência](../../../webview2-api-reference.md) para obter a referência da API mais recente.</span><span class="sxs-lookup"><span data-stu-id="75dfb-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2Host
  : public IUnknown
```

<span data-ttu-id="75dfb-107">Essa interface é o proprietário do objeto CoreWebView2 e fornece suporte para redimensionar, mostrar e ocultar, enfocar e outras funcionalidades relacionadas à janela e composição.</span><span class="sxs-lookup"><span data-stu-id="75dfb-107">This interface is the owner of the CoreWebView2 object, and provides support for resizing, showing and hiding, focusing, and other functionality related to windowing and composition.</span></span>

## <span data-ttu-id="75dfb-108">Resumo</span><span class="sxs-lookup"><span data-stu-id="75dfb-108">Summary</span></span>

 <span data-ttu-id="75dfb-109">Parte</span><span class="sxs-lookup"><span data-stu-id="75dfb-109">Members</span></span>                        | <span data-ttu-id="75dfb-110">Descrições</span><span class="sxs-lookup"><span data-stu-id="75dfb-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="75dfb-111">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="75dfb-111">get_IsVisible</span></span>](#get_isvisible) | <span data-ttu-id="75dfb-112">A propriedade IsVisible Determina se deseja mostrar ou ocultar o WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-112">The IsVisible property determines whether to show or hide the webview.</span></span>
[<span data-ttu-id="75dfb-113">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="75dfb-113">put_IsVisible</span></span>](#put_isvisible) | <span data-ttu-id="75dfb-114">Defina a propriedade IsVisible.</span><span class="sxs-lookup"><span data-stu-id="75dfb-114">Set the IsVisible property.</span></span>
[<span data-ttu-id="75dfb-115">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="75dfb-115">get_Bounds</span></span>](#get_bounds) | <span data-ttu-id="75dfb-116">Os limites da WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-116">The webview bounds.</span></span>
[<span data-ttu-id="75dfb-117">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="75dfb-117">put_Bounds</span></span>](#put_bounds) | <span data-ttu-id="75dfb-118">Defina a propriedade Bounds.</span><span class="sxs-lookup"><span data-stu-id="75dfb-118">Set the Bounds property.</span></span>
[<span data-ttu-id="75dfb-119">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="75dfb-119">get_ZoomFactor</span></span>](#get_zoomfactor) | <span data-ttu-id="75dfb-120">O fator de zoom para o WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-120">The zoom factor for the WebView.</span></span>
[<span data-ttu-id="75dfb-121">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="75dfb-121">put_ZoomFactor</span></span>](#put_zoomfactor) | <span data-ttu-id="75dfb-122">Defina a propriedade ZoomFactor.</span><span class="sxs-lookup"><span data-stu-id="75dfb-122">Set the ZoomFactor property.</span></span>
[<span data-ttu-id="75dfb-123">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="75dfb-123">add_ZoomFactorChanged</span></span>](#add_zoomfactorchanged) | <span data-ttu-id="75dfb-124">Adicione um manipulador de eventos para o evento ZoomFactorChanged.</span><span class="sxs-lookup"><span data-stu-id="75dfb-124">Add an event handler for the ZoomFactorChanged event.</span></span>
[<span data-ttu-id="75dfb-125">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="75dfb-125">remove_ZoomFactorChanged</span></span>](#remove_zoomfactorchanged) | <span data-ttu-id="75dfb-126">Remover um manipulador de eventos adicionado anteriormente com add_ZoomFactorChanged.</span><span class="sxs-lookup"><span data-stu-id="75dfb-126">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>
[<span data-ttu-id="75dfb-127">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="75dfb-127">SetBoundsAndZoomFactor</span></span>](#setboundsandzoomfactor) | <span data-ttu-id="75dfb-128">Atualize as propriedades Bounds e ZoomFactor ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="75dfb-128">Update Bounds and ZoomFactor properties at the same time.</span></span>
[<span data-ttu-id="75dfb-129">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="75dfb-129">MoveFocus</span></span>](#movefocus) | <span data-ttu-id="75dfb-130">Mover o foco para o WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-130">Move focus into WebView.</span></span>
[<span data-ttu-id="75dfb-131">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="75dfb-131">add_MoveFocusRequested</span></span>](#add_movefocusrequested) | <span data-ttu-id="75dfb-132">Adicione um manipulador de eventos para o evento MoveFocusRequested.</span><span class="sxs-lookup"><span data-stu-id="75dfb-132">Add an event handler for the MoveFocusRequested event.</span></span>
[<span data-ttu-id="75dfb-133">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="75dfb-133">remove_MoveFocusRequested</span></span>](#remove_movefocusrequested) | <span data-ttu-id="75dfb-134">Remover um manipulador de eventos adicionado anteriormente com add_MoveFocusRequested.</span><span class="sxs-lookup"><span data-stu-id="75dfb-134">Remove an event handler previously added with add_MoveFocusRequested.</span></span>
[<span data-ttu-id="75dfb-135">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="75dfb-135">add_GotFocus</span></span>](#add_gotfocus) | <span data-ttu-id="75dfb-136">Adicione um manipulador de eventos para o evento GotFocus.</span><span class="sxs-lookup"><span data-stu-id="75dfb-136">Add an event handler for the GotFocus event.</span></span>
[<span data-ttu-id="75dfb-137">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="75dfb-137">remove_GotFocus</span></span>](#remove_gotfocus) | <span data-ttu-id="75dfb-138">Remover um manipulador de eventos adicionado anteriormente com add_GotFocus.</span><span class="sxs-lookup"><span data-stu-id="75dfb-138">Remove an event handler previously added with add_GotFocus.</span></span>
[<span data-ttu-id="75dfb-139">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="75dfb-139">add_LostFocus</span></span>](#add_lostfocus) | <span data-ttu-id="75dfb-140">Adicione um manipulador de eventos para o evento LostFocus.</span><span class="sxs-lookup"><span data-stu-id="75dfb-140">Add an event handler for the LostFocus event.</span></span>
[<span data-ttu-id="75dfb-141">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="75dfb-141">remove_LostFocus</span></span>](#remove_lostfocus) | <span data-ttu-id="75dfb-142">Remover um manipulador de eventos adicionado anteriormente com add_LostFocus.</span><span class="sxs-lookup"><span data-stu-id="75dfb-142">Remove an event handler previously added with add_LostFocus.</span></span>
[<span data-ttu-id="75dfb-143">add_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="75dfb-143">add_AcceleratorKeyPressed</span></span>](#add_acceleratorkeypressed) | <span data-ttu-id="75dfb-144">Adicione um manipulador de eventos para o evento AcceleratorKeyPressed.</span><span class="sxs-lookup"><span data-stu-id="75dfb-144">Add an event handler for the AcceleratorKeyPressed event.</span></span>
[<span data-ttu-id="75dfb-145">remove_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="75dfb-145">remove_AcceleratorKeyPressed</span></span>](#remove_acceleratorkeypressed) | <span data-ttu-id="75dfb-146">Remover um manipulador de eventos adicionado anteriormente com add_AcceleratorKeyPressed.</span><span class="sxs-lookup"><span data-stu-id="75dfb-146">Remove an event handler previously added with add_AcceleratorKeyPressed.</span></span>
[<span data-ttu-id="75dfb-147">get_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="75dfb-147">get_ParentWindow</span></span>](#get_parentwindow) | <span data-ttu-id="75dfb-148">A janela pai fornecida pelo aplicativo que este WebView usa para renderizar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="75dfb-148">The parent window provided by the app that this WebView is using to render content.</span></span>
[<span data-ttu-id="75dfb-149">put_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="75dfb-149">put_ParentWindow</span></span>](#put_parentwindow) | <span data-ttu-id="75dfb-150">Defina a janela pai para o WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-150">Set the parent window for the WebView.</span></span>
[<span data-ttu-id="75dfb-151">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="75dfb-151">NotifyParentWindowPositionChanged</span></span>](#notifyparentwindowpositionchanged) | <span data-ttu-id="75dfb-152">Esta é uma notificação separada da put_Bounds que informa ao WebView o HWND pai (ou qualquer ancestral) movido.</span><span class="sxs-lookup"><span data-stu-id="75dfb-152">This is a notification separate from put_Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>
[<span data-ttu-id="75dfb-153">Fechar</span><span class="sxs-lookup"><span data-stu-id="75dfb-153">Close</span></span>](#close) | <span data-ttu-id="75dfb-154">Fecha a WebView e limpa a instância do navegador subjacente.</span><span class="sxs-lookup"><span data-stu-id="75dfb-154">Closes the WebView and cleans up the underlying browser instance.</span></span>
[<span data-ttu-id="75dfb-155">get_CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="75dfb-155">get_CoreWebView2</span></span>](#get_corewebview2) | <span data-ttu-id="75dfb-156">Obtém a CoreWebView2 associada a este CoreWebView2Host.</span><span class="sxs-lookup"><span data-stu-id="75dfb-156">Gets the CoreWebView2 associated with this CoreWebView2Host.</span></span>
[<span data-ttu-id="75dfb-157">CORE_WEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="75dfb-157">CORE_WEBVIEW2_MOVE_FOCUS_REASON</span></span>](#core_webview2_move_focus_reason) | <span data-ttu-id="75dfb-158">Motivo para mover o foco.</span><span class="sxs-lookup"><span data-stu-id="75dfb-158">Reason for moving focus.</span></span>
[<span data-ttu-id="75dfb-159">CORE_WEBVIEW2_KEY_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="75dfb-159">CORE_WEBVIEW2_KEY_EVENT_KIND</span></span>](#core_webview2_key_event_kind) | <span data-ttu-id="75dfb-160">O tipo de evento de chave que disparou um evento AcceleratorKeyPressed.</span><span class="sxs-lookup"><span data-stu-id="75dfb-160">The type of key event that triggered an AcceleratorKeyPressed event.</span></span>
[<span data-ttu-id="75dfb-161">CORE_WEBVIEW2_PHYSICAL_KEY_STATUS</span><span class="sxs-lookup"><span data-stu-id="75dfb-161">CORE_WEBVIEW2_PHYSICAL_KEY_STATUS</span></span>](#core_webview2_physical_key_status) | <span data-ttu-id="75dfb-162">Uma estrutura que representa as informações empacotadas no LPARAM fornecido a um evento de chave do Win32.</span><span class="sxs-lookup"><span data-stu-id="75dfb-162">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

<span data-ttu-id="75dfb-163">O CoreWebView2Host é proprietário do CoreWebView2 e, se todas as referências à CoreWebView2Host ficarem ausentes, o WebView será fechado.</span><span class="sxs-lookup"><span data-stu-id="75dfb-163">The CoreWebView2Host owns the CoreWebView2, and if all references to the CoreWebView2Host go away, the WebView will be closed.</span></span>

## <span data-ttu-id="75dfb-164">Parte</span><span class="sxs-lookup"><span data-stu-id="75dfb-164">Members</span></span>

#### <span data-ttu-id="75dfb-165">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="75dfb-165">get_IsVisible</span></span> 

<span data-ttu-id="75dfb-166">A propriedade IsVisible Determina se deseja mostrar ou ocultar o WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-166">The IsVisible property determines whether to show or hide the webview.</span></span>

> <span data-ttu-id="75dfb-167">[get_IsVisible](#get_isvisible)público HRESULT (bool \* IsVisible)</span><span class="sxs-lookup"><span data-stu-id="75dfb-167">public HRESULT [get_IsVisible](#get_isvisible)(BOOL \* isVisible)</span></span>

<span data-ttu-id="75dfb-168">Se IsVisible estiver definido como false, o WebView será transparente e não será renderizado.</span><span class="sxs-lookup"><span data-stu-id="75dfb-168">If IsVisible is set to false, the webview will be transparent and will not be rendered.</span></span> <span data-ttu-id="75dfb-169">No entanto, isso não afetará a janela que contém o WebView (o parâmetro HWND que foi passado para CreateCoreWebView2Host).</span><span class="sxs-lookup"><span data-stu-id="75dfb-169">However, this will not affect the window containing the webview (the HWND parameter that was passed to CreateCoreWebView2Host).</span></span> <span data-ttu-id="75dfb-170">Se você quiser que essa janela desapareça também, chame o recurso de janela diretamente, além de modificar a propriedade IsVisible.</span><span class="sxs-lookup"><span data-stu-id="75dfb-170">If you want that window to disappear too, call ShowWindow on it directly in addition to modifying the IsVisible property.</span></span> <span data-ttu-id="75dfb-171">A WebView como uma janela filho não obterá mensagens de janela quando a janela superior for minimizada ou restaurada.</span><span class="sxs-lookup"><span data-stu-id="75dfb-171">WebView as a child window won't get window messages when the top window is minimized or restored.</span></span> <span data-ttu-id="75dfb-172">Por motivo de desempenho, o desenvolvedor deve definir a propriedade IsVisible do WebView como false quando a janela do aplicativo é minimizada e retomada como true quando a janela do aplicativo for restaurada.</span><span class="sxs-lookup"><span data-stu-id="75dfb-172">For performance reason, developer should set IsVisible property of the WebView to false when the app window is minimized and back to true when app window is restored.</span></span> <span data-ttu-id="75dfb-173">A janela do aplicativo pode fazer isso ao manipular SC_MINIMIZE e SC_RESTORE comando ao receber WM_SYSCOMMAND mensagem.</span><span class="sxs-lookup"><span data-stu-id="75dfb-173">App window can do this by handling SC_MINIMIZE and SC_RESTORE command upon receiving WM_SYSCOMMAND message.</span></span>

```cpp
void ViewComponent::ToggleVisibility()
{
    BOOL visible;
    m_host->get_IsVisible(&visible);
    m_isVisible = !visible;
    m_host->put_IsVisible(m_isVisible);
}
```

#### <span data-ttu-id="75dfb-174">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="75dfb-174">put_IsVisible</span></span> 

<span data-ttu-id="75dfb-175">Defina a propriedade IsVisible.</span><span class="sxs-lookup"><span data-stu-id="75dfb-175">Set the IsVisible property.</span></span>

> <span data-ttu-id="75dfb-176">público HRESULT [put_IsVisible](#put_isvisible)(bool IsVisible)</span><span class="sxs-lookup"><span data-stu-id="75dfb-176">public HRESULT [put_IsVisible](#put_isvisible)(BOOL isVisible)</span></span>

```cpp
    if (message == WM_SYSCOMMAND)
    {
        if (wParam == SC_MINIMIZE)
        {
            // Hide the webview when the app window is minimized.
            m_host->put_IsVisible(FALSE);
        }
        else if (wParam == SC_RESTORE)
        {
            // When the app window is restored, show the webview
            // (unless the user has toggle visibility off).
            if (m_isVisible)
            {
                m_host->put_IsVisible(TRUE);
            }
        }
    }
```

#### <span data-ttu-id="75dfb-177">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="75dfb-177">get_Bounds</span></span> 

<span data-ttu-id="75dfb-178">Os limites da WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-178">The webview bounds.</span></span>

> <span data-ttu-id="75dfb-179">Associação Pública HRESULT [get_Bounds](#get_bounds)(Rect \*)</span><span class="sxs-lookup"><span data-stu-id="75dfb-179">public HRESULT [get_Bounds](#get_bounds)(RECT \* bounds)</span></span>

<span data-ttu-id="75dfb-180">Os limites são relativos ao HWND pai.</span><span class="sxs-lookup"><span data-stu-id="75dfb-180">Bounds are relative to the parent HWND.</span></span> <span data-ttu-id="75dfb-181">O aplicativo tem duas maneiras de posicionar um WebView:</span><span class="sxs-lookup"><span data-stu-id="75dfb-181">The app has two ways it can position a WebView:</span></span>

1. <span data-ttu-id="75dfb-182">Crie um HWND filho que seja o HWND pai do WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-182">Create a child HWND that is the WebView parent HWND.</span></span> <span data-ttu-id="75dfb-183">Posicione esta janela onde o WebView deve estar.</span><span class="sxs-lookup"><span data-stu-id="75dfb-183">Position this window where the WebView should be.</span></span> <span data-ttu-id="75dfb-184">Nesse caso, use (0, 0) para o canto superior esquerdo Bound's do WebView (o deslocamento).</span><span class="sxs-lookup"><span data-stu-id="75dfb-184">In this case, use (0, 0) for the WebView's Bound's top left corner (the offset).</span></span>

1. <span data-ttu-id="75dfb-185">Use a janela mais superior do aplicativo como o HWND pai do WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-185">Use the app's top most window as the WebView parent HWND.</span></span> <span data-ttu-id="75dfb-186">Defina o Bound's canto superior esquerdo da WebView para que o WebView esteja posicionado corretamente no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="75dfb-186">Set the WebView's Bound's top left corner so that the WebView is positioned correctly in the app.</span></span> <span data-ttu-id="75dfb-187">Os valores do limite estão no espaço de coordenadas do host.</span><span class="sxs-lookup"><span data-stu-id="75dfb-187">The Bound's values are in the host's coordinate space.</span></span>

#### <span data-ttu-id="75dfb-188">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="75dfb-188">put_Bounds</span></span> 

<span data-ttu-id="75dfb-189">Defina a propriedade Bounds.</span><span class="sxs-lookup"><span data-stu-id="75dfb-189">Set the Bounds property.</span></span>

> <span data-ttu-id="75dfb-190">[put_Bounds](#put_bounds)público HRESULT (limites Rect)</span><span class="sxs-lookup"><span data-stu-id="75dfb-190">public HRESULT [put_Bounds](#put_bounds)(RECT bounds)</span></span>

```cpp
// Update the bounds of the WebView window to fit available space.
void ViewComponent::ResizeWebView()
{
    SIZE webViewSize = {
            LONG((m_webViewBounds.right - m_webViewBounds.left) * m_webViewRatio * m_webViewScale),
            LONG((m_webViewBounds.bottom - m_webViewBounds.top) * m_webViewRatio * m_webViewScale) };

    RECT desiredBounds = m_webViewBounds;
    desiredBounds.bottom = LONG(
        webViewSize.cy + m_webViewBounds.top);
    desiredBounds.right = LONG(
        webViewSize.cx + m_webViewBounds.left);

    m_host->put_Bounds(desiredBounds);
}
```

#### <span data-ttu-id="75dfb-191">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="75dfb-191">get_ZoomFactor</span></span> 

<span data-ttu-id="75dfb-192">O fator de zoom para o WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-192">The zoom factor for the WebView.</span></span>

> <span data-ttu-id="75dfb-193">público HRESULT [get_ZoomFactor](#get_zoomfactor)(duplo \* ZoomFactor)</span><span class="sxs-lookup"><span data-stu-id="75dfb-193">public HRESULT [get_ZoomFactor](#get_zoomfactor)(double \* zoomFactor)</span></span>

<span data-ttu-id="75dfb-194">Observe que a alteração do fator de zoom pode fazer com que o `window.innerWidth/innerHeight` layout da página seja alterado.</span><span class="sxs-lookup"><span data-stu-id="75dfb-194">Note that changing zoom factor could cause `window.innerWidth/innerHeight` and page layout to change.</span></span> <span data-ttu-id="75dfb-195">Um fator de zoom aplicado pelo host chamando put_ZoomFactor se torna o novo zoom padrão para o WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-195">A zoom factor that is applied by the host by calling put_ZoomFactor becomes the new default zoom for the WebView.</span></span> <span data-ttu-id="75dfb-196">Esse fator de zoom se aplica a navegações e é o fator de zoom que é retornado quando o usuário pressiona Ctrl + 0.</span><span class="sxs-lookup"><span data-stu-id="75dfb-196">This zoom factor applies across navigations and is the zoom factor WebView is returned to when the user presses ctrl+0.</span></span> <span data-ttu-id="75dfb-197">Quando o fator de zoom é alterado pelo usuário (resultante do aplicativo que recebe ZoomFactorChanged), esse zoom se aplica apenas à página atual.</span><span class="sxs-lookup"><span data-stu-id="75dfb-197">When the zoom factor is changed by the user (resulting in the app receiving ZoomFactorChanged), that zoom applies only for the current page.</span></span> <span data-ttu-id="75dfb-198">O zoom aplicado pelo usuário é somente para a página atual e é redefinido em uma navegação.</span><span class="sxs-lookup"><span data-stu-id="75dfb-198">Any user applied zoom is only for the current page and is reset on a navigation.</span></span> <span data-ttu-id="75dfb-199">Não é permitido especificar um zoomFactor menor ou igual a 0.</span><span class="sxs-lookup"><span data-stu-id="75dfb-199">Specifying a zoomFactor less than or equal to 0 is not allowed.</span></span> <span data-ttu-id="75dfb-200">WebView também tem um intervalo de fator de zoom interno com suporte.</span><span class="sxs-lookup"><span data-stu-id="75dfb-200">WebView also has an internal supported zoom factor range.</span></span> <span data-ttu-id="75dfb-201">Quando um fator de zoom especificado estiver fora desse intervalo, ele será normalizado para estar dentro do intervalo, e um evento ZoomFactorChanged será acionado para o fator de zoom aplicado real.</span><span class="sxs-lookup"><span data-stu-id="75dfb-201">When a specified zoom factor is out of that range, it will be normalized to be within the range, and a ZoomFactorChanged event will be fired for the real applied zoom factor.</span></span> <span data-ttu-id="75dfb-202">Quando essa faixa de normalização acontece, a propriedade ZoomFactor relata o fator de zoom especificado durante a modificação anterior da propriedade ZoomFactor até que o evento ZoomFactorChanged seja recebido após o WebView se aplicar o fator de zoom normalizado.</span><span class="sxs-lookup"><span data-stu-id="75dfb-202">When this range normalization happens, the ZoomFactor property will report the zoom factor specified during the previous modification of the ZoomFactor property until the ZoomFactorChanged event is received after webview applies the normalized zoom factor.</span></span>

#### <span data-ttu-id="75dfb-203">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="75dfb-203">put_ZoomFactor</span></span> 

<span data-ttu-id="75dfb-204">Defina a propriedade ZoomFactor.</span><span class="sxs-lookup"><span data-stu-id="75dfb-204">Set the ZoomFactor property.</span></span>

> <span data-ttu-id="75dfb-205">público HRESULT [put_ZoomFactor](#put_zoomfactor)(ZoomFactor duplo)</span><span class="sxs-lookup"><span data-stu-id="75dfb-205">public HRESULT [put_ZoomFactor](#put_zoomfactor)(double zoomFactor)</span></span>

#### <span data-ttu-id="75dfb-206">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="75dfb-206">add_ZoomFactorChanged</span></span> 

<span data-ttu-id="75dfb-207">Adicione um manipulador de eventos para o evento ZoomFactorChanged.</span><span class="sxs-lookup"><span data-stu-id="75dfb-207">Add an event handler for the ZoomFactorChanged event.</span></span>

> <span data-ttu-id="75dfb-208">Public HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([ICoreWebView2ZoomFactorChangedEventHandler](ICoreWebView2ZoomFactorChangedEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="75dfb-208">public HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([ICoreWebView2ZoomFactorChangedEventHandler](ICoreWebView2ZoomFactorChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="75dfb-209">O evento é acionado quando a propriedade ZoomFactor da WebView é alterada.</span><span class="sxs-lookup"><span data-stu-id="75dfb-209">The event fires when the ZoomFactor property of the WebView changes.</span></span> <span data-ttu-id="75dfb-210">O evento pode ser acionado porque o chamador modificou a propriedade ZoomFactor ou porque o usuário modificou manualmente o zoom.</span><span class="sxs-lookup"><span data-stu-id="75dfb-210">The event could fire because the caller modified the ZoomFactor property, or due to the user manually modifying the zoom.</span></span> <span data-ttu-id="75dfb-211">Quando ela é modificada pelo chamador por meio da propriedade ZoomFactor, o fator de zoom interno é atualizado imediatamente e não haverá um evento ZoomFactorChanged.</span><span class="sxs-lookup"><span data-stu-id="75dfb-211">When it is modified by the caller via the ZoomFactor property, the internal zoom factor is updated immediately and there will be no ZoomFactorChanged event.</span></span> <span data-ttu-id="75dfb-212">O WebView associa o último fator de zoom usado para cada site.</span><span class="sxs-lookup"><span data-stu-id="75dfb-212">WebView associates the last used zoom factor for each site.</span></span> <span data-ttu-id="75dfb-213">Portanto, é possível que o fator de zoom mude ao navegar para uma página diferente.</span><span class="sxs-lookup"><span data-stu-id="75dfb-213">Therefore, it is possible for the zoom factor to change when navigating to a different page.</span></span> <span data-ttu-id="75dfb-214">Quando o fator de zoom muda devido a isso, o evento ZoomFactorChanged é acionado logo após o evento ContentLoading.</span><span class="sxs-lookup"><span data-stu-id="75dfb-214">When the zoom factor changes due to this, the ZoomFactorChanged event fires right after the ContentLoading event.</span></span>

```cpp
    // Register a handler for the ZoomFactorChanged event.
    // This handler just announces the new level of zoom on the window's title bar.
    CHECK_FAILURE(m_host->add_ZoomFactorChanged(
        Callback<ICoreWebView2ZoomFactorChangedEventHandler>(
            [this](ICoreWebView2Host* sender, IUnknown* args) -> HRESULT {
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

#### <span data-ttu-id="75dfb-215">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="75dfb-215">remove_ZoomFactorChanged</span></span> 

<span data-ttu-id="75dfb-216">Remover um manipulador de eventos adicionado anteriormente com add_ZoomFactorChanged.</span><span class="sxs-lookup"><span data-stu-id="75dfb-216">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>

> <span data-ttu-id="75dfb-217">[remove_ZoomFactorChanged](#remove_zoomfactorchanged)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="75dfb-217">public HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="75dfb-218">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="75dfb-218">SetBoundsAndZoomFactor</span></span> 

<span data-ttu-id="75dfb-219">Atualize as propriedades Bounds e ZoomFactor ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="75dfb-219">Update Bounds and ZoomFactor properties at the same time.</span></span>

> <span data-ttu-id="75dfb-220">Public HRESULT [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(limites Rect, zoomFactor duplo)</span><span class="sxs-lookup"><span data-stu-id="75dfb-220">public HRESULT [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(RECT bounds,double zoomFactor)</span></span>

<span data-ttu-id="75dfb-221">Esta operação é atômica a partir da perspecry do host.</span><span class="sxs-lookup"><span data-stu-id="75dfb-221">This operation is atomic from the host's perspecive.</span></span> <span data-ttu-id="75dfb-222">Após retornar dessa função, as propriedades Bounds e ZoomFactor terão ambos sido atualizadas se a função for bem-sucedida ou nenhuma será atualizada se a função falhar.</span><span class="sxs-lookup"><span data-stu-id="75dfb-222">After returning from this function, the Bounds and ZoomFactor properties will have both been updated if the function is successful, or neither will be updated if the function fails.</span></span> <span data-ttu-id="75dfb-223">Se os limites e ZoomFactor forem atualizados com a mesma escala (ou seja, os limites e ZoomFactor forem ambos duplicados), a página não verá uma alteração em Window. innerWidth/innerHeight e o WebView renderizará o conteúdo no novo tamanho e será aplicado sem renderizações intermediárias.</span><span class="sxs-lookup"><span data-stu-id="75dfb-223">If Bounds and ZoomFactor are both updated by the same scale (i.e. Bounds and ZoomFactor are both doubled), then the page will not see a change in window.innerWidth/innerHeight and the WebView will render the content at the new size and zoom without intermediate renderings.</span></span> <span data-ttu-id="75dfb-224">Essa função também pode ser usada para atualizar apenas um de ZoomFactor ou limites passando o novo valor para um e o valor atual para o outro.</span><span class="sxs-lookup"><span data-stu-id="75dfb-224">This function can also be used to update just one of ZoomFactor or Bounds by passing in the new value for one and the current value for the other.</span></span>

```cpp
void ViewComponent::SetScale(float scale)
{
    RECT bounds;
    CHECK_FAILURE(m_host->get_Bounds(&bounds));
    double scaleChange = scale / m_webViewScale;

    bounds.bottom = LONG(
        (bounds.bottom - bounds.top) * scaleChange + bounds.top);
    bounds.right = LONG(
        (bounds.right - bounds.left) * scaleChange + bounds.left);

    m_webViewScale = scale;
    m_host->SetBoundsAndZoomFactor(bounds, scale);
}
```

#### <span data-ttu-id="75dfb-225">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="75dfb-225">MoveFocus</span></span> 

<span data-ttu-id="75dfb-226">Mover o foco para o WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-226">Move focus into WebView.</span></span>

> <span data-ttu-id="75dfb-227">Public HRESULT [MoveFocus](#movefocus)(motivo[CORE_WEBVIEW2_MOVE_FOCUS_REASON](#core_webview2_move_focus_reason) )</span><span class="sxs-lookup"><span data-stu-id="75dfb-227">public HRESULT [MoveFocus](#movefocus)([CORE_WEBVIEW2_MOVE_FOCUS_REASON](#core_webview2_move_focus_reason) reason)</span></span>

<span data-ttu-id="75dfb-228">O WebView receberá o foco e o foco será definido como elemento correspondente na página hospedada na WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-228">WebView will get focus and focus will be set to correspondent element in the page hosted in the WebView.</span></span> <span data-ttu-id="75dfb-229">Para motivo programático, o foco é definido como elemento prefoco anteriormente ou o elemento padrão se não houver nenhum elemento focalizado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="75dfb-229">For Programmatic reason, focus is set to previously focused element or the default element if there is no previously focused element.</span></span> <span data-ttu-id="75dfb-230">Para o próximo motivo, o foco é definido como o primeiro elemento.</span><span class="sxs-lookup"><span data-stu-id="75dfb-230">For Next reason, focus is set to the first element.</span></span> <span data-ttu-id="75dfb-231">Para o motivo anterior, o foco é definido como o último elemento.</span><span class="sxs-lookup"><span data-stu-id="75dfb-231">For Previous reason, focus is set to the last element.</span></span> <span data-ttu-id="75dfb-232">A WebView também pode ter o foco por meio da interação do usuário, como clicar em um WebView ou Tab.</span><span class="sxs-lookup"><span data-stu-id="75dfb-232">WebView can also got focus through user interaction like clicking into WebView or Tab into it.</span></span> <span data-ttu-id="75dfb-233">Para tabulação, o aplicativo pode chamar MoveFocus com o próximo ou o anterior para alinhar-se com Tab e Shift + Tab, respectivamente, quando decide que o WebView é o próximo elemento que pode ser tabulado.</span><span class="sxs-lookup"><span data-stu-id="75dfb-233">For tabbing, the app can call MoveFocus with Next or Previous to align with tab and shift+tab respectively when it decides the WebView is the next tabbable element.</span></span> <span data-ttu-id="75dfb-234">Ou, o aplicativo pode chamar IsDialogMessage como parte de seu loop de mensagem para permitir que a plataforma manipule a Tabulação automaticamente.</span><span class="sxs-lookup"><span data-stu-id="75dfb-234">Or, the app can call IsDialogMessage as part of its message loop to allow the platform to auto handle tabbing.</span></span> <span data-ttu-id="75dfb-235">A plataforma irá girar por todas as janelas com WS_TABSTOP.</span><span class="sxs-lookup"><span data-stu-id="75dfb-235">The platform will rotate through all windows with WS_TABSTOP.</span></span> <span data-ttu-id="75dfb-236">Quando a WebView se concentrar no IsDialogMessage, o foco será inserido internamente no primeiro ou último elemento para Tab e Shift + Tab respectivamente.</span><span class="sxs-lookup"><span data-stu-id="75dfb-236">When the WebView gets focus from IsDialogMessage, it will internally put the focus on the first or last element for tab and shift+tab respectively.</span></span>

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
    m_host->MoveFocus(CORE_WEBVIEW2_MOVE_FOCUS_REASON_NEXT);
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
    CHECK_FAILURE(m_host->MoveFocus(CORE_WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS));
}
```

#### <span data-ttu-id="75dfb-237">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="75dfb-237">add_MoveFocusRequested</span></span> 

<span data-ttu-id="75dfb-238">Adicione um manipulador de eventos para o evento MoveFocusRequested.</span><span class="sxs-lookup"><span data-stu-id="75dfb-238">Add an event handler for the MoveFocusRequested event.</span></span>

> <span data-ttu-id="75dfb-239">Public HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([ICoreWebView2MoveFocusRequestedEventHandler](ICoreWebView2MoveFocusRequestedEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="75dfb-239">public HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([ICoreWebView2MoveFocusRequestedEventHandler](ICoreWebView2MoveFocusRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="75dfb-240">MoveFocusRequested é acionado quando o usuário tenta Tab no WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-240">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span> <span data-ttu-id="75dfb-241">O foco da WebView não mudou quando esse evento é acionado.</span><span class="sxs-lookup"><span data-stu-id="75dfb-241">The WebView's focus has not changed when this event is fired.</span></span>

```cpp
    // Register a handler for the MoveFocusRequested event.
    // This event will be fired when the user tabs out of the webview.
    // The handler will focus another window in the app, depending on which
    // direction the focus is being shifted.
    CHECK_FAILURE(m_host->add_MoveFocusRequested(
        Callback<ICoreWebView2MoveFocusRequestedEventHandler>(
            [this](
                ICoreWebView2Host* sender,
                ICoreWebView2MoveFocusRequestedEventArgs* args) -> HRESULT {
                if (!g_autoTabHandle)
                {
                    CORE_WEBVIEW2_MOVE_FOCUS_REASON reason;
                    CHECK_FAILURE(args->get_Reason(&reason));

                    if (reason == CORE_WEBVIEW2_MOVE_FOCUS_REASON_NEXT)
                    {
                        TabForwards(-1);
                    }
                    else if (reason == CORE_WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS)
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

#### <span data-ttu-id="75dfb-242">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="75dfb-242">remove_MoveFocusRequested</span></span> 

<span data-ttu-id="75dfb-243">Remover um manipulador de eventos adicionado anteriormente com add_MoveFocusRequested.</span><span class="sxs-lookup"><span data-stu-id="75dfb-243">Remove an event handler previously added with add_MoveFocusRequested.</span></span>

> <span data-ttu-id="75dfb-244">[remove_MoveFocusRequested](#remove_movefocusrequested)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="75dfb-244">public HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="75dfb-245">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="75dfb-245">add_GotFocus</span></span> 

<span data-ttu-id="75dfb-246">Adicione um manipulador de eventos para o evento GotFocus.</span><span class="sxs-lookup"><span data-stu-id="75dfb-246">Add an event handler for the GotFocus event.</span></span>

> <span data-ttu-id="75dfb-247">Public HRESULT [add_GotFocus](#add_gotfocus)([ICoreWebView2FocusChangedEventHandler](ICoreWebView2FocusChangedEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="75dfb-247">public HRESULT [add_GotFocus](#add_gotfocus)([ICoreWebView2FocusChangedEventHandler](ICoreWebView2FocusChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="75dfb-248">GotFocus é acionado quando o WebView tem foco.</span><span class="sxs-lookup"><span data-stu-id="75dfb-248">GotFocus fires when WebView got focus.</span></span>

#### <span data-ttu-id="75dfb-249">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="75dfb-249">remove_GotFocus</span></span> 

<span data-ttu-id="75dfb-250">Remover um manipulador de eventos adicionado anteriormente com add_GotFocus.</span><span class="sxs-lookup"><span data-stu-id="75dfb-250">Remove an event handler previously added with add_GotFocus.</span></span>

> <span data-ttu-id="75dfb-251">[remove_GotFocus](#remove_gotfocus)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="75dfb-251">public HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="75dfb-252">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="75dfb-252">add_LostFocus</span></span> 

<span data-ttu-id="75dfb-253">Adicione um manipulador de eventos para o evento LostFocus.</span><span class="sxs-lookup"><span data-stu-id="75dfb-253">Add an event handler for the LostFocus event.</span></span>

> <span data-ttu-id="75dfb-254">Public HRESULT [add_LostFocus](#add_lostfocus)([ICoreWebView2FocusChangedEventHandler](ICoreWebView2FocusChangedEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="75dfb-254">public HRESULT [add_LostFocus](#add_lostfocus)([ICoreWebView2FocusChangedEventHandler](ICoreWebView2FocusChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="75dfb-255">LostFocus é acionado quando o WebView perdeu o foco.</span><span class="sxs-lookup"><span data-stu-id="75dfb-255">LostFocus fires when WebView lost focus.</span></span> <span data-ttu-id="75dfb-256">No caso em que o evento MoveFocusRequested é acionado, o foco continua no WebView quando o evento MoveFocusRequested é acionado.</span><span class="sxs-lookup"><span data-stu-id="75dfb-256">In the case where MoveFocusRequested event is fired, the focus is still on WebView when MoveFocusRequested event fires.</span></span> <span data-ttu-id="75dfb-257">O foco perdido só será acionado depois que o código do aplicativo ou a ação padrão do conjunto de eventos MoveFocusRequested se concentrar em uma exibição de exibição ausente.</span><span class="sxs-lookup"><span data-stu-id="75dfb-257">Lost focus only fires afterwards when app's code or default action of MoveFocusRequested event set focus away from WebView.</span></span>

#### <span data-ttu-id="75dfb-258">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="75dfb-258">remove_LostFocus</span></span> 

<span data-ttu-id="75dfb-259">Remover um manipulador de eventos adicionado anteriormente com add_LostFocus.</span><span class="sxs-lookup"><span data-stu-id="75dfb-259">Remove an event handler previously added with add_LostFocus.</span></span>

> <span data-ttu-id="75dfb-260">[remove_LostFocus](#remove_lostfocus)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="75dfb-260">public HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="75dfb-261">add_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="75dfb-261">add_AcceleratorKeyPressed</span></span> 

<span data-ttu-id="75dfb-262">Adicione um manipulador de eventos para o evento AcceleratorKeyPressed.</span><span class="sxs-lookup"><span data-stu-id="75dfb-262">Add an event handler for the AcceleratorKeyPressed event.</span></span>

> <span data-ttu-id="75dfb-263">Public HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)([ICoreWebView2AcceleratorKeyPressedEventHandler](ICoreWebView2AcceleratorKeyPressedEventHandler.md) \* EventHandler, EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="75dfb-263">public HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)([ICoreWebView2AcceleratorKeyPressedEventHandler](ICoreWebView2AcceleratorKeyPressedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="75dfb-264">AcceleratorKeyPressed é acionado quando uma tecla de aceleração ou combinação de teclas é pressionada ou lançada enquanto o WebView está focalizado.</span><span class="sxs-lookup"><span data-stu-id="75dfb-264">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span> <span data-ttu-id="75dfb-265">Uma tecla é considerada um acelerador se:</span><span class="sxs-lookup"><span data-stu-id="75dfb-265">A key is considered an accelerator if either:</span></span>

1. <span data-ttu-id="75dfb-266">A tecla CTRL ou Alt está sendo mantida no momento ou</span><span class="sxs-lookup"><span data-stu-id="75dfb-266">Ctrl or Alt is currently being held, or</span></span>

1. <span data-ttu-id="75dfb-267">a tecla pressionada não é mapeada para um caractere.</span><span class="sxs-lookup"><span data-stu-id="75dfb-267">the pressed key does not map to a character.</span></span> <span data-ttu-id="75dfb-268">Algumas teclas específicas nunca são consideradas aceleradores, como Shift.</span><span class="sxs-lookup"><span data-stu-id="75dfb-268">A few specific keys are never considered accelerators, such as Shift.</span></span> <span data-ttu-id="75dfb-269">A tecla escape é sempre considerada um acelerador.</span><span class="sxs-lookup"><span data-stu-id="75dfb-269">The Escape key is always considered an accelerator.</span></span>

<span data-ttu-id="75dfb-270">Os eventos chave repetido com repetição causada pela manutenção da tecla para baixo também acionarão esse evento.</span><span class="sxs-lookup"><span data-stu-id="75dfb-270">Autorepeated key events caused by holding the key down will also fire this event.</span></span> <span data-ttu-id="75dfb-271">Você pode filtrá-los verificando os argumentos do evento KeyEventLParam ou PhysicalKeyStatus.</span><span class="sxs-lookup"><span data-stu-id="75dfb-271">You can filter these out by checking the event args' KeyEventLParam or PhysicalKeyStatus.</span></span>

<span data-ttu-id="75dfb-272">No modo de janela, esse manipulador de eventos é chamado sincronicamente.</span><span class="sxs-lookup"><span data-stu-id="75dfb-272">In windowed mode, this event handler is called synchronously.</span></span> <span data-ttu-id="75dfb-273">Até que você chame Handle () nos argumentos do evento ou o manipulador de eventos seja retornado, o processo do navegador será bloqueado e as chamadas COM saída cruzada de processo não funcionarão com RPC_E_CANTCALLOUT_ININPUTSYNCCALL.</span><span class="sxs-lookup"><span data-stu-id="75dfb-273">Until you call Handle() on the event args or the event handler returns, the browser process will be blocked and outgoing cross-process COM calls will fail with RPC_E_CANTCALLOUT_ININPUTSYNCCALL.</span></span> <span data-ttu-id="75dfb-274">No entanto, todos os métodos de API CoreWebView2 funcionarão.</span><span class="sxs-lookup"><span data-stu-id="75dfb-274">All CoreWebView2 API methods will work, however.</span></span>

<span data-ttu-id="75dfb-275">No modo sem janela, o manipulador de eventos é chamado de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="75dfb-275">In windowless mode, the event handler is called asynchronously.</span></span> <span data-ttu-id="75dfb-276">A entrada adicional não entrará em contato com o navegador até que o manipulador de eventos retorne ou manipule () seja chamado, mas o processo do navegador em si não será bloqueado, e as chamadas COM de saída funcionarão normalmente.</span><span class="sxs-lookup"><span data-stu-id="75dfb-276">Further input will not reach the browser until the event handler returns or Handle() is called, but the browser process itself will not be blocked, and outgoing COM calls will work normally.</span></span>

<span data-ttu-id="75dfb-277">É recomendável chamar Handle (TRUE), como o mais cedo possível, se souber que deseja manipular a tecla aceleradora.</span><span class="sxs-lookup"><span data-stu-id="75dfb-277">It is recommended to call Handle(TRUE) as early as you can know that you want to handle the accelerator key.</span></span>

```cpp
    // Register a handler for the AcceleratorKeyPressed event.
    CHECK_FAILURE(m_host->add_AcceleratorKeyPressed(
        Callback<ICoreWebView2AcceleratorKeyPressedEventHandler>(
            [this](
                ICoreWebView2Host* sender,
                ICoreWebView2AcceleratorKeyPressedEventArgs* args) -> HRESULT {
                CORE_WEBVIEW2_KEY_EVENT_KIND kind;
                CHECK_FAILURE(args->get_KeyEventKind(&kind));
                // We only care about key down events.
                if (kind == CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_DOWN ||
                    kind == CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN)
                {
                    UINT key;
                    CHECK_FAILURE(args->get_VirtualKey(&key));
                    // Check if the key is one we want to handle.
                    if (std::function<void()> action =
                            m_appWindow->GetAcceleratorKeyFunction(key))
                    {
                        // Keep the browser from handling this key, whether it's autorepeated or
                        // not.
                        CHECK_FAILURE(args->put_Handled(TRUE));

                        // Filter out autorepeated keys.
                        CORE_WEBVIEW2_PHYSICAL_KEY_STATUS status;
                        CHECK_FAILURE(args->get_PhysicalKeyStatus(&status));
                        if (!status.WasKeyDown)
                        {
                            // Perform the action asynchronously to avoid blocking the
                            // browser process's event queue.
                            m_appWindow->RunAsync(action);
                        }
                    }
                }
                return S_OK;
            })
            .Get(),
        &m_acceleratorKeyPressedToken));
```

#### <span data-ttu-id="75dfb-278">remove_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="75dfb-278">remove_AcceleratorKeyPressed</span></span> 

<span data-ttu-id="75dfb-279">Remover um manipulador de eventos adicionado anteriormente com add_AcceleratorKeyPressed.</span><span class="sxs-lookup"><span data-stu-id="75dfb-279">Remove an event handler previously added with add_AcceleratorKeyPressed.</span></span>

> <span data-ttu-id="75dfb-280">[remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)público HRESULT (token EventRegistrationToken)</span><span class="sxs-lookup"><span data-stu-id="75dfb-280">public HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="75dfb-281">get_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="75dfb-281">get_ParentWindow</span></span> 

<span data-ttu-id="75dfb-282">A janela pai fornecida pelo aplicativo que este WebView usa para renderizar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="75dfb-282">The parent window provided by the app that this WebView is using to render content.</span></span>

> <span data-ttu-id="75dfb-283">Public HRESULT [get_ParentWindow](#get_parentwindow)(HWND \* topLevelWindow)</span><span class="sxs-lookup"><span data-stu-id="75dfb-283">public HRESULT [get_ParentWindow](#get_parentwindow)(HWND \* topLevelWindow)</span></span>

<span data-ttu-id="75dfb-284">Esta API inicialmente retorna a janela passada para CreateCoreWebView2Host.</span><span class="sxs-lookup"><span data-stu-id="75dfb-284">This API initially returns the window passed into CreateCoreWebView2Host.</span></span>

#### <span data-ttu-id="75dfb-285">put_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="75dfb-285">put_ParentWindow</span></span> 

<span data-ttu-id="75dfb-286">Defina a janela pai para o WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-286">Set the parent window for the WebView.</span></span>

> <span data-ttu-id="75dfb-287">[put_ParentWindow](#put_parentwindow)público HRESULT (HWND topLevelWindow)</span><span class="sxs-lookup"><span data-stu-id="75dfb-287">public HRESULT [put_ParentWindow](#put_parentwindow)(HWND topLevelWindow)</span></span>

<span data-ttu-id="75dfb-288">Isso fará com que o WebView retenha o pai da janela para a janela recém fornecida.</span><span class="sxs-lookup"><span data-stu-id="75dfb-288">This will cause the WebView to reparent its window to the newly provided window.</span></span>

#### <span data-ttu-id="75dfb-289">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="75dfb-289">NotifyParentWindowPositionChanged</span></span> 

<span data-ttu-id="75dfb-290">Esta é uma notificação separada da put_Bounds que informa ao WebView o HWND pai (ou qualquer ancestral) movido.</span><span class="sxs-lookup"><span data-stu-id="75dfb-290">This is a notification separate from put_Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>

> <span data-ttu-id="75dfb-291">Public HRESULT [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()</span><span class="sxs-lookup"><span data-stu-id="75dfb-291">public HRESULT [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()</span></span>

<span data-ttu-id="75dfb-292">Isso é necessário para acessibilidade e determinadas caixas de diálogo no WebView para funcionar corretamente.</span><span class="sxs-lookup"><span data-stu-id="75dfb-292">This is needed for accessibility and certain dialogs in WebView to work correctly.</span></span> 

```cpp
    if (message == WM_MOVE || message == WM_MOVING)
    {
        m_host->NotifyParentWindowPositionChanged();
        return true;
    }
```

#### <span data-ttu-id="75dfb-293">Fechar</span><span class="sxs-lookup"><span data-stu-id="75dfb-293">Close</span></span> 

<span data-ttu-id="75dfb-294">Fecha a WebView e limpa a instância do navegador subjacente.</span><span class="sxs-lookup"><span data-stu-id="75dfb-294">Closes the WebView and cleans up the underlying browser instance.</span></span>

> <span data-ttu-id="75dfb-295">público HRESULT [fechar](#close)()</span><span class="sxs-lookup"><span data-stu-id="75dfb-295">public HRESULT [Close](#close)()</span></span>

<span data-ttu-id="75dfb-296">A limpeza do navegador instace liberará os recursos que reabrirão o WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-296">Cleaning up the browser instace will release the resources powering the WebView.</span></span> <span data-ttu-id="75dfb-297">A instância do navegador será encerrada se não houver outros webviews que o usam.</span><span class="sxs-lookup"><span data-stu-id="75dfb-297">The browser instance will be shut down if there are no other WebViews using it.</span></span>

<span data-ttu-id="75dfb-298">Depois de chamar Close, todas as chamadas de método falharão e os manipuladores de eventos deixarão de ser acionados.</span><span class="sxs-lookup"><span data-stu-id="75dfb-298">After calling Close, all method calls will fail and event handlers will stop firing.</span></span> <span data-ttu-id="75dfb-299">Especificamente, a WebView liberará suas referências a seus manipuladores de eventos quando Close for chamado.</span><span class="sxs-lookup"><span data-stu-id="75dfb-299">Specifically, the WebView will release its references to its event handlers when Close is called.</span></span>

<span data-ttu-id="75dfb-300">Fechar é chamado implicitamente quando o CoreWebView2Host perde sua referência final e é destruido.</span><span class="sxs-lookup"><span data-stu-id="75dfb-300">Close is implicitly called when the CoreWebView2Host loses its final reference and is destructed.</span></span> <span data-ttu-id="75dfb-301">Mas é uma prática recomendada chamar o fechamento explicitamente para evitar qualquer ciclo acidental de referências entre o WebView e o código do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="75dfb-301">But it is best practice to explicitly call Close to avoid any accidental cycle of references between the WebView and the app code.</span></span> <span data-ttu-id="75dfb-302">Especificamente, se você capturar uma referência ao WebView em um manipulador de eventos, criará um ciclo de referência entre o WebView e o manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="75dfb-302">Specifically, if you capture a reference to the WebView in an event handler you will create a reference cycle between the WebView and the event handler.</span></span> <span data-ttu-id="75dfb-303">Chamar Close irá interromper esse ciclo liberando todos os manipuladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="75dfb-303">Calling Close will break this cycle by releasing all event handlers.</span></span> <span data-ttu-id="75dfb-304">Mas para evitar essa situação, é recomendável que a chamada seja fechada explicitamente no WebView e não Capture uma referência para o WebView para garantir que o WebView possa ser limpo corretamente.</span><span class="sxs-lookup"><span data-stu-id="75dfb-304">But to avoid this situation it is best practice both to explicitly call Close on the WebView and to not capture a reference to the WebView to ensure the WebView can be cleaned up correctly.</span></span>

```cpp
// Close the WebView and deinitialize related state. This doesn't close the app window.
void AppWindow::CloseWebView(bool cleanupUserDataFolder)
{
    DeleteAllComponents();
    if (m_host)
    {
        m_host->Close();
        m_host = nullptr;
        m_webView = nullptr;
    }
    m_webViewEnvironment = nullptr;
    if (cleanupUserDataFolder)
    {
        // For non-UWP apps, the default user data folder {Executable File Name}.WebView2
        // is in the same directory next to the app executable. If end
        // developers specify userDataFolder during WebView environment
        // creation, they would need to pass in that explicit value here.
        // For more information about userDataFolder:
        // https://docs.microsoft.com/microsoft-edge/hosting/webview2/reference/win32/0-9-488/webview2.idl#createwebview2environmentwithdetails
        WCHAR userDataFolder[MAX_PATH] = L"";
        // Obtain the absolute path for relative paths that include "./" or "../"
        _wfullpath(
            userDataFolder, GetLocalPath(L"WebView2APISample.exe.WebView2").c_str(), MAX_PATH);
        std::wstring userDataFolderPath(userDataFolder);

        std::wstring message = L"Are you sure you want to clean up the user data folder at\n";
        message += userDataFolderPath;
        message += L"\n?\nWarning: This action is not reversible.\n\n";
        message += L"Click No if there are other open WebView instnaces.\n";

        if (MessageBox(m_mainWindow, message.c_str(), L"Cleanup User Data Folder", MB_YESNO) ==
            IDYES)
        {
            CHECK_FAILURE(DeleteFileRecursive(userDataFolderPath));
        }
    }
}
```

#### <span data-ttu-id="75dfb-305">get_CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="75dfb-305">get_CoreWebView2</span></span> 

<span data-ttu-id="75dfb-306">Obtém a CoreWebView2 associada a este CoreWebView2Host.</span><span class="sxs-lookup"><span data-stu-id="75dfb-306">Gets the CoreWebView2 associated with this CoreWebView2Host.</span></span>

> <span data-ttu-id="75dfb-307">Public HRESULT [get_CoreWebView2](#get_corewebview2)([ICoreWebView2](ICoreWebView2.md) \* \* CoreWebView2)</span><span class="sxs-lookup"><span data-stu-id="75dfb-307">public HRESULT [get_CoreWebView2](#get_corewebview2)([ICoreWebView2](ICoreWebView2.md) \*\* coreWebView2)</span></span>

#### <span data-ttu-id="75dfb-308">CORE_WEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="75dfb-308">CORE_WEBVIEW2_MOVE_FOCUS_REASON</span></span> 

<span data-ttu-id="75dfb-309">Motivo para mover o foco.</span><span class="sxs-lookup"><span data-stu-id="75dfb-309">Reason for moving focus.</span></span>

> <span data-ttu-id="75dfb-310">Enumeração [CORE_WEBVIEW2_MOVE_FOCUS_REASON](#core_webview2_move_focus_reason)</span><span class="sxs-lookup"><span data-stu-id="75dfb-310">enum [CORE_WEBVIEW2_MOVE_FOCUS_REASON](#core_webview2_move_focus_reason)</span></span>

 <span data-ttu-id="75dfb-311">Valores</span><span class="sxs-lookup"><span data-stu-id="75dfb-311">Values</span></span>                         | <span data-ttu-id="75dfb-312">Descrições</span><span class="sxs-lookup"><span data-stu-id="75dfb-312">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="75dfb-313">CORE_WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span><span class="sxs-lookup"><span data-stu-id="75dfb-313">CORE_WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span></span>            | <span data-ttu-id="75dfb-314">Configuração de código focalizada no WebView.</span><span class="sxs-lookup"><span data-stu-id="75dfb-314">Code setting focus into WebView.</span></span>
<span data-ttu-id="75dfb-315">CORE_WEBVIEW2_MOVE_FOCUS_REASON_NEXT</span><span class="sxs-lookup"><span data-stu-id="75dfb-315">CORE_WEBVIEW2_MOVE_FOCUS_REASON_NEXT</span></span>            | <span data-ttu-id="75dfb-316">Movendo o foco devido à guia passagem para frente.</span><span class="sxs-lookup"><span data-stu-id="75dfb-316">Moving focus due to Tab traversal forward.</span></span>
<span data-ttu-id="75dfb-317">CORE_WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span><span class="sxs-lookup"><span data-stu-id="75dfb-317">CORE_WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span></span>            | <span data-ttu-id="75dfb-318">Movendo o foco devido a Tabulação de passagem para trás.</span><span class="sxs-lookup"><span data-stu-id="75dfb-318">Moving focus due to Tab traversal backward.</span></span>

#### <span data-ttu-id="75dfb-319">CORE_WEBVIEW2_KEY_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="75dfb-319">CORE_WEBVIEW2_KEY_EVENT_KIND</span></span> 

<span data-ttu-id="75dfb-320">O tipo de evento de chave que disparou um evento AcceleratorKeyPressed.</span><span class="sxs-lookup"><span data-stu-id="75dfb-320">The type of key event that triggered an AcceleratorKeyPressed event.</span></span>

> <span data-ttu-id="75dfb-321">Enumeração [CORE_WEBVIEW2_KEY_EVENT_KIND](#core_webview2_key_event_kind)</span><span class="sxs-lookup"><span data-stu-id="75dfb-321">enum [CORE_WEBVIEW2_KEY_EVENT_KIND](#core_webview2_key_event_kind)</span></span>

 <span data-ttu-id="75dfb-322">Valores</span><span class="sxs-lookup"><span data-stu-id="75dfb-322">Values</span></span>                         | <span data-ttu-id="75dfb-323">Descrições</span><span class="sxs-lookup"><span data-stu-id="75dfb-323">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="75dfb-324">CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_DOWN</span><span class="sxs-lookup"><span data-stu-id="75dfb-324">CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_DOWN</span></span>            | <span data-ttu-id="75dfb-325">Corresponde à mensagem do Window WM_KEYDOWN.</span><span class="sxs-lookup"><span data-stu-id="75dfb-325">Correspond to window message WM_KEYDOWN.</span></span>
<span data-ttu-id="75dfb-326">CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_UP</span><span class="sxs-lookup"><span data-stu-id="75dfb-326">CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_UP</span></span>            | <span data-ttu-id="75dfb-327">Corresponde à mensagem do Window WM_KEYUP.</span><span class="sxs-lookup"><span data-stu-id="75dfb-327">Correspond to window message WM_KEYUP.</span></span>
<span data-ttu-id="75dfb-328">CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN</span><span class="sxs-lookup"><span data-stu-id="75dfb-328">CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN</span></span>            | <span data-ttu-id="75dfb-329">Corresponde à mensagem do Window WM_SYSKEYDOWN.</span><span class="sxs-lookup"><span data-stu-id="75dfb-329">Correspond to window message WM_SYSKEYDOWN.</span></span>
<span data-ttu-id="75dfb-330">CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_UP</span><span class="sxs-lookup"><span data-stu-id="75dfb-330">CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_UP</span></span>            | <span data-ttu-id="75dfb-331">Corresponde à mensagem do Window WM_SYSKEYUP.</span><span class="sxs-lookup"><span data-stu-id="75dfb-331">Correspond to window message WM_SYSKEYUP.</span></span>

#### <span data-ttu-id="75dfb-332">CORE_WEBVIEW2_PHYSICAL_KEY_STATUS</span><span class="sxs-lookup"><span data-stu-id="75dfb-332">CORE_WEBVIEW2_PHYSICAL_KEY_STATUS</span></span> 

<span data-ttu-id="75dfb-333">Uma estrutura que representa as informações empacotadas no LPARAM fornecido a um evento de chave do Win32.</span><span class="sxs-lookup"><span data-stu-id="75dfb-333">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

> <span data-ttu-id="75dfb-334">typedef [CORE_WEBVIEW2_PHYSICAL_KEY_STATUS](#core_webview2_physical_key_status)</span><span class="sxs-lookup"><span data-stu-id="75dfb-334">typedef [CORE_WEBVIEW2_PHYSICAL_KEY_STATUS](#core_webview2_physical_key_status)</span></span>

<span data-ttu-id="75dfb-335">Consulte a documentação do WM_KEYDOWN para obter detalhes em[https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)</span><span class="sxs-lookup"><span data-stu-id="75dfb-335">See the documentation for WM_KEYDOWN for details at [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)</span></span>
