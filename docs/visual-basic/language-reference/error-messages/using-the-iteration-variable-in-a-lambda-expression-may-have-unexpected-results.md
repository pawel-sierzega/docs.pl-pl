---
title: "Użycie zmiennej iteracyjnej w wyrażeniu lambda może spowodować nieoczekiwane wyniki"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fb707cd4e09a149d21b70bb0f998a40c7ed58b49
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a>Użycie zmiennej iteracyjnej w wyrażeniu lambda może spowodować nieoczekiwane wyniki
Użycie zmiennej iteracyjnej w wyrażeniu lambda może spowodować nieoczekiwane wyniki. Zamiast tego Utwórz zmienną lokalną w pętli i przypisz jej wartość zmiennej iteracyjnej.  
  
 To ostrzeżenie jest wyświetlane, gdy używasz zmiennej iteracji pętli w wyrażeniu lambda, która jest zadeklarowana w pętli. Na przykład poniższy przykład powoduje, że ostrzeżenia.  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 W poniższym przykładzie przedstawiono nieoczekiwane wyniki, które mogą wystąpić.  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            array1(i) = Function() i  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
 `For` Pętli tworzy tablicę wyrażenia lambda, z których każdy zwraca wartość zmiennej iteracji pętli `i`. Gdy wyrażenia lambda są obliczane w `For Each` pętli, można oczekiwać, zobacz 0, 1, 2, 3 i 4 wyświetlany, kolejnych wartości `i` w `For` pętli. Zamiast tego zobacz końcowa wartość `i` wyświetlane pięć razy:  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 Domyślnie ten komunikat jest ostrzeżenie. Aby uzyskać więcej informacji na temat ukrywanie ostrzeżenia lub traktowanie ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identyfikator błędu:** BC42324  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
-   Przypisz wartość zmiennej iteracyjnej do zmiennej lokalnej, a następnie użyć zmiennej lokalnej w wyrażeniu lambda.  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            Dim j = i  
            array1(i) = Function() j  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Wyrażenia lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
