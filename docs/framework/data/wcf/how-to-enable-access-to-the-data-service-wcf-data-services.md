---
title: "Porady: Zapewnianie dostępu do usługi Data (usługi danych WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f481a3a918282bf598277dcd4e1bf29d63edddc1
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a>Porady: Zapewnianie dostępu do usługi Data (usługi danych WCF)
W [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], należy jawnie zezwolić na dostęp do zasobów, które są udostępniane przez usługi danych. Oznacza to, że po utworzeniu nowej usługi danych musi nadal jawnie Podaj, dostęp do poszczególnych zasobów jako zestawy jednostek. W tym temacie przedstawiono sposób włączania odczytu i zapisu do pięciu jednostki ustawia w usłudze danych Northwind, który jest tworzony po zakończeniu [szybkiego startu](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Ponieważ <xref:System.Data.Services.EntitySetRights> wyliczenie zdefiniowano przy użyciu <xref:System.FlagsAttribute>, można użyć logiczną lub ustaw operatora, aby określić wiele uprawnienia dla pojedynczej jednostki.  
  
> [!NOTE]
>  Klienta, który można uzyskać dostęp do aplikacji ASP.NET można również uzyskać dostęp do zasobów, udostępnianych przez usługę danych. W usłudze danych w środowisku produkcyjnym aby uniemożliwić nieautoryzowany dostęp do zasobów, należy również zabezpieczyć samej aplikacji. Aby uzyskać więcej informacji, zobacz [NIB: zabezpieczenia w programie ASP.NET](http://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d).  
  
### <a name="to-enable-access-to-the-data-service"></a>Aby włączyć dostęp do usługi danych  
  
-   W kodzie dla usługi data, Zastąp kod symbol zastępczy w `InitializeService` funkcji z następujących czynności:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     Dzięki temu klienci miał do odczytu i zapisu do `Orders` i `Order_Details` zestawów jednostek i dostęp tylko do odczytu do `Customers` zestawów jednostek.  
  
## <a name="see-also"></a>Zobacz też  
 [Instrukcje: Tworzenie usługi danych WCF działającej na serwerze IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)  
 [Konfigurowanie usługi danych](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
