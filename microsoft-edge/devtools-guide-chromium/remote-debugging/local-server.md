---
title: Acessar servidores locais
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: Microsoft Edge, desenvolvimento na Web, Ferramentas F12, devtools
ms.openlocfilehash: c038e8b7f612f4c2185ae1c62a08d32b72f8aa0d
ms.sourcegitcommit: 33663cd7838dddee86228dde469a5e9551bddb02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611823"
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





# <span data-ttu-id="0b95f-103">Acessar servidores locais</span><span class="sxs-lookup"><span data-stu-id="0b95f-103">Access Local Servers</span></span>   




<span data-ttu-id="0b95f-104">Hospede um site em um servidor Web do computador de desenvolvimento e acesse o conteúdo de um dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="0b95f-104">Host a site on a development machine web server, then access the content from an Android device.</span></span>  

<span data-ttu-id="0b95f-105">Com um cabo USB e o Microsoft Edge DevTools, execute um site a partir de um computador de desenvolvimento e, em seguida, exiba o site em um dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="0b95f-105">With a USB cable and Microsoft Edge DevTools, run a site from a development machine and then view the site on an Android device.</span></span>  

### <span data-ttu-id="0b95f-106">Resumo</span><span class="sxs-lookup"><span data-stu-id="0b95f-106">Summary</span></span>  

*   <span data-ttu-id="0b95f-107">O encaminhamento de porta permite que você veja o conteúdo hospedado pelo servidor Web em execução em seu computador de desenvolvimento em seu dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="0b95f-107">Port forwarding enables you to view content hosted by the web server running in your development machine on your Android device.</span></span>  
*   <span data-ttu-id="0b95f-108">Se seu servidor Web estiver usando um domínio personalizado, configure seu dispositivo Android para acessar o conteúdo nesse domínio com mapeamento de domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="0b95f-108">If your web server is using a custom domain, set up your Android device to access the content at that domain with custom domain mapping.</span></span>  

## <span data-ttu-id="0b95f-109">Configurar o encaminhamento de porta</span><span class="sxs-lookup"><span data-stu-id="0b95f-109">Set up port forwarding</span></span>   

<span data-ttu-id="0b95f-110">O encaminhamento de porta permite que seu dispositivo Android acesse o conteúdo que está sendo hospedado no servidor Web em execução na máquina de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="0b95f-110">Port forwarding enables your Android device to access content that is being hosted on the web server running in your development machine.</span></span>  <span data-ttu-id="0b95f-111">O encaminhamento de porta funciona criando uma porta TCP de escuta em seu dispositivo Android que mapeia para uma porta TCP em seu computador de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="0b95f-111">Port forwarding works by creating a listening TCP port on your Android device that maps to a TCP port on your development machine.</span></span>  <span data-ttu-id="0b95f-112">O tráfego entre as portas trafegam pela conexão USB entre seu dispositivo Android e seu computador de desenvolvimento, portanto, a conexão não depende da configuração da sua rede.</span><span class="sxs-lookup"><span data-stu-id="0b95f-112">Traffic between the ports travel through the USB connection between your Android device and development machine, so the connection does not depend on your network configuration.</span></span>  

<span data-ttu-id="0b95f-113">Para habilitar o encaminhamento de porta:</span><span class="sxs-lookup"><span data-stu-id="0b95f-113">To enable port forwarding:</span></span>  

1.  <span data-ttu-id="0b95f-114">Configure a [depuração remota][RemoteDebuggingGettingStarted] entre sua máquina de desenvolvimento e seu dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="0b95f-114">Set up [remote debugging][RemoteDebuggingGettingStarted] between your development machine and your Android device.</span></span>  <span data-ttu-id="0b95f-115">Quando terminar, você verá seu dispositivo Android no menu à esquerda da caixa de diálogo **inspecionar dispositivos** e um indicador de status **conectado** .</span><span class="sxs-lookup"><span data-stu-id="0b95f-115">When you are finished, you should see your Android device in the left-hand menu of the **Inspect Devices** dialog and a **Connected** status indicator.</span></span>  
1.  <span data-ttu-id="0b95f-116">Na caixa de diálogo **inspecionar dispositivos** no devtools, habilite o **encaminhamento de porta**.</span><span class="sxs-lookup"><span data-stu-id="0b95f-116">In the **Inspect Devices** dialog in DevTools, enable **Port forwarding**.</span></span>  
1.  <span data-ttu-id="0b95f-117">Selecione **Adicionar regra**.</span><span class="sxs-lookup"><span data-stu-id="0b95f-117">Select **Add rule**.</span></span>  
    
    > ##### <span data-ttu-id="0b95f-118">Figura 1</span><span class="sxs-lookup"><span data-stu-id="0b95f-118">Figure 1</span></span>  
    > <span data-ttu-id="0b95f-119">Adicionando uma regra de encaminhamento de porta</span><span class="sxs-lookup"><span data-stu-id="0b95f-119">Adding a port forwarding rule</span></span>  
    > ![Adicionando uma regra de encaminhamento de porta][ImageAddRule]  
    
1.  <span data-ttu-id="0b95f-121">Na caixa de texto **porta do dispositivo** à esquerda, insira o `localhost` número da porta da qual você deseja poder acessar o site no seu dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="0b95f-121">In the **Device port** textbox on the left, enter the `localhost` port number from which you want to be able to access the site on your Android device.</span></span>  <span data-ttu-id="0b95f-122">Por exemplo, se você quisesse acessar o site de `localhost:5000` Enter `5000` .</span><span class="sxs-lookup"><span data-stu-id="0b95f-122">For example, if you wanted to access the site from `localhost:5000` enter `5000`.</span></span>  
1.  <span data-ttu-id="0b95f-123">Na caixa de texto **local do endereço** à direita, digite o endereço IP ou o nome do host em que seu site está hospedado no servidor Web em execução na máquina de desenvolvimento, seguido do número da porta.</span><span class="sxs-lookup"><span data-stu-id="0b95f-123">In the **Local address** textbox on the right, enter the IP address or hostname on which your site is hosted on the web server running in your development machine, followed by the port number.</span></span>  <span data-ttu-id="0b95f-124">Por exemplo, se o seu site estiver sendo executado durante a `localhost:7331` entrada `localhost:7331` .</span><span class="sxs-lookup"><span data-stu-id="0b95f-124">For example, if your site is running on `localhost:7331` enter `localhost:7331`.</span></span>  
1.  <span data-ttu-id="0b95f-125">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0b95f-125">Select **Add**.</span></span>  

<span data-ttu-id="0b95f-126">O encaminhamento de portas agora está configurado.</span><span class="sxs-lookup"><span data-stu-id="0b95f-126">Port forwarding is now set up.</span></span>  <span data-ttu-id="0b95f-127">Consulte o indicador de status para que a porta encaminhe na guia do seu dispositivo na caixa de diálogo **inspecionar dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="0b95f-127">See the status indicator for the port forward on the tab on your device within the **Inspect Devices** dialog.</span></span>  

> ##### <span data-ttu-id="0b95f-128">Figura 2</span><span class="sxs-lookup"><span data-stu-id="0b95f-128">Figure 2</span></span>  
> <span data-ttu-id="0b95f-129">Status de encaminhamento de porta</span><span class="sxs-lookup"><span data-stu-id="0b95f-129">Port forwarding status</span></span>  
> ![Status de encaminhamento de porta][ImagePortForwardingStatus]  

<span data-ttu-id="0b95f-131">Para exibir o conteúdo, abra o Microsoft Edge no seu dispositivo Android e vá para a `localhost` porta que você especificou no campo **porta do dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="0b95f-131">To view the content, open up Microsoft Edge on your Android device and go to the `localhost` port that you specified in the **Device port** field.</span></span>  <span data-ttu-id="0b95f-132">Por exemplo, se você inseriu `5000` no campo, acesse `localhost:5000` .</span><span class="sxs-lookup"><span data-stu-id="0b95f-132">For example, if you entered `5000` in the field, visit `localhost:5000`.</span></span>  

## <span data-ttu-id="0b95f-133">Mapear para domínios locais personalizados</span><span class="sxs-lookup"><span data-stu-id="0b95f-133">Map to custom local domains</span></span>   

<span data-ttu-id="0b95f-134">O mapeamento de domínio personalizado permite exibir o conteúdo em um dispositivo Android de um servidor Web na máquina de desenvolvimento que está usando um domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="0b95f-134">Custom domain mapping enables you to view content on an Android device from a web server on your development machine that is using a custom domain.</span></span>  

<span data-ttu-id="0b95f-135">Por exemplo, suponha que seu site usa uma biblioteca JavaScript de terceiros que só funciona no domínio `microsoft-edge.devtools` .</span><span class="sxs-lookup"><span data-stu-id="0b95f-135">For example, suppose that your site uses a third-party JavaScript library that only works on the domain `microsoft-edge.devtools`.</span></span>  <span data-ttu-id="0b95f-136">Portanto, você cria uma entrada em seu `hosts` arquivo em seu computador de desenvolvimento para mapear esse domínio para `localhost` \ (por exemplo, `127.0.0.1 microsoft-edge.devtools` \).</span><span class="sxs-lookup"><span data-stu-id="0b95f-136">So, you create an entry in your `hosts` file on your development machine to map this domain to `localhost` \(for example, `127.0.0.1 microsoft-edge.devtools`\).</span></span>  <span data-ttu-id="0b95f-137">Depois de configurar o mapeamento de domínio personalizado e o encaminhamento de porta, exiba o site em seu dispositivo Android na URL `microsoft-edge.devtools` .</span><span class="sxs-lookup"><span data-stu-id="0b95f-137">After setting up custom domain mapping and port forwarding, view the site on your Android device at the URL `microsoft-edge.devtools`.</span></span>  

### <span data-ttu-id="0b95f-138">Configurar o encaminhamento de porta para o servidor proxy</span><span class="sxs-lookup"><span data-stu-id="0b95f-138">Set up port forwarding to proxy server</span></span>  

<span data-ttu-id="0b95f-139">Para mapear um domínio personalizado, você deve executar um servidor proxy em seu computador de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="0b95f-139">To map a custom domain you must run a proxy server on your development machine.</span></span>  <span data-ttu-id="0b95f-140">Exemplos de servidores proxy são [Charles][CharlesWebDebuggingProxy], [Lula][SquidOptimisingWebDelivery]e [Fiddler][FiddlerWebDebuggingProxy].</span><span class="sxs-lookup"><span data-stu-id="0b95f-140">Examples of proxy servers are [Charles][CharlesWebDebuggingProxy], [Squid][SquidOptimisingWebDelivery], and [Fiddler][FiddlerWebDebuggingProxy].</span></span>  

<span data-ttu-id="0b95f-141">Para configurar o encaminhamento de porta para um proxy:</span><span class="sxs-lookup"><span data-stu-id="0b95f-141">To set up port forwarding to a proxy:</span></span>  

1.  <span data-ttu-id="0b95f-142">Execute o servidor proxy e grave a porta que ele está usando.</span><span class="sxs-lookup"><span data-stu-id="0b95f-142">Run the proxy server and record the port that it is using.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="0b95f-143">O servidor proxy e o servidor Web devem ser executados em diferentes portas.</span><span class="sxs-lookup"><span data-stu-id="0b95f-143">The proxy server and your web server must run on different ports.</span></span>  
    
1.  <span data-ttu-id="0b95f-144">Configure o [encaminhamento de porta](#set-up-port-forwarding) para seu dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="0b95f-144">Set up [port forwarding](#set-up-port-forwarding) to your Android device.</span></span>  <span data-ttu-id="0b95f-145">Para o campo **endereço local** , insira `localhost:` seguido pela porta em que o servidor proxy está em execução.</span><span class="sxs-lookup"><span data-stu-id="0b95f-145">For the **local address** field, enter `localhost:` followed by the port that your proxy server is running on.</span></span>  <span data-ttu-id="0b95f-146">Por exemplo, se estiver em execução na porta `8000` , acesse `localhost:8000` .</span><span class="sxs-lookup"><span data-stu-id="0b95f-146">For example, if it is running on port `8000`, visit `localhost:8000`.</span></span>  <span data-ttu-id="0b95f-147">No campo **porta do dispositivo** , digite o número que você deseja que seu dispositivo Android Ouça, como `3333` .</span><span class="sxs-lookup"><span data-stu-id="0b95f-147">In the **device port** field enter the number that you want your Android device to listen on, such as `3333`.</span></span>  

### <span data-ttu-id="0b95f-148">Definir configurações de proxy em seu dispositivo</span><span class="sxs-lookup"><span data-stu-id="0b95f-148">Configure proxy settings on your device</span></span>  

<span data-ttu-id="0b95f-149">Em seguida, você precisa configurar seu dispositivo Android para se comunicar com o servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="0b95f-149">Next, you need to configure your Android device to communicate with the proxy server.</span></span>  

1.  <span data-ttu-id="0b95f-150">Em seu dispositivo Android, vá para **configurações**  >  **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="0b95f-150">On your Android device go to **Settings** > **Wi-Fi**.</span></span>  
1.  <span data-ttu-id="0b95f-151">Longo-pressione o nome da rede à qual você está conectado no momento.</span><span class="sxs-lookup"><span data-stu-id="0b95f-151">Long-press the name of the network to which you are currently connected.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="0b95f-152">As configurações de proxy se aplicam por rede.</span><span class="sxs-lookup"><span data-stu-id="0b95f-152">Proxy settings apply per network.</span></span>  
    
1.  <span data-ttu-id="0b95f-153">Selecione **Modificar rede**.</span><span class="sxs-lookup"><span data-stu-id="0b95f-153">Select **Modify network**.</span></span>  
1.  <span data-ttu-id="0b95f-154">Selecione **Opções avançadas**.</span><span class="sxs-lookup"><span data-stu-id="0b95f-154">Select **Advanced options**.</span></span>  <span data-ttu-id="0b95f-155">As configurações de proxy são exibidas.</span><span class="sxs-lookup"><span data-stu-id="0b95f-155">The proxy settings display.</span></span>  
1.  <span data-ttu-id="0b95f-156">Selecione o menu **proxy** e selecione **manual**.</span><span class="sxs-lookup"><span data-stu-id="0b95f-156">Select the **Proxy** menu and select **Manual**.</span></span>  
1.  <span data-ttu-id="0b95f-157">Para o campo **hostname do proxy** , insira `localhost` .</span><span class="sxs-lookup"><span data-stu-id="0b95f-157">For the **Proxy hostname** field, enter `localhost`.</span></span>  
1.  <span data-ttu-id="0b95f-158">Para o campo **porta de proxy** , insira o número da porta que você inseriu para a porta do **dispositivo** na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="0b95f-158">For the **Proxy port** field, enter the port number that you entered for **device port** in the previous section.</span></span>  
1.  <span data-ttu-id="0b95f-159">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0b95f-159">Select **Save**.</span></span>  

<span data-ttu-id="0b95f-160">Com essas configurações, seu dispositivo encaminha todas as suas solicitações para o proxy no seu computador de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="0b95f-160">With these settings, your device forwards all of its requests to the proxy on your development machine.</span></span>  <span data-ttu-id="0b95f-161">O proxy faz solicitações em nome do seu dispositivo, portanto, as solicitações para o seu domínio local personalizado são corretamente resolvidas.</span><span class="sxs-lookup"><span data-stu-id="0b95f-161">The proxy makes requests on behalf of your device, so requests to your customized local domain are properly resolved.</span></span>  

<span data-ttu-id="0b95f-162">Acesse agora os domínios personalizados em seu dispositivo Android, exatamente como no computador de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="0b95f-162">Now access custom domains on your Android device just like on the development machine.</span></span>  

<span data-ttu-id="0b95f-163">Se seu servidor Web estiver fora de uma porta não padrão, lembre-se de especificar a porta ao solicitar o conteúdo do seu dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="0b95f-163">If your web server is running off of a non-standard port, remember to specify the port when requesting the content from your Android device.</span></span>  <span data-ttu-id="0b95f-164">Por exemplo, se seu servidor Web estiver usando o domínio personalizado `microsoft-edge.devtools` na porta `7331` , quando você exibir o site do seu dispositivo Android, você deverá usar a URL `microsoft-edge.devtools:7331` .</span><span class="sxs-lookup"><span data-stu-id="0b95f-164">For example, if your web server is using the custom domain `microsoft-edge.devtools` on port `7331`, when you view the site from your Android device you should be using the URL `microsoft-edge.devtools:7331`.</span></span>  

> [!TIP]
> <span data-ttu-id="0b95f-165">Para retomar a navegação normal, lembre-se de reverter as configurações de proxy em seu dispositivo Android após desconectar-se da máquina de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="0b95f-165">To resume normal browsing, remember to revert the proxy settings on your Android device after you disconnect from the development machine.</span></span>  

<!--  -->  



<!-- image links -->  

[ImageAddRule]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png "Figura 1: adicionando uma regra de encaminhamento de porta"  
[ImagePortForwardingStatus]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png "Figura 2: status de encaminhamento de porta"  

<!-- links -->  

[RemoteDebuggingGettingStarted]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "Introdução à depuração remota de dispositivos Android"  

[CharlesWebDebuggingProxy]: https://www.charlesproxy.com "Proxy de depuração da Web Charles"  

[SquidOptimisingWebDelivery]: https://www.squid-cache.org "Lula: Optimising Web Delivery"  

[FiddlerWebDebuggingProxy]: https://www.telerik.com/fiddler "Fiddler – proxy de depuração de Web gratuito"  

> [!NOTE]
> <span data-ttu-id="0b95f-172">Partes desta página são modificações com base no trabalho criado e [compartilhado pelo Google][GoogleSitePolicies] e usados de acordo com os termos descritos na [licença internacional Creative Commons][CCA4IL]rereference 4,0 International.</span><span class="sxs-lookup"><span data-stu-id="0b95f-172">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0b95f-173">A página original é encontrada [aqui](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server) e é criada por [Kayce Basques][KayceBasques] \ (redator técnico, Chrome devtools \ & Lighthouse \) e [Meggin Kearney][MegginKearney] \ (Tech Writer \).</span><span class="sxs-lookup"><span data-stu-id="0b95f-173">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Licença Creative Commons][CCby4Image]][CCA4IL]  
<span data-ttu-id="0b95f-175">Esse trabalho é licenciado sob uma [Licença Attribution 4.0 International (CC BY 4.0) da Creative Commons][CCA4IL].</span><span class="sxs-lookup"><span data-stu-id="0b95f-175">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  