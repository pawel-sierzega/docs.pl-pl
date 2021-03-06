---
title: "Wpływ kultury na ciągi w Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- locale [Visual Basic], effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b61f008edc446445fd5873b6138b64f29e0b8b8c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-culture-affects-strings-in-visual-basic"></a>Wpływ kultury na ciągi w Visual Basic
Ta strona pomocy opisano sposób [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] używa kultury informacji na temat wykonywania konwersji ciągów i porównania.  
  
## <a name="when-to-use-culture-specific-strings"></a>Kiedy należy używać ciągów specyficzne dla kultury  
 Zazwyczaj powinien Użyj parametrów specyficzne dla kultury dla wszystkich danych, przedstawione i odczytywać użytkowników, użyj parametrów niezmiennej kultury dla danych wewnętrznych aplikacji.  
  
 Na przykład jeśli aplikacja prosi użytkowników o celu wprowadź datę jako ciąg, powinien oczekiwać użytkowników do formatowania ciągi zgodnie z ich kultury, a aplikacji należy odpowiednio przekonwertować ciągu. Jeśli następnie aplikacja przedstawia datę w interfejsie użytkownika, jego powinni przedstawić kulturę użytkownika.  
  
 Jednak jeśli aplikacja prześle daty do centralnego serwera, należy sformatować ciągu zgodnie z jedną określoną kulturę, aby uniknąć pomylenia formaty daty innej.  
  
## <a name="culture-sensitive-functions"></a>Funkcje zależne od kultury  
 Wszystkie [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] funkcji konwersji ciągów (z wyjątkiem `Str` i `Val` funkcje) informacji o kulturze aplikacji umożliwia upewnienie się, że konwersje i porównania są odpowiednie dla kultury użytkownik aplikacji.  
  
 Aby pomyślnie przy użyciu funkcji konwersji ciągów na aplikacje, które działają na komputerach z ustawieniami inną kulturę należy zrozumieć, jakie funkcje ustawienie określoną kulturę, a które wykorzystują bieżące ustawienie kultury. Zwróć uwagę, że aplikacja, ustawienia kultury domyślnie dziedziczone z ustawienia kultury, system operacyjny. Aby uzyskać więcej informacji, zobacz <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>, <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A>, i [funkcje konwersji typu](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 `Str` (Konwertuje wartości do ciągów) i `Val` funkcji (konwertowania ciągów na liczby) nie należy używać informacji o kulturze aplikacji podczas konwersji między ciągi i liczby. Zamiast tego uznają tylko kropki (.), prawidłowe separatorem dziesiętnym. Kulturalnie obsługujący stosować te funkcje są:  
  
-   **Konwersje korzystających z bieżącej kultury.** `CStr` i `Format` funkcje konwertowanie liczby na ciąg znaków i `CDbl` i `CInt` funkcji: konwertowanie ciągu na liczbę.  
  
-   **Konwersje korzystających z określoną kulturę.** Każdy obiekt numer ma `ToString(IFormatProvider)` metodę, która konwertuje liczbę na ciąg znaków, i `Parse(String, IFormatProvider)` metodę, która konwertuje ciąg na liczbę. Na przykład `Double` typ zapewnia <xref:System.Double.ToString%28System.IFormatProvider%29> i <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29> metody.  
  
 Aby uzyskać więcej informacji, zobacz <xref:Microsoft.VisualBasic.Conversion.Str%2A> i <xref:Microsoft.VisualBasic.Conversion.Val%2A>.  
  
## <a name="using-a-specific-culture"></a>Używając określonej kultury  
 Załóżmy, że opracowujesz aplikację, która wysyła do usługi sieci Web Data (sformatowany jako ciąg). W takim przypadku aplikacja musi używać określoną kulturę konwersji ciągu. Aby zilustrować przyczyny, należy wziąć pod uwagę wynik z datą <xref:System.DateTime.ToString> metody: Jeśli aplikacja korzysta z tej metody do formatowania daty 4 lipca 2005 zwraca "2005-7/4 12:00:00 AM" uruchomienia z kulturą Polska angielski (en US), ale zwraca " 04.07.2005 00:00:00 "uruchomienia z kulturą niemiecki (de-DE).  
  
 Gdy trzeba wykonać Konwersja ciągu w formacie określoną kulturę, należy używać `CultureInfo` klasy, która jest wbudowana w [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Można utworzyć nowy `CultureInfo` obiektu dla określonej kultury przekazując nazwę kultury <xref:System.Globalization.CultureInfo.%23ctor%2A> konstruktora. Nazwy kultury obsługiwane są wymienione w <xref:System.Globalization.CultureInfo> klasy strony pomocy.  
  
 Alternatywnie można pobrać wystąpienia *Niezmienna kultura* z <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> właściwości. Niezmienna kultura opiera się na angielski kultury, ale istnieją pewne różnice. Na przykład Niezmienna kultura określa 24-godzinnym zamiast 12-godzinnym.  
  
 Aby przekonwertować datę na ciąg kultury, należy przekazać <xref:System.Globalization.CultureInfo> obiektu do obiektu data <xref:System.DateTime.ToString%28System.IFormatProvider%29> metody. Na przykład poniższy kod wyświetla "07/04/2005 00:00:00", niezależnie od ustawienia kultury aplikacji.  
  
 [!code-vb[VbVbalrConcepts#1](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/how-culture-affects-strings_1.vb)]  
  
> [!NOTE]
>  Literały daty są zawsze interpretowane zgodnie z kulturą angielskiej wersji językowej.  
  
## <a name="comparing-strings"></a>Porównywanie ciągów  
 Istnieją dwie sytuacje ważne, gdy są potrzebne porównywania ciągów:  
  
-   **Sortowanie danych w celu wyświetlenia dla użytkownika.** Użyj operacji oparte na bieżącej kultury, więc ciągi odpowiednio sortować.  
  
-   **Określanie, czy dwa ciągi wewnętrznych aplikacji dokładnie odpowiadać (zazwyczaj ze względów bezpieczeństwa).** Użyj operacji, które pominąć bieżącej kultury.  
  
 Można wykonać porównania z obu typów [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Strings.StrComp%2A> funkcji. Określ opcjonalny `Compare` argumentu, aby kontrolować typ porównania: `Text` dla większości danych wejściowych i wyjściowych `Binary` określania dokładne dopasowania.  
  
 `StrComp` Funkcja zwróci liczbę całkowitą wskazującą relacji między dwa ciągi porównaniu na podstawie kolejności sortowania. Wartość dodatnią dla wyniku wskazuje, że pierwszy ciąg jest większy niż drugi ciąg. Wynik negatywny wskazuje pierwszy ciąg jest mniejszy, a następnie zero oznacza równość ciągi.  
  
 [!code-vb[VbVbalrStrings#22](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_2.vb)]  
  
 Można również użyć [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] partnera partner of `StrComp` funkcji <xref:System.String.Compare%2A?displayProperty=nameWithType> metody. Jest to statyczne, przeciążonej metody klasy podstawowej ciągu. Poniższy przykład przedstawia, jak ta metoda jest używana:  
  
 [!code-vb[VbVbalrStrings#48](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_3.vb)]  
  
 Aby uzyskać bardziej precyzyjną kontrolę nad realizację porównanie, można użyć dodatkowych przeciążeń <xref:System.String.Compare%2A> metody. Z <xref:System.String.Compare%2A?displayProperty=nameWithType> metody, można użyć `comparisonType` argumentu, aby określić typ porównania do użycia.  
  
|Wartość `comparisonType` argumentu|Typ porównania|Kiedy używać|  
|---|---|---|  
|`Ordinal`|Porównanie w bajtach składnika ciągów.|Użyj tej wartości, podczas porównywania: identyfikatory z uwzględnieniem wielkości liter, ustawienia zabezpieczeń lub innych identyfikatorów językowe, gdzie bajtów muszą być zgodne.|  
|`OrdinalIgnoreCase`|Porównanie w bajtach składnika ciągów.<br /><br /> `OrdinalIgnoreCase`Niezmienna kultura informacje są używane do określania, kiedy dwa znaki różnią się tylko wielkością liter.|Użyj tej wartości, podczas porównywania: identyfikatorów bez uwzględniania wielkości liter, ustawień zabezpieczeń i danych przechowywanych w systemie Windows.|  
|`CurrentCulture`lub`CurrentCultureIgnoreCase`|Porównań opartych na ciągi są interpretacji w bieżącej kultury.|Użyj tych wartości, podczas porównywania: dane wyświetlane dla użytkownika, większość danych wejściowych użytkownika i inne dane, które wymaga interpretacji językowe.|  
|`InvariantCulture`lub`InvariantCultureIgnoreCase`|Porównań opartych na ciągi są interpretacji w Niezmienna kultura.<br /><br /> Ta lokalizacja jest inna niż `Ordinal` i `OrdinalIgnoreCase`, ponieważ Niezmienna kultura traktuje znaki poza zakresem akceptowane jako równoważne niezmiennej znaków.|Tylko przy porównywaniu danych trwałych lub wyświetlania zależnej odpowiednie dane, które wymaga stałej sortowania, należy użyć tych wartości.|  
  
### <a name="security-considerations"></a>Zagadnienia dotyczące zabezpieczeń  
 Jeśli aplikacji podejmowania decyzji w procesie zabezpieczeń na podstawie wyniku porównania lub operacji w przypadku zmiany, a następnie należy użyć operacji <xref:System.String.Compare%2A?displayProperty=nameWithType> — metoda i przekazać `Ordinal` lub `OrdinalIgnoreCase` dla `comparisonType` argumentu.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Globalization.CultureInfo>  
 [Wprowadzenie do ciągów w Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [Funkcje konwersji typu](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
