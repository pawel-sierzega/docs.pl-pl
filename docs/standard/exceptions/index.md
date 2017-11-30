---
title: "Obsługa i zgłaszanie wyjątków"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET Framework], exceptions
- exceptions [.NET Framework], throwing
- exceptions [.NET Framework]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b064dc39f5807b154a1529eebe17493ae84981cf
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2017
---
# <a name="handling-and-throwing-exceptions-in-net"></a><span data-ttu-id="4ec02-102">Obsługa i zgłaszanie wyjątków w .NET</span><span class="sxs-lookup"><span data-stu-id="4ec02-102">Handling and throwing exceptions in .NET</span></span>

<span data-ttu-id="4ec02-103">Aplikacji musi mieć możliwość obsługi błędów występujących podczas wykonywania w sposób ciągły.</span><span class="sxs-lookup"><span data-stu-id="4ec02-103">Applications must be able to handle errors that occur during execution in a consistent manner.</span></span> <span data-ttu-id="4ec02-104">.NET udostępnia model dotyczące powiadamiania aplikacji błędy ujednolicone: operacje .NET wskazania błędu przez zgłaszanie wyjątków.</span><span class="sxs-lookup"><span data-stu-id="4ec02-104">.NET provides a model for notifying applications of errors in a uniform way: .NET operations indicate failure by throwing exceptions.</span></span>

## <a name="exceptions"></a><span data-ttu-id="4ec02-105">Wyjątki</span><span class="sxs-lookup"><span data-stu-id="4ec02-105">Exceptions</span></span>

<span data-ttu-id="4ec02-106">Wyjątkiem jest żadnego warunku błędu nieoczekiwanego zachowania, które napotkano przez wykonywania programu.</span><span class="sxs-lookup"><span data-stu-id="4ec02-106">An exception is any error condition or unexpected behavior that is encountered by an executing program.</span></span> <span data-ttu-id="4ec02-107">Wyjątki może zostać wygenerowany z powodu błędów w kodzie lub kod, który wywołania (na przykład biblioteki udostępnionej), zasobów niedostępny systemu operacyjnego, nieoczekiwane warunki, które napotyka środowiska uruchomieniowego (na przykład kod, którego nie można zweryfikować) i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="4ec02-107">Exceptions can be thrown because of a fault in your code or in code that you call (such as a shared library), unavailable operating system resources, unexpected conditions that the runtime encounters (such as code that cannot be verified), and so on.</span></span> <span data-ttu-id="4ec02-108">Aplikację można odzyskać z niektórych z tych warunków, ale nie od innych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="4ec02-108">Your application can recover from some of these conditions, but not from others.</span></span> <span data-ttu-id="4ec02-109">Mimo że można odzyskać z większości wyjątków aplikacji, nie można odzyskać z większości wyjątków w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="4ec02-109">Although you can recover from most application exceptions, you cannot recover from most runtime exceptions.</span></span>

<span data-ttu-id="4ec02-110">W środowisku .NET, wyjątek jest obiekt, który dziedziczy <xref:System.Exception?displayProperty=nameWithType> klasy.</span><span class="sxs-lookup"><span data-stu-id="4ec02-110">In .NET, an exception is an object that inherits from the <xref:System.Exception?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="4ec02-111">Wyjątek z obszaru kodu, w którym wystąpił problem.</span><span class="sxs-lookup"><span data-stu-id="4ec02-111">An exception is thrown from an area of code where a problem has occurred.</span></span> <span data-ttu-id="4ec02-112">Wyjątek jest przekazywany w górę stosu, dopóki aplikacja obsługuje ją lub program zakończy.</span><span class="sxs-lookup"><span data-stu-id="4ec02-112">The exception is passed up the stack until the application handles it or the program terminates.</span></span>

## <a name="exceptions-vs-traditional-error-handling-methods"></a><span data-ttu-id="4ec02-113">Wyjątki, a tradycyjnych metod obsługi błędów</span><span class="sxs-lookup"><span data-stu-id="4ec02-113">Exceptions vs. traditional error-handling methods</span></span>

<span data-ttu-id="4ec02-114">Tradycyjnie model Obsługa błędów języka stosowane w sposób unikatowy zarówno w języku wykrywanie błędów i lokalizowanie programy obsługi dla nich lub mechanizm obsługi błędów dostarczane przez system operacyjny.</span><span class="sxs-lookup"><span data-stu-id="4ec02-114">Traditionally, a language's error-handling model relied on either the language's unique way of detecting errors and locating handlers for them, or on the error-handling mechanism provided by the operating system.</span></span> <span data-ttu-id="4ec02-115">Sposób obsługi wyjątków implementuje platformy .NET ma następujące zalety:</span><span class="sxs-lookup"><span data-stu-id="4ec02-115">The way .NET implements exception handling provides the following advantages:</span></span>

- <span data-ttu-id="4ec02-116">Wyjątek zgłaszanie i obsługa działa tak samo dla języków programowania .NET.</span><span class="sxs-lookup"><span data-stu-id="4ec02-116">Exception throwing and handling works the same for .NET programming languages.</span></span>

- <span data-ttu-id="4ec02-117">Nie wymaga żadnych składni konkretnego języka do obsługi wyjątków, ale umożliwia każdego języka zdefiniować własny składni.</span><span class="sxs-lookup"><span data-stu-id="4ec02-117">Does not require any particular language syntax for handling exceptions, but allows each language to define its own syntax.</span></span>

- <span data-ttu-id="4ec02-118">Wyjątki może zostać wygenerowany przez proces, a nawet granic.</span><span class="sxs-lookup"><span data-stu-id="4ec02-118">Exceptions can be thrown across process and even machine boundaries.</span></span>

- <span data-ttu-id="4ec02-119">Kod obsługi wyjątków można dodać do aplikacji w celu zwiększenia niezawodności programu.</span><span class="sxs-lookup"><span data-stu-id="4ec02-119">Exception-handling code can be added to an application to increase program reliability.</span></span>

<span data-ttu-id="4ec02-120">Wyjątki oferują zalet w porównaniu z innych metod powiadomienie o błędzie, takich jak kody powrotu.</span><span class="sxs-lookup"><span data-stu-id="4ec02-120">Exceptions offer advantages over other methods of error notification, such as return codes.</span></span> <span data-ttu-id="4ec02-121">Błędy nie pozostać niezauważone, ponieważ jest zgłaszany wyjątek, nie Obsługuj go środowiska uruchomieniowego kończy aplikacji.</span><span class="sxs-lookup"><span data-stu-id="4ec02-121">Failures do not go unnoticed because if an exception is thrown and you don't handle it, the runtime terminates your application.</span></span> <span data-ttu-id="4ec02-122">Nieprawidłowe wartości nie należy kontynuować propagację za pośrednictwem systemu wyniku kodu, który zakończy się niepowodzeniem, aby wyszukać zwracając kod błędu.</span><span class="sxs-lookup"><span data-stu-id="4ec02-122">Invalid values do not continue to propagate through the system as a result of code that fails to check for a failure return code.</span></span> 

## <a name="common-exceptions"></a><span data-ttu-id="4ec02-123">Typowe wyjątków</span><span class="sxs-lookup"><span data-stu-id="4ec02-123">Common Exceptions</span></span>

<span data-ttu-id="4ec02-124">W poniższej tabeli przedstawiono niektóre typowe wyjątki z przykładami, co może spowodować ich.</span><span class="sxs-lookup"><span data-stu-id="4ec02-124">The following table lists some common exceptions with examples of what can cause them.</span></span>

| <span data-ttu-id="4ec02-125">Typ wyjątku</span><span class="sxs-lookup"><span data-stu-id="4ec02-125">Exception type</span></span> | <span data-ttu-id="4ec02-126">Typ podstawowy</span><span class="sxs-lookup"><span data-stu-id="4ec02-126">Base type</span></span> | <span data-ttu-id="4ec02-127">Opis</span><span class="sxs-lookup"><span data-stu-id="4ec02-127">Description</span></span> | <span data-ttu-id="4ec02-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="4ec02-128">Example</span></span> |
| -------------- | --------- | ----------- | ------- |
| <xref:System.Exception> | <xref:System.Object> | <span data-ttu-id="4ec02-129">Klasa podstawowa dla wszystkich wyjątków.</span><span class="sxs-lookup"><span data-stu-id="4ec02-129">Base class for all exceptions.</span></span> | <span data-ttu-id="4ec02-130">Brak (Użyj klasy pochodnej tego wyjątku).</span><span class="sxs-lookup"><span data-stu-id="4ec02-130">None (use a derived class of this exception).</span></span> |
| <xref:System.IndexOutOfRangeException> | <xref:System.Exception> | <span data-ttu-id="4ec02-131">Wyjątek w czasie wykonywania tylko wtedy, gdy tablica jest indeksowana nieprawidłowo.</span><span class="sxs-lookup"><span data-stu-id="4ec02-131">Thrown by the runtime only when an array is indexed improperly.</span></span> | <span data-ttu-id="4ec02-132">Indeksowanie tablicy poza prawidłowym zakresem:`arr[arr.Length+1]`</span><span class="sxs-lookup"><span data-stu-id="4ec02-132">Indexing an array outside its valid range: `arr[arr.Length+1]`</span></span> |
| <xref:System.NullReferenceException> | <xref:System.Exception> | <span data-ttu-id="4ec02-133">Wyjątek w czasie wykonywania tylko wtedy, gdy odwołuje się obiekt zerowy.</span><span class="sxs-lookup"><span data-stu-id="4ec02-133">Thrown by the runtime only when a null object is referenced.</span></span> | `object o = null; o.ToString();` |
| <xref:System.InvalidOperationException> | <xref:System.Exception> | <span data-ttu-id="4ec02-134">Element zgłaszany, za pomocą metod w nieprawidłowym stanie.</span><span class="sxs-lookup"><span data-stu-id="4ec02-134">Thrown by methods when in an invalid state.</span></span> | <span data-ttu-id="4ec02-135">Wywoływanie `Enumerator.GetNext()` po usunięciu elementu z kolekcji źródłowej.</span><span class="sxs-lookup"><span data-stu-id="4ec02-135">Calling `Enumerator.GetNext()` after removing an Item from the underlying collection.</span></span> |
| <xref:System.ArgumentException> | <xref:System.Exception> | <span data-ttu-id="4ec02-136">Klasa podstawowa dla wszystkich wyjątków argumentów.</span><span class="sxs-lookup"><span data-stu-id="4ec02-136">Base class for all argument exceptions.</span></span> | <span data-ttu-id="4ec02-137">Brak (Użyj klasy pochodnej tego wyjątku).</span><span class="sxs-lookup"><span data-stu-id="4ec02-137">None (use a derived class of this exception).</span></span> |
| <xref:System.ArgumentNullException> | <xref:System.Exception> | <span data-ttu-id="4ec02-138">Element zgłaszany, za pomocą metod, które nie zezwalają na argument mieć wartości null.</span><span class="sxs-lookup"><span data-stu-id="4ec02-138">Thrown by methods that do not allow an argument to be null.</span></span> | `String s = null; "Calculate".IndexOf (s);` |
| <xref:System.ArgumentOutOfRangeException> | <xref:System.Exception> | <span data-ttu-id="4ec02-139">Element zgłaszany, za pomocą metod, które pozwalają sprawdzić, czy argumenty w danym zakresie.</span><span class="sxs-lookup"><span data-stu-id="4ec02-139">Thrown by methods that verify that arguments are in a given range.</span></span> | `String s = "string"; s.Substring(s.Length+1);` |

## <a name="see-also"></a><span data-ttu-id="4ec02-140">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4ec02-140">See Also</span></span>

* [<span data-ttu-id="4ec02-141">Właściwości i klasy wyjątków</span><span class="sxs-lookup"><span data-stu-id="4ec02-141">Exception Class and Properties</span></span>](exception-class-and-properties.md)
* [<span data-ttu-id="4ec02-142">Porady: umożliwia przechwytywanie wyjątków w bloku Try-Catch</span><span class="sxs-lookup"><span data-stu-id="4ec02-142">How to: Use the Try-Catch Block to Catch Exceptions</span></span>](how-to-use-the-try-catch-block-to-catch-exceptions.md)
* [<span data-ttu-id="4ec02-143">Porady: użycie określonych wyjątków w bloku Catch</span><span class="sxs-lookup"><span data-stu-id="4ec02-143">How to: Use Specific Exceptions in a Catch Block</span></span>](how-to-use-specific-exceptions-in-a-catch-block.md)
* [<span data-ttu-id="4ec02-144">Porady: jawne zgłaszanie wyjątków</span><span class="sxs-lookup"><span data-stu-id="4ec02-144">How to: Explicitly Throw Exceptions</span></span>](how-to-explicitly-throw-exceptions.md)
* [<span data-ttu-id="4ec02-145">Porady: Tworzenie wyjątków zdefiniowanych przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="4ec02-145">How to: Create User-Defined Exceptions</span></span>](how-to-create-user-defined-exceptions.md)
* [<span data-ttu-id="4ec02-146">Przy użyciu obsługi wyjątków filtrowanych przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="4ec02-146">Using User-Filtered Exception Handlers</span></span>](using-user-filtered-exception-handlers.md)
* [<span data-ttu-id="4ec02-147">Porady: użycie bloków Finally</span><span class="sxs-lookup"><span data-stu-id="4ec02-147">How to: Use Finally Blocks</span></span>](how-to-use-finally-blocks.md)
* [<span data-ttu-id="4ec02-148">Obsługa wyjątków międzyoperacyjności COM</span><span class="sxs-lookup"><span data-stu-id="4ec02-148">Handling COM Interop Exceptions</span></span>](handling-com-interop-exceptions.md)
* [<span data-ttu-id="4ec02-149">Najlepsze praktyki dotyczące wyjątków</span><span class="sxs-lookup"><span data-stu-id="4ec02-149">Best Practices for Exceptions</span></span>](best-practices-for-exceptions.md)

<span data-ttu-id="4ec02-150">Aby dowiedzieć się więcej na temat działania wyjątki .NET, zobacz [deweloperów co co trzeba wiedzieć o wyjątków w czasie wykonywania](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="4ec02-150">To learn more about how exceptions work in .NET, see [What Every Dev needs to Know About Exceptions in the Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md).</span></span>