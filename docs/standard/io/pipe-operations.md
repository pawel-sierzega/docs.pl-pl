---
title: Operacje potokowe w oprogramowaniu .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 68c1ad34952ee4d20dbf56aa8ca437a3f99db751
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/23/2017
---
# <a name="pipe-operations-in-the-net-framework"></a>Operacje potokowe w oprogramowaniu .NET Framework
Potoki umożliwiają do komunikacji międzyprocesowej. Istnieją dwa typy potoków:  
  
-   Potoki anonimowe.  
  
     Potoki anonimowe zapewnienia komunikacji międzyprocesowej na komputerze lokalnym. Potoki anonimowe wymagają mniejsze koszty niż nazwane potoki, ale oferuje ograniczonych usług. Potoki anonimowe są jednokierunkowe i nie można używać w sieci. Obsługuje tylko jeden serwer wystąpienie. Potoki anonimowe są przydatne w przypadku komunikacji między wątkami lub między procesami nadrzędnych i podrzędnych, których dojścia potoku mogą być łatwo przekazywane do procesu podrzędnego podczas jego tworzenia.  
  
     W programie .NET Framework potoków anonimowych wdrożyć przy użyciu <xref:System.IO.Pipes.AnonymousPipeServerStream> i <xref:System.IO.Pipes.AnonymousPipeClientStream> klasy.  
  
     Zobacz [porady: stosowanie anonimowych potoków do lokalnej komunikacji międzyprocesowej](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).  
  
-   Nazwane potoki.  
  
     Nazwane potoki zapewniają komunikację międzyprocesorową pomiędzy serwerem potoku i jednym lub kilkoma klientami potoku. Nazwane potoki mogą być jednokierunkowe lub dwukierunkowego. Obsługuje komunikacja oparta na komunikat, a Zezwalaj wielu klientom na łączenie się jednocześnie do procesu serwera przy użyciu tej samej nazwy potoku. Nazwane potoki obsługują także personifikacji, dzięki czemu łączącego procesów własnych uprawnień na serwerach zdalnych.  
  
     W programie .NET Framework nazwanych potoków można wdrożyć przy użyciu <xref:System.IO.Pipes.NamedPipeServerStream> i <xref:System.IO.Pipes.NamedPipeClientStream> klasy.  
  
     Zobacz [porady: stosowanie nazwanych potoków do sieciowej komunikacji międzyprocesowej](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Plik i strumienia I-O](../../../docs/standard/io/index.md)  
 [Instrukcje: stosowanie potoków anonimowych do lokalnej komunikacji międzyprocesowej](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)  
 [Instrukcje: stosowanie potoków nazwanych do sieciowej komunikacji międzyprocesowej](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
