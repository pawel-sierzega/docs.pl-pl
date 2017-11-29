---
title: "&lt;proceduresignature1&gt; nie jest zgodne ze specyfikacją CLS, ponieważ przeciąża &lt;proceduresignature2&gt; który różni się od niego tylko tablicą typów parametrów tablicowych lub rangą typów parametrów tablicowych"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords: BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fa9fca7f0590846f60577787aa476539a2c872a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="30497-102">&lt;proceduresignature1&gt; nie jest zgodne ze specyfikacją CLS, ponieważ przeciąża &lt;proceduresignature2&gt; który różni się od niego tylko tablicą typów parametrów tablicowych lub rangą typów parametrów tablicowych</span><span class="sxs-lookup"><span data-stu-id="30497-102">&lt;proceduresignature1&gt; is not CLS-compliant because it overloads &lt;proceduresignature2&gt; which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>
<span data-ttu-id="30497-103">Procedura lub właściwość jest oznaczona jako `<CLSCompliant(True)>` po zastępują innej procedury lub właściwości i jest jedyną różnicą między ich listy parametrów poziom zagnieżdżenia tablicy nieregularnej lub rangę tablicy.</span><span class="sxs-lookup"><span data-stu-id="30497-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>  
  
 <span data-ttu-id="30497-104">W deklaracjach następujące deklaracje drugiego i trzeciego Generowanie tego błędu.</span><span class="sxs-lookup"><span data-stu-id="30497-104">In the following declarations, the second and third declarations generate this error.</span></span>  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 <span data-ttu-id="30497-105">Druga deklaracja zmienia pierwotny parametr jednowymiarowa `arrayParam` do tablicy tablic.</span><span class="sxs-lookup"><span data-stu-id="30497-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="30497-106">Trzeci zmiany deklaracji `arrayParam` z tablicą dwuwymiarową (pozycja 2).</span><span class="sxs-lookup"><span data-stu-id="30497-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="30497-107">Chociaż Visual Basic pozwala przeciążenia mogą się różnić tylko przez jeden z tych zmian, takich przeciążanie nie jest zgodne z [niezależność od języka i elementy niezależne od języka](https://msdn.microsoft.com/library/12a7a7h3) (ze specyfikacją CLS).</span><span class="sxs-lookup"><span data-stu-id="30497-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span></span>  
  
 <span data-ttu-id="30497-108">Po zastosowaniu <xref:System.CLSCompliantAttribute> do elementu programistycznego, ten atrybut zostanie ustawiony `isCompliant` albo parametr `True` lub `False` zgodności lub niezgodności.</span><span class="sxs-lookup"><span data-stu-id="30497-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="30497-109">Nie jest domyślnie dla tego parametru, a należy podać wartość.</span><span class="sxs-lookup"><span data-stu-id="30497-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="30497-110">Jeśli nie mają zastosowania <xref:System.CLSCompliantAttribute> do elementu, jest uznawane za niezgodne.</span><span class="sxs-lookup"><span data-stu-id="30497-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="30497-111">Domyślnie ten komunikat jest ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="30497-111">By default, this message is a warning.</span></span> <span data-ttu-id="30497-112">Aby uzyskać informacje na ukrywanie ostrzeżenia lub traktowanie ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="30497-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="30497-113">**Identyfikator błędu:** BC40035</span><span class="sxs-lookup"><span data-stu-id="30497-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="30497-114">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="30497-114">To correct this error</span></span>  
  
-   <span data-ttu-id="30497-115">Jeśli potrzebujesz zgodności ze specyfikacją CLS, zdefiniuj z przeciążeń mogą się różnić od siebie na więcej sposobów niż tylko zmiany wymienione na tej stronie pomocy.</span><span class="sxs-lookup"><span data-stu-id="30497-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>  
  
-   <span data-ttu-id="30497-116">Jeśli wymagasz, że przeciążeń różnią się jedynie przez zmiany wymienione w tej pomocy strony, Usuń <xref:System.CLSCompliantAttribute> z ich definicje lub oznaczyć je jako `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="30497-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30497-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="30497-117">See Also</span></span>  
 [<span data-ttu-id="30497-118">\<PAVE za pośrednictwem > Pisanie kodu zgodne ze specyfikacją CLS</span><span class="sxs-lookup"><span data-stu-id="30497-118">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)  
 [<span data-ttu-id="30497-119">Przeciążanie procedury</span><span class="sxs-lookup"><span data-stu-id="30497-119">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [<span data-ttu-id="30497-120">Przeciążenia</span><span class="sxs-lookup"><span data-stu-id="30497-120">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)