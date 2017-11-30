---
title: "Konwertowanie typów danych (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4733694c2a9fd7c83520b0bf2edea6ebffb47041
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="converting-data-types-c"></a><span data-ttu-id="0bfc3-102">Konwertowanie typów danych (C#)</span><span class="sxs-lookup"><span data-stu-id="0bfc3-102">Converting Data Types (C#)</span></span>
<span data-ttu-id="0bfc3-103">Metody konwersji Zmień typ wejściowy obiektów.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="0bfc3-104">Konwersja operacje kwerend LINQ są przydatne w wielu aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="0bfc3-105">Poniżej przedstawiono kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="0bfc3-105">Following are some examples:</span></span>  
  
-   <span data-ttu-id="0bfc3-106"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> Metody można użyć do ukrywania typ implementacji niestandardowego operatora standardowej kwerendy.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
-   <span data-ttu-id="0bfc3-107"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> — Metoda można włączyć kolekcji bez parametrów na potrzeby zapytań LINQ.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
-   <span data-ttu-id="0bfc3-108"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, I <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> metod można użyć, aby wymusić wykonanie zapytania bezpośredniego zamiast odkładanie go, dopóki wyliczeniu zapytania.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0bfc3-109">Metody</span><span class="sxs-lookup"><span data-stu-id="0bfc3-109">Methods</span></span>  
 <span data-ttu-id="0bfc3-110">W poniższej tabeli wymieniono metody — operator zapytań standardowe, wykonujących konwersji typu danych.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="0bfc3-111">Zmień typ statyczny kolekcji źródłowej metody konwersji w tej tabeli, których nazwy rozpoczynają się od "Jako", ale nie wyliczyć.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="0bfc3-112">Typ metody, których nazwy rozpoczynają się od "Do wyliczyć kolekcji źródłowej i elementy do odpowiedniej kolekcji".</span><span class="sxs-lookup"><span data-stu-id="0bfc3-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="0bfc3-113">Nazwa metody</span><span class="sxs-lookup"><span data-stu-id="0bfc3-113">Method Name</span></span>|<span data-ttu-id="0bfc3-114">Opis</span><span class="sxs-lookup"><span data-stu-id="0bfc3-114">Description</span></span>|<span data-ttu-id="0bfc3-115">Składnia wyrażenia zapytania C#</span><span class="sxs-lookup"><span data-stu-id="0bfc3-115">C# Query Expression Syntax</span></span>|<span data-ttu-id="0bfc3-116">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="0bfc3-116">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="0bfc3-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="0bfc3-117">AsEnumerable</span></span>|<span data-ttu-id="0bfc3-118">Zwraca dane wejściowe typu <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="0bfc3-119">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0bfc3-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="0bfc3-120">AsQueryable</span></span>|<span data-ttu-id="0bfc3-121">Konwertuje (ogólny) <xref:System.Collections.IEnumerable> do (ogólny) <xref:System.Linq.IQueryable>.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="0bfc3-122">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0bfc3-123">Rzutowanie</span><span class="sxs-lookup"><span data-stu-id="0bfc3-123">Cast</span></span>|<span data-ttu-id="0bfc3-124">Rzutuje elementy kolekcji do określonego typu.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-124">Casts the elements of a collection to a specified type.</span></span>|<span data-ttu-id="0bfc3-125">Można użyć zmiennej zakresu jawnie typu.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-125">Use an explicitly typed range variable.</span></span> <span data-ttu-id="0bfc3-126">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="0bfc3-126">For example:</span></span><br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0bfc3-127">OfType</span><span class="sxs-lookup"><span data-stu-id="0bfc3-127">OfType</span></span>|<span data-ttu-id="0bfc3-128">Filtruje wartości, w zależności od ich możliwości można rzutować na określony typ.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-128">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="0bfc3-129">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0bfc3-130">toArray</span><span class="sxs-lookup"><span data-stu-id="0bfc3-130">ToArray</span></span>|<span data-ttu-id="0bfc3-131">Konwertuje kolekcję na tablicę.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-131">Converts a collection to an array.</span></span> <span data-ttu-id="0bfc3-132">Ta metoda powoduje wykonanie kwerendy.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-132">This method forces query execution.</span></span>|<span data-ttu-id="0bfc3-133">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-133">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0bfc3-134">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="0bfc3-134">ToDictionary</span></span>|<span data-ttu-id="0bfc3-135">Umieszcza elementy do <xref:System.Collections.Generic.Dictionary%602> oparte na funkcji selektora kluczy.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-135">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="0bfc3-136">Ta metoda powoduje wykonanie kwerendy.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-136">This method forces query execution.</span></span>|<span data-ttu-id="0bfc3-137">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-137">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0bfc3-138">tolist —</span><span class="sxs-lookup"><span data-stu-id="0bfc3-138">ToList</span></span>|<span data-ttu-id="0bfc3-139">Konwertuje kolekcję do <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-139">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="0bfc3-140">Ta metoda powoduje wykonanie kwerendy.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-140">This method forces query execution.</span></span>|<span data-ttu-id="0bfc3-141">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-141">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0bfc3-142">ToLookup</span><span class="sxs-lookup"><span data-stu-id="0bfc3-142">ToLookup</span></span>|<span data-ttu-id="0bfc3-143">Umieszcza elementy do <xref:System.Linq.Lookup%602> (Słownik jeden do wielu) oparte na funkcji selektora kluczy.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-143">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="0bfc3-144">Ta metoda powoduje wykonanie kwerendy.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-144">This method forces query execution.</span></span>|<span data-ttu-id="0bfc3-145">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-145">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="0bfc3-146">Przykład składni wyrażenia zapytania</span><span class="sxs-lookup"><span data-stu-id="0bfc3-146">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="0bfc3-147">Poniższy przykład kodu wykorzystuje zmiennej zakresu jawnie określone typy do rzutowania typu z podtypem przed uzyskaniem dostępu do elementu członkowskiego, który jest dostępny tylko na podtyp.</span><span class="sxs-lookup"><span data-stu-id="0bfc3-147">The following code example uses an explicitly-typed range variable  to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
```csharp  
class Plant  
{  
    public string Name { get; set; }  
}  
  
class CarnivorousPlant : Plant  
{  
    public string TrapType { get; set; }  
}  
  
static void Cast()  
{  
    Plant[] plants = new Plant[] {  
        new CarnivorousPlant { Name = "Venus Fly Trap", TrapType = "Snap Trap" },  
        new CarnivorousPlant { Name = "Pitcher Plant", TrapType = "Pitfall Trap" },  
        new CarnivorousPlant { Name = "Sundew", TrapType = "Flypaper Trap" },  
        new CarnivorousPlant { Name = "Waterwheel Plant", TrapType = "Snap Trap" }  
    };  
  
    var query = from CarnivorousPlant cPlant in plants  
                where cPlant.TrapType == "Snap Trap"  
                select cPlant;  
  
    foreach (Plant plant in query)  
        Console.WriteLine(plant.Name);  
  
    /* This code produces the following output:  
  
        Venus Fly Trap  
        Waterwheel Plant  
    */  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0bfc3-148">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0bfc3-148">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="0bfc3-149">Operatory standardowe zapytań — omówienie (C#)</span><span class="sxs-lookup"><span data-stu-id="0bfc3-149">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="0bfc3-150">Klauzula FROM</span><span class="sxs-lookup"><span data-stu-id="0bfc3-150">from clause</span></span>](../../../../csharp/language-reference/keywords/from-clause.md)  
 [<span data-ttu-id="0bfc3-151">Wyrażenia zapytań LINQ</span><span class="sxs-lookup"><span data-stu-id="0bfc3-151">LINQ Query Expressions</span></span>](../../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="0bfc3-152">Porady: zapytanie w ArrayList za pomocą LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="0bfc3-152">How to: Query an ArrayList with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)