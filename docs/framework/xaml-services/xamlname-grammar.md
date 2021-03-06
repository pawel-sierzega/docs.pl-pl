---
title: "XamlName — Gramatyka"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
caps.latest.revision: "13"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47a2d72ea9558003412cc3773e26fb5be751fa19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="xamlname-grammar"></a>XamlName — Gramatyka
Xamlname — gramatyka jest określonych gramatyki, która jest zdefiniowana w specyfikacji języka XAML [MS-XAML], który jest podany tutaj dla wygody.  
  
## <a name="from-the-xaml-specification"></a>W specyfikacji języka XAML  
 Specification [MS-XAML] określa gramatyki xamlname — do identyfikowania zestawów prawne symboliczne identyfikatory używane dla typów i właściwości.  
  
 Ciąg typu, który musi odpowiadać xamlname — gramatyka następujące wartości:  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 Dział następujące wartości ogólne kategorii zgodnie z definicją w bazie danych znak Unicode  
  
```  
Lu  
Letter, Uppercase  
Ll  
Letter, Lowercase  
Lt  
Letter, Titlecase  
Lm  
Letter, Modifier  
Lo  
Letter, Other  
Mn  
Mark, Non-Spacing  
Mc  
Mark, Spacing Combining  
Nd  
Number, Decimal  
Nl  
Number, Letter  
```  
  
 XAML definiuje drugi gramatyki, dottedxamlname —, która jest używana dla właściwości i zdarzenia kwalifikowanego odwołania, a także dla dołączone elementy członkowskie. Aby uzyskać więcej informacji, zobacz <xref:System.Windows.DependencyProperty> i [omówienie XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
 Ciąg wartości, które są dottedxamlname — musi odpowiadać gramatyce następującego typu:  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>Uwagi  
 Pełne specyfikacji, zobacz [ \[MS XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).
