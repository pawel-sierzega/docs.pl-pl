---
title: "Chronione elementy członkowskie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 03d9eac41e693568da2d057bc1394c426df4c736
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/23/2017
---
# <a name="protected-members"></a>Chronione elementy członkowskie
Chronione elementy członkowskie samodzielnie nie dostarcza żadnych rozszerzalności, ale może wprowadzić bardziej zaawansowanych rozszerzeń przez podklasy. One może służyć do udostępnienia opcje zaawansowane dostosowywanie bez niepotrzebnie komplikując głównego interfejs publiczny.  
  
 Projektanci Framework konieczne należy zachować ostrożność przy chronionych elementów członkowskich, ponieważ nazwa "protected", który pozwala false rozumieniu zabezpieczeń. Każda osoba, która jest w stanie podklasą klasy niezapieczętowany i dostęp do chronionych elementów członkowskich, a więc te same obrony praktyk kodowania elementów publicznych dotyczą chronionych elementów członkowskich.  
  
 **ROZWAŻ ✓** przy użyciu chronione elementy członkowskie dostosowania zaawansowanego.  
  
 **CZY ✓** Traktuj chronionych elementów członkowskich w klasach otwarty jako public na potrzeby analizy zabezpieczeń, dokumentacji i zgodności.  
  
 Każda osoba, która dziedziczy z klasy, a dostęp do chronionych elementów członkowskich.  
  
 *Fragmenty © 2005, 2009 Microsoft Corporation. Wszelkie prawa zastrzeżone.*  
  
 *Drukowane uprawnieniami wariancji x edukacji, Inc. z [Framework zaleceń dotyczących projektowania: konwencje, Idioms i wzorce dla bibliotek .NET wielokrotnego użytku, wydanie 2](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina i Abrams Brada opublikowane 22 Oct 2008 przez Professional Addison-Wesley jako część serii rozwoju systemu Windows firmy Microsoft.*  
  
## <a name="see-also"></a>Zobacz też  
 [Struktura — zalecenia dotyczące projektowania](../../../docs/standard/design-guidelines/index.md)  
 [Projektowanie pod kątem rozszerzalności](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
