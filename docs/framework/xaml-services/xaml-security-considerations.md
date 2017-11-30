---
title: "Zagadnienia dotyczące zabezpieczeń XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
caps.latest.revision: "7"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 59d0b835a0de3e84e2cb6e77ed368511bfe21b19
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="xaml-security-considerations"></a><span data-ttu-id="f3609-102">Zagadnienia dotyczące zabezpieczeń XAML</span><span class="sxs-lookup"><span data-stu-id="f3609-102">XAML Security Considerations</span></span>
<span data-ttu-id="f3609-103">W tym temacie opisano najlepsze rozwiązania dotyczące zabezpieczeń w aplikacji, korzystając z języka XAML i .NET Framework XAML Services API.</span><span class="sxs-lookup"><span data-stu-id="f3609-103">This topic describes best practices for security in applications when you use XAML and .NET Framework XAML Services API.</span></span>  
  
## <a name="untrusted-xaml-in-applications"></a><span data-ttu-id="f3609-104">Niezaufane XAML w aplikacjach</span><span class="sxs-lookup"><span data-stu-id="f3609-104">Untrusted XAML in Applications</span></span>  
 <span data-ttu-id="f3609-105">W tym sensie, najbardziej ogólnym niezaufanej XAML jest dowolnego źródła XAML, które aplikacji nie zostały nie obejmują lub emisji.</span><span class="sxs-lookup"><span data-stu-id="f3609-105">In the most general sense, untrusted XAML is any XAML source that your application did not specifically include or emit.</span></span>  
  
 <span data-ttu-id="f3609-106">XAML skompilowany w lub przechowywane jako `resx`— typ zasobu w zestawie zaufanych i podpisem nie jest z założenia niezaufanych.</span><span class="sxs-lookup"><span data-stu-id="f3609-106">XAML that is compiled into or stored as a `resx`-type resource within a trusted and signed assembly is not inherently untrusted.</span></span> <span data-ttu-id="f3609-107">Można ufać XAML, jak zaufania zestawu jako całość.</span><span class="sxs-lookup"><span data-stu-id="f3609-107">You can trust the XAML as much as you trust the assembly as a whole.</span></span> <span data-ttu-id="f3609-108">W większości przypadków dotyczy tylko aspekty zaufania utracić XAML, która jest źródłem XAML, że zostały załadowane z strumienia lub inne we/wy.</span><span class="sxs-lookup"><span data-stu-id="f3609-108">In most cases, you are only concerned with the trust aspects of loose XAML, which is a XAML source that you load from a stream or other IO.</span></span> <span data-ttu-id="f3609-109">Utracić XAML nie jest określony składnik lub funkcji z wdrażanie i opakowanie infrastruktury modelu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f3609-109">Loose XAML is not a specific component or feature of an application model with a deployment and packaging infrastructure.</span></span> <span data-ttu-id="f3609-110">Jednak zestaw może zastosować zachowania, które obejmuje ładowanie utracić XAML.</span><span class="sxs-lookup"><span data-stu-id="f3609-110">However, an assembly might implement a behavior that involves loading loose XAML.</span></span>  
  
 <span data-ttu-id="f3609-111">Dla XAML niezaufanych należy traktować go ogólnie takie same tak, jakby była kodzie niezaufanym.</span><span class="sxs-lookup"><span data-stu-id="f3609-111">For untrusted XAML, you should treat it generally the same as if it were untrusted code.</span></span> <span data-ttu-id="f3609-112">Aby uniemożliwić dostęp do zaufanego kodu XAML prawdopodobnie niezaufanych, należy użyć sandboxing lub innych metafory.</span><span class="sxs-lookup"><span data-stu-id="f3609-112">Use sandboxing or other metaphors to prevent possibly untrusted XAML from accessing your trusted code.</span></span>  
  
 <span data-ttu-id="f3609-113">Rodzaj XAML możliwości daje XAML prawo do tworzenia obiektów i ustawiania ich właściwości.</span><span class="sxs-lookup"><span data-stu-id="f3609-113">The nature of XAML capabilities gives the XAML the right to construct objects and set their properties.</span></span> <span data-ttu-id="f3609-114">Te możliwości również obejmować dostęp do typy konwerterów mapowania i uzyskiwania dostępu do zestawów w domenie aplikacji przy użyciu rozszerzenia znaczników `x:Code` bloków i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="f3609-114">These capabilities also include accessing type converters, mapping and accessing assemblies in the application domain, using markup extensions, `x:Code` blocks, and so on.</span></span>  
  
 <span data-ttu-id="f3609-115">Oprócz możliwości poziom języka XAML jest używany do definicji interfejsu użytkownika w wielu technologii.</span><span class="sxs-lookup"><span data-stu-id="f3609-115">In addition to its language-level capabilities, XAML is used for UI definition in many technologies.</span></span> <span data-ttu-id="f3609-116">Ładowanie niezaufanych XAML może to oznaczać ładowania złośliwego fałszowaniem interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f3609-116">Loading untrusted XAML might mean loading a malicious spoofing UI.</span></span>  
  
## <a name="sharing-context-between-readers-and-writers"></a><span data-ttu-id="f3609-117">Udostępnianie kontekstu między czytelników i zapisywania</span><span class="sxs-lookup"><span data-stu-id="f3609-117">Sharing Context Between Readers and Writers</span></span>  
 <span data-ttu-id="f3609-118">Architektura usług .NET Framework XAML dla czytników XAML i autorzy XAML wymaga często udostępnianie czytnik XAML do zapisywania XAML lub udostępnionego kontekst schematu XAML.</span><span class="sxs-lookup"><span data-stu-id="f3609-118">The .NET Framework XAML Services architecture for XAML readers and XAML writers often requires sharing a XAML reader to a XAML writer, or a shared XAML schema context.</span></span> <span data-ttu-id="f3609-119">Udostępnianie obiektów lub kontekstów może być wymagane, jeśli pisania logiki pętli węzła XAML, lub zapewniając niestandardowego Zapisz ścieżkę.</span><span class="sxs-lookup"><span data-stu-id="f3609-119">Sharing objects or contexts might be required if you are writing XAML node loop logic, or providing a custom save path.</span></span> <span data-ttu-id="f3609-120">Nie powinna współużytkować wystąpień czytnika XAML, kontekst schematu XAML niestandardowe lub ustawienia dla klas odczytywania/zapisywania XAML między kodem zaufanych i niezaufanych.</span><span class="sxs-lookup"><span data-stu-id="f3609-120">You should not share XAML reader instances, nondefault XAML schema context, or settings for XAML reader/writer classes between trusted and untrusted code.</span></span>  
  
 <span data-ttu-id="f3609-121">Większość scenariuszy i operacji dotyczących obiektu XAML zapisywania dla typu CLR na podstawie kopii służy tylko domyślny kontekst schematu XAML.</span><span class="sxs-lookup"><span data-stu-id="f3609-121">Most scenarios and operations involving XAML object writing for a CLR-based type backing can just use default XAML schema context.</span></span> <span data-ttu-id="f3609-122">Domyślny kontekst schematu XAML nie ma jawnie ustawień, które mogą negatywnie wpłynąć na pełne zaufanie.</span><span class="sxs-lookup"><span data-stu-id="f3609-122">The default XAML schema context does not explicitly include settings that could compromise full trust.</span></span> <span data-ttu-id="f3609-123">W związku z tym jest bezpieczne udostępnianie kontekstu między składnikami odczytywania/zapisywania XAML zaufanych i niezaufanych.</span><span class="sxs-lookup"><span data-stu-id="f3609-123">It is thus safe to share context between trusted and untrusted XAML reader/writer components.</span></span> <span data-ttu-id="f3609-124">Jednak jeśli to zrobisz, nadal jest najlepszym rozwiązaniem, aby zachować takie czytniki i zapisywania w oddzielnym <xref:System.AppDomain> zakresów z jednego z nich w szczególności zamierzony/piaskownicy dla częściowej relacji zaufania.</span><span class="sxs-lookup"><span data-stu-id="f3609-124">However, if you do this, it is still a best practice to keep such readers and writers in separate <xref:System.AppDomain> scopes, with one of them specifically intended/sandboxed for partial trust.</span></span>  
  
## <a name="xaml-namespaces-and-assembly-trust"></a><span data-ttu-id="f3609-125">Przestrzeń nazw XAML i zaufanych zestawów</span><span class="sxs-lookup"><span data-stu-id="f3609-125">XAML Namespaces and Assembly Trust</span></span>  
 <span data-ttu-id="f3609-126">Podstawowa składnia niekwalifikowanych i definicję dla interpretowanie niestandardowe mapowania przestrzeni nazw XAML do zestawu XAML nie rozróżnia zaufanych i niezaufanych zestawu jako załadowane do tej domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f3609-126">The basic unqualified syntax and definition for how XAML interprets a custom XAML namespace mapping to an assembly does not distinguish between a trusted and untrusted assembly as loaded into the application domain.</span></span> <span data-ttu-id="f3609-127">W związku z tym jest technicznie możliwe niezaufanego zestawu sfałszować zaufanym zestawem zamierzone mapowania przestrzeni nazw XAML i przechwytywania obiekt zadeklarowane źródłem XAML i informacje dotyczące właściwości.</span><span class="sxs-lookup"><span data-stu-id="f3609-127">Thus, it is technically possible for an untrusted assembly to spoof a trusted assembly's intended XAML namespace mapping and capture a XAML source's declared object and property information.</span></span> <span data-ttu-id="f3609-128">Jeśli wymagania dotyczące zabezpieczeń, aby uniknąć tej sytuacji, należy wprowadzać zamierzone mapowanie przestrzeni nazw XAML przy użyciu jednej z następujących metod:</span><span class="sxs-lookup"><span data-stu-id="f3609-128">If you have security requirements to avoid this situation, your intended XAML namespace mapping should be made using one of the following techniques:</span></span>  
  
-   <span data-ttu-id="f3609-129">Użyj pełni kwalifikowanej nazwy zestawu z mocną nazwą w mapowania przestrzeni nazw XAML, wszelkie wprowadzone przez użytkownika aplikacji XAML.</span><span class="sxs-lookup"><span data-stu-id="f3609-129">Use a fully qualified assembly name with strong name in any XAML namespace mapping made by your application's XAML.</span></span>  
  
-   <span data-ttu-id="f3609-130">Ograniczanie mapowania ustalony zbiór zestawów odwołań, tworząc określonego zestawu <xref:System.Xaml.XamlSchemaContext> dla Twojego XAML czytników oraz XAML obiekt modułów zapisujących.</span><span class="sxs-lookup"><span data-stu-id="f3609-130">Restrict assembly mapping to a fixed set of reference assemblies, by constructing a specific <xref:System.Xaml.XamlSchemaContext> for your XAML readers and XAML object writers.</span></span> <span data-ttu-id="f3609-131">Zobacz <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>.</span><span class="sxs-lookup"><span data-stu-id="f3609-131">See <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>.</span></span>  
  
## <a name="xaml-type-mapping-and-type-system-access"></a><span data-ttu-id="f3609-132">Mapowanie typu XAML i typ dostępu do systemu</span><span class="sxs-lookup"><span data-stu-id="f3609-132">XAML Type Mapping and Type System Access</span></span>  
 <span data-ttu-id="f3609-133">XAML obsługuje własny typ system, czyli na wiele sposobów elementu równorzędnego do jak CLR implementuje podstawowe system typów CLR.</span><span class="sxs-lookup"><span data-stu-id="f3609-133">XAML supports its own type system, which in many ways is a peer to how CLR implements the basic CLR type system.</span></span> <span data-ttu-id="f3609-134">Niektórych aspektów świadomości typu, gdzie są podejmowanie decyzji dotyczących typu, na podstawie informacji o jego typu zaufania należy odroczyć do informacji o typie CLR kopii typów.</span><span class="sxs-lookup"><span data-stu-id="f3609-134">However, for certain aspects of type awareness where you are making trust decisions about a type based on its type information, you should defer to the type information in the CLR backing types.</span></span> <span data-ttu-id="f3609-135">Jest tak, ponieważ niektóre z określonych funkcji raportowania system typów języka XAML pozostają otwarte, jako metody wirtualne i w związku z tym nie są całkowicie pod kontrolą oryginalnej implementacji usług .NET Framework XAML.</span><span class="sxs-lookup"><span data-stu-id="f3609-135">This is because some of the specific reporting capabilities of the XAML type system are left open as virtual methods and are therefore, not fully under the control of the original .NET Framework XAML Services implementations.</span></span> <span data-ttu-id="f3609-136">Te punkty rozszerzeń istnieje, ponieważ system typu XAML nie jest otwarty, aby dopasować rozszerzalności języka XAML, sama i jego możliwych alternatywnych strategii mapowanie typu lub domyślna implementacja kopii CLR i domyślny kontekst schematu XAML.</span><span class="sxs-lookup"><span data-stu-id="f3609-136">These extensibility points exist because the XAML type system is extensible, to match the extensibility of XAML itself and its possible alternative type-mapping strategies versus the default CLR-backed implementation and default XAML schema context.</span></span> <span data-ttu-id="f3609-137">Aby uzyskać więcej informacji, zobacz uwagi określonych w przypadku kilku właściwości <xref:System.Xaml.XamlType> i <xref:System.Xaml.XamlMember>.</span><span class="sxs-lookup"><span data-stu-id="f3609-137">For more information, see the specific notes on several of the properties of <xref:System.Xaml.XamlType> and <xref:System.Xaml.XamlMember>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3609-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f3609-138">See Also</span></span>  
 <xref:System.Xaml.Permissions.XamlAccessLevel>