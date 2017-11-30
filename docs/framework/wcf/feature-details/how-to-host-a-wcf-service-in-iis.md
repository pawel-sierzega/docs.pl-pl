---
title: "Instrukcje: Hostowanie usługi WCF w programie IIS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
caps.latest.revision: "28"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4fb3957543d6a0fcf3b375f9cb43ae089ac9d600
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="32a25-102">Instrukcje: Hostowanie usługi WCF w programie IIS</span><span class="sxs-lookup"><span data-stu-id="32a25-102">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="32a25-103">W tym temacie przedstawiono podstawowe czynności wymagane do utworzenia [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] usługi hostowanej w Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="32a25-103">This topic outlines the basic steps required to create a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="32a25-104">W tym temacie założono zapoznali się z usługami IIS i zrozumieć, jak używać narzędzia zarządzania usług IIS do tworzenia i zarządzania aplikacjami usług IIS.</span><span class="sxs-lookup"><span data-stu-id="32a25-104">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="32a25-105">Usługi IIS zobacz [Internetowe usługi informacyjne](http://go.microsoft.com/fwlink/?LinkId=132449).</span><span class="sxs-lookup"><span data-stu-id="32a25-105"> IIS see [Internet Information Services](http://go.microsoft.com/fwlink/?LinkId=132449).</span></span> <span data-ttu-id="32a25-106">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usługi, który jest uruchamiany w środowisku usług IIS w pełni korzysta funkcje usług IIS, takie jak odtwarzanie procesów, bezczynności zamykania, monitorowanie kondycji procesów i aktywacji opartej na wiadomość.</span><span class="sxs-lookup"><span data-stu-id="32a25-106">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="32a25-107">Ta opcja hostingu wymaga usług IIS zostać prawidłowo skonfigurowane, ale nie wymaga się, że każdy kod hostingu można zapisywać w ramach aplikacji.</span><span class="sxs-lookup"><span data-stu-id="32a25-107">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="32a25-108">Można użyć tylko z transportem HTTP hostowanie usług IIS.</span><span class="sxs-lookup"><span data-stu-id="32a25-108">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="32a25-109">jak [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] i [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interakcji, zobacz [usługi WCF i platformy ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="32a25-109"> how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interact, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="32a25-110">Konfigurowanie zabezpieczeń, zobacz [zabezpieczeń](../../../../docs/framework/wcf/feature-details/security.md).</span><span class="sxs-lookup"><span data-stu-id="32a25-110"> configuring security, see [Security](../../../../docs/framework/wcf/feature-details/security.md).</span></span>  
  
 <span data-ttu-id="32a25-111">Dla źródła kopię w tym przykładzie [IIS Hosting przy użyciu kodu wbudowanego](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span><span class="sxs-lookup"><span data-stu-id="32a25-111">For the source copy of this example, see [IIS Hosting Using Inline Code](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="32a25-112">Tworzenie usługi hostowanej przez Internetowe usługi informacyjne</span><span class="sxs-lookup"><span data-stu-id="32a25-112">To create a service hosted by IIS</span></span>  
  
1.  <span data-ttu-id="32a25-113">Upewnij się, że usługi IIS jest zainstalowana i uruchomiona na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="32a25-113">Confirm that IIS is installed and running on your computer.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="32a25-114">Instalowanie i konfigurowanie usług IIS zobacz [Instalowanie i konfigurowanie usług IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=132128)</span><span class="sxs-lookup"><span data-stu-id="32a25-114"> installing and configuring IIS see [Installing and Configuring IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=132128)</span></span>  
  
2.  <span data-ttu-id="32a25-115">Utwórz nowy folder o nazwie "IISHostedCalcService" plików aplikacji, upewnij się, że [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ma dostęp do zawartości folderu i narzędzia zarządzania usług IIS umożliwia utworzenie nowej aplikacji usług IIS, która jest fizycznie zlokalizowany w tej aplikacji katalog.</span><span class="sxs-lookup"><span data-stu-id="32a25-115">Create a new folder for your application files called "IISHostedCalcService", ensure that [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="32a25-116">Podczas tworzenia aliasu katalogu aplikacji do użytku "IISHostedCalc".</span><span class="sxs-lookup"><span data-stu-id="32a25-116">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3.  <span data-ttu-id="32a25-117">Utwórz nowy plik o nazwie "service.svc" w katalogu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="32a25-117">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="32a25-118">Edytowanie tego pliku przez dodanie poniższego @ServiceHost elementu.</span><span class="sxs-lookup"><span data-stu-id="32a25-118">Edit this file by adding the following @ServiceHost element.</span></span>  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>  
    ```  
  
4.  <span data-ttu-id="32a25-119">Utwórz App_Code podkatalogu w katalogu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="32a25-119">Create an App_Code subdirectory within the application directory.</span></span>  
  
5.  <span data-ttu-id="32a25-120">Utwórz plik kodu o nazwie Service.cs w podkatalogu App_Code.</span><span class="sxs-lookup"><span data-stu-id="32a25-120">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6.  <span data-ttu-id="32a25-121">Dodaj następujące instrukcje using do początku pliku Service.cs.</span><span class="sxs-lookup"><span data-stu-id="32a25-121">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7.  <span data-ttu-id="32a25-122">Dodaj następujące deklaracji przestrzeni nazw przy użyciu instrukcji.</span><span class="sxs-lookup"><span data-stu-id="32a25-122">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8.  <span data-ttu-id="32a25-123">Definiowanie kontraktu usługi wewnątrz deklaracji przestrzeni nazw, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="32a25-123">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="32a25-124">Implementowanie kontraktu usługi, po usługi definicja kontraktu, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="32a25-124">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="32a25-125">Utwórz plik o nazwie "Web.config" w katalogu aplikacji i Dodaj następujący kod konfiguracji do pliku.</span><span class="sxs-lookup"><span data-stu-id="32a25-125">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="32a25-126">W czasie wykonywania [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastruktury używa tych informacji do utworzenia punktu końcowego, który aplikacje klienckie mogą komunikować się z.</span><span class="sxs-lookup"><span data-stu-id="32a25-126">At runtime, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]      
  
     <span data-ttu-id="32a25-127">W tym przykładzie jawnie określa punkty końcowe w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="32a25-127">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="32a25-128">Jeśli nie dodawaj żadnych punktów końcowych do usługi, środowisko uruchomieniowe dodaje domyślne punkty końcowe.</span><span class="sxs-lookup"><span data-stu-id="32a25-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="32a25-129">punkty końcowe, powiązania i zachowania domyślnego, zobacz [uproszczony konfiguracji](../../../../docs/framework/wcf/simplified-configuration.md) i [uproszczona konfiguracja usług WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="32a25-129"> default endpoints, bindings, and behaviors see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="32a25-130">Aby upewnić się, że usługa działa prawidłowo, otwórz wystąpienie programu Internet Explorer i przejdź do adresu URL usługi:`http://localhost/IISHostedCalc/Service.svc`</span><span class="sxs-lookup"><span data-stu-id="32a25-130">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="32a25-131">Przykład</span><span class="sxs-lookup"><span data-stu-id="32a25-131">Example</span></span>  
 <span data-ttu-id="32a25-132">Poniżej znajduje się, że Kalkulator usługi hostowanej pełną listę kod dla usług IIS.</span><span class="sxs-lookup"><span data-stu-id="32a25-132">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)] 
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)] 
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="32a25-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="32a25-133">See Also</span></span>  
 [<span data-ttu-id="32a25-134">Hostowanie przez Internetowe usługi informacyjne</span><span class="sxs-lookup"><span data-stu-id="32a25-134">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [<span data-ttu-id="32a25-135">Usługi hostingowe</span><span class="sxs-lookup"><span data-stu-id="32a25-135">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="32a25-136">Usługi WCF i platformy ASP.NET</span><span class="sxs-lookup"><span data-stu-id="32a25-136">WCF Services and ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [<span data-ttu-id="32a25-137">Zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="32a25-137">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
 [<span data-ttu-id="32a25-138">Windows Server AppFabric funkcje hostingu</span><span class="sxs-lookup"><span data-stu-id="32a25-138">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)