---
title: "Literał instrukcji przetwarzającej kod XML (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9ce0f2d0dff80072beefdb4f84643ea28e2cf165
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>Literał instrukcji przetwarzającej kod XML (Visual Basic)
Literał reprezentujący <xref:System.Xml.Linq.XProcessingInstruction> obiektu.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Części  
 `<?`  
 Wymagany. Oznacza początek literał instrukcji przetwarzania XML.  
  
 `piName`  
 Wymagany. Nazwa wskazująca, która aplikacja docelowych instrukcji przetwarzania. Nie może rozpoczynać się od "xml" lub "XML".  
  
 `piData`  
 Opcjonalny. Ciąg wskazujący, jak aplikacja objęci `piName` powinna przetworzyć dokumentu XML.  
  
 `?>`  
 Wymagany. Oznacza koniec instrukcji przetwarzania.  
  
## <a name="return-value"></a>Wartość zwracana  
 <xref:System.Xml.Linq.XProcessingInstruction> Obiektu.  
  
## <a name="remarks"></a>Uwagi  
 Literały instrukcji przetwarzania XML wskazują, jak aplikacje powinna przetworzyć dokumentu XML. Podczas ładowania dokumentu XML aplikacji aplikacji można sprawdzić instrukcji przetwarzania XML do określenia sposobu przetwarzania dokumentu. Aplikacja interpretuje znaczenie `piName` i `piData`.  
  
 Literał dokumentu XML używa składni, która jest podobna do instrukcji przetwarzania XML. Aby uzyskać więcej informacji, zobacz [literał dokumentu XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
>  `piName` Elementu nie może rozpoczynać się od ciągów "xml" lub "XML" ponieważ Specyfikacja XML 1.0 rezerwuje tych identyfikatorów.  
  
 Można przypisać literał instrukcji przetwarzania XML do zmiennej lub objąć literał dokumentu XML.  
  
> [!NOTE]
>  Literał XML może obejmować wiele wierszy bez konieczności znaki kontynuacji wiersza. Dzięki temu można kopiować zawartości z dokumentu XML i wklej go bezpośrednio do [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Kompilatora konwertuje literał instrukcji przetwarzania XML do wywołania <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> konstruktora.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład tworzy instrukcji przetwarzania identyfikujący arkusz stylów dla dokumentu XML.  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 [Literał dokumentu XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [Literały XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Tworzenie XML w Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
