---
title: "Usuwanie zawartości węzła w modelu DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 76be90829a414b091d3b311b96bf9bab9a2b56ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="removing-node-content-in-the-dom"></a><span data-ttu-id="cbb59-102">Usuwanie zawartości węzła w modelu DOM</span><span class="sxs-lookup"><span data-stu-id="cbb59-102">Removing Node Content in the DOM</span></span>
<span data-ttu-id="cbb59-103">Dla typów węzłów, które dziedziczą z <xref:System.Xml.XmlCharacterData>, które są <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, i <xref:System.Xml.XmlSignificantWhitespace> typy węzłów, można usunąć znaki przy użyciu <xref:System.Xml.XmlCharacterData.DeleteData%2A> metodę, która usuwa zakres znaki z węzła.</span><span class="sxs-lookup"><span data-stu-id="cbb59-103">For node types that inherit from <xref:System.Xml.XmlCharacterData>, which are the <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, and <xref:System.Xml.XmlSignificantWhitespace> node types, you can remove characters using the <xref:System.Xml.XmlCharacterData.DeleteData%2A> method, which removes a range of characters from the node.</span></span> <span data-ttu-id="cbb59-104">Jeśli chcesz całkowicie usunąć zawartości, należy usunąć węzeł z zawartością.</span><span class="sxs-lookup"><span data-stu-id="cbb59-104">If you want to remove content completely, you remove the node that contains the content.</span></span> <span data-ttu-id="cbb59-105">Jeśli chcesz zachować węzeł, ale zawartość jest nieprawidłowa, następnie zmodyfikować zawartość.</span><span class="sxs-lookup"><span data-stu-id="cbb59-105">If you want to keep the node, but the content is incorrect, then modify the content.</span></span> <span data-ttu-id="cbb59-106">Aby uzyskać informacje na temat modyfikowania zawartości węzła, zobacz [modyfikowanie węzłów, zawartość i wartości w dokumencie XML](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="cbb59-106">For information on modifying the content of a node, see [Modifying Nodes, Content, and Values in an XML Document](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbb59-107">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cbb59-107">See Also</span></span>  
 [<span data-ttu-id="cbb59-108">Modelu obiektu dokumentu XML modelu DOM)</span><span class="sxs-lookup"><span data-stu-id="cbb59-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)