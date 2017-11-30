---
title: Interfejsy (Visual Studio)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, interfaces
- interfaces [Visual Basic], Visual Basic
- interfaces
- interfaces [Visual Basic]
ms.assetid: 61b06674-12c9-430b-be68-cc67ecee1f5b
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c26bb7322064d0b8cdf733e74f8b37e81b1e620c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2017
---
# <a name="interfaces-visual-basic"></a><span data-ttu-id="cf210-102">Interfejsy (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="cf210-102">Interfaces (Visual Basic)</span></span>
<span data-ttu-id="cf210-103">*Interfejsy* Definiowanie właściwości, metod i zdarzeń, które można zaimplementować klasy.</span><span class="sxs-lookup"><span data-stu-id="cf210-103">*Interfaces* define the properties, methods, and events that classes can implement.</span></span> <span data-ttu-id="cf210-104">Interfejsy umożliwiają definiowanie funkcji jako małych grup ściśle powiązane właściwości, metod i zdarzeń; Zmniejsza to problemy ze zgodnością, ponieważ możesz utworzyć rozszerzoną implementacje interfejsów sieci bez narażenia istniejącego kodu.</span><span class="sxs-lookup"><span data-stu-id="cf210-104">Interfaces allow you to define features as small groups of closely related properties, methods, and events; this reduces compatibility problems because you can develop enhanced implementations for your interfaces without jeopardizing existing code.</span></span> <span data-ttu-id="cf210-105">Możesz dodać nowe funkcje w dowolnym momencie przez tworzenie implementacji i dodatkowe interfejsy.</span><span class="sxs-lookup"><span data-stu-id="cf210-105">You can add new features at any time by developing additional interfaces and implementations.</span></span>  
  
 <span data-ttu-id="cf210-106">Istnieje kilka innych przyczyn, dlaczego warto używać interfejsów zamiast dziedziczenia klas:</span><span class="sxs-lookup"><span data-stu-id="cf210-106">There are several other reasons why you might want to use interfaces instead of class inheritance:</span></span>  
  
-   <span data-ttu-id="cf210-107">Interfejsy są bardziej odpowiednie do sytuacji, w których aplikacje wymagają się, że prawdopodobnie wielu niepowiązanych typów obiektów, które umożliwiają korzystanie z niektórych funkcji.</span><span class="sxs-lookup"><span data-stu-id="cf210-107">Interfaces are better suited to situations in which your applications require many possibly unrelated object types to provide certain functionality.</span></span>  
  
-   <span data-ttu-id="cf210-108">Interfejsy są bardziej elastyczne niż klasy podstawowej, ponieważ można określić pojedynczej implementacji, które można zaimplementować wiele interfejsów.</span><span class="sxs-lookup"><span data-stu-id="cf210-108">Interfaces are more flexible than base classes because you can define a single implementation that can implement multiple interfaces.</span></span>  
  
-   <span data-ttu-id="cf210-109">Interfejsy są lepsze w sytuacjach, w których nie masz dziedziczenia z klasy podstawowej implementacji.</span><span class="sxs-lookup"><span data-stu-id="cf210-109">Interfaces are better in situations in which you do not have to inherit implementation from a base class.</span></span>  
  
-   <span data-ttu-id="cf210-110">Interfejsy są przydatne, gdy nie można użyć dziedziczenia klas.</span><span class="sxs-lookup"><span data-stu-id="cf210-110">Interfaces are useful when you cannot use class inheritance.</span></span> <span data-ttu-id="cf210-111">Na przykład struktury nie może dziedziczyć z klasy, ale miały zaimplementowane interfejsy.</span><span class="sxs-lookup"><span data-stu-id="cf210-111">For example, structures cannot inherit from classes, but they can implement interfaces.</span></span>  
  
## <a name="declaring-interfaces"></a><span data-ttu-id="cf210-112">Deklarowanie interfejsów</span><span class="sxs-lookup"><span data-stu-id="cf210-112">Declaring Interfaces</span></span>  
 <span data-ttu-id="cf210-113">Definicje interfejsu są ujęte w `Interface` i `End Interface` instrukcje.</span><span class="sxs-lookup"><span data-stu-id="cf210-113">Interface definitions are enclosed within the `Interface` and `End Interface` statements.</span></span> <span data-ttu-id="cf210-114">Po `Interface` instrukcji, można dodać opcjonalne `Inherits` instrukcji, która zawiera jeden lub więcej dziedziczonych interfejsach.</span><span class="sxs-lookup"><span data-stu-id="cf210-114">Following the `Interface` statement, you can add an optional `Inherits` statement that lists one or more inherited interfaces.</span></span> <span data-ttu-id="cf210-115">`Inherits` Instrukcje musi poprzedzać wszystkie inne instrukcje w deklaracji z wyjątkiem komentarze.</span><span class="sxs-lookup"><span data-stu-id="cf210-115">The `Inherits` statements must precede all other statements in the declaration except comments.</span></span> <span data-ttu-id="cf210-116">Pozostałe instrukcje w definicji interfejsu powinny być `Event`, `Sub`, `Function`, `Property`, `Interface`, `Class`, `Structure`, i `Enum` instrukcje.</span><span class="sxs-lookup"><span data-stu-id="cf210-116">The remaining statements in the interface definition should be `Event`, `Sub`, `Function`, `Property`, `Interface`, `Class`, `Structure`, and `Enum` statements.</span></span> <span data-ttu-id="cf210-117">Interfejsy nie mogą zawierać kod implementacji ani instrukcji skojarzony z kodem wdrożenia, takich jak `End Sub` lub `End Property`.</span><span class="sxs-lookup"><span data-stu-id="cf210-117">Interfaces cannot contain any implementation code or statements associated with implementation code, such as `End Sub` or `End Property`.</span></span>  
  
 <span data-ttu-id="cf210-118">W przypadku przestrzeni nazw są instrukcje interfejsu `Friend` domyślnie, ale one mogą również być jawnie deklarowane jako `Public` lub `Friend`.</span><span class="sxs-lookup"><span data-stu-id="cf210-118">In a namespace, interface statements are `Friend` by default, but they can also be explicitly declared as `Public` or `Friend`.</span></span> <span data-ttu-id="cf210-119">Interfejsy zdefiniowane w obrębie klasy, modułów, interfejsów i struktury są `Public` domyślnie, ale one mogą również być jawnie deklarowane jako `Public`, `Friend`, `Protected`, lub `Private`.</span><span class="sxs-lookup"><span data-stu-id="cf210-119">Interfaces defined within classes, modules, interfaces, and structures are `Public` by default, but they can also be explicitly declared as `Public`, `Friend`, `Protected`, or `Private`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf210-120">`Shadows` — Słowo kluczowe może odnosić się do wszystkich członków interfejsu.</span><span class="sxs-lookup"><span data-stu-id="cf210-120">The `Shadows` keyword can be applied to all interface members.</span></span> <span data-ttu-id="cf210-121">`Overloads` — Słowo kluczowe może odnosić się do `Sub`, `Function`, i `Property` instrukcje zadeklarowany w definicji interfejsu.</span><span class="sxs-lookup"><span data-stu-id="cf210-121">The `Overloads` keyword can be applied to `Sub`, `Function`, and `Property` statements declared in an interface definition.</span></span> <span data-ttu-id="cf210-122">Ponadto `Property` instrukcje mogą mieć `Default`, `ReadOnly`, lub `WriteOnly` modyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="cf210-122">In addition, `Property` statements can have the `Default`, `ReadOnly`, or `WriteOnly` modifiers.</span></span> <span data-ttu-id="cf210-123">Brak innych modyfikatorów —`Public`, `Private`, `Friend`, `Protected`, `Shared`, `Overrides`, `MustOverride`, lub `Overridable`— są dozwolone.</span><span class="sxs-lookup"><span data-stu-id="cf210-123">None of the other modifiers—`Public`, `Private`, `Friend`, `Protected`, `Shared`, `Overrides`, `MustOverride`, or `Overridable`—are allowed.</span></span> <span data-ttu-id="cf210-124">Aby uzyskać więcej informacji, zobacz [kontekst deklaracji i domyślne poziomy dostępu](../../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="cf210-124">For more information, see [Declaration Contexts and Default Access Levels](../../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="cf210-125">Na przykład poniższy kod definiuje interfejs z jednej funkcji, jednej właściwości i jedno zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="cf210-125">For example, the following code defines an interface with one function, one property, and one event.</span></span>  
  
 [!code-vb[VbVbalrOOP#17](../../../../visual-basic/misc/codesnippet/VisualBasic/index_1.vb)]  
  
## <a name="implementing-interfaces"></a><span data-ttu-id="cf210-126">Implementowanie interfejsów</span><span class="sxs-lookup"><span data-stu-id="cf210-126">Implementing Interfaces</span></span>  
 <span data-ttu-id="cf210-127">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Słowa zarezerwowanego `Implements` jest używany na dwa sposoby.</span><span class="sxs-lookup"><span data-stu-id="cf210-127">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] reserved word `Implements` is used in two ways.</span></span> <span data-ttu-id="cf210-128">`Implements` Instrukcji oznacza, że klasy lub struktury implementuje interfejs.</span><span class="sxs-lookup"><span data-stu-id="cf210-128">The `Implements` statement signifies that a class or structure implements an interface.</span></span> <span data-ttu-id="cf210-129">`Implements` — Słowo kluczowe oznacza, że element członkowski klasy lub struktury element członkowski implementuje członkiem określonego interfejsu.</span><span class="sxs-lookup"><span data-stu-id="cf210-129">The `Implements` keyword signifies that a class member or structure member implements a specific interface member.</span></span>  
  
### <a name="implements-statement"></a><span data-ttu-id="cf210-130">Implements — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="cf210-130">Implements Statement</span></span>  
 <span data-ttu-id="cf210-131">Jeśli klasy lub struktury implementuje jeden lub więcej interfejsów, musi on zawierać `Implements` instrukcji natychmiast po `Class` lub `Structure` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="cf210-131">If a class or structure implements one or more interfaces, it must include the `Implements` statement immediately after the `Class` or `Structure` statement.</span></span> <span data-ttu-id="cf210-132">`Implements` Instrukcja wymaga rozdzielana przecinkami lista interfejsy do zaimplementowania przez klasę.</span><span class="sxs-lookup"><span data-stu-id="cf210-132">The `Implements` statement requires a comma-separated list of interfaces to be implemented by a class.</span></span> <span data-ttu-id="cf210-133">Klasy lub struktury musi implementować wszystkie elementy członkowskie interfejsu za pomocą `Implements` — słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="cf210-133">The class or structure must implement all interface members using the `Implements` keyword.</span></span>  
  
### <a name="implements-keyword"></a><span data-ttu-id="cf210-134">Implements — słowo kluczowe</span><span class="sxs-lookup"><span data-stu-id="cf210-134">Implements Keyword</span></span>  
 <span data-ttu-id="cf210-135">`Implements` — Słowo kluczowe wymaga rozdzielana przecinkami lista członków interfejsu do zaimplementowania.</span><span class="sxs-lookup"><span data-stu-id="cf210-135">The `Implements` keyword requires a comma-separated list of interface members to be implemented.</span></span> <span data-ttu-id="cf210-136">Ogólnie rzecz biorąc tylko członek jeden interfejs jest określony, ale można określić wiele elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="cf210-136">Generally, only a single interface member is specified, but you can specify multiple members.</span></span> <span data-ttu-id="cf210-137">Specyfikacja elementu członkowskiego interfejsu, który składa się z nazwy interfejsu, która musi zostać określona w instrukcji implementuje w obrębie klasy; okres; i nazwa funkcji członkowskiej, właściwość lub zdarzenie, które mają zostać wdrożone.</span><span class="sxs-lookup"><span data-stu-id="cf210-137">The specification of an interface member consists of the interface name, which must be specified in an implements statement within the class; a period; and the name of the member function, property, or event to be implemented.</span></span> <span data-ttu-id="cf210-138">Nazwa elementu członkowskiego, który implementuje element członkowski można użyć dowolnego poprawnego identyfikatora i nie jest ograniczona do `InterfaceName_MethodName` Konwencji używany w starszych wersjach [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf210-138">The name of a member that implements an interface member can use any legal identifier, and it is not limited to the `InterfaceName_MethodName` convention used in earlier versions of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="cf210-139">Na przykład poniższy kod przedstawia sposób Zadeklaruj procedury o nazwie `Sub1` implementującej metody interfejsu:</span><span class="sxs-lookup"><span data-stu-id="cf210-139">For example, the following code shows how to declare a subroutine named `Sub1` that implements a method of an interface:</span></span>  
  
 [!code-vb[VbVbalrOOP#69](../../../../visual-basic/misc/codesnippet/VisualBasic/index_2.vb)]  
  
 <span data-ttu-id="cf210-140">Typy parametrów i zwracanych typów implementujący element członkowski musi być zgodna deklaracja właściwości lub elementu członkowskiego interfejsu w interfejsie.</span><span class="sxs-lookup"><span data-stu-id="cf210-140">The parameter types and return types of the implementing member must match the interface property or member declaration in the interface.</span></span> <span data-ttu-id="cf210-141">Najbardziej typowe sposób implementowania elementem interfejsu jest z elementu członkowskiego, który ma taką samą nazwę jak interfejs, jak pokazano w poprzednim przykładzie.</span><span class="sxs-lookup"><span data-stu-id="cf210-141">The most common way to implement an element of an interface is with a member that has the same name as the interface, as shown in the previous example.</span></span>  
  
 <span data-ttu-id="cf210-142">Aby zadeklarować implementacja metody interfejsu, można użyć wszelkie atrybuty, które są prawnych w deklaracjach metody wystąpienia, w tym `Overloads`, `Overrides`, `Overridable`, `Public`, `Private`, `Protected`, `Friend`, `Protected Friend`, `MustOverride`, `Default`, i `Static`.</span><span class="sxs-lookup"><span data-stu-id="cf210-142">To declare the implementation of an interface method, you can use any attributes that are legal on instance method declarations, including `Overloads`, `Overrides`, `Overridable`, `Public`, `Private`, `Protected`, `Friend`, `Protected Friend`, `MustOverride`, `Default`, and `Static`.</span></span> <span data-ttu-id="cf210-143">`Shared` Atrybutu jest niedozwolona, ponieważ definiuje klasę zamiast metody wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="cf210-143">The `Shared` attribute is not legal since it defines a class rather than an instance method.</span></span>  
  
 <span data-ttu-id="cf210-144">Przy użyciu `Implements`, można także zapisywać pojedynczej metody, która implementuje wiele metod zdefiniowane w interfejsie, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="cf210-144">Using `Implements`, you can also write a single method that implements multiple methods defined in an interface, as in the following example:</span></span>  
  
 [!code-vb[VbVbalrOOP#70](../../../../visual-basic/misc/codesnippet/VisualBasic/index_3.vb)]  
  
 <span data-ttu-id="cf210-145">Prywatnego elementu członkowskiego służy do implementowania elementem interfejsu.</span><span class="sxs-lookup"><span data-stu-id="cf210-145">You can use a private member to implement an interface member.</span></span> <span data-ttu-id="cf210-146">Członek prywatny implementuje elementu członkowskiego interfejsu, ten element członkowski staje się dostępna na interfejsie mimo że nie jest dostępny bezpośrednio na zmienne obiektów w klasie.</span><span class="sxs-lookup"><span data-stu-id="cf210-146">When a private member implements a member of an interface, that member becomes available by way of the interface even though it is not available directly on object variables for the class.</span></span>  
  
### <a name="interface-implementation-examples"></a><span data-ttu-id="cf210-147">Przykłady implementacji interfejsu</span><span class="sxs-lookup"><span data-stu-id="cf210-147">Interface Implementation Examples</span></span>  
 <span data-ttu-id="cf210-148">Klasy, które implementują interfejs musi implementować jego właściwości, metod i zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="cf210-148">Classes that implement an interface must implement all its properties, methods, and events.</span></span>  
  
 <span data-ttu-id="cf210-149">W poniższym przykładzie zdefiniowano dwa interfejsy.</span><span class="sxs-lookup"><span data-stu-id="cf210-149">The following example defines two interfaces.</span></span> <span data-ttu-id="cf210-150">Drugi interfejs `Interface2`, dziedziczy `Interface1` i definiuje dodatkowe właściwości i metody.</span><span class="sxs-lookup"><span data-stu-id="cf210-150">The second interface, `Interface2`, inherits `Interface1` and defines an additional property and method.</span></span>  
  
 [!code-vb[VbVbalrOOP#39](../../../../visual-basic/misc/codesnippet/VisualBasic/index_4.vb)]  
  
 <span data-ttu-id="cf210-151">Implementuje w następnym przykładzie `Interface1`, interface, określone w poprzednim przykładzie:</span><span class="sxs-lookup"><span data-stu-id="cf210-151">The next example implements `Interface1`, the interface defined in the previous example:</span></span>  
  
 [!code-vb[VbVbalrOOP#40](../../../../visual-basic/misc/codesnippet/VisualBasic/index_5.vb)]  
  
 <span data-ttu-id="cf210-152">Implementuje końcowy przykład `Interface2`, łącznie z metody dziedziczone z `Interface1`:</span><span class="sxs-lookup"><span data-stu-id="cf210-152">The final example implements `Interface2`, including a method inherited from `Interface1`:</span></span>  
  
 [!code-vb[VbVbalrOOP#41](../../../../visual-basic/misc/codesnippet/VisualBasic/index_6.vb)]  
  
 <span data-ttu-id="cf210-153">Można zaimplementować właściwość tylko do odczytu z właściwością readwrite (oznacza to, że nie masz zadeklarować on tylko do odczytu w klasie wykonawczych).</span><span class="sxs-lookup"><span data-stu-id="cf210-153">You can implement a readonly property with a readwrite property (that is, you do not have to declare it readonly in the implementing class).</span></span>  <span data-ttu-id="cf210-154">Implementowanie interfejsu zobowiązuje się do wdrożenia co najmniej elementów członkowskich, które deklaruje interfejsu, ale mogą oferować więcej możliwości, takie jak stosowanie równą możliwa do zapisu.</span><span class="sxs-lookup"><span data-stu-id="cf210-154">Implementing an interface promises to implement at least the members that the interface declares, but you can offer more functionality, such as allowing your property to be writable.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="cf210-155">Tematy pokrewne</span><span class="sxs-lookup"><span data-stu-id="cf210-155">Related Topics</span></span>  
  
|<span data-ttu-id="cf210-156">Tytuł</span><span class="sxs-lookup"><span data-stu-id="cf210-156">Title</span></span>|<span data-ttu-id="cf210-157">Opis</span><span class="sxs-lookup"><span data-stu-id="cf210-157">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="cf210-158">Wskazówki: Tworzenie i wdrażanie interfejsów</span><span class="sxs-lookup"><span data-stu-id="cf210-158">Walkthrough: Creating and Implementing Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/walkthrough-creating-and-implementing-interfaces.md)|<span data-ttu-id="cf210-159">Zawiera szczegółowe procedury, która przeprowadza użytkownika przez proces definiowanie i wdrażanie własnego interfejsu.</span><span class="sxs-lookup"><span data-stu-id="cf210-159">Provides a detailed procedure that takes you through the process of defining and implementing your own interface.</span></span>|  
|[<span data-ttu-id="cf210-160">Wariancje w interfejsach</span><span class="sxs-lookup"><span data-stu-id="cf210-160">Variance in Generic Interfaces</span></span>](../../concepts/covariance-contravariance/variance-in-generic-interfaces.md)|<span data-ttu-id="cf210-161">Zawiera omówienie Kowariancja i kontrawariancja w interfejsach, a także listę interfejsów ogólnych typu variant w programie .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf210-161">Discusses covariance and contravariance in generic interfaces and provides a list of variant generic interfaces in the .NET Framework.</span></span>|