---
title: "LINQ do XML dla wyrażenia XPath użytkowników (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 0e64911c-a7cc-4c20-b927-ca99078b5656
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb0666ee1ae5626a4721ea597a53889e1acf8b0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="linq-to-xml-for-xpath-users-visual-basic"></a>LINQ do XML dla wyrażenia XPath użytkowników (Visual Basic)

Ten zestaw tematów Pokaż liczbę wyrażenia XPath i ich [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] odpowiedniki.  
  
 Wszystkie przykłady korzystania z funkcji XPath w [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] który ma zostać udostępnione za pomocą metod rozszerzenia <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>. Przykłady wykonywania wyrażenia XPath i [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] wyrażenia. Każdy przykład następnie porównuje wyniki obu kwerend weryfikowania, czy wyrażenie XPath jest funkcjonalnym odpowiednikiem [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] zapytania. Oba typy zapytań zwrócenie węzły z tym samym drzewie XML, porównanie wyników zapytania jest wykonywane przy użyciu tożsamości referencyjnej.  
  
## <a name="in-this-section"></a>W tej sekcji  
  
|Temat|Opis|  
|-----------|-----------------|  
|[Porównanie XPath i LINQ do XML](../../../../visual-basic/programming-guide/concepts/linq/comparison-of-xpath-and-linq-to-xml.md)|Zawiera omówienie podobieństwa i różnice między XPath i [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].|  
|[Porady: znajdowanie elementu podrzędnego (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-child-element-xpath-linq-to-xml.md)|Porównuje osi elementu podrzędnego XPath do [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> metody.<br /><br /> Skojarzone wyrażenie XPath:`"DeliveryNotes"`.|  
|[Porady: lista elementów podrzędnych (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-list-of-child-elements-xpath-linq-to-xml.md)|Porównuje osi elementów podrzędnych wyrażenia XPath do [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> osi.<br /><br /> Skojarzone wyrażenie XPath jest:`"./*"`|  
|[Porady: znajdowanie elementem głównym (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-root-element-xpath-linq-to-xml.md)|Jak uzyskać elementu głównego z XPath porównuje i [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Skojarzone wyrażenie XPath jest:`"/PurchaseOrders"`|  
|[Porady: znajdowanie elementów podrzędnych (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-descendant-elements-xpath-linq-to-xml.md)|Jak uzyskać elementów podrzędnych o określonej nazwie z XPath porównuje i [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Skojarzone wyrażenie XPath jest:`"//Name"`|  
|[Porady: filtrowanie atrybutów (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-filter-on-an-attribute-xpath-linq-to-xml.md)|Jak uzyskać elementów podrzędnych o określonej nazwie i z atrybutem o określonej wartości z XPath porównuje i [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Skojarzone wyrażenie XPath jest:`".//Address[@Type='Shipping']"`|  
|[Porady: znajdowanie powiązanych elementów (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-related-elements-xpath-linq-to-xml.md)|Jak uzyskać, wybierając element na atrybut, który jest określana przez wartość innego elementu z języka XPath porównuje i [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Skojarzone wyrażenie XPath jest:`".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]"`|  
|[Porady: znajdowanie elementów w Namespace (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-elements-in-a-namespace.md)|Użycie wyrażenia XPath porównuje <xref:System.Xml.XmlNamespaceManager> klasy z [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XName.Namespace%2A> właściwość <xref:System.Xml.Linq.XName> klasy do pracy z przestrzeni nazw XML.<br /><br /> Skojarzone wyrażenie XPath jest:`"./aw:*"`|  
|[Porady: znajdowanie poprzedzających elementów równorzędnych (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-preceding-siblings-xpath-linq-to-xml.md)|Porównuje XPath `preceding-sibling` oś [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] podrzędnych <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> osi.<br /><br /> Skojarzone wyrażenie XPath jest:`"preceding-sibling::*"`|  
|[Porady: znajdowanie elementów podrzędnych elementu podrzędnego (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-descendants-of-a-child-element-xpath-linq-to-xml.md)|Jak uzyskać elementów podrzędnych elementu podrzędnego o określonej nazwie z XPath porównuje i [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Skojarzone wyrażenie XPath jest:`"./Paragraph//Text/text()"`|  
|[Porady: znajdowanie złożenie dwóch ścieżek lokalizacji (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-union-of-two-location-paths-xpath.md)|Porównuje użycia operatora union <code>&#124;</code>, w elemencie XPath z <xref:System.Linq.Enumerable.Concat%2A> — operator zapytań standardowe w [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Skojarzone wyrażenie XPath jest:<code>"//Category&#124;//Price"</code>|  
|[Porady: znajdowanie węzłami tego samego poziomu (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-sibling-nodes-xpath-linq-to-xml.md)|Jak znaleźć wszystkich elementów równorzędnych węzła, o określonej nazwie z XPath porównuje i [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Skojarzone wyrażenie XPath jest:`"../Book"`|  
|[Porady: znajdowanie atrybutu nadrzędnego (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml.md)|Porównuje jak Przejdź do elementu nadrzędnego i Znajdź skojarzony atrybut za pomocą XPath i [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Skojarzone wyrażenie XPath jest:`"../@id"`|  
|[Porady: znajdowanie atrybuty elementów równorzędnych o określonej nazwie (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-attributes-of-siblings-with-a-specific-name.md)|Jak znaleźć określonych atrybutów elementów równorzędnych węzła kontekstu z XPath porównuje i [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Skojarzone wyrażenie XPath jest:`"``../Book/@id``"`|  
|[Porady: znajdowanie elementów z określonym atrybutem (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-elements-with-a-specific-attribute.md)|Jak znaleźć al elementów zawierających określony atrybut za pomocą XPath porównuje i [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Skojarzone wyrażenie XPath jest:`"./*[@Select]"`|  
|[Porady: znajdowanie elementów podrzędnych na podstawie pozycji (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-child-elements-based-on-position.md)|Jak znaleźć elementu oparte na jego względne położenie za pomocą XPath porównuje i [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Skojarzone wyrażenie XPath jest:`"Test[position() >= 2 and position() <= 4]"`|  
|[Porady: znajdowanie natychmiastowego poprzedniego elementu równorzędnego (XPath-LINQ do XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml.md)|Jak znaleźć natychmiastowego równorzędnym poprzedniego węzła za pomocą XPath porównuje i [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Skojarzone wyrażenie XPath jest:`"preceding-sibling::*[1]"`|  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Xml.XPath?displayProperty=nameWithType>  
 [Wykonywanie zapytania drzewa XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)  
 [Przetwarzania danych XML przy użyciu modelu danych XPath](../../../../standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
