---
title: "Język zapytania zintegrowanym (LINQ)"
description: "Wprowadza języka zintegrowane zapytania (LINQ) w języku C#"
keywords: .NET, .NET core, LINQ, C#
author: BillWagner
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 007cc736-f5cf-4919-b99b-0c00ab2814ce
ms.openlocfilehash: c4c26e2b7b0693ec940958a9b7d2d306001090e7
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2017
---
# <a name="language-integrated-query-linq"></a><span data-ttu-id="31710-104">Język zapytania zintegrowanym (LINQ)</span><span class="sxs-lookup"><span data-stu-id="31710-104">Language Integrated Query (LINQ)</span></span>

<span data-ttu-id="31710-105">Zapytanie języku zintegrowanym (LINQ) jest nazwą zestawu technologii oparty na integracji możliwość wykonywania kwerend bezpośrednio w języku C#.</span><span class="sxs-lookup"><span data-stu-id="31710-105">Language-Integrated Query (LINQ) is the name for a set of technologies based on the integration of query capabilities directly into the C# language.</span></span> <span data-ttu-id="31710-106">Tradycyjnym zapytań dotyczących danych są wyrażane jako skompilować prostego parametry bez typu sprawdzania w czasie lub obsługę funkcji IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="31710-106">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="31710-107">Ponadto należy dowiedzieć się język kwerendy różne dla każdego typu źródła danych: SQL bazy danych, dokumentów XML, różnych usług sieci Web i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="31710-107">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="31710-108">Za pomocą LINQ zapytanie jest konstrukcję języka najwyższej jakości tak samo jak klasy, metody, zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="31710-108">With LINQ, a query is a first-class language construct, just like classes, methods, events.</span></span>

<span data-ttu-id="31710-109">Dla deweloperów, który zapisuje zapytania najbardziej widocznej części "języku zintegrowanym" LINQ jest wyrażenie zapytania.</span><span class="sxs-lookup"><span data-stu-id="31710-109">For a developer who writes queries, the most visible "language-integrated" part of LINQ is the query expression.</span></span> <span data-ttu-id="31710-110">Wyrażenia zapytania są zapisywane w declarative *Składnia kwerendy*.</span><span class="sxs-lookup"><span data-stu-id="31710-110">Query expressions are written in a declarative *query syntax*.</span></span> <span data-ttu-id="31710-111">Za pomocą składni zapytań, można wykonać filtrowania, kolejność i operacji grupowania na źródeł danych z co najmniej kodu.</span><span class="sxs-lookup"><span data-stu-id="31710-111">By using query syntax, you can perform filtering, ordering, and grouping operations on data sources with a minimum of code.</span></span> <span data-ttu-id="31710-112">Te same wzory wyrażenia zapytania podstawowego służy do wykonywania zapytań i przekształcania danych bazy danych SQL, ADO .NET z zestawów danych, dokumentów XML i strumieni i kolekcji .NET.</span><span class="sxs-lookup"><span data-stu-id="31710-112">You use the same basic query expression patterns to query and transform data in SQL databases, ADO .NET Datasets, XML documents and streams, and .NET collections.</span></span>

<span data-ttu-id="31710-113">Poniższy przykład przedstawia operację pełnej kwerendy.</span><span class="sxs-lookup"><span data-stu-id="31710-113">The following example shows the complete query operation.</span></span> <span data-ttu-id="31710-114">Ukończenia operacji obejmuje tworzenie źródła danych, definiujący wyrażenie zapytania i wykonywania zapytania w `foreach` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="31710-114">The complete operation includes creating a data source, defining the query expression, and executing the query in a `foreach` statement.</span></span>

[!code-csharp[csProgGuideLINQ#11](../../../samples/snippets/csharp/concepts/linq/index_1.cs)]

## <a name="query-expression-overview"></a><span data-ttu-id="31710-115">Omówienie wyrażenia zapytania</span><span class="sxs-lookup"><span data-stu-id="31710-115">Query expression overview</span></span>

-   <span data-ttu-id="31710-116">Wyrażenia zapytań może służyć do badania i przekształcania danych z dowolnego źródła danych z obsługą LINQ.</span><span class="sxs-lookup"><span data-stu-id="31710-116">Query expressions can be used to query and to transform data from any LINQ-enabled data source.</span></span> <span data-ttu-id="31710-117">Na przykład pojedynczego zapytania można pobrać danych z bazy danych SQL i tworzy strumień XML jako dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="31710-117">For example, a single query can retrieve data from a SQL database, and produce an XML stream as output.</span></span>  
  
-   <span data-ttu-id="31710-118">Wyrażenia zapytań są łatwe do głównego, ponieważ jest używany przez wiele znanych konstrukcji języka C#.</span><span class="sxs-lookup"><span data-stu-id="31710-118">Query expressions are easy to master because they use many familiar C# language constructs.</span></span>  
  
-   <span data-ttu-id="31710-119">Zmienne w wyrażeniu zapytania są wszystkie silnie typizowane, chociaż w wielu przypadkach trzeba jawnie Podaj typ ponieważ kompilator można go rozpoznać.</span><span class="sxs-lookup"><span data-stu-id="31710-119">The variables in a query expression are all strongly typed, although in many cases you do not have to provide the type explicitly because the compiler can infer it.</span></span> <span data-ttu-id="31710-120">Aby uzyskać więcej informacji, zobacz [relacje typu w składniku LINQ zapytania operacji](../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="31710-120">For more information, see [Type relationships in LINQ query operations](../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>  
  
-   <span data-ttu-id="31710-121">Zapytanie nie jest wykonywane, dopóki iteracja zmienną zapytania, na przykład w `foreach` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="31710-121">A query is not executed until you iterate over the query variable, for example, in a `foreach` statement.</span></span> <span data-ttu-id="31710-122">Aby uzyskać więcej informacji, zobacz [wprowadzenie do kwerend LINQ](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="31710-122">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
-   <span data-ttu-id="31710-123">W czasie kompilacji wyrażeń zapytania są konwertowane na wywołania metody standardowe — Operator zapytań zgodnie z regułami określonymi w specyfikacji języka C#.</span><span class="sxs-lookup"><span data-stu-id="31710-123">At compile time, query expressions are converted to Standard Query Operator method calls according to the rules set forth in the C# specification.</span></span> <span data-ttu-id="31710-124">Wszelkie zapytania, które można wyrazić przy użyciu składni zapytania można wyrazić w taki sposób, przy użyciu składni metody.</span><span class="sxs-lookup"><span data-stu-id="31710-124">Any query that can be expressed by using query syntax can also be expressed by using method syntax.</span></span> <span data-ttu-id="31710-125">Jednak w większości przypadków składnia zapytania jest bardziej czytelny i zwięzłe.</span><span class="sxs-lookup"><span data-stu-id="31710-125">However, in most cases query syntax is more readable and concise.</span></span> <span data-ttu-id="31710-126">Aby uzyskać więcej informacji, zobacz [specyfikacji języka C#](../language-reference/language-specification/index.md) i [operatory standardowe zapytań — omówienie](../programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="31710-126">For more information, see [C# language specification](../language-reference/language-specification/index.md) and [Standard query operators overview](../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
-   <span data-ttu-id="31710-127">Zgodnie z zasadą podczas pisania zapytań LINQ firma Microsoft zaleca użycie składni zapytania w miarę możliwości i metody zawsze, gdy jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="31710-127">As a rule when you write LINQ queries, we recommend that you use query syntax whenever possible and method syntax whenever necessary.</span></span> <span data-ttu-id="31710-128">Nie istnieje nie semantycznego lub różnicy wydajności między dwa sposoby.</span><span class="sxs-lookup"><span data-stu-id="31710-128">There is no semantic or performance difference between the two different forms.</span></span> <span data-ttu-id="31710-129">Wyrażenia zapytań są często bardziej czytelny niż równoważne wyrażenia napisany w składni metody.</span><span class="sxs-lookup"><span data-stu-id="31710-129">Query expressions are often more readable than equivalent expressions written in method syntax.</span></span>  
  
-   <span data-ttu-id="31710-130">Zapytanie niektóre operacje, takie jak <xref:System.Linq.Enumerable.Count%2A> lub <xref:System.Linq.Enumerable.Max%2A>, nie generują braku klauzuli wyrażenia zapytania równoważne oraz w związku z tym muszą być wyrażone jako wywołania metody.</span><span class="sxs-lookup"><span data-stu-id="31710-130">Some query operations, such as <xref:System.Linq.Enumerable.Count%2A> or <xref:System.Linq.Enumerable.Max%2A>, have no equivalent query expression clause and must therefore be expressed as a method call.</span></span> <span data-ttu-id="31710-131">Składnia metody można łączyć z składnia zapytania na różne sposoby.</span><span class="sxs-lookup"><span data-stu-id="31710-131">Method syntax can be combined with query syntax in various ways.</span></span> <span data-ttu-id="31710-132">Aby uzyskać więcej informacji, zobacz [składnia zapytania i metody w technologii LINQ](../programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span><span class="sxs-lookup"><span data-stu-id="31710-132">For more information, see [Query syntax and method syntax in LINQ](../programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
-   <span data-ttu-id="31710-133">Wyrażenia zapytania mogą być kompilowane na drzewa wyrażeń lub do delegatów, w zależności od typu dotyczy zapytanie.</span><span class="sxs-lookup"><span data-stu-id="31710-133">Query expressions can be compiled to expression trees or to delegates, depending on the type that the query is applied to.</span></span> <span data-ttu-id="31710-134"><xref:System.Collections.Generic.IEnumerable%601>zapytania są kompilowane do delegatów.</span><span class="sxs-lookup"><span data-stu-id="31710-134"><xref:System.Collections.Generic.IEnumerable%601> queries are compiled to delegates.</span></span> <span data-ttu-id="31710-135"><xref:System.Linq.IQueryable>i <xref:System.Linq.IQueryable%601> zapytania są kompilowane na drzewa wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="31710-135"><xref:System.Linq.IQueryable> and <xref:System.Linq.IQueryable%601> queries are compiled to expression trees.</span></span> <span data-ttu-id="31710-136">Aby uzyskać więcej informacji, zobacz [drzew wyrażeń](../expression-trees.md).</span><span class="sxs-lookup"><span data-stu-id="31710-136">For more information, see [Expression trees](../expression-trees.md).</span></span>  

## <a name="next-steps"></a><span data-ttu-id="31710-137">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="31710-137">Next steps</span></span>

<span data-ttu-id="31710-138">Aby uzyskać więcej informacji na temat LINQ, Rozpocznij od staje się poznać niektóre podstawowe pojęcia związane z [podstawowe informacje o wyrażeniach zapytań](query-expression-basics.md), a następnie zapoznaj się z dokumentacją w technologii LINQ, w której jesteś zainteresowany:</span><span class="sxs-lookup"><span data-stu-id="31710-138">To learn more details about LINQ, start by becoming familiar with some basic concepts in [Query expression basics](query-expression-basics.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>   
-   <span data-ttu-id="31710-139">Dokumenty XML: [LINQ do XML](../programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="31710-139">XML documents: [LINQ to XML](../programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="31710-140">ADO.NET Entity Framework: [LINQ do jednostek](../../framework/data/adonet/ef/language-reference/linq-to-entities.md)</span><span class="sxs-lookup"><span data-stu-id="31710-140">ADO.NET Entity Framework: [LINQ to entities](../../framework/data/adonet/ef/language-reference/linq-to-entities.md)</span></span>  
  
-   <span data-ttu-id="31710-141">Kolekcje .NET, plików, ciągi i tak dalej: [LINQ do obiektów](../programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="31710-141">.NET collections, files, strings and so on: [LINQ to objects](../programming-guide/concepts/linq/linq-to-objects.md)</span></span>

<span data-ttu-id="31710-142">Aby bardziej zrozumieć LINQ ogólnie rzecz biorąc, zobacz [LINQ w C#](linq-in-csharp.md).</span><span class="sxs-lookup"><span data-stu-id="31710-142">To gain a deeper understanding of LINQ in general, see [LINQ in C#](linq-in-csharp.md).</span></span>

<span data-ttu-id="31710-143">Aby rozpocząć pracę z LINQ w C#, zobacz samouczek [pracy za pomocą LINQ](../tutorials/working-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="31710-143">To start working with LINQ in C#, see the tutorial [Working with LINQ](../tutorials/working-with-linq.md).</span></span>

