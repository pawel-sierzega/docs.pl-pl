---
title: "Jaki &#39; s Nowość w ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bb65d38-cce2-46f5-b979-e5c505e95e10
caps.latest.revision: "25"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fb23f329906e21f3d8558139075c5f575f2f13bd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2018
---
# <a name="what39s-new-in-adonet"></a>Jaki &#39; s Nowość w ADO.NET
Następujące funkcje są nowością w programie [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] w [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].  
  
## <a name="sqlclient-data-provider"></a>Dostawca danych SqlClient  
 Następujące funkcje są nowością w programie [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawcy danych dla [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] w [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]:  
  
-   ConnectRetryCount i ConnectRetryInterval słowa kluczowe parametrów połączenia (<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>) pozwalają na kontrolowanie funkcji odporności bezczynnego połączenia.  
  
-   Obsługa z przesyłania strumieniowego [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] do aplikacji obsługuje scenariusze, w którym dane na serwerze nie ma określonej struktury.  Zobacz [obsługę przesyłania strumieniowego SqlClient](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md) Aby uzyskać więcej informacji.  
  
-   Dodano obsługę programowania asynchronicznego.  Zobacz [programowania asynchronicznego](../../../../docs/framework/data/adonet/asynchronous-programming.md) Aby uzyskać więcej informacji.  
  
-   Liczba błędów połączenia będą teraz rejestrowane w dzienniku zdarzeń rozszerzonych. Aby uzyskać więcej informacji, zobacz [danych śledzenia w ADO.NET](../../../../docs/framework/data/adonet/data-tracing.md).  
  
-   Klient SQL ma teraz obsługę [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]w wysokiej dostępności, funkcji odzyskiwania po awarii (AlwaysOn). Aby uzyskać więcej informacji, zobacz [SqlClient obsługę wysokiej dostępności, odzyskiwania po awarii](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).  
  
-   Hasła mogą być przekazywane jako <xref:System.Security.SecureString> przy użyciu [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] uwierzytelniania. Aby uzyskać więcej informacji, zobacz <xref:System.Data.SqlClient.SqlCredential>.  
  
-   Gdy `TrustServerCertificate` ma wartość false i `Encrypt` jest wartość PRAWDA, nazwę serwera (lub adres IP) w [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] certyfikat SSL musi dokładnie odpowiadać serwera nazwę (lub adres IP) określona w parametrach połączenia. W przeciwnym razie próba połączenia zakończy się niepowodzeniem. Aby uzyskać więcej informacji, zobacz opis `Encrypt` opcji połączenia w <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
     Jeśli ta zmiana spowoduje istniejącej aplikacji do już połączyć, można naprawić aplikacji przy użyciu jednej z następujących czynności:  
  
    -   Wystawić certyfikat, który określa krótką nazwę w polu Nazwa pospolita (CN) lub alternatywnej nazwy podmiotu (SAN). To rozwiązanie będzie działać dublowania bazy danych.  
  
    -   Dodaj alias, który mapuje krótką nazwę na w pełni kwalifikowaną nazwę domeny.  
  
    -   Użyj w pełni kwalifikowaną nazwę domeny w parametrach połączenia.  
  
-   SqlClient obsługuje ochrony rozszerzonej. Aby uzyskać więcej informacji na temat ochrony rozszerzonej, zobacz [nawiązywania połączenia z bazą danych aparatu przy użyciu ochrony rozszerzonej](http://go.microsoft.com/fwlink/?LinkId=219978).  
  
-   SqlClient obsługuje połączenia z bazami danych LocalDB. Aby uzyskać więcej informacji, zobacz [SqlClient obsługę LocalDB](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-localdb.md).  
  
-   `Type System Version=SQL Server 2012;`jest nową wartość do przekazania do `Type System Version` właściwości połączenia. `Type System Version=Latest;` Wartość jest teraz przestarzałe i wprowadzono odpowiednikiem `Type System Version=SQL Server 2008;`. Aby uzyskać więcej informacji, zobacz <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
-   SqlClient obsługuje dodatkowych kolumn rozrzedzonych, funkcji, które zostały dodane w programie SQL Server 2008. Jeśli już aplikacja uzyskuje dostęp do danych w tabeli, która używa kolumn rozrzedzonych, powinna zostać wyświetlona wzrost wydajności. Nazwa kolumny IsColumnSet <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> wskazuje, czy kolumna jest kolumną rozrzedzoną, który jest członkiem zestawu kolumn. <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>Wskazuje, czy kolumna jest kolumną rozrzedzoną (zobacz [kolekcje schematów programu SQL Server](../../../../docs/framework/data/adonet/sql-server-schema-collections.md) Aby uzyskać więcej informacji). Aby uzyskać więcej informacji na temat kolumn rozrzedzonych, zobacz [przy użyciu kolumn rozrzedzonych](http://go.microsoft.com/fwlink/?LinkId=224244).  
  
-   Zestaw Microsoft.SqlServer.Types.dll, który zawiera typy danych przestrzennych, został uaktualniony z wersji 10.0 do wersji 11.0. Aplikacje, które odwołują się do tego zestawu może zakończyć się niepowodzeniem. Aby uzyskać więcej informacji, zobacz [fundamentalne zmiany do funkcji aparatu bazy danych](http://go.microsoft.com/fwlink/?LinkId=224367).  
  
## <a name="adonet-entity-framework"></a>Program Entity Framework na platformie ADO.NET  
 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] Dodaje interfejsów API, które umożliwiają nowych scenariuszy podczas pracy z programu Entity Framework 5.0. Aby uzyskać więcej informacji o udoskonaleniach i funkcje, które zostały dodane do programu Entity Framework 5.0, zobacz następujące tematy: [What's New](http://go.microsoft.com/fwlink/?LinkID=251106) i [Entity Framework wersjach and Versioning](http://go.microsoft.com/fwlink/?LinkId=234899).  
  
## <a name="see-also"></a>Zobacz też  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)  
 [Omówienie ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [SQL Server i ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 [What's New in usługi danych WCF](http://msdn.microsoft.com/library/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)  
 [ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów](http://go.microsoft.com/fwlink/?LinkId=217917)
