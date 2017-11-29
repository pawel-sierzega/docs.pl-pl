---
title: Podsumowanie procesu wnioskowania schematu zestawu danych
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 15469e917129db7668df17f22fb71b166993d4fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="summary-of-the-dataset-schema-inference-process"></a><span data-ttu-id="3ce16-102">Podsumowanie procesu wnioskowania schematu zestawu danych</span><span class="sxs-lookup"><span data-stu-id="3ce16-102">Summary of the DataSet Schema Inference Process</span></span>
<span data-ttu-id="3ce16-103">Proces wnioskowania najpierw określi, z dokumentu XML, elementy, które będzie można wywnioskować jako tabele.</span><span class="sxs-lookup"><span data-stu-id="3ce16-103">The inference process first determines, from the XML document, which elements will be inferred as tables.</span></span> <span data-ttu-id="3ce16-104">Z pozostałych pliku XML proces wnioskowania określa kolumn dla tych tabel.</span><span class="sxs-lookup"><span data-stu-id="3ce16-104">From the remaining XML, the inference process determines the columns for those tables.</span></span> <span data-ttu-id="3ce16-105">Zagnieżdżone tabele procesu wnioskowania generuje zagnieżdżonych <xref:System.Data.DataRelation> i <xref:System.Data.ForeignKeyConstraint> obiektów.</span><span class="sxs-lookup"><span data-stu-id="3ce16-105">For nested tables, the inference process generates nested <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects.</span></span>  
  
 <span data-ttu-id="3ce16-106">Poniżej znajduje się krótki opis reguły wnioskowania:</span><span class="sxs-lookup"><span data-stu-id="3ce16-106">Following is a brief summary of inference rules:</span></span>  
  
-   <span data-ttu-id="3ce16-107">Elementów, które mają atrybuty są wywnioskować jako tabele.</span><span class="sxs-lookup"><span data-stu-id="3ce16-107">Elements that have attributes are inferred as tables.</span></span>  
  
-   <span data-ttu-id="3ce16-108">Elementów, które mają elementy podrzędne są wywnioskować jako tabele.</span><span class="sxs-lookup"><span data-stu-id="3ce16-108">Elements that have child elements are inferred as tables.</span></span>  
  
-   <span data-ttu-id="3ce16-109">Elementy powtarzające się wywnioskować jako pojedynczej tabeli.</span><span class="sxs-lookup"><span data-stu-id="3ce16-109">Elements that repeat are inferred as a single table.</span></span>  
  
-   <span data-ttu-id="3ce16-110">Jeśli element dokumentu lub kluczu głównym ma żadnych atrybutów, a nie elementy podrzędne, które będzie można wywnioskować jako kolumny, jest wywnioskowany jako <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="3ce16-110">If the document, or root, element has no attributes, and no child elements that would be inferred as columns, it is inferred as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="3ce16-111">W przeciwnym razie element dokumentu jest wywnioskowany jako tabelę.</span><span class="sxs-lookup"><span data-stu-id="3ce16-111">Otherwise, the document element is inferred as a table.</span></span>  
  
-   <span data-ttu-id="3ce16-112">Atrybuty są wywnioskować jako kolumny.</span><span class="sxs-lookup"><span data-stu-id="3ce16-112">Attributes are inferred as columns.</span></span>  
  
-   <span data-ttu-id="3ce16-113">Elementy, które mają żadnych atrybutów ani elementów podrzędnych i nie powtarzaj, są wywnioskować jako kolumny.</span><span class="sxs-lookup"><span data-stu-id="3ce16-113">Elements that have no attributes or child elements, and that do not repeat, are inferred as columns.</span></span>  
  
-   <span data-ttu-id="3ce16-114">Dla elementów, które są wywnioskować jako tabele zagnieżdżone w obrębie innych elementów, które są również wywnioskować jak tabele, zagnieżdżoną **DataRelation** jest tworzona między dwiema tabelami.</span><span class="sxs-lookup"><span data-stu-id="3ce16-114">For elements that are inferred as nested tables within other elements that are also inferred as tables, a nested **DataRelation** is created between the two tables.</span></span> <span data-ttu-id="3ce16-115">Nowy, podstawowej kolumny klucza o nazwie **TableName_Id** jest dodawane do obu tabel i używana przez **DataRelation**.</span><span class="sxs-lookup"><span data-stu-id="3ce16-115">A new, primary key column named **TableName_Id** is added to both tables and used by the **DataRelation**.</span></span> <span data-ttu-id="3ce16-116">A **ForeignKeyConstraint** jest tworzona między dwiema tabelami przy użyciu **TableName_Id** kolumny.</span><span class="sxs-lookup"><span data-stu-id="3ce16-116">A **ForeignKeyConstraint** is created between the two tables using the **TableName_Id** column.</span></span>  
  
-   <span data-ttu-id="3ce16-117">Dla elementów, które są wywnioskować jako tabele i który zawiera tekst, ale mieć żadnych elementów podrzędnych, nową kolumnę o nazwie **TableName_Text** jest tworzony dla poszczególnych elementów tekstu.</span><span class="sxs-lookup"><span data-stu-id="3ce16-117">For elements that are inferred as tables and that contain text but have no child elements, a new column named **TableName_Text** is created for the text of each of the elements.</span></span> <span data-ttu-id="3ce16-118">Jeśli element jest wywnioskowany jako tabelę i tekstu, ale ma także elementy podrzędne, tekst jest ignorowany.</span><span class="sxs-lookup"><span data-stu-id="3ce16-118">If an element is inferred as a table and has text, but also has child elements, the text is ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce16-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3ce16-119">See Also</span></span>  
 [<span data-ttu-id="3ce16-120">Wnioskowanie struktury zestawu danych relacyjnych z pliku XML</span><span class="sxs-lookup"><span data-stu-id="3ce16-120">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="3ce16-121">Podczas ładowania zestawu danych z pliku XML</span><span class="sxs-lookup"><span data-stu-id="3ce16-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="3ce16-122">Ładowanie informacji o schemacie zestawu danych z pliku XML</span><span class="sxs-lookup"><span data-stu-id="3ce16-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="3ce16-123">Za pomocą języka XML w zestawie danych</span><span class="sxs-lookup"><span data-stu-id="3ce16-123">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="3ce16-124">Zbiory danych, DataTables i DataViews</span><span class="sxs-lookup"><span data-stu-id="3ce16-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="3ce16-125">ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów</span><span class="sxs-lookup"><span data-stu-id="3ce16-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)