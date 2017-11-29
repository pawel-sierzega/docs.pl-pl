---
title: Delegaty (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- delegates [Visual Basic]
- Visual Basic code, delegates
ms.assetid: 410b60dc-5e60-4ec0-bfae-426755a2ee28
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fe21d8c0dcefaea35d9f96cd2ecbff92a1c83d36
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="delegates-visual-basic"></a><span data-ttu-id="94d34-102">Delegaty (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94d34-102">Delegates (Visual Basic)</span></span>
<span data-ttu-id="94d34-103">Obiekty delegowane są obiekty, które odwołują się do metody.</span><span class="sxs-lookup"><span data-stu-id="94d34-103">Delegates are objects that refer to methods.</span></span> <span data-ttu-id="94d34-104">One nazywane *wskaźników funkcji bezpieczny* ponieważ są one podobne do wskaźników funkcji używane w innych językach programowania.</span><span class="sxs-lookup"><span data-stu-id="94d34-104">They are sometimes described as *type-safe function pointers* because they are similar to function pointers used in other programming languages.</span></span> <span data-ttu-id="94d34-105">Jednak w przeciwieństwie do wskaźników funkcji [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] obiektów delegowanych jest typem referencyjnym, oparty na klasie <xref:System.Delegate?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="94d34-105">But unlike function pointers, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] delegates are a reference type based on the class <xref:System.Delegate?displayProperty=nameWithType>.</span></span> <span data-ttu-id="94d34-106">Delegatów mogą odwoływać się obu metod udostępnionych — metody, które można wywołać bez określonego wystąpienia klasy — wystąpienie metody.</span><span class="sxs-lookup"><span data-stu-id="94d34-106">Delegates can reference both shared methods — methods that can be called without a specific instance of a class — and instance methods.</span></span>  
  
## <a name="delegates-and-events"></a><span data-ttu-id="94d34-107">Delegaci i zdarzenia</span><span class="sxs-lookup"><span data-stu-id="94d34-107">Delegates and Events</span></span>  
 <span data-ttu-id="94d34-108">Obiekty delegowane są przydatne w sytuacjach konieczne pośredniczący między wywołanie procedury i procedury wywoływanej.</span><span class="sxs-lookup"><span data-stu-id="94d34-108">Delegates are useful in situations where you need an intermediary between a calling procedure and the procedure being called.</span></span> <span data-ttu-id="94d34-109">Na przykład może być obiekt, który informuje o zdarzeniach, aby można było wywołać programów obsługi zdarzeń w różnych okolicznościach.</span><span class="sxs-lookup"><span data-stu-id="94d34-109">For example, you might want an object that raises events to be able to call different event handlers under different circumstances.</span></span> <span data-ttu-id="94d34-110">Niestety obiekt wywoływanie zdarzeń nie może znać wcześniejsze obsługi zdarzeń, które obsługuje określone zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="94d34-110">Unfortunately, the object raising the events cannot know ahead of time which event handler is handling a specific event.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="94d34-111">Umożliwia obsługę zdarzeń dynamicznie Powiąż ze zdarzeniami, tworząc delegowanego dla Ciebie, korzystając z `AddHandler` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="94d34-111"> lets you dynamically associate event handlers with events by creating a delegate for you when you use the `AddHandler` statement.</span></span> <span data-ttu-id="94d34-112">W czasie wykonywania delegat przekazuje wywołań obsługi zdarzeń odpowiednie.</span><span class="sxs-lookup"><span data-stu-id="94d34-112">At run time, the delegate forwards calls to the appropriate event handler.</span></span>  
  
 <span data-ttu-id="94d34-113">Chociaż można tworzyć własne delegatów w większości przypadków [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] tworzy delegata i zajmuje się szczegóły dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="94d34-113">Although you can create your own delegates, in most cases [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] creates the delegate and takes care of the details for you.</span></span> <span data-ttu-id="94d34-114">Na przykład `Event` instrukcji niejawnie definiuje klasę delegata o nazwie `<EventName>EventHandler` jako klasa zagnieżdżona zawierających klasy `Event` instrukcji i z takiego samego podpisu jak zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="94d34-114">For example, an `Event` statement implicitly defines a delegate class named `<EventName>EventHandler` as a nested class of the class containing the `Event` statement, and with the same signature as the event.</span></span> <span data-ttu-id="94d34-115">`AddressOf` Instrukcja niejawnie tworzy wystąpienia delegata, który odwołuje się do określonej procedury.</span><span class="sxs-lookup"><span data-stu-id="94d34-115">The `AddressOf` statement implicitly creates an instance of a delegate that refers to a specific procedure.</span></span> <span data-ttu-id="94d34-116">Następujące dwa wiersze kodu są równoważne.</span><span class="sxs-lookup"><span data-stu-id="94d34-116">The following two lines of code are equivalent.</span></span> <span data-ttu-id="94d34-117">W pierwszym wierszu, zobacz jawne utworzenie wystąpienia `Eventhandler`, z odwołaniem do metody `Button1_Click` wysyłane jako argument.</span><span class="sxs-lookup"><span data-stu-id="94d34-117">In the first line, you see the explicit creation of an instance of `Eventhandler`, with a reference to method `Button1_Click` sent as the argument.</span></span> <span data-ttu-id="94d34-118">Drugi wiersz jest wygodny sposób, aby zrobić to samo.</span><span class="sxs-lookup"><span data-stu-id="94d34-118">The second line is a more convenient way to do the same thing.</span></span>  
  
 [!code-vb[VbVbalrDelegates#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegates_1.vb)]  
  
 <span data-ttu-id="94d34-119">Można użyć skrótu sposobem tworzenia delegatów w dowolnym miejscu kompilator może ustalić typu delegata w kontekście.</span><span class="sxs-lookup"><span data-stu-id="94d34-119">You can use the shorthand way of creating delegates anywhere the compiler can determine the delegate's type by the context.</span></span>  
  
## <a name="declaring-events-that-use-an-existing-delegate-type"></a><span data-ttu-id="94d34-120">Typ delegata zdarzenia deklarujący Użyj istniejącego</span><span class="sxs-lookup"><span data-stu-id="94d34-120">Declaring Events that Use an Existing Delegate Type</span></span>  
 <span data-ttu-id="94d34-121">W niektórych sytuacjach można zadeklarować zdarzenia, aby użyć istniejącego typu delegata jako jego podstawowy delegata.</span><span class="sxs-lookup"><span data-stu-id="94d34-121">In some situations, you may want to declare an event to use an existing delegate type as its underlying delegate.</span></span> <span data-ttu-id="94d34-122">Następującej składni pokazano, jak:</span><span class="sxs-lookup"><span data-stu-id="94d34-122">The following syntax demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrDelegates#7](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegates_2.vb)]  
  
 <span data-ttu-id="94d34-123">Jest to przydatne, gdy chcesz rozesłać wiele zdarzeń do tej procedury obsługi.</span><span class="sxs-lookup"><span data-stu-id="94d34-123">This is useful when you want to route multiple events to the same handler.</span></span>  
  
## <a name="delegate-variables-and-parameters"></a><span data-ttu-id="94d34-124">Parametry i zmienne delegata</span><span class="sxs-lookup"><span data-stu-id="94d34-124">Delegate Variables and Parameters</span></span>  
 <span data-ttu-id="94d34-125">Można używać delegatów dla innych, niż zdarzenie powiązane zadania, takie jak wolnych wątków lub za pomocą procedur, które należy wywołać różne wersje funkcji w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="94d34-125">You can use delegates for other, non-event related tasks, such as free threading or with procedures that need to call different versions of functions at run time.</span></span>  
  
 <span data-ttu-id="94d34-126">Załóżmy na przykład, aplikacja sklasyfikowane ad, która zawiera pola listy z nazwami samochodów.</span><span class="sxs-lookup"><span data-stu-id="94d34-126">For example, suppose you have a classified-ad application that includes a list box with the names of cars.</span></span> <span data-ttu-id="94d34-127">Reklam są sortowane według tytułu, który jest zwykle markę samochód.</span><span class="sxs-lookup"><span data-stu-id="94d34-127">The ads are sorted by title, which is normally the make of the car.</span></span> <span data-ttu-id="94d34-128">Problem, które mogą się spodziewać występuje, gdy niektóre samochodów obejmują roku samochodu przed markę.</span><span class="sxs-lookup"><span data-stu-id="94d34-128">A problem you may face occurs when some cars include the year of the car before the make.</span></span> <span data-ttu-id="94d34-129">Problem jest, że funkcje wbudowane sortowania pola listy sortuje tylko przez kody znaków; umieszcza wszystkie reklam, począwszy od daty najpierw, a następnie reklam, począwszy od marki.</span><span class="sxs-lookup"><span data-stu-id="94d34-129">The problem is that the built-in sort functionality of the list box sorts only by character codes; it places all the ads starting with dates first, followed by the ads starting with the make.</span></span>  
  
 <span data-ttu-id="94d34-130">Aby rozwiązać ten problem, można utworzyć procedury sortowania w klasie, która używa standardowych sortowania alfabetycznego na większości pola listy, ale może przełączyć się w czasie wykonywania procedury sortowania niestandardowego samochodu reklam.</span><span class="sxs-lookup"><span data-stu-id="94d34-130">To fix this, you can create a sort procedure in a class that uses the standard alphabetic sort on most list boxes, but is able to switch at run time to the custom sort procedure for car ads.</span></span> <span data-ttu-id="94d34-131">Aby to zrobić, należy przekazać procedury sortowania niestandardowego do klasy sortowania w czasie wykonywania, używanie delegatów.</span><span class="sxs-lookup"><span data-stu-id="94d34-131">To do this, you pass the custom sort procedure to the sort class at run time, using delegates.</span></span>  
  
## <a name="addressof-and-lambda-expressions"></a><span data-ttu-id="94d34-132">AddressOf i wyrażenia Lambda</span><span class="sxs-lookup"><span data-stu-id="94d34-132">AddressOf and Lambda Expressions</span></span>  
 <span data-ttu-id="94d34-133">Każda klasa delegata definiuje konstruktora, który jest przekazywany specyfikację metody obiektu.</span><span class="sxs-lookup"><span data-stu-id="94d34-133">Each delegate class defines a constructor that is passed the specification of an object method.</span></span> <span data-ttu-id="94d34-134">Argument do konstruktora delegata musi być odwołaniem do metody lub wyrażenia lambda.</span><span class="sxs-lookup"><span data-stu-id="94d34-134">An argument to a delegate constructor must be a reference to a method, or a lambda expression.</span></span>  
  
 <span data-ttu-id="94d34-135">Aby określić odwołań do metody, należy użyć następującej składni:</span><span class="sxs-lookup"><span data-stu-id="94d34-135">To specify a reference to a method, use the following syntax:</span></span>  
  
 <span data-ttu-id="94d34-136">`AddressOf` [`expression`.]`methodName`</span><span class="sxs-lookup"><span data-stu-id="94d34-136">`AddressOf` [`expression`.]`methodName`</span></span>  
  
 <span data-ttu-id="94d34-137">Typ kompilacji `expression` musi być nazwą klasy lub interfejsu, który zawiera metodę o określonej nazwie, w których Podpis pasuje do podpisu klasie obiektów delegowanych.</span><span class="sxs-lookup"><span data-stu-id="94d34-137">The compile-time type of the `expression` must be the name of a class or an interface that contains a method of the specified name whose signature matches the signature of the delegate class.</span></span> <span data-ttu-id="94d34-138">`methodName` Może być udostępnionej metody lub metodą wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="94d34-138">The `methodName` can be either a shared method or an instance method.</span></span> <span data-ttu-id="94d34-139">`methodName` Nie jest opcjonalny, nawet w przypadku utworzenia delegata dla metody domyślnej klasy.</span><span class="sxs-lookup"><span data-stu-id="94d34-139">The `methodName` is not optional, even if you create a delegate for the default method of the class.</span></span>  
  
 <span data-ttu-id="94d34-140">Aby określić wyrażenie lambda, użyj następującej składni:</span><span class="sxs-lookup"><span data-stu-id="94d34-140">To specify a lambda expression, use the following syntax:</span></span>  
  
 <span data-ttu-id="94d34-141">`Function`([`parm` Jako `type`, `parm2` jako `type2`,...])`expression`</span><span class="sxs-lookup"><span data-stu-id="94d34-141">`Function` ([`parm` As `type`, `parm2` As `type2`, ...]) `expression`</span></span>  
  
 <span data-ttu-id="94d34-142">W poniższym przykładzie przedstawiono oba `AddressOf` i wyrażenia lambda, można określić odwołania do delegata.</span><span class="sxs-lookup"><span data-stu-id="94d34-142">The following example shows both `AddressOf` and lambda expressions used to specify the reference for a delegate.</span></span>  
  
 [!code-vb[VbVbalrDelegates#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegates_3.vb)]  
  
 <span data-ttu-id="94d34-143">Podpis funkcji musi być zgodny z typem obiektu delegowanego.</span><span class="sxs-lookup"><span data-stu-id="94d34-143">The signature of the function must match that of the delegate type.</span></span> <span data-ttu-id="94d34-144">Aby uzyskać więcej informacji na temat wyrażeń lambda, zobacz [wyrażenia Lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="94d34-144">For more information about lambda expressions, see [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span> <span data-ttu-id="94d34-145">Aby uzyskać więcej przykładów wyrażenia lambda i `AddressOf` przypisania do delegatów, zobacz [swobodna konwersja delegatów](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="94d34-145">For more examples of lambda expression and `AddressOf` assignments to delegates, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="94d34-146">Tematy pokrewne</span><span class="sxs-lookup"><span data-stu-id="94d34-146">Related Topics</span></span>  
  
|<span data-ttu-id="94d34-147">Tytuł</span><span class="sxs-lookup"><span data-stu-id="94d34-147">Title</span></span>|<span data-ttu-id="94d34-148">Opis</span><span class="sxs-lookup"><span data-stu-id="94d34-148">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="94d34-149">Porady: wywoływanie metody delegata</span><span class="sxs-lookup"><span data-stu-id="94d34-149">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)|<span data-ttu-id="94d34-150">Przykład pokazujący sposób skojarzyć metodę z delegata, a następnie wywołać tej metody za pomocą obiektu delegowanego.</span><span class="sxs-lookup"><span data-stu-id="94d34-150">Provides an example that shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>|  
|[<span data-ttu-id="94d34-151">Porady: przekazywanie procedur do innej procedury w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94d34-151">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)|<span data-ttu-id="94d34-152">Pokazuje, jak używać delegatów do przekazania jednej procedury do innej procedury.</span><span class="sxs-lookup"><span data-stu-id="94d34-152">Demonstrates how to use delegates to pass one procedure to another procedure.</span></span>|  
|[<span data-ttu-id="94d34-153">Swobodna konwersja delegatów</span><span class="sxs-lookup"><span data-stu-id="94d34-153">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)|<span data-ttu-id="94d34-154">W tym artykule opisano, jak można przypisać typu Sub i funkcji do delegatów lub obsługi nawet wtedy, gdy ich podpisów nie są identyczne</span><span class="sxs-lookup"><span data-stu-id="94d34-154">Describes how you can assign subs and functions to delegates or handlers even when their signatures are not identical</span></span>|  
|[<span data-ttu-id="94d34-155">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="94d34-155">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)|<span data-ttu-id="94d34-156">Zawiera omówienie zdarzeń w języku Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="94d34-156">Provides an overview of events in Visual Basic.</span></span>|