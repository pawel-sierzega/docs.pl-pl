---
title: "AndAlso — Operator (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5f92f4ed226c2923c3d95a7b80db3872b7ac33dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="f75ac-102">AndAlso — Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f75ac-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="f75ac-103">Wykonuje skrótowe połączenie logiczne dwóch wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="f75ac-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f75ac-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f75ac-104">Syntax</span></span>  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="f75ac-105">Części</span><span class="sxs-lookup"><span data-stu-id="f75ac-105">Parts</span></span>  
  
|<span data-ttu-id="f75ac-106">Termin</span><span class="sxs-lookup"><span data-stu-id="f75ac-106">Term</span></span>|<span data-ttu-id="f75ac-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="f75ac-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="f75ac-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="f75ac-108">Required.</span></span> <span data-ttu-id="f75ac-109">Wszelkie `Boolean` wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="f75ac-109">Any `Boolean` expression.</span></span> <span data-ttu-id="f75ac-110">W rezultacie `Boolean` wynik porównania dwóch wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="f75ac-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="f75ac-111">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="f75ac-111">Required.</span></span> <span data-ttu-id="f75ac-112">Wszelkie `Boolean` wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="f75ac-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="f75ac-113">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="f75ac-113">Required.</span></span> <span data-ttu-id="f75ac-114">Wszelkie `Boolean` wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="f75ac-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f75ac-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f75ac-115">Remarks</span></span>  
 <span data-ttu-id="f75ac-116">Operacja logiczna jest określany jako *zwarcie* Jeśli skompilowanego kodu można pominąć obliczania jednego wyrażenia w zależności od wyniku innego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="f75ac-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="f75ac-117">Jeśli wynik pierwsze wyrażenie obliczane określa końcowego wyniku operacji, jest niepotrzebna można oszacować wyrażenia drugiego, ponieważ nie można zmienić wynik końcowy.</span><span class="sxs-lookup"><span data-stu-id="f75ac-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="f75ac-118">Zwarcie może zwiększyć wydajność, jeśli pominięto wyrażenie jest złożony, czy obejmuje on wywołań procedur.</span><span class="sxs-lookup"><span data-stu-id="f75ac-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="f75ac-119">Jeśli oba wyrażenia mają `True`, `result` jest `True`.</span><span class="sxs-lookup"><span data-stu-id="f75ac-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="f75ac-120">W poniższej tabeli przedstawiono sposób `result` jest określana.</span><span class="sxs-lookup"><span data-stu-id="f75ac-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="f75ac-121">Jeśli `expression1` jest</span><span class="sxs-lookup"><span data-stu-id="f75ac-121">If `expression1` is</span></span>|<span data-ttu-id="f75ac-122">I `expression2` jest</span><span class="sxs-lookup"><span data-stu-id="f75ac-122">And `expression2` is</span></span>|<span data-ttu-id="f75ac-123">Wartość `result` jest</span><span class="sxs-lookup"><span data-stu-id="f75ac-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="f75ac-124">(nie jest oceniany)</span><span class="sxs-lookup"><span data-stu-id="f75ac-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="f75ac-125">Typy danych</span><span class="sxs-lookup"><span data-stu-id="f75ac-125">Data Types</span></span>  
 <span data-ttu-id="f75ac-126">`AndAlso` Operator jest zdefiniowana tylko dla [— typ danych logicznych](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="f75ac-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="f75ac-127">Visual Basic konwertuje każdy argument operacji niezbędny do `Boolean` i wykonuje operację wyłącznie w `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="f75ac-127">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="f75ac-128">Przypisz wynik do typu liczbowego, Visual Basic przekonwertuje go z `Boolean` dla tego typu.</span><span class="sxs-lookup"><span data-stu-id="f75ac-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="f75ac-129">Można to osiągnąć nieoczekiwane zachowanie.</span><span class="sxs-lookup"><span data-stu-id="f75ac-129">This could produce unexpected behavior.</span></span> <span data-ttu-id="f75ac-130">Na przykład `5 AndAlso 12` powoduje `–1` po konwersji na `Integer`.</span><span class="sxs-lookup"><span data-stu-id="f75ac-130">For example, `5 AndAlso 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f75ac-131">Przeciążenie</span><span class="sxs-lookup"><span data-stu-id="f75ac-131">Overloading</span></span>  
 <span data-ttu-id="f75ac-132">[i operatora](../../../visual-basic/language-reference/operators/and-operator.md) i [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) może być *przeciążony*, co oznacza, że klasy lub struktury można zmienić ich zachowania, gdy argument operacji ma typ, który klasy lub struktury.</span><span class="sxs-lookup"><span data-stu-id="f75ac-132">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f75ac-133">Przeciążanie `And` i `IsFalse` operatory wpływa na działanie `AndAlso` operatora.</span><span class="sxs-lookup"><span data-stu-id="f75ac-133">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="f75ac-134">Jeśli używa Twój kod `AndAlso` na klasę lub strukturę, która overloads `And` i `IsFalse`, trzeba koniecznie zapoznać się ich zachowanie ponownie zdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="f75ac-134">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="f75ac-135">Aby uzyskać więcej informacji, zobacz [procedury operatorów](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f75ac-135">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f75ac-136">Przykład</span><span class="sxs-lookup"><span data-stu-id="f75ac-136">Example</span></span>  
 <span data-ttu-id="f75ac-137">W poniższym przykładzie użyto `AndAlso` operatora, aby wykonać koniunkcję logiczną na dwóch wyrażeniach.</span><span class="sxs-lookup"><span data-stu-id="f75ac-137">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="f75ac-138">Wynik jest `Boolean` wartość wskazującą, czy cały conjoined wyrażenie ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="f75ac-138">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="f75ac-139">Jeśli pierwsze wyrażenie jest `False`, drugie nie jest obliczane.</span><span class="sxs-lookup"><span data-stu-id="f75ac-139">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 <span data-ttu-id="f75ac-140">Powyższy przykład produkuje wyniki `True`, `False`, i `False`odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="f75ac-140">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="f75ac-141">Podczas obliczania `secondCheck`, drugie wyrażenie nie jest oceniany, ponieważ pierwszy jest już `False`.</span><span class="sxs-lookup"><span data-stu-id="f75ac-141">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="f75ac-142">Jednak drugie wyrażenie jest obliczane w obliczeniach `thirdCheck`.</span><span class="sxs-lookup"><span data-stu-id="f75ac-142">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f75ac-143">Przykład</span><span class="sxs-lookup"><span data-stu-id="f75ac-143">Example</span></span>  
 <span data-ttu-id="f75ac-144">W poniższym przykładzie przedstawiono `Function` procedury, która przeszukuje dla danej wartości między elementami tablicy.</span><span class="sxs-lookup"><span data-stu-id="f75ac-144">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="f75ac-145">Jeśli tablica jest pusta lub przekroczeniu długości tablicy `While` instrukcji nie sprawdza elementu tablicy względem wartości wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="f75ac-145">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f75ac-146">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f75ac-146">See Also</span></span>  
 [<span data-ttu-id="f75ac-147">Operatory logiczne/bitowe (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f75ac-147">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="f75ac-148">Kolejność wykonywania w języku Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f75ac-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="f75ac-149">Operatory według funkcji</span><span class="sxs-lookup"><span data-stu-id="f75ac-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="f75ac-150">And — Operator</span><span class="sxs-lookup"><span data-stu-id="f75ac-150">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)  
 [<span data-ttu-id="f75ac-151">IsFalse — Operator</span><span class="sxs-lookup"><span data-stu-id="f75ac-151">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="f75ac-152">Operatory logiczne i bitowe w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f75ac-152">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)