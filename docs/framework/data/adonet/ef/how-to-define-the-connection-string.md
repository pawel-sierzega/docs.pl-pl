---
title: "Porady: Definiowanie parametrów połączenia"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 355d313fd607ccf85ba55b09b9ece4d9c88e298f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-define-the-connection-string"></a>Porady: Definiowanie parametrów połączenia
W tym temacie przedstawiono sposób zdefiniowanie ciągu połączenia, używaną podczas nawiązywania połączenia z modelu koncepcyjnego. W tym temacie jest oparta na [sprzedaży AdventureWorks](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) modelu koncepcyjnego. Model sprzedaży AdventureWorks jest używany w tematach dotyczących zadań w [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] dokumentacji. W tym temacie założono, że została już skonfigurowana [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] i zdefiniowane AdventureWorks modelu sprzedaży. Aby uzyskać więcej informacji, zobacz [porady: ręczne definiowanie modelu i mapowania plików](http://msdn.microsoft.com/library/d4fd6864-f2a1-48f0-aa32-1e318775a99a). Procedury przedstawione w tym temacie znajdują się również w [porady: ręczne konfigurowanie projektu programu Entity Framework](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  Jeśli używasz [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] kreatora w [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] projektu, automatycznie generuje plik edmx i konfiguruje projektu do [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Aby uzyskać więcej informacji, zobacz [porady: Użyj Kreatora modelu danych jednostki](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)  
  
### <a name="to-define-the-entity-framework-connection-string"></a>Aby określić parametry połączenia programu Entity Framework  
  
-   Otwórz plik konfiguracji projektu aplikacji (app.config) i dodaj następujące parametry połączenia:  
  
  
  
     Jeśli projekt nie ma pliku konfiguracji aplikacji, możesz dodać kategorię, wybierając **Dodaj nowy element** z **projektu** menu, wybierając **ogólne** kategorii, Wybieranie **pliku konfiguracji aplikacji**, a następnie klikając pozycję **Dodaj**.  
  
## <a name="see-also"></a>Zobacz też  
 [Szybki start](http://msdn.microsoft.com/library/0bc534be-789f-4819-b9f6-76e51d961675)  
 [Porady: Tworzenie nowego pliku edmx](http://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2)  
 [ADO.NET Entity Data Model Tools](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
