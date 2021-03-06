---
title: "LINQ do SQL N-warstwowa z usługami sieci Web"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9cb10eb8-957f-4beb-a271-5f682016fed2
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 79b9b1270f99720dec6b6369706f8a2f601d249e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2018
---
# <a name="linq-to-sql-n-tier-with-web-services"></a>LINQ do SQL N-warstwowa z usługami sieci Web
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]jest przeznaczonym zwłaszcza do użycia w warstwie środkowej warstwy dostępu luźno połączonych danych (DAL) na przykład usługi sieci Web. Jeśli Warstwa prezentacji prowadzi do strony sieci Web ASP.NET, a następnie używasz <xref:System.Web.UI.WebControls.LinqDataSource> formant serwera do zarządzania przesyłaniem danych między interfejs użytkownika sieci Web i [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] na warstwy środkowej. Jeśli Warstwa prezentacji nie jest strony platformy ASP.NET, następnie zarówno warstwy środkowej i warstwy prezentacji wykonaj wykonania dodatkowych czynności, aby zarządzać serializacji i deserializacji obiektu danych.  
  
## <a name="setting-up-linq-to-sql-on-the-middle-tier"></a>Konfigurowanie składnika LINQ to SQL na warstwy środkowej  
 W usłudze sieci Web lub aplikacji warstwowych warstwy środkowej zawiera kontekstu danych oraz klas jednostek. Można utworzyć tych klas, ręcznie lub za pomocą obu SQLMetal.exe lub [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] zgodnie z opisem w innym miejscu w dokumentacji. W czasie projektowania użytkownik może być możliwy do serializacji klas jednostek. Aby uzyskać więcej informacji, zobacz [jak: utworzyć serializacji jednostek](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md). Innym rozwiązaniem jest tworzyć osobne zestawy klas, które zapewniają dane do serializacji i projektu do tych typów możliwych do serializacji, po powrocie do danych w sieci [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] zapytania.  
  
 Następnie zdefiniuj interfejsu za pomocą metod wywołujących klientów pobierania, wstawiania i aktualizowania danych. Zawijaj metod interfejsu użytkownika [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] zapytania. Dowolny rodzaj mechanizmu serializacji służy do obsługi wywołania metody zdalnego i serializacja danych. Jedynym wymaganiem jest to, że jeśli masz cykliczne lub dwukierunkowe relacje w modelu obiektu, takim jak między klientami a zamówień w standardowy model obiektów Northwind, to należy użyć serializatora, który go obsługuje. Windows Communication Foundation (WCF) <xref:System.Runtime.Serialization.DataContractSerializer> obsługuje dwukierunkowe relacje, ale element XmlSerializer, używany z usługami sieci Web z systemem innym niż — WCF nie. Jeśli wybrano opcję XmlSerializer, musi upewnij się, że model obiektów ma Brak relacji cyklicznej.  
  
 Aby uzyskać więcej informacji na temat programu Windows Communication Foundation, zobacz [usług Windows Communication Foundation oraz usługi danych WCF w programie Visual Studio](/visualstudio/data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio).  
  
 Implementowanie reguł biznesowych lub innych logiki specyficznego dla domeny przy użyciu klasy częściowe i metody na <xref:System.Data.Linq.DataContext> oraz klas jednostek do przyłączanie się do [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zdarzeniach środowiska uruchomieniowego. Aby uzyskać więcej informacji, zobacz [implementacji logiki biznesowej N-warstwowa](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md).  
  
## <a name="defining-the-serializable-types"></a>Definiowanie typów możliwych do serializacji  
 Warstwa prezentacji lub klienta musi mieć definicji typu dla klasy, które będą otrzymywać od warstwy środkowej. Tych typów może być klas jednostek, samodzielnie lub specjalne klasy, które zawijać się tylko niektóre pola z klas jednostek dla niego komunikację zdalną. W każdym przypadku [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] jest całkowicie unconcerned o jak warstwy prezentacji uzyskuje te definicje typów. Na przykład warstwy prezentacji można użyć WCF można automatycznie wygenerować typy może mieć kopię bibliotekę DLL, w których te typy są definiowane lub po prostu zdefiniować własny wersji typów.  
  
## <a name="retrieving-and-inserting-data"></a>Trwa pobieranie i wstawianie danych  
 Warstwy środkowej definiuje interfejs, który określa, jak Warstwa prezentacji uzyskuje dostęp do danych. Na przykład `GetProductByID(int productID)`, lub `GetCustomers()`. W warstwie środkowej treści metody zazwyczaj tworzy nowe wystąpienie klasy <xref:System.Data.Linq.DataContext>, wykonuje zapytania dotyczącego co najmniej jednego z jego tabeli. Warstwy środkowej zwraca wynik w postaci <xref:System.Collections.Generic.IEnumerable%601>, gdzie `T` jest klasą jednostki lub innego typu, który jest używany do serializacji. Warstwa prezentacji nigdy nie wysyła lub odbiera zmiennych zapytania bezpośrednio do lub z warstwy środkowej. Dwie warstwy wymiany wartości, obiektów i kolekcji konkretnych danych. Po odebraniu kolekcji, można użyć warstwy prezentacji [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] do obiektów do badania go, jeśli to konieczne.  
  
 Podczas wstawiania danych, warstwy prezentacji można utworzyć nowego obiektu i wysyłania go do warstwy środkowej, lub mogą mieć konstruowania obiektu na podstawie wartości, które zapewnia warstwę środkową. Ogólnie rzecz biorąc pobieranie i wstawianie danych w aplikacjach warstwowych nie różni się znacznie w procesie w aplikacji warstwy 2. Aby uzyskać więcej informacji, zobacz [kwerendy bazy danych](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md) i [tworzenie i przesyłanie zmian danych](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md).  
  
## <a name="tracking-changes-for-updates-and-deletes"></a>Śledzenie zmian aktualizacji i usunięć  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]obsługuje optymistycznej współbieżności na podstawie sygnatury czasowe (nazywana również RowVersions) a oryginalnych wartości. Jeśli tabel bazy danych są sygnatury czasowe, następnie aktualizacji i usunięć wymaga niewiele dodatkowej pracy w warstwie warstwy środkowej albo prezentacji. Jednak jeśli oryginalne wartości musi być używany dla sprawdzenie optymistycznej współbieżności, następnie warstwy prezentacji jest odpowiedzialny za śledzenia te wartości i wysyła je po ułatwia aktualizacji. Jest to spowodowane jednostek w warstwie prezentacji zostały wprowadzone zmiany nie są śledzone na warstwy środkowej. W rzeczywistości oryginalnego pobierania jednostki i aktualizacji ostatecznego je są najczęściej wykonywane przez dwa osobne wystąpienia <xref:System.Data.Linq.DataContext>.  
  
 Większa liczba zmian, które zapewnia warstwę prezentacji, tym bardziej złożone, które staje się on do śledzenia tych zmian i pakiet, który je z powrotem do warstwy środkowej. Implementacja mechanizm komunikacji zmiany zależy całkowicie aplikacji. Jedynym wymaganiem jest to, że [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] muszą mieć te oryginalnych wartości, które są wymagane dla sprawdzenie optymistycznej współbieżności.  
  
 Aby uzyskać więcej informacji, zobacz [pobierania danych i CUD operacje w aplikacjach warstwowych (LINQ to SQL)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md).  
  
## <a name="see-also"></a>Zobacz też  
 [N-warstwowe i zdalne aplikacje z użyciem LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)  
 [NIB: Informacje o formancie serwera sieci Web LinqDataSource](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136)
