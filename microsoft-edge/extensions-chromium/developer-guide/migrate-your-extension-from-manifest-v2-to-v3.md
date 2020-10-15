---
description: Saiba mais sobre como atualizar a extensão do manifesto v2 para v3
title: Preparar-se para atualizar as extensões do manifesto v2 para v3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/13/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: Edge-Chromium, desenvolvimento de extensões, extensões de borda, extensões do navegador, Complementos, desenvolvedor, manifesto v3, migrar para o manifesto v3
ms.openlocfilehash: 262a5cab54dd23f596791c93ec1238619e247333
ms.sourcegitcommit: 1ad087b00df16fd7718a5d95226de57e29b335e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117823"
---
# <span data-ttu-id="50ba2-104">Preparar-se para atualizar as extensões do manifesto v2 para v3</span><span class="sxs-lookup"><span data-stu-id="50ba2-104">Prepare to update your extensions from Manifest v2 to v3</span></span> 

<span data-ttu-id="50ba2-105">Este documento lista as alterações importantes que estão sendo implementadas como parte do manifesto v3, que é a próxima versão da plataforma de extensões do Chromium.</span><span class="sxs-lookup"><span data-stu-id="50ba2-105">This document lists important changes that's being implemented as part of Manifest v3, which is the next version of the Chromium Extensions platform.</span></span> <span data-ttu-id="50ba2-106">Atualizaremos este documento à medida que a implementação estiver em andamento.</span><span class="sxs-lookup"><span data-stu-id="50ba2-106">We'll update this document as the implementation progresses.</span></span> <span data-ttu-id="50ba2-107">Para obter orientações detalhadas sobre como migrar sua extensão para o manifesto v3, navegue até [migrar para o manifesto v3][Google_Migrate_to_MV3].</span><span class="sxs-lookup"><span data-stu-id="50ba2-107">For detailed guidance on migrating your extension to Manifest v3, navigate to [Migrating to Manifest V3][Google_Migrate_to_MV3].</span></span> 

## <span data-ttu-id="50ba2-108">Código hospedado remotamente</span><span class="sxs-lookup"><span data-stu-id="50ba2-108">Remotely hosted code</span></span>  

<span data-ttu-id="50ba2-109">Hoje, as extensões podem hospedar partes do código remotamente, e não incluí-las como parte do pacote de extensão durante o processo de validação.</span><span class="sxs-lookup"><span data-stu-id="50ba2-109">Today, extensions can host parts of their code remotely, and not include it as part of the extension package during the validation process.</span></span> <span data-ttu-id="50ba2-110">Embora isso ofereça flexibilidade para alterar o código sem reenviar a extensão à loja, o código pode ser explorado após a instalação.</span><span class="sxs-lookup"><span data-stu-id="50ba2-110">While this offers flexibility to change code without resubmitting the extension to the store, the code can be exploited after installation.</span></span> <span data-ttu-id="50ba2-111">Para garantir que os complementos do [Microsoft Edge][EdgeAddons] listem extensões validadas, não estamos permitindo que as extensões usem código hospedado remotamente.</span><span class="sxs-lookup"><span data-stu-id="50ba2-111">To ensure [Microsoft Edge Add-ons][EdgeAddons] lists validated extensions, we're disallowing extensions from using remotely hosted code.</span></span> <span data-ttu-id="50ba2-112">Essa alteração torna as extensões mais seguras.</span><span class="sxs-lookup"><span data-stu-id="50ba2-112">This change makes extensions more secure.</span></span> <span data-ttu-id="50ba2-113">Os desenvolvedores precisarão empacotar e enviar todo o código usado pela extensão para a validação.</span><span class="sxs-lookup"><span data-stu-id="50ba2-113">Developers will need to package and submit all code that's used by the extension for validation.</span></span> <span data-ttu-id="50ba2-114">Como alternativa, os desenvolvedores podem usar a função eval () em um [ambiente em área restrita][sandboxingEval].</span><span class="sxs-lookup"><span data-stu-id="50ba2-114">Alternatively, developers can use the eval() function in a [sandboxed environment][sandboxingEval].</span></span> 

## <span data-ttu-id="50ba2-115">Permissões de host em tempo de execução</span><span class="sxs-lookup"><span data-stu-id="50ba2-115">Run-time host permissions</span></span>  

<span data-ttu-id="50ba2-116">No momento da instalação, as extensões podem solicitar permissões amplas para acessar todos os sites e conteúdo.</span><span class="sxs-lookup"><span data-stu-id="50ba2-116">At installation time, extensions may request blanket permissions to access all sites and content.</span></span> <span data-ttu-id="50ba2-117">Essas permissões permitem que as extensões operem com a intervenção mínima e criem um risco para a privacidade e a segurança do usuário.</span><span class="sxs-lookup"><span data-stu-id="50ba2-117">These permissions allow extensions to operate with minimum intervention, and create a risk to user privacy and security.</span></span> <span data-ttu-id="50ba2-118">Para melhorar a transparência, estamos fornecendo controles para que os usuários permitam ou restringissem o acesso a sites em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="50ba2-118">To improve transparency, we're providing controls for users to allow or restrict access to websites at runtime.</span></span> 

## <span data-ttu-id="50ba2-119">Solicitações entre origens em scripts de conteúdo</span><span class="sxs-lookup"><span data-stu-id="50ba2-119">Cross-origin requests in content scripts</span></span>  

<span data-ttu-id="50ba2-120">Os scripts de conteúdo hoje podem solicitar acesso a qualquer origem, incluindo origens que não são permitidas pelo website.</span><span class="sxs-lookup"><span data-stu-id="50ba2-120">Today content scripts can request access to any origin including origins that aren't allowed by the website.</span></span> <span data-ttu-id="50ba2-121">Esse comportamento divide os princípios de origem cruzada.</span><span class="sxs-lookup"><span data-stu-id="50ba2-121">This behavior breaks cross-origin principles.</span></span> <span data-ttu-id="50ba2-122">No entanto, exige-se que os scripts de conteúdo tenham as mesmas permissões que a página que eles estão injetando, fechando um Loophole de segurança potencial.</span><span class="sxs-lookup"><span data-stu-id="50ba2-122">Going forward, we'll require content scripts to have the same permissions as the page they're injected into, closing a potential security loophole.</span></span> <span data-ttu-id="50ba2-123">Para executar solicitações entre origens, você precisará usar scripts em segundo plano para redirecionar respostas para scripts de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="50ba2-123">To perform cross-origin requests, you'll need to use background scripts to relay responses back to content scripts.</span></span> <span data-ttu-id="50ba2-124">Essas alterações estão disponíveis e atrás de um sinalizador.</span><span class="sxs-lookup"><span data-stu-id="50ba2-124">These changes are available and behind a flag.</span></span> <span data-ttu-id="50ba2-125">Para obter mais informações, navegue até este [documento][CORS].</span><span class="sxs-lookup"><span data-stu-id="50ba2-125">For more information, navigate to this [document][CORS].</span></span> 

## <span data-ttu-id="50ba2-126">API de solicitação da Web</span><span class="sxs-lookup"><span data-stu-id="50ba2-126">Web Request API</span></span>  

<span data-ttu-id="50ba2-127">Estamos substituindo a [API de solicitação da Web][WebRequestAPI] pela [API declarativa de solicitação de rede][DeclarativeNetRequestAPI], mas continuará a manter os recursos de observação da API de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="50ba2-127">We're replacing [Web Request API][WebRequestAPI] with [Declarative Net Request API][DeclarativeNetRequestAPI], but will continue to keep Web Request API's observational capabilities.</span></span> <span data-ttu-id="50ba2-128">Exceto em alguns cenários específicos em que os recursos de observação da API de solicitação da Web são exigidos pela extensão, recomendamos usar apenas as APIs DNR.</span><span class="sxs-lookup"><span data-stu-id="50ba2-128">Except in some specific scenarios where observational capabilities of the Web Request API are required by the extension, we recommend using the DNR APIs only.</span></span> <span data-ttu-id="50ba2-129">Acreditamos que essa alteração terá um impacto positivo nas extensões que usam recursos declarativos avançados de recursos.</span><span class="sxs-lookup"><span data-stu-id="50ba2-129">We believe this change will have positive impact on extensions that use feature-rich declarative capabilities.</span></span> <span data-ttu-id="50ba2-130">À medida que mais extensões se transformam em APIs do DNR, essa alteração melhorará a privacidade do usuário, que contribui para melhorar a confiança no uso de extensões.</span><span class="sxs-lookup"><span data-stu-id="50ba2-130">As more extensions transition to the DNR APIs, this change will improve user privacy, which contributes to enhancing trust in the use of extensions.</span></span>
<span data-ttu-id="50ba2-131">As empresas podem continuar a usar o comportamento de bloqueio da API de solicitação da Web para extensões gerenciadas por meio de políticas corporativas.</span><span class="sxs-lookup"><span data-stu-id="50ba2-131">Enterprises can continue to use the blocking behavior of the Web Request API for extensions managed through enterprise policies.</span></span> <span data-ttu-id="50ba2-132">Para obter mais informações sobre as políticas de extensão, navegue até [Microsoft Edge – políticas][MicrosoftEdgePolicies].</span><span class="sxs-lookup"><span data-stu-id="50ba2-132">For more information about extension policies, navigate to [Microsoft Edge – Policies][MicrosoftEdgePolicies].</span></span> 

## <span data-ttu-id="50ba2-133">Trabalhadores de serviço em segundo plano</span><span class="sxs-lookup"><span data-stu-id="50ba2-133">Background service workers</span></span>  
 
<span data-ttu-id="50ba2-134">Os funcionários de serviço estão disponíveis para teste no Canárias.</span><span class="sxs-lookup"><span data-stu-id="50ba2-134">Service workers are available for testing in Canary.</span></span> <span data-ttu-id="50ba2-135">Para migrar suas extensões de páginas de plano de fundo para trabalhadores do serviço, consulte [migrando de páginas de plano de fundo para trabalhadores do serviço][ServiceWorkers].</span><span class="sxs-lookup"><span data-stu-id="50ba2-135">To migrate your extensions from background pages to service workers, refer to [Migrating from Background Pages to Service Workers][ServiceWorkers].</span></span> <span data-ttu-id="50ba2-136">Estamos avaliando & investigando o impacto que essa alteração traz para desenvolvedores e usuários.</span><span class="sxs-lookup"><span data-stu-id="50ba2-136">We're evaluating & investigating the impact that this change brings to both developers and users.</span></span> <span data-ttu-id="50ba2-137">Vamos adicionar mais detalhes sobre essa alteração para este documento no futuro.</span><span class="sxs-lookup"><span data-stu-id="50ba2-137">We'll add  additional details on this change to this document in the future.</span></span> 

## <span data-ttu-id="50ba2-138">Quando essas alterações estarão disponíveis no Microsoft Edge?</span><span class="sxs-lookup"><span data-stu-id="50ba2-138">When will these changes be available in Microsoft Edge?</span></span>

<span data-ttu-id="50ba2-139">A implementação da API de solicitação líquida da rede atual está disponível em nossos canais estáveis e beta.</span><span class="sxs-lookup"><span data-stu-id="50ba2-139">The current declarative net request API implementation is available in our Stable and Beta channels.</span></span> <span data-ttu-id="50ba2-140">Os desenvolvedores podem testar essas alterações e fornecer comentários.</span><span class="sxs-lookup"><span data-stu-id="50ba2-140">Developers can test these changes, and provide feedback.</span></span> <span data-ttu-id="50ba2-141">Vamos contribuir para os esforços de desenvolvimento e investigar outras alterações.</span><span class="sxs-lookup"><span data-stu-id="50ba2-141">We'll contribute to development efforts and investigate further changes.</span></span> 

| <span data-ttu-id="50ba2-142">Nome do canal</span><span class="sxs-lookup"><span data-stu-id="50ba2-142">Channel name</span></span> | <span data-ttu-id="50ba2-143">Descrição</span><span class="sxs-lookup"><span data-stu-id="50ba2-143">Description</span></span> |
|:--- |:--- |  
| <span data-ttu-id="50ba2-144">Microsoft Edge 84 estável</span><span class="sxs-lookup"><span data-stu-id="50ba2-144">Microsoft Edge 84 Stable</span></span> | <span data-ttu-id="50ba2-145">A API DNR está disponível para teste</span><span class="sxs-lookup"><span data-stu-id="50ba2-145">DNR API is available for testing</span></span> |  
| <span data-ttu-id="50ba2-146">Microsoft Edge 85 beta</span><span class="sxs-lookup"><span data-stu-id="50ba2-146">Microsoft Edge 85 Beta</span></span> | <span data-ttu-id="50ba2-147">O suporte à modificação de cabeçalho está disponível</span><span class="sxs-lookup"><span data-stu-id="50ba2-147">Header modification support is available</span></span>| 

<span data-ttu-id="50ba2-148">Quando as alterações são feitas no Chromium, compartilhamos cronogramas para que os desenvolvedores possam atualizar seu código e republicar extensões na loja.</span><span class="sxs-lookup"><span data-stu-id="50ba2-148">When the changes are made to Chromium, we'll share timelines so that developers can update their code and republish extensions to the store.</span></span> 

<span data-ttu-id="50ba2-149">Continuaremos a publicação de atualizações em nosso blog.</span><span class="sxs-lookup"><span data-stu-id="50ba2-149">We'll continue publishing updates on our blog.</span></span> <span data-ttu-id="50ba2-150">Você pode enviar seus comentários sobre essas alterações por meio do [TechCommunity][TechCommunity].</span><span class="sxs-lookup"><span data-stu-id="50ba2-150">You can provide your feedback on these changes through [TechCommunity][TechCommunity].</span></span>

<!-- links -->  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/ "Complementos do Microsoft Edge"  
[MicrosoftBlog]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/  
[MicrosoftEdgePolicies]: https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions 

[TechCommunity]: https://techcommunity.microsoft.com/t5/articles/manifest-v3-changes-are-now-available-in-microsoft-edge/m-p/1780254 "Comunidade técnica"  


[Google_Migrate_to_MV3]: https://developer.chrome.com/extensions/migrating_to_manifest_v3   
[SandboxingEval]: https://developer.chrome.com/apps/sandboxingEval "Usar eval em extensões Chrome. Com segurança."
[CORS]: https://www.chromium.org/Home/chromium-security/extension-content-script-fetches "Alterações em solicitações entre origens em scripts de conteúdo de extensão"
[WebRequestAPI]: https://developer.chrome.com/extensions/webRequest "API de solicitação da Web"  
[DeclarativeNetRequestAPI]: https://developer.chrome.com/extensions/declarativeNetRequest/ "API de solicitação de rede declarativa"
[ServiceWorkers]:  https://developers.chrome.com/extensions/migrating_to_service_workers

