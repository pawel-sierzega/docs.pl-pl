---
title: 'Porady: odczyt i zapis w plikach w izolowanym magazynie'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- files, isolated storage
- reading data
- storing data using isolated storage, reading and writing to files
- writing to files within store
- data storage using isolated storage, reading and writing to files
- reading files within store
- isolated storage, reading and writing to files
- data stores, reading and writing to files
- stores, reading and writing to files
ms.assetid: f977ebdc-1b55-475a-bc3d-3376470b08ae
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cfb1500150d2dfb500a698713c0de6b8e5518010
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-read-and-write-to-files-in-isolated-storage"></a>Porady: odczyt i zapis w plikach w izolowanym magazynie
Aby odczytać lub zapisać do pliku w magazynie izolowanym, użyj <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> obiektu Czytnik strumienia (<xref:System.IO.StreamReader> obiektu) lub piszący strumienia (<xref:System.IO.StreamWriter> obiektu).  
  
## <a name="example"></a>Przykład  
 Poniższy przykładowy kod uzyskuje izolowanego magazynu i sprawdza, czy istnieje plik o nazwie TestStore.txt w magazynie. Jeśli nie istnieje, tworzy plik i zapisuje dane w pliku "Hello izolowanych magazynów". Jeśli TestStore.txt już istnieje, przykładowy kod odczytuje z pliku.  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 <xref:System.IO.FileMode?displayProperty=nameWithType>  
 <xref:System.IO.FileAccess?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader?displayProperty=nameWithType>  
 <xref:System.IO.StreamWriter?displayProperty=nameWithType>  
 [Plik i strumienia I-O](../../../docs/standard/io/index.md)  
 [Wydzielona pamięć masowa](../../../docs/standard/io/isolated-storage.md)
