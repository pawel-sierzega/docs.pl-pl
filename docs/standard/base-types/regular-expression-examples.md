---
title: "Przykłady wyrażeń regularnych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- regular expressions [.NET Framework], examples
- regular expressions [.NET Framework]
- strings [.NET Framework], regular expressions
ms.assetid: e9fd53f2-ed56-4b09-b2ea-e9bc9d65e6d6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4d2d3aced78d2afed3f0d1396efe5e954ef84102
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/23/2017
---
# <a name="regular-expression-examples"></a>Przykłady wyrażeń regularnych
Ta sekcja zawiera przykłady kodu, ilustrujące używanie wyrażeń regularnych w typowych zastosowań.  
  
> [!NOTE]
>  <xref:System.Web.RegularExpressions> Przestrzeń nazw zawiera wiele obiektów wyrażeń regularnych, implementujących wzorców wstępnie zdefiniowanych wyrażeń regularnych do analizowania ciągów z dokumentów HTML, XML i programu ASP.NET. Na przykład <xref:System.Web.RegularExpressions.TagRegex> klasy identyfikuje początkowe tagi w ciągu i <xref:System.Web.RegularExpressions.CommentRegex> klasy identyfikuje komentarze ASP.NET w ciągu.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Przykład: Wyszukiwanie wartości HREF](../../../docs/standard/base-types/regular-expression-example-scanning-for-hrefs.md)  
 Zawiera przykład, w którym wyszukuje ciąg wejściowy i drukowania wszystkich href = "..." wartości i ich lokalizacji w ciągu.  
  
 [Przykład: Zmienianie formatów daty](../../../docs/standard/base-types/regular-expression-example-changing-date-formats.md)  
 Przykład zastępujący daty w formacie mm/dd/rr z daty w formacie dd-mm rr.  
  
 [Instrukcje: Wyodrębnianie protokołu i numeru portu z adresu URL](../../../docs/standard/base-types/how-to-extract-a-protocol-and-port-number-from-a-url.md)  
 Przykład wyodrębniające protokołem i numerem portu z ciąg znaków zawierający adres URL. Na przykład "http://www.contoso.com:8080/letters/readme.html" zwraca "http:8080".  
  
 [Instrukcje: Usuwanie nieprawidłowych znaków z ciągów](../../../docs/standard/base-types/how-to-strip-invalid-characters-from-a-string.md)  
 Przykład wyodrębniania nieprawidłowe znaki inne niż alfanumeryczne z ciągu.  
  
 [Instrukcje: Sprawdzanie, czy format poczty e-mail ciągów jest prawidłowy](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md)  
 Zawiera przykład, w którym można użyć, aby sprawdzić, czy ciąg w formacie prawidłowy adres e-mail.  
  
## <a name="reference"></a>Tematy pomocy  
 <xref:System.Text.RegularExpressions>  
 Zawiera informacje o odwołaniu biblioteki klas dla programu .NET **System.Text.RegularExpressions** przestrzeni nazw.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Wyrażeń regularnych programu .NET](../../../docs/standard/base-types/regular-expressions.md)  
 Omówienie programowania aspekt język wyrażeń regularnych.  
  
 [Model obiektów wyrażeń regularnych](../../../docs/standard/base-types/the-regular-expression-object-model.md)  
 W tym artykule opisano klasy wyrażeń regularnych zawarte w `System.Text.RegularExpression` przestrzeni nazw i przykłady ich użycia.  
  
 [Szczegóły dotyczące zachowania wyrażeń regularnych](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)  
 Zawiera informacje dotyczące możliwości i zachowania wyrażeń regularnych programu .NET.  
  
 [Język wyrażeń regularnych — podręczny wykaz](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 Zawiera informacje dotyczące zestawu znaków, Operatorzy i konstrukcji, których można użyć do zdefiniowania wyrażeń regularnych.
