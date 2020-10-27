---
description: Saiba como usar o Microsoft Edge DevTools para exibir e alterar a CSS de uma página CSS.
title: Inspecionar a grade CSS no Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, desenvolvimento na Web, ferramentas F12, devtools
ms.openlocfilehash: 150aea57aa676580b554cc74292671ed567a0a2c
ms.sourcegitcommit: 6e2b26d41a0aa56ac34e6edc7dddd852ddb415b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2020
ms.locfileid: "11133917"
---
# <span data-ttu-id="9c745-104">Inspecionar grade CSS</span><span class="sxs-lookup"><span data-stu-id="9c745-104">Inspect CSS Grid</span></span>  

<span data-ttu-id="9c745-105">Este artigo orienta você na identificação de grades CSS em um site e na depuração de problemas de layout de grade usando sobreposições de grade personalizáveis.</span><span class="sxs-lookup"><span data-stu-id="9c745-105">This article walks you through identifying CSS grids on a website and debugging grid layout issues using customizable grid overlays.</span></span>  

<span data-ttu-id="9c745-106">Os exemplos usados nos números deste artigo são retirados das páginas da Web a seguir.</span><span class="sxs-lookup"><span data-stu-id="9c745-106">The examples used in the figures in this article are taken from the following webpages.</span></span>  

*   [<span data-ttu-id="9c745-107">Caixa de frutas</span><span class="sxs-lookup"><span data-stu-id="9c745-107">Fruit box</span></span>][JecFyiDemoCssGridFruit]  
*   [<span data-ttu-id="9c745-108">Caixa de lanche</span><span class="sxs-lookup"><span data-stu-id="9c745-108">Snack box</span></span>][JecFyiDemoCssGridSnack]  

## <span data-ttu-id="9c745-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="9c745-109">Before you begin</span></span>  

<span data-ttu-id="9c745-110">A grade CSS é um poderoso paradigma de layout para a Web.</span><span class="sxs-lookup"><span data-stu-id="9c745-110">CSS Grid is a powerful layout paradigm for the web.</span></span>  <span data-ttu-id="9c745-111">Um ótimo lugar para começar a aprender sobre a grade CSS e os muitos recursos é o [Guia de layout de grade CSS][MdnCssGridLayout] em MDN.</span><span class="sxs-lookup"><span data-stu-id="9c745-111">A great place to get started learning about CSS Grid and the many features is the [CSS Grid Layout guide][MdnCssGridLayout] on MDN.</span></span>  

## <span data-ttu-id="9c745-112">Descobrir grades CSS</span><span class="sxs-lookup"><span data-stu-id="9c745-112">Discover CSS grids</span></span>  

<span data-ttu-id="9c745-113">Quando um elemento HTML na sua página tiver `display: grid` ou `display: inline-grid` aplicado a ele, um `grid` emblema será exibido ao lado dele no painel de [elementos][DevtoolsGuideChromiumOpen] .</span><span class="sxs-lookup"><span data-stu-id="9c745-113">When an HTML element on your page has `display: grid` or `display: inline-grid` applied to it, a `grid` badge is displayed next to it in the [Elements][DevtoolsGuideChromiumOpen] panel.</span></span>  

:::image type="complex" source="../media/grid-discover-grid.msft.png" alt-text="Descobrir grade" lightbox="../media/grid-discover-grid.msft.png":::
   <span data-ttu-id="9c745-115">Descobrir grade</span><span class="sxs-lookup"><span data-stu-id="9c745-115">Discover grid</span></span>  
:::image-end:::  

<span data-ttu-id="9c745-116">Selecione o selo para alternar a exibição de uma sobreposição de grade na página.</span><span class="sxs-lookup"><span data-stu-id="9c745-116">Select the badge to toggle the display of a grid overlay on the page.</span></span>  <span data-ttu-id="9c745-117">A sobreposição aparece sobre o elemento, disposta como uma grade para exibir a posição das linhas de grade e as faixas:</span><span class="sxs-lookup"><span data-stu-id="9c745-117">The overlay appears over the element, laid out like a grid to display the position of the grid lines and tracks:</span></span>  

:::image type="complex" source="../media/grid-highlight-grid.msft.png" alt-text="Descobrir grade" lightbox="../media/grid-highlight-grid.msft.png":::
   <span data-ttu-id="9c745-119">Alternar o selo da grade</span><span class="sxs-lookup"><span data-stu-id="9c745-119">Toggle grid badge</span></span>  
:::image-end:::  

<span data-ttu-id="9c745-120">Abrir o painel de **layout** .</span><span class="sxs-lookup"><span data-stu-id="9c745-120">Open the **Layout** pane.</span></span>  <span data-ttu-id="9c745-121">Quando as grades são incluídas em uma página, o painel de **layout** inclui uma seção de **grade** contendo várias opções para exibir as grades.</span><span class="sxs-lookup"><span data-stu-id="9c745-121">When grids are included on a page, the **Layout** pane includes a **Grid** section containing a number of options for viewing the grids.</span></span>  

:::image type="complex" source="../media/grid-layout-pane.msft.png" alt-text="Descobrir grade" lightbox="../media/grid-layout-pane.msft.png":::
   <span data-ttu-id="9c745-123">Painel de **layout**</span><span class="sxs-lookup"><span data-stu-id="9c745-123">**Layout** pane</span></span>  
:::image-end:::  

<span data-ttu-id="9c745-124">A seção **grade** no painel **layout** contém as 2 subseções a seguir.</span><span class="sxs-lookup"><span data-stu-id="9c745-124">The **Grid** section in the **Layout** pane contains the following 2 sub-sections.</span></span>  

*   <span data-ttu-id="9c745-125">Configurações de exibição de sobreposição</span><span class="sxs-lookup"><span data-stu-id="9c745-125">Overlay display settings</span></span>  
*   <span data-ttu-id="9c745-126">Sobreposições de grade</span><span class="sxs-lookup"><span data-stu-id="9c745-126">Grid overlays</span></span>  

<!--todo: @zoher verify the details for each of the sub-sections.  -->  

## <span data-ttu-id="9c745-127">Configurações de exibição de sobreposição</span><span class="sxs-lookup"><span data-stu-id="9c745-127">Overlay display settings</span></span>  

<span data-ttu-id="9c745-128">As **configurações de exibição de sobreposição** consistem nas duas partes a seguir.</span><span class="sxs-lookup"><span data-stu-id="9c745-128">The **Overlay display settings** consists of following 2 parts.</span></span>  

*   <span data-ttu-id="9c745-129">Escolha uma das opções a seguir no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="9c745-129">Choose one of the following options from the dropdown menu.</span></span>  
    
    | <span data-ttu-id="9c745-130">Opção de linha</span><span class="sxs-lookup"><span data-stu-id="9c745-130">Line option</span></span> | <span data-ttu-id="9c745-131">Detalhes</span><span class="sxs-lookup"><span data-stu-id="9c745-131">Details</span></span> |  
    |:--- |:--- |  
    | **<span data-ttu-id="9c745-132">Ocultar rótulos de linha</span><span class="sxs-lookup"><span data-stu-id="9c745-132">Hide line labels</span></span>** | <span data-ttu-id="9c745-133">Ocultar os rótulos das linhas para cada sobreposição de grade.</span><span class="sxs-lookup"><span data-stu-id="9c745-133">Hide the labels of the lines for each grid overlay.</span></span> |  
    | **<span data-ttu-id="9c745-134">Mostrar números de linha</span><span class="sxs-lookup"><span data-stu-id="9c745-134">Show line numbers</span></span>** | <span data-ttu-id="9c745-135">Exiba os números das linhas para cada sobreposição de grade \ (selecionada por padrão \).</span><span class="sxs-lookup"><span data-stu-id="9c745-135">Display the numbers of the lines for each grid overlay \(selected by default\).</span></span> |  
    | **<span data-ttu-id="9c745-136">Mostrar nomes de linha</span><span class="sxs-lookup"><span data-stu-id="9c745-136">Show line names</span></span>** | <span data-ttu-id="9c745-137">Exiba os nomes das linhas para cada sobreposição de grade quando os nomes forem fornecidos.</span><span class="sxs-lookup"><span data-stu-id="9c745-137">Display the names of the lines for each grid overlay when names are provided.</span></span> |  
    
*  <span data-ttu-id="9c745-138">Selecione a caixa de seleção ao lado das opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="9c745-138">Choose the checkbox next the following options.</span></span>  
    
    | <span data-ttu-id="9c745-139">Opção</span><span class="sxs-lookup"><span data-stu-id="9c745-139">Option</span></span> | <span data-ttu-id="9c745-140">Detalhes</span><span class="sxs-lookup"><span data-stu-id="9c745-140">Details</span></span> |  
    |:--- |:--- |  
    | **<span data-ttu-id="9c745-141">Mostrar tamanhos de faixas</span><span class="sxs-lookup"><span data-stu-id="9c745-141">Show track sizes</span></span>**  | <span data-ttu-id="9c745-142">Exibir \ (ou ocultar \) os tamanhos das faixas.</span><span class="sxs-lookup"><span data-stu-id="9c745-142">Display \(or hide\) the sizes of the tracks.</span></span> |  
    | **<span data-ttu-id="9c745-143">Mostrar nomes de área</span><span class="sxs-lookup"><span data-stu-id="9c745-143">Show area names</span></span>** | <span data-ttu-id="9c745-144">Exiba \ (ou oculte \) os nomes da área, quando os nomes são fornecidos.</span><span class="sxs-lookup"><span data-stu-id="9c745-144">Display \(or hide\) the names of the area, when names are provided.</span></span> |  
    | **<span data-ttu-id="9c745-145">Estender linhas de grade</span><span class="sxs-lookup"><span data-stu-id="9c745-145">Extend grid lines</span></span>** | <span data-ttu-id="9c745-146">Exibe \ (ou oculta \) as extensões das dimensões da grade ao longo de cada eixo.</span><span class="sxs-lookup"><span data-stu-id="9c745-146">Displays \(or hides\) the extensions of the grid dimensions along each axis.</span></span>  <span data-ttu-id="9c745-147">Por padrão, as linhas de grade são mostradas apenas dentro do elemento com `display: grid` ou `display: inline-grid` CSS definidas nela.</span><span class="sxs-lookup"><span data-stu-id="9c745-147">By default, grid lines are only shown inside the element with `display: grid` or `display: inline-grid` CSS set on it.</span></span> |  
    
<span data-ttu-id="9c745-148">As seções a seguir fornecem detalhes para cada uma das **configurações de exibição de sobreposição**.</span><span class="sxs-lookup"><span data-stu-id="9c745-148">The following sections provide details for each of the **Overlay display settings**.</span></span>  

### <span data-ttu-id="9c745-149">Mostrar números de linha</span><span class="sxs-lookup"><span data-stu-id="9c745-149">Show line numbers</span></span>  

<span data-ttu-id="9c745-150">Por padrão, os números de linha positivos e negativos são exibidos na sobreposição de grade.</span><span class="sxs-lookup"><span data-stu-id="9c745-150">By default, the positive and negative line numbers are displayed on the grid overlay.</span></span>  

<span data-ttu-id="9c745-151">Para obter mais informações sobre números negativos na sobreposição de grade, navegue até [posicionamento baseado em linha com grade CSS][MdnLineBasedPlacementCssGrid].</span><span class="sxs-lookup"><span data-stu-id="9c745-151">For more information about negative numbers in the grid overlay, navigate to [Line-based placement with CSS Grid][MdnLineBasedPlacementCssGrid].</span></span>  

:::image type="complex" source="../media/grid-show-line-numbers.msft.png" alt-text="Descobrir grade" lightbox="../media/grid-show-line-numbers.msft.png":::
   <span data-ttu-id="9c745-153">Exibir números de linha</span><span class="sxs-lookup"><span data-stu-id="9c745-153">Display line numbers</span></span>  
:::image-end:::  

### <span data-ttu-id="9c745-154">Ocultar rótulos de linha</span><span class="sxs-lookup"><span data-stu-id="9c745-154">Hide line labels</span></span>  

<span data-ttu-id="9c745-155">Selecione **ocultar rótulos de linha** para ocultar os números de linha.</span><span class="sxs-lookup"><span data-stu-id="9c745-155">Select **Hide line labels** to hide the line numbers.</span></span>  

:::image type="complex" source="../media/grid-hide-line-labels.msft.png" alt-text="Descobrir grade" lightbox="../media/grid-hide-line-labels.msft.png":::
   <span data-ttu-id="9c745-157">Ocultar rótulos de linha</span><span class="sxs-lookup"><span data-stu-id="9c745-157">Hide line labels</span></span>  
:::image-end:::  

### <span data-ttu-id="9c745-158">Mostrar nomes de linha</span><span class="sxs-lookup"><span data-stu-id="9c745-158">Show line names</span></span>  

<!--todo: @rachel verify the link and text for line name -->  
<span data-ttu-id="9c745-159">Para obter mais informações sobre nomes de linha na sobreposição de grade, navegue até [layout usando linhas de grade nomeadas][MdnLayoutUsingNamedGridLines].</span><span class="sxs-lookup"><span data-stu-id="9c745-159">For more information about line names in the grid overlay, navigate to [Layout using named grid lines][MdnLayoutUsingNamedGridLines].</span></span>  

<span data-ttu-id="9c745-160">Selecione **Mostrar nomes de linha** para exibir os nomes das linhas em vez de números.</span><span class="sxs-lookup"><span data-stu-id="9c745-160">Select **Show line names** to view the line names instead of numbers.</span></span>  <span data-ttu-id="9c745-161">No exemplo, 4 linhas têm nomes: `left` ,, `middle1` `middle2` e `right` .</span><span class="sxs-lookup"><span data-stu-id="9c745-161">In the example, 4 lines have names: `left`, `middle1`, `middle2`, and `right`.</span></span>  

<!--In the demo, **orange** element spans from left to right, with `grid-column: left` and `grid-column: right` CSS.  Showing line names makes it easier to visualize the start and end position of the element.  -->  

:::image type="complex" source="../media/grid-show-line-names.msft.png" alt-text="Descobrir grade" lightbox="../media/grid-show-line-names.msft.png":::
   **<span data-ttu-id="9c745-163">Mostrar nomes de linha</span><span class="sxs-lookup"><span data-stu-id="9c745-163">Show line names</span></span>**  
:::image-end:::  

### <span data-ttu-id="9c745-164">Mostrar tamanhos de faixas</span><span class="sxs-lookup"><span data-stu-id="9c745-164">Show track sizes</span></span>  

<span data-ttu-id="9c745-165">Habilite a caixa de seleção **Mostrar tamanhos de faixas** para exibir os tamanhos de faixa da grade.</span><span class="sxs-lookup"><span data-stu-id="9c745-165">Enable the **Show track sizes** checkbox to view the track sizes of the grid.</span></span>  

<span data-ttu-id="9c745-166">DevTools exibe `[authored size]` e `[computed size]` em cada rótulo de linha.</span><span class="sxs-lookup"><span data-stu-id="9c745-166">DevTools displays `[authored size]` and `[computed size]` in each line label.</span></span>  

| <span data-ttu-id="9c745-167">Size</span><span class="sxs-lookup"><span data-stu-id="9c745-167">Size</span></span> | <span data-ttu-id="9c745-168">Detalhes</span><span class="sxs-lookup"><span data-stu-id="9c745-168">Details</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="9c745-169">tamanho da criação</span><span class="sxs-lookup"><span data-stu-id="9c745-169">authored size</span></span>** | <span data-ttu-id="9c745-170">O tamanho definido em stylesheet \ (omitido se não definido \).</span><span class="sxs-lookup"><span data-stu-id="9c745-170">The size defined in stylesheet \(omitted if not defined\).</span></span> |  
| **<span data-ttu-id="9c745-171">tamanho calculado</span><span class="sxs-lookup"><span data-stu-id="9c745-171">computed size</span></span>** | <span data-ttu-id="9c745-172">O tamanho real na tela.</span><span class="sxs-lookup"><span data-stu-id="9c745-172">The actual size on screen.</span></span> |  

<span data-ttu-id="9c745-173">Na demonstração, os `snack-box` tamanhos das colunas são definidos no `grid-template-columns:1fr 2fr;` CSS.</span><span class="sxs-lookup"><span data-stu-id="9c745-173">In the demo, the `snack-box` column sizes are defined in the `grid-template-columns:1fr 2fr;` CSS.</span></span>  <span data-ttu-id="9c745-174">Portanto, os rótulos de linha da coluna exibem os tamanhos criados e calculados.</span><span class="sxs-lookup"><span data-stu-id="9c745-174">Therefore, the column line labels display both authored and computed sizes.</span></span>  

| <span data-ttu-id="9c745-175">Tamanho da faixa</span><span class="sxs-lookup"><span data-stu-id="9c745-175">Track size</span></span> | <span data-ttu-id="9c745-176">Tamanho da criação</span><span class="sxs-lookup"><span data-stu-id="9c745-176">Authored size</span></span> | <span data-ttu-id="9c745-177">Tamanho calculado</span><span class="sxs-lookup"><span data-stu-id="9c745-177">Computed size</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="9c745-178">**1fr** &#x2022; **96.66 PX**</span><span class="sxs-lookup"><span data-stu-id="9c745-178">**1fr** &#x2022; **96.66px**</span></span> | <span data-ttu-id="9c745-179">1fr</span><span class="sxs-lookup"><span data-stu-id="9c745-179">1fr</span></span> | <span data-ttu-id="9c745-180">96.66 px</span><span class="sxs-lookup"><span data-stu-id="9c745-180">96.66px</span></span> |  
| <span data-ttu-id="9c745-181">**2fr** &#x2022; **193.32 px**</span><span class="sxs-lookup"><span data-stu-id="9c745-181">**2fr** &#x2022; **193.32px**</span></span> | <span data-ttu-id="9c745-182">2fr</span><span class="sxs-lookup"><span data-stu-id="9c745-182">2fr</span></span> | <span data-ttu-id="9c745-183">193.32 px</span><span class="sxs-lookup"><span data-stu-id="9c745-183">193.32px</span></span> |  

<span data-ttu-id="9c745-184">Os rótulos de linha de linha exibem apenas os tamanhos calculados, pois não há tamanhos de linha definidos na folha de estilos.</span><span class="sxs-lookup"><span data-stu-id="9c745-184">The row line labels display only computed sizes, since there are no row sizes defined in the stylesheet.</span></span>  

| <span data-ttu-id="9c745-185">Tamanho da faixa</span><span class="sxs-lookup"><span data-stu-id="9c745-185">Track size</span></span> | <span data-ttu-id="9c745-186">Tamanho da criação</span><span class="sxs-lookup"><span data-stu-id="9c745-186">Authored size</span></span> | <span data-ttu-id="9c745-187">Tamanho calculado</span><span class="sxs-lookup"><span data-stu-id="9c745-187">Computed size</span></span> |  
|:--- |:--- |:--- |  
| **<span data-ttu-id="9c745-188">80px</span><span class="sxs-lookup"><span data-stu-id="9c745-188">80px</span></span>** | &nbsp;| <span data-ttu-id="9c745-189">80px</span><span class="sxs-lookup"><span data-stu-id="9c745-189">80px</span></span> |  
| **<span data-ttu-id="9c745-190">80px</span><span class="sxs-lookup"><span data-stu-id="9c745-190">80px</span></span>** | &nbsp;| <span data-ttu-id="9c745-191">80px</span><span class="sxs-lookup"><span data-stu-id="9c745-191">80px</span></span> |  

:::image type="complex" source="../media/grid-show-track-sizes.msft.png" alt-text="Descobrir grade" lightbox="../media/grid-show-track-sizes.msft.png":::
   **<span data-ttu-id="9c745-193">Mostrar tamanhos de faixas</span><span class="sxs-lookup"><span data-stu-id="9c745-193">Show track sizes</span></span>**  
:::image-end:::  

### <span data-ttu-id="9c745-194">Mostrar nomes de área</span><span class="sxs-lookup"><span data-stu-id="9c745-194">Show area names</span></span>  

<span data-ttu-id="9c745-195">Para exibir os nomes das áreas, habilite a caixa de seleção **Mostrar nomes de área** .</span><span class="sxs-lookup"><span data-stu-id="9c745-195">To view the area names, enable the **Show area names** checkbox.</span></span>  <span data-ttu-id="9c745-196">No exemplo, há três áreas na grade: **superior**, **bottom1** e **bottom2**.</span><span class="sxs-lookup"><span data-stu-id="9c745-196">In the example, there are 3 areas in the grid: **top**, **bottom1** and **bottom2**.</span></span>  

:::image type="complex" source="../media/grid-show-area-names.msft.png" alt-text="Descobrir grade" lightbox="../media/grid-show-area-names.msft.png":::
   **<span data-ttu-id="9c745-198">Mostrar nomes de área</span><span class="sxs-lookup"><span data-stu-id="9c745-198">Show area names</span></span>**  
:::image-end:::  

### <span data-ttu-id="9c745-199">Estender linhas de grade</span><span class="sxs-lookup"><span data-stu-id="9c745-199">Extend grid lines</span></span>  

<span data-ttu-id="9c745-200">Habilite a caixa de seleção **estender linhas de grade** para estender as linhas de grade para a borda da viewport ao longo de cada eixo.</span><span class="sxs-lookup"><span data-stu-id="9c745-200">Enable the **Extend grid lines** checkbox to extend the grid lines to the edge of the viewport along each axis.</span></span>  

:::image type="complex" source="../media/grid-extend-grid-lines.msft.png" alt-text="Descobrir grade" lightbox="../media/grid-extend-grid-lines.msft.png":::
   **<span data-ttu-id="9c745-202">Estender linhas de grade</span><span class="sxs-lookup"><span data-stu-id="9c745-202">Extend grid lines</span></span>**  
:::image-end:::  

## <span data-ttu-id="9c745-203">Sobreposições de grade</span><span class="sxs-lookup"><span data-stu-id="9c745-203">Grid overlays</span></span>  

<span data-ttu-id="9c745-204">A seção **sobreposições de grade** contém uma lista de grades que estão presentes na página, cada uma com uma caixa de seleção, juntamente com várias opções.</span><span class="sxs-lookup"><span data-stu-id="9c745-204">The **Grid overlays** section contains a list of grids that are present on the page, each with a checkbox, along with various options.</span></span>  

### <span data-ttu-id="9c745-205">Habilitar modos de exibição de sobreposição de várias grades</span><span class="sxs-lookup"><span data-stu-id="9c745-205">Enable overlay views of multiple grids</span></span>  

<!--todo: @zoher verify and provide updates -->  

<span data-ttu-id="9c745-206">Para exibir a grade de sobreposição para várias grades, escolha a caixa de seleção ao lado de cada nome da grade.</span><span class="sxs-lookup"><span data-stu-id="9c745-206">To display the overlay grid for multiple grids, choose the checkbox next to each name of the grid.</span></span>  <span data-ttu-id="9c745-207">No exemplo, há duas sobreposições de grade habilitadas que são representadas com cores diferentes.</span><span class="sxs-lookup"><span data-stu-id="9c745-207">In the example, there are 2 grid overlays enabled that are each represented with different colors.</span></span>  

*   `main`  
*   `div.snack-box`  
    
:::image type="complex" source="../media/grid-grid-overlays.msft.png" alt-text="Descobrir grade" lightbox="../media/grid-grid-overlays.msft.png":::
   <span data-ttu-id="9c745-209">Habilitar modos de exibição de sobreposição de várias grades</span><span class="sxs-lookup"><span data-stu-id="9c745-209">Enable overlay views of multiple grids</span></span>  
:::image-end:::  

### <span data-ttu-id="9c745-210">Personalizar a cor da sobreposição de grade</span><span class="sxs-lookup"><span data-stu-id="9c745-210">Customize the grid overlay color</span></span>  

<span data-ttu-id="9c745-211">Para abrir o seletor de cores e personalizar a cor da sobreposição de grade, escolha a caixa ao lado do nome da sobreposição de grade.</span><span class="sxs-lookup"><span data-stu-id="9c745-211">To open the color picker and customize the grid overlay color, choose the box next to the name of the grid overlay.</span></span>  

:::image type="complex" source="../media/grid-grid-overlays-color.msft.png" alt-text="Descobrir grade" lightbox="../media/grid-grid-overlays-color.msft.png":::
   <span data-ttu-id="9c745-213">Personalizar a cor da sobreposição de grade</span><span class="sxs-lookup"><span data-stu-id="9c745-213">Customize the grid overlay color</span></span>  
:::image-end:::  

### <span data-ttu-id="9c745-214">Realçar a grade</span><span class="sxs-lookup"><span data-stu-id="9c745-214">Highlight the grid</span></span>  

<span data-ttu-id="9c745-215">Para realçar o elemento HTML no painel **elementos** e rolar para ele na página da Web, escolha o **elemento Mostrar no painel elementos** \ ( ![ Mostrar elemento no ícone do painel elementos ][ImageShowElementInElementsPanelIcon] \) ícone.</span><span class="sxs-lookup"><span data-stu-id="9c745-215">To highlight the HTML element in the **Elements** panel and scroll to it on the webpage, choose the **Show element in the Elements panel** \(![Show element in the Elements panel icon][ImageShowElementInElementsPanelIcon]\) icon.</span></span>  

:::image type="complex" source="../media/grid-grid-overlays-highlight.msft.png" alt-text="Descobrir grade" lightbox="../media/grid-grid-overlays-highlight.msft.png":::
   <span data-ttu-id="9c745-217">Realçar a grade</span><span class="sxs-lookup"><span data-stu-id="9c745-217">Highlight the grid</span></span>  
:::image-end:::  

## <span data-ttu-id="9c745-218">Entrar em contato com a equipe Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="9c745-218">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageShowElementInElementsPanelIcon]: ../media/show-element-in-element-panel-icon.msft.png  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open.md "Abrir o Microsoft Edge DevTools | Documentos da Microsoft"  

[JecFyiDemoCssGridFruit]: https://jec.fyi/demo/css-grid-fruit "Grade CSS | JEC. FYI"  
[JecFyiDemoCssGridSnack]: https://jec.fyi/demo/css-grid-snack "Grade CSS | JEC. FYI"  

[MdnCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "Layout de grade CSS | MDN"  
[MdnLayoutUsingNamedGridLines]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Layout_using_Named_Grid_Lines "Layout usando linhas de grade nomeadas | MDN"  
[MdnLineBasedPlacementCssGrid]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid "Posicionamento baseado em linhas com grade CSS | MDN"  

> [!NOTE]
> <span data-ttu-id="9c745-225">Partes desta página são modificações com base no trabalho criado e [compartilhado pelo Google][GoogleSitePolicies] e usados de acordo com os termos descritos na [licença internacional Creative Commons][CCA4IL]rereference 4,0 International.</span><span class="sxs-lookup"><span data-stu-id="9c745-225">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9c745-226">A página original é encontrada [aqui](https://developers.google.com/web/tools/chrome-devtools/css/grid) e é criada por [Jecelyn Yeen][JecelynYeen] \ (defensora do desenvolvedor, Chrome devtools \).</span><span class="sxs-lookup"><span data-stu-id="9c745-226">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/grid) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Licença Creative Commons][CCby4Image]][CCA4IL]  
<span data-ttu-id="9c745-228">Esse trabalho é licenciado sob uma [Licença Attribution 4.0 International (CC BY 4.0) da Creative Commons][CCA4IL].</span><span class="sxs-lookup"><span data-stu-id="9c745-228">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  