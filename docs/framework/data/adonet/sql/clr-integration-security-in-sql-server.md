---
title: "CLR Integration zabezpieczeń w programie SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 37437d827fc0ff6583178f33f4cceaa86f5175dd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2018
---
# <a name="clr-integration-security-in-sql-server"></a>CLR Integration zabezpieczeń w programie SQL Server
Microsoft SQL Server zapewnia integrację składnika wspólne języka wspólnego (CLR) programu .NET Framework. Integrację środowiska CLR umożliwia pisanie procedur składowanych, wyzwalaczy, typy danych zdefiniowane przez użytkownika, funkcjach zdefiniowanych przez użytkownika, agregacje zdefiniowane przez użytkownika i przesyłania strumieniowego funkcji zwracającej tabelę przy użyciu dowolnego języka .NET Framework, takich jak Microsoft Visual Basic .NET lub Microsoft Visual C#.  
  
 Środowisko CLR obsługuje model zabezpieczeń o nazwie zabezpieczenia dostępu kodu (CAS) dla kodu zarządzanego. W tym modelu przyznano uprawnienia do zestawów w oparciu o dowody dostarczone przez kod w metadanych. SQL Server model zabezpieczeń oparty na użytkownika programu SQL Server jest zintegrowany z modelu zabezpieczeń opartego na dostępie kodu środowiska CLR.  
  
## <a name="external-resources"></a>Zasoby zewnętrzne  
 Aby uzyskać więcej informacji o integracji środowiska CLR programu SQL Server zobacz następujące zasoby.  
  
|Zasób|Opis|  
|--------------|-----------------|  
|[Zabezpieczenia dostępu kodu](http://msdn.microsoft.com/library/23a20143-241d-4fe5-9d9f-3933fd594c03)|Zawiera tematy opisujące urzędów certyfikacji w programie .NET Framework.|  
|[Zabezpieczenia integracji środowiska CLR](http://go.microsoft.com/fwlink/?LinkId=59998)|Omówienie modelu zabezpieczeń wykonania kodu zarządzanego wewnątrz programu SQL Server.|  
  
## <a name="see-also"></a>Zobacz też  
 [Zabezpieczanie aplikacji ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Scenariusze zabezpieczeń aplikacji w programie SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Integracja aparatu plików wykonywalnych języka wspólnego z programem SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 [ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów](http://go.microsoft.com/fwlink/?LinkId=217917)
