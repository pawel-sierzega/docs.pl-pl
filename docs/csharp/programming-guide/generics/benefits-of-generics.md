---
title: "Zalety typów ogólnych (Przewodnik programowania w języku C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], benefits
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2eb4aad3d23e459af738045b37ae3f1e8f33da06
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/19/2018
---
# <a name="benefits-of-generics-c-programming-guide"></a>Zalety typów ogólnych (Przewodnik programowania w języku C#)
Ogólne stanowią rozwiązanie do ograniczenia we wcześniejszych wersjach środowiska CLR i języka C# w którym generalizacji odbywa się przez rzutowanie typów do i z typem bazowym uniwersalnych <xref:System.Object>. Tworząc klasy ogólnej, można utworzyć kolekcję, która jest bezpieczne podczas kompilacji.  
  
 Ograniczenia używania klas kolekcja nierodzajową wykazać, pisząc krótki program, który używa <xref:System.Collections.ArrayList> klasy kolekcji w bibliotece klas programu .NET. Wystąpienie <xref:System.Collections.ArrayList> klasa umożliwia przechowywanie dowolnego typu odwołanie lub wartość.  
  
 [!code-csharp[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]  
  
 Ale ten wygody pochodzi się to kosztem. Odwołanie lub wartość typu, który jest dodawany do <xref:System.Collections.ArrayList> jest niejawnie upcast do <xref:System.Object>. Jeśli elementy są typy wartości, musi zostać opakowany gdy są dodane do listy i rozpakowany, gdy są one pobierane. Zarówno rzutowanie i operacje konwersja boxing i rozpakowywanie obniżyć wydajność; efekt boxing i konwersja unboxing może być bardzo istotne w scenariuszach, w którym musi iteracja dużych kolekcjach.  
  
 Inne ograniczenia jest Brak typu kompilacji sprawdzanie; Ponieważ <xref:System.Collections.ArrayList> rzutuje wszystkie informacje niezbędne do <xref:System.Object>, w czasie kompilacji, aby zapobiec robi takich jak ta kodu klienta nie istnieje sposób:  
  
 [!code-csharp[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]  
  
 Doskonale dopuszczalne i czasami zamierzone, w przypadku tworzenia kolekcji heterogenicznych, łączenie ciągów i `ints` w jednej <xref:System.Collections.ArrayList> jest bardziej prawdopodobnie błąd programowania i ten błąd nie zostanie wykryty do środowiska wykonawczego.  
  
 W wersjach 1.0 i 1.1 języka C# można uniknąć zagrożenia uogólniony kodu w klasach kolekcji .NET Framework klasy podstawowej biblioteki pisząc własne kolekcje określonego typu. Oczywiście taka klasa nie jest wielokrotnego użytku do więcej niż jednego typu danych, utratę zalet generalizacji i trzeba przepisywania klasy dla każdego typu, które będą przechowywane.  
  
 Co <xref:System.Collections.ArrayList> i inne podobne klasy są naprawdę potrzebne jest sposobem kodu klienta określić, na podstawie na wystąpienie typu danych, które będą one używane. Który wyeliminować potrzebę rozszerzające do <xref:System.Object> , a także umożliwiłoby dla kompilatora na typ sprawdzania. Innymi słowy <xref:System.Collections.ArrayList> wymaga parametru typu. Dokładnie to zapewniają ogólne. W ogólnej <xref:System.Collections.Generic.List%601> kolekcji w <xref:System.Collections.Generic> przestrzeni nazw, w tej samej operacji dodawania elementów do kolekcji przypomina to:  
  
 [!code-csharp[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]  
  
 W przypadku kodu klienta tylko dodać składni <xref:System.Collections.Generic.List%601> w porównaniu do <xref:System.Collections.ArrayList> jest argumentem typu w deklaracji i konkretyzacji. W zamian za ten wymaga nieco więcej kodowania złożoności, można utworzyć listę, która nie jest tylko bezpieczniejszy niż <xref:System.Collections.ArrayList>, ale również znacznie szybsze, szczególnie w przypadku typów wartości są elementy listy.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Collections.Generic>  
 [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)  
 [Wprowadzenie do typów ogólnych](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [Konwersja boxing i konwersja unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)  
 [Kiedy należy używać kolekcji ogólnych](../../../standard/collections/when-to-use-generic-collections.md)  
 [Wytyczne dotyczące kolekcji](../../../standard/design-guidelines/guidelines-for-collections.md)   
