---
title: REF (jednostka SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: dfc91b60c68f55def8e7f81c2c5dd068c23f6e69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ref-entity-sql"></a><span data-ttu-id="728bc-102">REF (jednostka SQL)</span><span class="sxs-lookup"><span data-stu-id="728bc-102">REF (Entity SQL)</span></span>
<span data-ttu-id="728bc-103">Zwraca odwołanie do wystąpienia jednostki.</span><span class="sxs-lookup"><span data-stu-id="728bc-103">Returns a reference to an entity instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="728bc-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="728bc-104">Syntax</span></span>  
  
```  
REF( expression )   
```  
  
## <a name="arguments"></a><span data-ttu-id="728bc-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="728bc-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="728bc-106">Dowolne prawidłowe wyrażenie zwracające wystąpienia typu jednostki.</span><span class="sxs-lookup"><span data-stu-id="728bc-106">Any valid expression that yields an instance of an entity type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="728bc-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="728bc-107">Return Value</span></span>  
 <span data-ttu-id="728bc-108">Odwołanie do wystąpienia określonej jednostki.</span><span class="sxs-lookup"><span data-stu-id="728bc-108">A reference to the specified entity instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="728bc-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="728bc-109">Remarks</span></span>  
 <span data-ttu-id="728bc-110">Odwołanie do jednostki składa się z kluczem jednostki i nazwa zestawu jednostek.</span><span class="sxs-lookup"><span data-stu-id="728bc-110">An entity reference consists of the entity key and an entity set name.</span></span> <span data-ttu-id="728bc-111">Ponieważ zestawów jednostek różnych może bazować na ten sam typ obiektu klucza danego podmiotu może występować w wielu zestawach jednostek.</span><span class="sxs-lookup"><span data-stu-id="728bc-111">Because different entity sets can be based on the same entity type, a particular entity key can appear in multiple entity sets.</span></span> <span data-ttu-id="728bc-112">Jednak odwołania do obiektu jest zawsze unikatowa.</span><span class="sxs-lookup"><span data-stu-id="728bc-112">However, an entity reference is always unique.</span></span> <span data-ttu-id="728bc-113">Jeśli wyrażenie wejściowe reprezentuje jednostkę utrwalonego, zostanie zwrócony odwołania do tej jednostki.</span><span class="sxs-lookup"><span data-stu-id="728bc-113">If the input expression represents a persisted entity, a reference to this entity will be returned.</span></span> <span data-ttu-id="728bc-114">Jeśli wyrażenie wejściowe nie jest utrwalona jednostki, zostanie zwrócony odwołanie o wartości null.</span><span class="sxs-lookup"><span data-stu-id="728bc-114">If the input expression is not a persisted entity, a null reference will be returned.</span></span>  
  
 <span data-ttu-id="728bc-115">Jeśli właściwość operator wyodrębniania (.) są używane do dostępu do właściwości jednostki, odwołanie jest automatycznie wyłuskiwany.</span><span class="sxs-lookup"><span data-stu-id="728bc-115">If the property extraction operator (.) is used to access a property of an entity, the reference is automatically dereferenced.</span></span>  
  
## <a name="example"></a><span data-ttu-id="728bc-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="728bc-116">Example</span></span>  
 <span data-ttu-id="728bc-117">Następujące zapytanie SQL jednostki używa operatora REF do zwrócenia odwołania dla argumentu wejściowego jednostki.</span><span class="sxs-lookup"><span data-stu-id="728bc-117">The following Entity SQL query uses the REF operator to return the reference for an input entity argument.</span></span> <span data-ttu-id="728bc-118">Samo zapytanie wyłuskań odwołanie, ponieważ operacja wyodrębniania właściwości (.) jest używany do dostępu do właściwości jednostki produktu.</span><span class="sxs-lookup"><span data-stu-id="728bc-118">The same query dereferences the reference because we are using a property extraction operation (.) to access a property of the Product entity.</span></span> <span data-ttu-id="728bc-119">Kwerenda jest oparta na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="728bc-119">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="728bc-120">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="728bc-120">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="728bc-121">Postępuj zgodnie z procedurą w [porady: wykonywanie zapytań tego zwraca wyniki PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="728bc-121">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="728bc-122">Przekaż następujące zapytanie jako argument do `ExecutePrimitiveTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="728bc-122">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## <a name="see-also"></a><span data-ttu-id="728bc-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="728bc-123">See Also</span></span>  
 [<span data-ttu-id="728bc-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="728bc-124">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [<span data-ttu-id="728bc-125">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="728bc-125">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [<span data-ttu-id="728bc-126">KLUCZ</span><span class="sxs-lookup"><span data-stu-id="728bc-126">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="728bc-127">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="728bc-127">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="728bc-128">Definicje typów</span><span class="sxs-lookup"><span data-stu-id="728bc-128">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)