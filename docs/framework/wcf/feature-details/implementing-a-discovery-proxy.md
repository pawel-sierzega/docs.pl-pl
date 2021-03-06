---
title: Implementowanie serwera proxy odnajdywania
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2996eb07c883947210c48471a2c60ba49495566d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-a-discovery-proxy"></a>Implementowanie serwera proxy odnajdywania
W tej sekcji opisano kroki wymagane do wdrożenia serwera proxy odnajdywania. Serwer proxy odnajdywania jest usługi autonomicznej, który zawiera repozytorium usług. Klienci mogą wykonywać kwerendę serwera proxy odnajdywania można znaleźć wykrywalny usługi Serwer proxy jest znane. Jak serwer proxy jest wypełniane przy użyciu usługi jest implementujący. Na przykład serwera proxy odnajdywania można połączyć się z istniejącą repozytorium usługi i stał się wykrywalny, administrator może użyć interfejsu API zarządzania, aby dodać wykrywalny usługi na serwerze proxy lub serwera proxy odnajdywania może używać funkcji anonsu do tych informacji Zaktualizuj swojej wewnętrznej pamięci podręcznej.  
  
 Implementacja WCF udostępnia klas podstawowych, które umożliwiają łatwe tworzenie serwera proxy. Mogą wykorzystywać te interfejsy API do tworzenia serwera Proxy odnajdywania na podstawie istniejących repozytorium.  
  
 Serwera proxy odnajdywania zaimplementowana w tym miejscu jest podobnie jak inne usługi WCF, możesz również ustawić serwera proxy odnajdywania wykrywalny, a klienci mogą zlokalizować jego punktów końcowych.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Instrukcje: wdrażanie serwera proxy odnajdywania](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 Opisuje sposób wdrożenia serwera proxy odnajdywania.  
  
 [Instrukcje: implementowanie odnajdywanej usługi rejestrowanej za pomocą serwera proxy odnajdywania](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 Opisuje sposób wdrożenia wykrywalny [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usługi, która rejestruje z serwera proxy odnajdywania.  
  
 [Instrukcje: wdrażanie aplikacji klienta znajdującej usługę przy użyciu serwera proxy odnajdywania](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)  
 Opisuje sposób wdrożenia [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikacji klienckiej, która używa serwera proxy odnajdywania do wyszukiwania dla usługi.  
  
 [Instrukcje: testowanie serwera proxy odnajdywania](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md)  
 Opisuje sposoby testowania kod napisany w poprzednim trzy tematy.  
  
## <a name="see-also"></a>Zobacz też  
 [Odnajdywanie w programie WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery.md)  
 [Instrukcje: programowe dodawanie możliwości odnajdywania do usługi i klienta WCF](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
