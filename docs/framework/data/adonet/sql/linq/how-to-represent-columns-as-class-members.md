---
title: "Porady: reprezentuje kolumn jako elementy członkowskie klasy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 31344d69df3db78303752e201a9aab84048d4ea1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-represent-columns-as-class-members"></a>Porady: reprezentuje kolumn jako elementy członkowskie klasy
Użyj [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu, aby skojarzyć pola lub właściwości z kolumną bazy danych.  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a>Aby mapować pola lub właściwości do kolumny bazy danych  
  
-   Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu deklaracji właściwości lub pola.  
  
## <a name="example"></a>Przykład  
 Poniższy kod mapy `CustomerID` w `Customer` klasy do `CustomerID` kolumny w `Customers` tabeli bazy danych.  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 Nie trzeba określać <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> właściwości, jeśli można wywnioskować nazwy. Jeśli nie określisz nazwy, nazwa jest uznawany za taką samą nazwę jak właściwości lub pola.  
  
## <a name="see-also"></a>Zobacz też  
 [Model obiektu LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
