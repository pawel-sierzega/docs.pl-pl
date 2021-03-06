---
title: "Migrowanie usług sieci Web na platformie ASP.NET do programu WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f90f7dd508e2ff4058b787fc29d152abc18f24fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="migrating-aspnet-web-services-to-wcf"></a>Migrowanie usług sieci Web na platformie ASP.NET do programu WCF
Program ASP.NET udostępnia biblioteki klas .NET Framework i narzędzia do tworzenia usług sieci Web, a także urządzenia do hostingu usług w ramach usługi Internet Information Services (IIS). [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]udostępnia biblioteki klas .NET Framework, narzędzia i hostingu urządzenia do włączania jednostek oprogramowania do komunikowania się przy użyciu protokołów, w tym używanych przez usługi sieci Web.  Migrowanie usług sieci Web ASP.NET do [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pozwala aplikacjom korzystać z nowych funkcji i ulepszeń, które są unikatowe dla [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]ma kilka zalet ważne względem usługi sieci Web ASP.NET. Narzędzia usług sieci Web ASP.NET są przeznaczone wyłącznie na potrzeby tworzenia usług sieci Web [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] udostępnia narzędzia, które można użyć w przypadku oprogramowania jednostek muszą być wprowadzane do komunikowania się ze sobą. Zmniejszy to liczbę technologie wymagane do uwzględnienia scenariusze komunikacji innego oprogramowania, które z kolei zostanie obniżony koszt zasobów rozwoju oprogramowania, a także czas wymagany do ukończenia oprogramowania deweloperów rozwoju projektów.  
  
 Nawet w przypadku projektów rozwoju usług sieci Web [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] obsługuje więcej sieci Web usługi protokołów niż Obsługa usług sieci Web ASP.NET. Te dodatkowe protokoły zapewniają bardziej zaawansowanych rozwiązań obejmujące, między inne rzeczy, niezawodne sesje i transakcji.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]obsługuje protokoły więcej do transportu wiadomości niż usługi sieci Web ASP.NET. Usługi sieci Web programu ASP.NET obsługują tylko wysyłanie wiadomości przy użyciu protokołu HTTP (Hypertext Transfer). [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]obsługuje wysyłanie wiadomości przy użyciu protokołu HTTP, a także Transmission Control Protocol (TCP), nazwanych potoków i usługi kolejkowania wiadomości firmy Microsoft (MSMQ). Większe znaczenie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] może zostać rozszerzony do obsługi dodatkowych protokołów. W związku z tym utworzony przy użyciu oprogramowania [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mogą być dostosowywane do współdziała z szeroką gamę innego oprogramowania, zwiększając możliwości zwrot z inwestycji.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]Wdrażanie aplikacji i zarządzanie nimi niż usług sieci Web ASP.NET zapewnia znacznie bardziej zaawansowane funkcje urządzeń. Oprócz system konfiguracji, który ma także ASP.NET, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] oferuje edytora konfiguracji, śledzenie działania od nadawcy do odbiorników i powrotem przy użyciu dowolnej liczby pośredników, przeglądarka śledzenia, rejestrowanie komunikatów, przeważająca liczbę wydajności liczniki i pomocy technicznej dla Instrumentacji zarządzania Windows.  
  
 Podane tych potencjalnych korzyści z [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] względem usługi sieci Web ASP.NET, jeśli są używane lub są biorąc pod uwagę przy użyciu usługi sieci Web ASP.NET jest kilka opcji:  
  
-   Nadal używać usług sieci Web ASP.NET i przyznano korzyści proffered przez [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   Zachowaj przy użyciu usług sieci Web ASP.NET w celu przyjęcia [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] w czasie w przyszłości. Tematy w tej sekcji wyjaśniono, jak zmaksymalizować perspektyw było go używać nowej aplikacji usługi sieci Web ASP.NET razem z przyszłości [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikacji. Tematy w tej sekcji opisano również do tworzenia usług, aby ułatwić ich migracja do nowej sieci Web ASP.NET [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Jednak jeśli ważne jest zabezpieczenie usługi lub gwarancje niezawodności lub transakcji są wymagane, czy niestandardowych obiektów zarządzania musi być skonstruowany, a następnie jest lepszym rozwiązaniem przyjęcie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]jest przeznaczona dla dokładnie takich scenariuszy.  
  
-   Przyjmuje [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dla nowych aplikacji, pozostawiając Obsługa istniejących aplikacji usługi sieci Web ASP.NET. Ten wybór jest bardzo prawdopodobne optymalny. Zapewni ona korzyści wynikające z [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], podczas Reserve Sparing Table koszt modyfikacji istniejących aplikacji z niego korzystać. W tym scenariuszu nowe [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikacje mogą współistnieć z istniejących aplikacji ASP.NET. Nowy [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikacje będą mogły używać istniejącej usługi sieci Web ASP.NET, i [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] może służyć do programu nowe funkcje operacyjne w aplikacji ASP.NET, na mocy niniejszej [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tryb zgodności ASP.NET.  
  
-   Przyjmuje [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] i przeprowadzić migrację istniejących aplikacji usługi sieci Web ASP.NET do [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Można wybrać tę opcję, aby zwiększyć istniejących aplikacji z funkcji udostępnianych przez [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], lub do odtworzenia funkcjonalności istniejących usług sieci Web ASP.NET w ramach nowych, bardziej wydajne [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikacji.  
  
> [!NOTE]
>  Należy zwrócić uwagę, jeśli [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usługa jest obsługiwana przez program IIS został odinstalowany 5.x i platformy ASP.NET. Gdy [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usługa jest obsługiwana przez usługi IIS 5.x, kod usługi może wystąpić w przypadku odinstalowania programu ASP.NET. Po odinstalowaniu programu ASP.NET w systemie operacyjnym, który jest uruchomiony program IIS 5.x i [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] jest odinstalowywana, plik z rozszerzeniem .svc jest uznawany za plik tekstowy i zawartość, łącznie z dowolnego kodu źródłowego, jest zwracany do obiektu żądającego.  
  
 W tej sekcji opisano te opcje szczegółowo, porównanie usług sieci Web ASP.NET do [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] i instrukcje dotyczące sposobu przeprowadzenia migracji kodzie usług sieci Web ASP.NET w celu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="see-also"></a>Zobacz też  
 [Prognozowanie wdrożeń programu Windows Communication Foundation: ułatwianie migracji w przyszłości](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)  
 [Prognozowanie wdrożeń programu Windows Communication Foundation: ułatwianie integracji w przyszłości](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)  
 [Adoptowanie programu Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/adopting-wcf.md)  
 [Porównanie usług internetowych platformy ASP.NET i architektury WCF na podstawie przeznaczenia oraz stosowanych standardów](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)  
 [Porównywanie usług internetowych platformy ASP.NET z programem WCF na podstawie procesów programistycznych](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
