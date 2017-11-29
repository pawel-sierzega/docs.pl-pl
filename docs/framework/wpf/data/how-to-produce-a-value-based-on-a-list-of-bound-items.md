---
title: "Jak uzyskać wartość w oparciu o listę powiązanych elementów"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d16a198ed78c1ffd9dcaad595e9cc9be3cb2de0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="b978b-102">Jak uzyskać wartość w oparciu o listę powiązanych elementów</span><span class="sxs-lookup"><span data-stu-id="b978b-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<span data-ttu-id="b978b-103"><xref:System.Windows.Data.MultiBinding>Umożliwia powiązać właściwość target powiązanie listę właściwości źródła, a następnie zastosować logiki w celu utworzenia wartości o dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="b978b-103"><xref:System.Windows.Data.MultiBinding> allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="b978b-104">W tym przykładzie przedstawiono sposób użycia <xref:System.Windows.Data.MultiBinding>.</span><span class="sxs-lookup"><span data-stu-id="b978b-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b978b-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="b978b-105">Example</span></span>  
 <span data-ttu-id="b978b-106">W poniższym przykładzie `NameListData` odwołuje się do kolekcji `PersonName` obiektów, które są obiekty, które zawierają dwie właściwości, `firstName` i `lastName`.</span><span class="sxs-lookup"><span data-stu-id="b978b-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="b978b-107">Poniższy przykład tworzy <xref:System.Windows.Controls.TextBlock> który pokazuje imiona i nazwiska osoby z nazwisko pierwszy.</span><span class="sxs-lookup"><span data-stu-id="b978b-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="b978b-108">Aby zrozumieć, jak jest generowany format ostatnich nazwę pierwszego, Spójrzmy na implementacji `NameConverter`:</span><span class="sxs-lookup"><span data-stu-id="b978b-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 <span data-ttu-id="b978b-109">`NameConverter`implementuje <xref:System.Windows.Data.IMultiValueConverter> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="b978b-109">`NameConverter` implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> <span data-ttu-id="b978b-110">`NameConverter`pobiera wartości poszczególnych powiązania i przechowuje je w tablicy wartości obiektu.</span><span class="sxs-lookup"><span data-stu-id="b978b-110">`NameConverter` takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="b978b-111">Kolejność <xref:System.Windows.Data.Binding> elementy są wyświetlane w obszarze <xref:System.Windows.Data.MultiBinding> element to kolejność, w jakiej te wartości są przechowywane w tablicy.</span><span class="sxs-lookup"><span data-stu-id="b978b-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="b978b-112">Wartość <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> odwołuje się atrybut argument parametru <xref:System.Windows.Data.MultiBinding.Converter%2A> metodę, która wykonuje przełącznik na parametr, aby określić, w jaki format nazwy.</span><span class="sxs-lookup"><span data-stu-id="b978b-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b978b-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b978b-113">See Also</span></span>  
 [<span data-ttu-id="b978b-114">Konwertuj powiązana z danymi</span><span class="sxs-lookup"><span data-stu-id="b978b-114">Convert Bound Data</span></span>](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)  
 [<span data-ttu-id="b978b-115">Omówienie powiązania danych</span><span class="sxs-lookup"><span data-stu-id="b978b-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="b978b-116">Tematy porad</span><span class="sxs-lookup"><span data-stu-id="b978b-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)