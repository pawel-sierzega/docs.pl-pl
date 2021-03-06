---
title: "Wyrażenie lambda nie zostanie usunięte z tej obsługi zdarzeń"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1a4c57d1f8f41d2d9ebb645d3f2628c32a2c4e4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a>Wyrażenie lambda nie zostanie usunięte z tej obsługi zdarzeń
Wyrażenie lambda nie zostanie usunięte z tej obsługi zdarzeń. Przypisz Wyrażenie lambda do zmiennej i użyj zmiennej do dodawania i usuwania zdarzenia.  
  
 Podczas wyrażenia lambda są używane z obsługi zdarzeń, nie może zostać wyświetlony oczekiwane zachowanie. Kompilator generuje nową metodę dla każdej definicji wyrażenia lambda, nawet jeśli są one identyczne. W związku z tym poniższy kod przedstawia `False`.  
  
```vb  
Module Module1  
  
    Sub Main()  
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1  
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1  
        Console.WriteLine(fun1 = fun2)  
    End Sub  
  
    Delegate Function ChangeInteger(ByVal x As Integer) As Integer  
  
End Module  
```  
  
 Wyrażenia lambda są używane z obsługi zdarzeń, może to spowodować nieoczekiwane wyniki. W poniższym przykładzie, wyrażenia lambda dodane przez `AddHandler` nie został usunięty przez `RemoveHandler` instrukcji.  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Sub Main()  
  
        ' The following line adds one listener to the event.  
        AddHandler ProcessInteger, Function(m As Integer) m  
  
        ' The following statement searches the current listeners   
        ' for a match to remove. However, this lambda is not the same  
        ' as the previous one, so nothing is removed.  
        RemoveHandler ProcessInteger, Function(m As Integer) m  
  
    End Sub  
End Module  
```  
  
 Domyślnie ten komunikat jest ostrzeżenie. Aby uzyskać więcej informacji na temat Ukryj ostrzeżenia lub Traktuj ostrzeżenia jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identyfikator błędu:** BC42326  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
-   Aby uniknąć tego ostrzeżenia, a następnie usuń wyrażenia lambda, przypisz Wyrażenie lambda do zmiennej i użycia zmiennej w obu `AddHandler` i `RemoveHandler` instrukcje, jak pokazano w poniższym przykładzie.  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Dim PrintHandler As ProcessIntegerEventHandler  
  
    Sub Main()  
  
        ' Assign the lambda expression to a variable.  
        PrintHandler = Function(m As Integer) m  
  
        ' Use the variable to add the listener.  
        AddHandler ProcessInteger, PrintHandler  
  
        ' Use the variable again when you want to remove the listener.  
        RemoveHandler ProcessInteger, PrintHandler  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Wyrażenia lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Swobodna konwersja delegatów](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Zdarzenia](../../../visual-basic/programming-guide/language-features/events/index.md)
