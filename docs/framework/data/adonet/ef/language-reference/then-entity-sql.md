---
title: "NASTĘPNIE (jednostka SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 99fd941c963ff87203d7b315beb606d40001224d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="then-entity-sql"></a><span data-ttu-id="ba139-102">NASTĘPNIE (jednostka SQL)</span><span class="sxs-lookup"><span data-stu-id="ba139-102">THEN (Entity SQL)</span></span>
<span data-ttu-id="ba139-103">Wynik klauzuli WHEN podczas daje w wyniku `true`.</span><span class="sxs-lookup"><span data-stu-id="ba139-103">The result of a WHEN clause when it evaluates to `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba139-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ba139-104">Syntax</span></span>  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ba139-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="ba139-105">Arguments</span></span>  
 `when_expression`  
 <span data-ttu-id="ba139-106">Prawidłowe wyrażenie logiczne.</span><span class="sxs-lookup"><span data-stu-id="ba139-106">Any valid Boolean expression.</span></span>  
  
 `then_expression`  
 <span data-ttu-id="ba139-107">Dowolne wyrażenie prawidłową kwerendę, która zwraca kolekcję.</span><span class="sxs-lookup"><span data-stu-id="ba139-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba139-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ba139-108">Remarks</span></span>  
 <span data-ttu-id="ba139-109">Jeśli `when_expression` daje w wyniku wartość `true`, wynikiem jest odpowiednie `then-expression`.</span><span class="sxs-lookup"><span data-stu-id="ba139-109">If `when_expression` evaluates to the value `true`, the result is the corresponding `then-expression`.</span></span> <span data-ttu-id="ba139-110">Jeśli żadna z WHEN warunki są spełnione, `else-expression` oceny.</span><span class="sxs-lookup"><span data-stu-id="ba139-110">If none of the WHEN conditions are satisfied, the `else-expression` is evaluated.</span></span> <span data-ttu-id="ba139-111">Jednak w przypadku nie `else-expression`, wynikiem jest wartość null.</span><span class="sxs-lookup"><span data-stu-id="ba139-111">However, if there is no `else-expression`, the result is null.</span></span>  
  
 <span data-ttu-id="ba139-112">Na przykład zobacz [przypadku](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ba139-112">For an example, see [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba139-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="ba139-113">Example</span></span>  
 <span data-ttu-id="ba139-114">Następujące zapytanie SQL jednostki użyto wyrażenia CASE można obliczyć zestawu `Boolean` wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="ba139-114">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions.</span></span> <span data-ttu-id="ba139-115">Kwerenda jest oparta na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ba139-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ba139-116">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="ba139-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ba139-117">Postępuj zgodnie z procedurą w [porady: wykonywanie zapytań tego zwraca wyniki PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ba139-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="ba139-118">Przekaż następujące zapytanie jako argument do `ExecutePrimitiveTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="ba139-118">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="ba139-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ba139-119">See Also</span></span>  
 [<span data-ttu-id="ba139-120">CASE</span><span class="sxs-lookup"><span data-stu-id="ba139-120">CASE</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)  
 [<span data-ttu-id="ba139-121">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="ba139-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)