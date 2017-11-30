---
title: "Wstępne Atomizacja XName obiektów (LINQ do XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 967e41afc70290a4e4bdccabb8f3f4dd4ac4f6ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a><span data-ttu-id="50ba8-102">Wstępne Atomizacja XName obiektów (LINQ do XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50ba8-102">Pre-Atomization of XName Objects (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="50ba8-103">Jednym ze sposobów poprawy wydajności w składniku LINQ to XML ma wstępnie rozproszyć <xref:System.Xml.Linq.XName> obiektów.</span><span class="sxs-lookup"><span data-stu-id="50ba8-103">One way to improve performance in LINQ to XML is to pre-atomize <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="50ba8-104">Wstępne Atomizacja oznacza, że można przypisać ciąg <xref:System.Xml.Linq.XName> obiekt przed utworzeniem drzewa XML za pomocą konstruktorów <xref:System.Xml.Linq.XElement> i <xref:System.Xml.Linq.XAttribute> klasy.</span><span class="sxs-lookup"><span data-stu-id="50ba8-104">Pre-atomization means that you assign a string to an <xref:System.Xml.Linq.XName> object before you create the XML tree by using the constructors of the <xref:System.Xml.Linq.XElement> and  <xref:System.Xml.Linq.XAttribute> classes.</span></span> <span data-ttu-id="50ba8-105">Następnie, zamiast przekazywanie ciąg konstruktora, który użyć niejawna konwersja z ciągu na <xref:System.Xml.Linq.XName>, należy przekazać zainicjowane <xref:System.Xml.Linq.XName> obiektu.</span><span class="sxs-lookup"><span data-stu-id="50ba8-105">Then, instead of passing a string to the constructor, which would use the implicit conversion from string to <xref:System.Xml.Linq.XName>, you pass the initialized <xref:System.Xml.Linq.XName> object.</span></span>  
  
 <span data-ttu-id="50ba8-106">Poprawia to wydajność, podczas tworzenia dużych drzewa XML, w którym są powtarzane konkretne nazwy.</span><span class="sxs-lookup"><span data-stu-id="50ba8-106">This improves performance when you create a large XML tree in which specific names are repeated.</span></span> <span data-ttu-id="50ba8-107">W tym celu należy zadeklarować i zainicjuj <xref:System.Xml.Linq.XName> obiekty przed skonstruuj drzewo XML, a następnie użyć <xref:System.Xml.Linq.XName> obiektów zamiast określania ciągów dla nazw elementów i atrybutów.</span><span class="sxs-lookup"><span data-stu-id="50ba8-107">To do this, you declare and initialize <xref:System.Xml.Linq.XName> objects before you construct the XML tree, and then use the <xref:System.Xml.Linq.XName> objects instead of specifying strings for the element and attribute names.</span></span> <span data-ttu-id="50ba8-108">Ta technika może spowodować znaczący wzrost wydajności w przypadku tworzenia dużą liczbę elementów (lub atrybutów) o takiej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="50ba8-108">This technique can yield significant performance gains if you are creating a large number of elements (or attributes) with the same name.</span></span>  
  
 <span data-ttu-id="50ba8-109">Należy przetestować przed Atomizacja z danego scenariusza zdecydować, czy należy z niej korzystać.</span><span class="sxs-lookup"><span data-stu-id="50ba8-109">You should test pre-atomization with your scenario to decide if you should use it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50ba8-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="50ba8-110">Example</span></span>  
 <span data-ttu-id="50ba8-111">W poniższym przykładzie pokazano to.</span><span class="sxs-lookup"><span data-stu-id="50ba8-111">The following example demonstrates this.</span></span>  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 <span data-ttu-id="50ba8-112">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="50ba8-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 <span data-ttu-id="50ba8-113">W poniższym przykładzie przedstawiono tę samą metodę, gdy dokument XML jest w przestrzeni nazw:</span><span class="sxs-lookup"><span data-stu-id="50ba8-113">The following example shows the same technique where the XML document is in a namespace:</span></span>  
  
```vb  
Dim aw As XNamespace = "http://www.adventure-works.com"  
Dim Root__1 As XName = aw + "Root"  
Dim Data As XName = aw + "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XAttribute(XNamespace.Xmlns + "aw", aw), New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 <span data-ttu-id="50ba8-114">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="50ba8-114">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 <span data-ttu-id="50ba8-115">Poniższy przykład przypomina więcej co prawdopodobnie wystąpią w świecie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="50ba8-115">The following example is more similar to what you will likely encounter in the real world.</span></span> <span data-ttu-id="50ba8-116">W tym przykładzie zawartość elementu jest dostarczana przez kwerendę:</span><span class="sxs-lookup"><span data-stu-id="50ba8-116">In this example, the content of the element is supplied by a query:</span></span>  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim t1 As DateTime = DateTime.Now  
Dim root__2 As New XElement(Root__1, From i In System.Linq.Enumerable.Range(1, 100000)New XElement(Data, New XAttribute(ID, i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
 <span data-ttu-id="50ba8-117">Poprzedni przykład wykonuje lepszą wydajność niż poniższy przykład, w którym nazwy nie są wstępnie atomized:</span><span class="sxs-lookup"><span data-stu-id="50ba8-117">The previous example performs better than the following example, in which names are not pre-atomized:</span></span>  
  
```vb  
Dim t1 As DateTime = DateTime.Now  
Dim root As New XElement("Root", From i In System.Linq.Enumerable.Range(1, 100000)New XElement("Data", New XAttribute("ID", i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="50ba8-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="50ba8-118">See Also</span></span>  
 [<span data-ttu-id="50ba8-119">Wydajność (LINQ do XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50ba8-119">Performance (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)  
 [<span data-ttu-id="50ba8-120">Atomized XName i XNamespace obiektów (LINQ do XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50ba8-120">Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/atomized-xname-and-xnamespace-objects-linq-to-xml.md)