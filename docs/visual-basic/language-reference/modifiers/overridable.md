---
title: Overridable (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f7d5dd33f8591be1b4305e954e55e035882626c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="overridable-visual-basic"></a>Overridable (Visual Basic)
Określa, że właściwość lub procedura może być zastąpiona przez o identycznej nazwie właściwość lub procedura w klasie pochodnej.  
  
## <a name="remarks"></a>Uwagi  
 `Overridable` Modyfikator umożliwia właściwości lub metody w klasie do zastąpienia w klasie pochodnej. [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modyfikator zapobiega zastępowaniu w klasie pochodnej właściwości lub metody.  Aby uzyskać więcej informacji, zobacz [podstawowe informacje o dziedziczeniu](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Jeśli `Overridable` lub `NotOverridable` modyfikator nie zostanie określony, domyślnie zależy od tego, czy właściwości lub metody zastępuje właściwości klasy podstawowej lub metody. Jeśli właściwość lub metoda zastępuje właściwości klasy podstawowej lub metody, ustawienie domyślne to `Overridable`; w przeciwnym razie jest `NotOverridable`.  
  
 Można w tle lub zastąpienie do ponownego zdefiniowania odziedziczonego elementu, ale są istotne różnice między dwa podejścia. Aby uzyskać więcej informacji, zobacz [przesłanianie w Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
 Element, który może zostać zastąpiona jest czasami nazywany *wirtualnego* elementu. Jeśli może zostać zastąpiona, ale nie musi być, czasem nazywana jest również *konkretnych* elementu.  
  
 Można użyć `Overridable` tylko w instrukcji deklaracji właściwość lub procedura.  
  
## <a name="combined-modifiers"></a>Modyfikatory połączone  
 Nie można określić `Overridable` lub `NotOverridable` dla `Private` metody.  
  
 Nie można określić `Overridable` razem z `MustOverride`, `NotOverridable`, lub `Shared` w tej samej deklaracji.  
  
 Zastępowanie elementu jest niejawnie możliwym do zastąpienia, nie można łączyć `Overridable` z `Overrides`.  
  
## <a name="usage"></a>Użycie  
 `Overridable` Modyfikatora można używać w tych sytuacjach:  
  
 [Function — instrukcja](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property — instrukcja](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub — instrukcja](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Zobacz też  
 [Modyfikatory](../../../visual-basic/language-reference/modifiers/index.md)  
 [Podstawowe informacje o dziedziczeniu](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [Zastąpienia](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Słowa kluczowe](../../../visual-basic/language-reference/keywords/index.md)  
 [Przesłanianie w Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
