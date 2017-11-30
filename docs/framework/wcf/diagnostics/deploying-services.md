---
title: "Wdrażanie usług"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 75069b00fa07078ff0eb2d49e64f046d5415d154
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-services"></a><span data-ttu-id="307d2-102">Wdrażanie usług</span><span class="sxs-lookup"><span data-stu-id="307d2-102">Deploying Services</span></span>
<span data-ttu-id="307d2-103">W tym temacie opisano sposób wdrażania [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] aplikacji w środowisku czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="307d2-103">This topic describes how you can deploy a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="307d2-104">Wybieranie środowiska macierzystego dla aplikacji</span><span class="sxs-lookup"><span data-stu-id="307d2-104">Choosing the Hosting Environment for Your Application</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="307d2-105">usługi są przeznaczone do uruchamiania w dowolnym procesie systemu Windows obsługuje kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="307d2-105"> services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="307d2-106">Staje się aktywny, usługa musi być hostowany w środowisku czasu wykonywania, która tworzy go i kontroluje jego kontekstu i okresem istnienia.</span><span class="sxs-lookup"><span data-stu-id="307d2-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="307d2-107">Hosting zakres opcje uruchamiania wewnątrz najprostszym aplikacji konsoli do środowiska serwera, takich jak usługi systemu Windows, Internet Information Services (IIS), lub w ramach procesu roboczego zarządzane przez usługę aktywacji systemu Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="307d2-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="307d2-108">Aby przejrzeć różne opcje hostingu dla Twojego [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikacji, zobacz [Hosting usług](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="307d2-108">To review the different hosting options for your [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="307d2-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="307d2-109">See Also</span></span>  
 [<span data-ttu-id="307d2-110">Hosting</span><span class="sxs-lookup"><span data-stu-id="307d2-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)  
 [<span data-ttu-id="307d2-111">Usługi hostingowe</span><span class="sxs-lookup"><span data-stu-id="307d2-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)