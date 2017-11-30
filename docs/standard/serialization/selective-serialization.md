---
title: Selektywne serializacji
ms.date: 08/07/2017
ms.prod: .net
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f583c0c7f2895b16ac0aea883dd98b4768179127
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="selective-serialization"></a><span data-ttu-id="05abf-102">Selektywne serializacji</span><span class="sxs-lookup"><span data-stu-id="05abf-102">Selective serialization</span></span>
<span data-ttu-id="05abf-103">Klasa często zawiera pola, które nie powinny być serializowane.</span><span class="sxs-lookup"><span data-stu-id="05abf-103">A class often contains fields that shouldn't be serialized.</span></span> <span data-ttu-id="05abf-104">Załóżmy na przykład, że identyfikator wątku w klasie są przechowywane w zmiennej członkowskiej.</span><span class="sxs-lookup"><span data-stu-id="05abf-104">For example, assume a class stores a thread ID in a member variable.</span></span> <span data-ttu-id="05abf-105">Podczas deserializacji jest klasa, wątek przechowywane identyfikator kiedy została wykonana serializacja klasy nie może być uruchomiony; Dlatego serializacji tej wartości nie ma sensu.</span><span class="sxs-lookup"><span data-stu-id="05abf-105">When the class is deserialized, the thread stored the ID for when the class was serialized might no longer be running; so serializing this value doesn't make sense.</span></span> <span data-ttu-id="05abf-106">Zmienne Członkowskie uniemożliwi serializowana oznaczając je za pomocą [NonSerialized](xref:System.NonSerializedAttribute) atrybutu w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="05abf-106">You can prevent member variables from being serialized by marking them with the [NonSerialized](xref:System.NonSerializedAttribute) attribute as follows.</span></span>  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

<span data-ttu-id="05abf-107">Jeśli to możliwe należy obiekt zawierający dane dotyczące zabezpieczeń nonserializable.</span><span class="sxs-lookup"><span data-stu-id="05abf-107">If possible, make an object that could contain security-sensitive data nonserializable.</span></span> <span data-ttu-id="05abf-108">Jeśli obiekt musi być serializowany, zastosuj `NonSerialized` atrybutu określonych pól, które przechowują dane poufne.</span><span class="sxs-lookup"><span data-stu-id="05abf-108">If the object must be serialized, apply the `NonSerialized` attribute to specific fields that store sensitive data.</span></span> <span data-ttu-id="05abf-109">Nie można wykluczyć te pola z serializacji, należy pamiętać, że dane, które przechowują są widoczne dla żadnego kodu, który ma uprawnienia do serializacji.</span><span class="sxs-lookup"><span data-stu-id="05abf-109">If you don't exclude these fields from serialization, be aware that the data they store are exposed to any code that has permission to serialize.</span></span> <span data-ttu-id="05abf-110">Aby uzyskać więcej informacji na temat pisania kodu serializacji bezpieczny, zobacz [zabezpieczenia i serializacja](../../../docs/framework/misc/security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="05abf-110">For more information about writing secure serialization code, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="05abf-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="05abf-111">See also</span></span>  
 [<span data-ttu-id="05abf-112">Serializacja binarna</span><span class="sxs-lookup"><span data-stu-id="05abf-112">Binary Serialization</span></span>](binary-serialization.md)  
 [<span data-ttu-id="05abf-113">XML i serializacji SOAP</span><span class="sxs-lookup"><span data-stu-id="05abf-113">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)  
 [<span data-ttu-id="05abf-114">Zabezpieczenia i serializacja</span><span class="sxs-lookup"><span data-stu-id="05abf-114">Security and Serialization</span></span>](../../../docs/framework/misc/security-and-serialization.md)