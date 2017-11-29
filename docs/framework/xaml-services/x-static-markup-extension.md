---
title: "x:Static — Rozszerzenie znaczników"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
caps.latest.revision: "25"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: d006c8d0937a454dcbe092dcc3e35c4644088e59
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="c2aca-102">x:Static — Rozszerzenie znaczników</span><span class="sxs-lookup"><span data-stu-id="c2aca-102">x:Static Markup Extension</span></span>
<span data-ttu-id="c2aca-103">Odwołuje się do dowolnej jednostki kodu przez wartość statyczną, która jest zdefiniowana w [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]— sposób zgodne.</span><span class="sxs-lookup"><span data-stu-id="c2aca-103">References any static by-value code entity that is defined in a [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]–compliant way.</span></span> <span data-ttu-id="c2aca-104">Właściwość statyczna, do którego odwołuje się może służyć do zapewnienia wartości właściwości w języku XAML.</span><span class="sxs-lookup"><span data-stu-id="c2aca-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="c2aca-105">Użycie atrybutu języka XAML</span><span class="sxs-lookup"><span data-stu-id="c2aca-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c2aca-106">Wartości XAML</span><span class="sxs-lookup"><span data-stu-id="c2aca-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`prefix`|<span data-ttu-id="c2aca-107">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="c2aca-107">Optional.</span></span> <span data-ttu-id="c2aca-108">Prefiks, który odwołuje się do mapowanej, innej niż domyślna przestrzeń nazw XAML.</span><span class="sxs-lookup"><span data-stu-id="c2aca-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="c2aca-109">`prefix`pokazano jawnie użycia, ponieważ odwołuje się rzadko statycznej właściwości, które pochodzą z domyślnej przestrzeni nazw XAML.</span><span class="sxs-lookup"><span data-stu-id="c2aca-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="c2aca-110">Zobacz uwagi.</span><span class="sxs-lookup"><span data-stu-id="c2aca-110">See Remarks.</span></span>|  
|`typeName`|<span data-ttu-id="c2aca-111">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="c2aca-111">Required.</span></span> <span data-ttu-id="c2aca-112">Nazwa typu, który definiuje żądany statycznego elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="c2aca-112">The name of the type that defines the desired static member.</span></span>|  
|`staticMemberName`|<span data-ttu-id="c2aca-113">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="c2aca-113">Required.</span></span> <span data-ttu-id="c2aca-114">Nazwa elementu członkowskiego żądaną wartość statyczną (stałą, właściwość statyczna, pole lub wartością wyliczenia).</span><span class="sxs-lookup"><span data-stu-id="c2aca-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2aca-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c2aca-115">Remarks</span></span>  
 <span data-ttu-id="c2aca-116">Jednostek kodu, do którego odwołuje się musi być jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="c2aca-116">The code entity that is referenced must be one of the following:</span></span>  
  
-   <span data-ttu-id="c2aca-117">Stała</span><span class="sxs-lookup"><span data-stu-id="c2aca-117">A constant</span></span>  
  
-   <span data-ttu-id="c2aca-118">Właściwość statyczna</span><span class="sxs-lookup"><span data-stu-id="c2aca-118">A static property</span></span>  
  
-   <span data-ttu-id="c2aca-119">Pola</span><span class="sxs-lookup"><span data-stu-id="c2aca-119">A field</span></span>  
  
-   <span data-ttu-id="c2aca-120">Wartość wyliczenia</span><span class="sxs-lookup"><span data-stu-id="c2aca-120">An enumeration value</span></span>  
  
 <span data-ttu-id="c2aca-121">Określenie żadnych innych jednostek kodu, takie jak niestatycznej właściwości, powoduje błąd kompilacji, jeśli XAML jest kompilacji znaczników lub wyjątek analizy czas ładowania XAML.</span><span class="sxs-lookup"><span data-stu-id="c2aca-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>  
  
 <span data-ttu-id="c2aca-122">Możesz wprowadzić `x:Static` odwołania do statycznego pola lub właściwości, które nie znajdują się w domyślnej przestrzeni nazw XAML dla bieżącego dokumentu XAML; jednak wymaga to mapowanie prefiksu.</span><span class="sxs-lookup"><span data-stu-id="c2aca-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="c2aca-123">Przestrzeń nazw XAML prawie zawsze są definiowane dla elementu głównego dokumentu XAML.</span><span class="sxs-lookup"><span data-stu-id="c2aca-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>  
  
 <span data-ttu-id="c2aca-124">Operacje wyszukiwania dla właściwości statyczne może zostać przeprowadzone przez usług .NET Framework XAML i czytników XAML i zapisywania XAML działają domyślny kontekst schematu XAML.</span><span class="sxs-lookup"><span data-stu-id="c2aca-124">The lookup operations for static properties can be performed by .NET Framework XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="c2aca-125">Ten kontekst schematu XAML służy odbicia CLR do zapewnienia niezbędnych wartości statyczne Tworzenie wykresu obiektu.</span><span class="sxs-lookup"><span data-stu-id="c2aca-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="c2aca-126">`typeName` Określ jest rzeczywiście XAML nazwę typu, nie nazwę typu CLR, chociaż są zasadniczo taką samą nazwę, używając domyślny kontekst schematu XAML lub w przypadku używania wszystkich istniejących struktur opartych na CLR XAML — wdrażanie.</span><span class="sxs-lookup"><span data-stu-id="c2aca-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>  
  
 <span data-ttu-id="c2aca-127">Należy zachować ostrożność podczas wprowadzania `x:Static` odwołań, które nie są bezpośrednio typ wartości właściwości.</span><span class="sxs-lookup"><span data-stu-id="c2aca-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="c2aca-128">W kodzie XAML przetwarzania udostępnia wartości z rozszerzeniem znacznika sekwencji nie wywołuj konwersja dodatkowe wartości.</span><span class="sxs-lookup"><span data-stu-id="c2aca-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="c2aca-129">Dotyczy to nawet wtedy, gdy Twoje `x:Static` odwołanie tworzy ciąg tekstowy, a konwersja wartości dla wartości atrybutu oparte na ciąg tekstowy zwykle odbywa się dla tego określonego elementu członkowskiego lub dla każdej wartości elementu członkowskiego typu zwracanego.</span><span class="sxs-lookup"><span data-stu-id="c2aca-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>  
  
 <span data-ttu-id="c2aca-130">Składnią atrybutu jest składnia najczęściej używana z tym rozszerzeniem znacznika.</span><span class="sxs-lookup"><span data-stu-id="c2aca-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="c2aca-131">Token ciągu po `x:Static` przypisany jako identyfikator ciągu <xref:System.Windows.Markup.StaticExtension.Member%2A> wartości podstawowych <xref:System.Windows.Markup.StaticExtension> rozszerzenie klasy.</span><span class="sxs-lookup"><span data-stu-id="c2aca-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>  
  
 <span data-ttu-id="c2aca-132">Istnieją dwa inne użycia XAML, które są często technicznie możliwa.</span><span class="sxs-lookup"><span data-stu-id="c2aca-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="c2aca-133">Jednak te użycia są mniej typowe, ponieważ są one niepotrzebnie pełne:</span><span class="sxs-lookup"><span data-stu-id="c2aca-133">However, these usages are less common because they are unnecessarily verbose:</span></span>  
  
 <span data-ttu-id="c2aca-134">**Obiekt składni elementu:** `<x:Static Member="` `prefix` `:` `typeName` `.` `staticMemberName``" .../>`</span><span class="sxs-lookup"><span data-stu-id="c2aca-134">**Object element syntax:** `<x:Static Member="` `prefix` `:` `typeName` `.` `staticMemberName` `" .../>`</span></span>  
  
 <span data-ttu-id="c2aca-135">**Atrybut składni jawną właściwość elementu członkowskiego dla ciągu inicjującego:** `<` `object`  ``  `property` `="{x:Static Member=` `prefix` `:` `typeName` `.` `staticMemberName``}" .../>`</span><span class="sxs-lookup"><span data-stu-id="c2aca-135">**Attribute syntax with explicit Member property for initialization string:** `<` `object` `` `property` `="{x:Static Member=` `prefix` `:` `typeName` `.` `staticMemberName` `}" .../>`</span></span>  
  
 <span data-ttu-id="c2aca-136">W implementacji usług .NET Framework XAML obsługę tego rozszerzenia znacznika jest definiowana za pomocą <xref:System.Windows.Markup.StaticExtension> klasy.</span><span class="sxs-lookup"><span data-stu-id="c2aca-136">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>  
  
 <span data-ttu-id="c2aca-137">`x:Static`to rozszerzenie znacznika.</span><span class="sxs-lookup"><span data-stu-id="c2aca-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="c2aca-138">Wszystkie rozszerzenia znaczników w XAML, użyj `{` i `}` znaków w ich składni atrybutu Konwencji, za pomocą którego procesora XAML rozpoznaje, że rozszerzenie znaczników należy podać wartość.</span><span class="sxs-lookup"><span data-stu-id="c2aca-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="c2aca-139">Aby uzyskać więcej informacji na temat rozszerzeń znaczników, zobacz [rozszerzenia znaczników dla przeglądu XAML](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c2aca-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="c2aca-140">Uwagi dotyczące użycia WPF</span><span class="sxs-lookup"><span data-stu-id="c2aca-140">WPF Usage Notes</span></span>  
 <span data-ttu-id="c2aca-141">Domyślna przestrzeń nazw XAML, użyj programowania WPF nie zawiera wiele przydatnych właściwości statycznej, a najbardziej przydatne właściwości statyczne obsługuje takie jak konwertery typu, które ułatwiają bez konieczności użycia `{x:Static}` .</span><span class="sxs-lookup"><span data-stu-id="c2aca-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="c2aca-142">W przypadku statycznej właściwości należy zamapować prefiksu dla przestrzeni nazw XAML po spełnieniu jednego z następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="c2aca-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>  
  
-   <span data-ttu-id="c2aca-143">Odwołanie do typu, który istnieje w WPF, ale nie jest częścią domyślnej przestrzeni nazw XAML WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="c2aca-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]).</span></span> <span data-ttu-id="c2aca-144">To jest dość typowy scenariusz dla przy użyciu `x:Static`.</span><span class="sxs-lookup"><span data-stu-id="c2aca-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="c2aca-145">Na przykład może użyć `x:Static` odwołanie z mapowania przestrzeni nazw XAML, aby <xref:System> przestrzeni nazw i mscorlib Zestaw CLR aby odwołanie statycznej właściwości <xref:System.Environment> klasy.</span><span class="sxs-lookup"><span data-stu-id="c2aca-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>  
  
-   <span data-ttu-id="c2aca-146">Z niestandardowego zestawu odwołuje się do typu.</span><span class="sxs-lookup"><span data-stu-id="c2aca-146">You are referencing a type from a custom assembly.</span></span>  
  
-   <span data-ttu-id="c2aca-147">Odwołujesz się do typu, który istnieje w zestawie WPF, ale ten typ znajduje się w przestrzeni nazw CLR, który nie został zmapowany jako część domyślnej WPF XAML przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="c2aca-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="c2aca-148">Mapowanie przestrzeni nazw CLR w domyślnej przestrzeni nazw XAML dla WPF jest wykonywane przez definicje w różnych zestawach WPF (Aby uzyskać więcej informacji dotyczących tej reguły, zobacz [przestrzeń nazw XAML i Namespace mapowanie dla WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span><span class="sxs-lookup"><span data-stu-id="c2aca-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="c2aca-149">Mapowane bez nazw CLR może istnieć, jeśli tej przestrzeni nazw CLR składa się przede wszystkim z definicje klas, które nie są zwykle przeznaczone dla XAML, takich jak <xref:System.Windows.Threading>.</span><span class="sxs-lookup"><span data-stu-id="c2aca-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>  
  
 <span data-ttu-id="c2aca-150">Aby uzyskać więcej informacji na temat korzystania z prefiksami i przestrzeni nazw XAML dla WPF, zobacz [przestrzeń nazw XAML i Namespace mapowanie WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="c2aca-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2aca-151">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c2aca-151">See Also</span></span>  
 [<span data-ttu-id="c2aca-152">x: Type — rozszerzenie znaczników</span><span class="sxs-lookup"><span data-stu-id="c2aca-152">x:Type Markup Extension</span></span>](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [<span data-ttu-id="c2aca-153">Typy migrowane z WPF do System.Xaml</span><span class="sxs-lookup"><span data-stu-id="c2aca-153">Types Migrated from WPF to System.Xaml</span></span>](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)