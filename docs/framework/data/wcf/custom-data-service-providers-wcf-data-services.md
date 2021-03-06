---
title: "Niestandardowych dostawców usług danych (usługi danych WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d7db780b97c1a7eadffbfa71f60be4afe590ccb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="custom-data-service-providers-wcf-data-services"></a>Niestandardowych dostawców usług danych (usługi danych WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]obejmuje zestaw dostawców, który umożliwia zdefiniowanie na podstawie typów danych z późnym wiązaniem modelu danych.  
  
|Dostawcy|Opis|  
|--------------|-----------------|  
|Dostawca metadanych|Jest to dostawca usług danych niestandardowych core umożliwia zdefiniowanie modelu danych niestandardowych w czasie wykonywania, implementując <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> interfejsu.|  
|Wyślij zapytanie do dostawcy|Ten dostawca umożliwia wykonywanie zapytań względem modelu danych niestandardowych, które zdefiniowano przy użyciu <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> interfejsu. Wyślij zapytanie do dostawcy jest tworzony przez wdrożenie <xref:System.Data.Services.Providers.IDataServiceQueryProvider> interfejsu.|  
|Aktualizowanie dostawcy|Ten dostawca pozwala na aktualizowanie typów, które są dostępne w dostawcy usług dane niestandardowe i zarządzać współbieżności. Zaimplementowanie tworzony jest dostawca aktualizacji <xref:System.Data.Services.Providers.IDataServiceUpdateProvider> — interfejs|  
|Dostawca stronicowania|Ten dostawca jest używany z dostawcą usług danych niestandardowych można włączyć obsługę stronicowania obsługiwanego przez serwer. Zaimplementowanie tworzony jest dostawca stronicowania dla usługi danych niestandardowych <xref:System.Data.Services.Providers.IDataServicePagingProvider> interfejsu.|  
|Dostawca przesyłania strumieniowego|Ten dostawca umożliwia ujawnia typy danych dużego obiektu binarnego jako strumień. Zaimplementowanie tworzony jest dostawca przesyłania strumieniowego <xref:System.Data.Services.Providers.IDataServiceStreamProvider> interfejsu. Dostawca przesyłania strumieniowego można również z programu Entity Framework i odbicie dostawcy źródła danych. Aby uzyskać więcej informacji, zobacz [przesyłania strumieniowego dostawcy](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).|  
  
 Aby uzyskać więcej informacji, zobacz artykuł [dostawców usług danych niestandardowych](http://go.microsoft.com/fwlink/?LinkID=186850) i [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Toolkit dostawcy w [OData SDK](http://go.microsoft.com/fwlink/?LinkId=186069).  
  
## <a name="see-also"></a>Zobacz też  
 [Dostawcy usług danych](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Dostawca programu Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
 [Dostawca odbicia](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
