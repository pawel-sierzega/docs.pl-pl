---
title: "Konstruowanie typów (jednostka SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41fa7bde-8d20-4a3f-a3d2-fb791e128010
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 48dab533e26d6353c29667d81ea547f4b15d280f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="constructing-types-entity-sql"></a><span data-ttu-id="b5d17-102">Konstruowanie typów (jednostka SQL)</span><span class="sxs-lookup"><span data-stu-id="b5d17-102">Constructing Types (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="b5d17-103">udostępnia trzy rodzaje konstruktory: wiersz konstruktorów, typ nazwany konstruktorów i konstruktorów kolekcji.</span><span class="sxs-lookup"><span data-stu-id="b5d17-103"> provides three kinds of constructors: row constructors, named type constructors, and collection constructors.</span></span>  
  
## <a name="row-constructors"></a><span data-ttu-id="b5d17-104">Konstruktory wiersza</span><span class="sxs-lookup"><span data-stu-id="b5d17-104">Row Constructors</span></span>  
 <span data-ttu-id="b5d17-105">Użyj konstruktorów wiersza w [!INCLUDE[esql](../../../../../../includes/esql-md.md)] do skonstruowania anonimowe, strukturę maszynowy rekordy z co najmniej jedną wartość.</span><span class="sxs-lookup"><span data-stu-id="b5d17-105">You use row constructors in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="b5d17-106">Typ wyniku konstruktorze wierszy jest typu wiersza, których typy pól odpowiadają typy wartości używane do utworzenia wiersza.</span><span class="sxs-lookup"><span data-stu-id="b5d17-106">The result type of a row constructor is a row type whose field types correspond to the types of the values used to construct the row.</span></span> <span data-ttu-id="b5d17-107">Na przykład poniższe wyrażenie tworzy wartość typu `Record(a int, b string, c int)`:</span><span class="sxs-lookup"><span data-stu-id="b5d17-107">For example, the following expression constructs a value of type `Record(a int, b string, c int)`:</span></span>  
  
 `ROW(1 AS a, "abc" AS b, a + 34 AS c)`  
  
 <span data-ttu-id="b5d17-108">Jeśli nie zostanie określona alias dla wyrażenia w Konstruktorze row, programu Entity Framework próbuje wygenerować.</span><span class="sxs-lookup"><span data-stu-id="b5d17-108">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="b5d17-109">Aby uzyskać więcej informacji, zobacz sekcję "Zasady aliasowania" w [identyfikatory](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b5d17-109">For more information, see the "Aliasing Rules" section in [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="b5d17-110">Wyrażenie aliasów w Konstruktorze row mają zastosowanie następujące reguły:</span><span class="sxs-lookup"><span data-stu-id="b5d17-110">The following rules apply to expression aliasing in a row constructor:</span></span>  
  
-   <span data-ttu-id="b5d17-111">Wyrażenia w Konstruktorze row nie może odwoływać się do innych aliasów w tej samej konstruktora.</span><span class="sxs-lookup"><span data-stu-id="b5d17-111">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>  
  
-   <span data-ttu-id="b5d17-112">Dwóch wyrażeń w tym samym Konstruktor row nie może mieć takiego samego aliasu.</span><span class="sxs-lookup"><span data-stu-id="b5d17-112">Two expressions in the same row constructor cannot have the same alias.</span></span>  
  
 <span data-ttu-id="b5d17-113">Aby uzyskać więcej informacji na temat konstruktorów wiersza, zobacz [wiersza](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b5d17-113">For more information about row constructors, see [ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).</span></span>  
  
## <a name="collection-constructors"></a><span data-ttu-id="b5d17-114">Konstruktory kolekcji</span><span class="sxs-lookup"><span data-stu-id="b5d17-114">Collection Constructors</span></span>  
 <span data-ttu-id="b5d17-115">Użyj konstruktorów kolekcji w [!INCLUDE[esql](../../../../../../includes/esql-md.md)] można utworzyć wystąpienia zestaw wielokrotny z listy wartości.</span><span class="sxs-lookup"><span data-stu-id="b5d17-115">You use collection constructors in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="b5d17-116">Wszystkie wartości w Konstruktorze musi być typu wzajemnie zgodne `T`, i konstruktora tworzy kolekcję typu `Multiset<T>`.</span><span class="sxs-lookup"><span data-stu-id="b5d17-116">All the values in the constructor must be of mutually compatible type `T`, and the constructor produces a collection of type `Multiset<T>`.</span></span> <span data-ttu-id="b5d17-117">Na przykład poniższe wyrażenie tworzy kolekcję liczb całkowitych:</span><span class="sxs-lookup"><span data-stu-id="b5d17-117">For example, the following expression creates a collection of integers:</span></span>  
  
 `Multiset(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
 <span data-ttu-id="b5d17-118">Pusty zestaw wielokrotny konstruktory nie są dozwolone, ponieważ nie można określić typu elementów.</span><span class="sxs-lookup"><span data-stu-id="b5d17-118">Empty multiset constructors are not allowed because the type of the elements cannot be determined.</span></span> <span data-ttu-id="b5d17-119">Następujący ciąg nie jest prawidłowy:</span><span class="sxs-lookup"><span data-stu-id="b5d17-119">The following is not valid:</span></span>  
  
 `multiset() {}`  
  
 <span data-ttu-id="b5d17-120">Aby uzyskać więcej informacji, zobacz [MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b5d17-120">For more information, see [MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md).</span></span>  
  
## <a name="named-type-constructors-namedtype-initializers"></a><span data-ttu-id="b5d17-121">Konstruktory typu nazwanego (NamedType inicjatory)</span><span class="sxs-lookup"><span data-stu-id="b5d17-121">Named Type Constructors (NamedType Initializers)</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="b5d17-122">Umożliwia konstruktorów typu (inicjatory), można utworzyć wystąpienia nazwanego typy złożone i typy jednostek.</span><span class="sxs-lookup"><span data-stu-id="b5d17-122"> allows type constructors (initializers) to create instances of named complex types and entity types.</span></span> <span data-ttu-id="b5d17-123">Na przykład poniższe wyrażenie tworzy wystąpienie `Person` typu.</span><span class="sxs-lookup"><span data-stu-id="b5d17-123">For example, the following expression creates an instance of a `Person` type.</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="b5d17-124">Poniższe wyrażenie powoduje utworzenie wystąpienia typu złożonego.</span><span class="sxs-lookup"><span data-stu-id="b5d17-124">The following expression creates an instance of a complex type.</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="b5d17-125">Poniższe wyrażenie tworzy wystąpienie zagnieżdżonego typu złożonego.</span><span class="sxs-lookup"><span data-stu-id="b5d17-125">The following expression creates an instance of a nested complex type.</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="b5d17-126">Poniższe wyrażenie tworzy wystąpienie obiektu zagnieżdżonego typu złożonego.</span><span class="sxs-lookup"><span data-stu-id="b5d17-126">The following expression creates an instance of an entity with a nested complex type.</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="b5d17-127">Poniższy przykład pokazuje, jak zainicjować właściwość typu złożonego do wartości null.</span><span class="sxs-lookup"><span data-stu-id="b5d17-127">The following example shows how to initialize a property of a complex type to null.</span></span> `MyModel.ZipCode(‘98118’, null)`  
  
 <span data-ttu-id="b5d17-128">Argumenty konstruktora są rozpatrywane w takiej samej kolejności jak deklaracja atrybuty typu.</span><span class="sxs-lookup"><span data-stu-id="b5d17-128">The arguments to the constructor are assumed to be in the same order as the declaration of the attributes of the type.</span></span>  
  
 <span data-ttu-id="b5d17-129">Aby uzyskać więcej informacji, zobacz [konstruktora typu o nazwie](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b5d17-129">For more information, see [Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5d17-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b5d17-130">See Also</span></span>  
 [<span data-ttu-id="b5d17-131">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="b5d17-131">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="b5d17-132">Omówienie SQL jednostki</span><span class="sxs-lookup"><span data-stu-id="b5d17-132">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="b5d17-133">System typów</span><span class="sxs-lookup"><span data-stu-id="b5d17-133">Type System</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)