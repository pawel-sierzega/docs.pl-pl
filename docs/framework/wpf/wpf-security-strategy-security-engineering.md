---
title: "Strategia zabezpieczeń WPF - projekt zabezpieczeń"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [WPF], testing techniques
- Security Development Lifecycle (SDL), security analysis [WPF]
- Security Development Lifecycle (SDL), threat modeling
- Security Development Lifecycle (SDL), testing techniques
- Security Development Lifecycle (SDL), source analysis tools
- Security Development Lifecycle (SDL), critical code management
- threat modeling [WPF]
ms.assetid: 0fc04394-4e47-49ca-b0cf-8cd1161d95b9
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c9237ed7467e87cd3e6ba72418c6964ce918751c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="wpf-security-strategy---security-engineering"></a><span data-ttu-id="a2126-102">Strategia zabezpieczeń WPF - projekt zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="a2126-102">WPF Security Strategy - Security Engineering</span></span>
<span data-ttu-id="a2126-103">Wiarygodne technologie komputerowe to inicjatywa firmy Microsoft dla zapewnienia produkcji bezpiecznego kodu.</span><span class="sxs-lookup"><span data-stu-id="a2126-103">Trustworthy Computing is a Microsoft initiative for ensuring the production of secure code.</span></span> <span data-ttu-id="a2126-104">Jest kluczowym elementem inicjatywy wiarygodne technologie komputerowe [!INCLUDE[TLA#tla_sdl](../../../includes/tlasharptla-sdl-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2126-104">A key element of the Trustworthy Computing initiative is the [!INCLUDE[TLA#tla_sdl](../../../includes/tlasharptla-sdl-md.md)].</span></span> <span data-ttu-id="a2126-105">[!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] Engineering rozwiązaniem, używany w połączeniu z standardowe inżynieryjnym do ułatwienia dostarczania bezpiecznego kodu.</span><span class="sxs-lookup"><span data-stu-id="a2126-105">The [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] is an engineering practice that is used in conjunction with standard engineering processes to facilitate the delivery of secure code.</span></span> <span data-ttu-id="a2126-106">[!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] Składa się z 10 fazy, które łączą najlepsze rozwiązania z ujęcie w formalne ramy, measurability i dodatkowe struktury, w tym:</span><span class="sxs-lookup"><span data-stu-id="a2126-106">The [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] consists of ten phases that combine best practices with formalization, measurability, and additional structure, including:</span></span>  
  
-   <span data-ttu-id="a2126-107">Analiza projektu zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="a2126-107">Security design analysis</span></span>  
  
-   <span data-ttu-id="a2126-108">Narzędzie oparte jakości kontroli</span><span class="sxs-lookup"><span data-stu-id="a2126-108">Tool-based quality checks</span></span>  
  
-   <span data-ttu-id="a2126-109">Testowanie penetracji</span><span class="sxs-lookup"><span data-stu-id="a2126-109">Penetration testing</span></span>  
  
-   <span data-ttu-id="a2126-110">Przegląd końcowy zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="a2126-110">Final security review</span></span>  
  
-   <span data-ttu-id="a2126-111">Zarządzanie zabezpieczeniami produktu wersji POST</span><span class="sxs-lookup"><span data-stu-id="a2126-111">Post release product security management</span></span>  
  
## <a name="wpf-specifics"></a><span data-ttu-id="a2126-112">Szczegóły WPF</span><span class="sxs-lookup"><span data-stu-id="a2126-112">WPF Specifics</span></span>  
 <span data-ttu-id="a2126-113">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Engineering team zarówno stosuje i rozszerza [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], kombinację obejmuje następujące kluczowe aspekty:</span><span class="sxs-lookup"><span data-stu-id="a2126-113">The [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] engineering team both applies and extends the [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], the combination of which includes the following key aspects:</span></span>  
  
 [<span data-ttu-id="a2126-114">Modelowanie zagrożeń</span><span class="sxs-lookup"><span data-stu-id="a2126-114">Threat Modeling</span></span>](#threat_modeling)  
  
 [<span data-ttu-id="a2126-115">Analiza zabezpieczeń oraz narzędzia do edycji</span><span class="sxs-lookup"><span data-stu-id="a2126-115">Security Analysis and Editing Tools</span></span>](#tools)  
  
 [<span data-ttu-id="a2126-116">Techniki testowania</span><span class="sxs-lookup"><span data-stu-id="a2126-116">Testing Techniques</span></span>](#techniques)  
  
 [<span data-ttu-id="a2126-117">Kod krytyczny dla zarządzania</span><span class="sxs-lookup"><span data-stu-id="a2126-117">Critical Code Management</span></span>](#critical_code)  
  
<a name="threat_modeling"></a>   
### <a name="threat-modeling"></a><span data-ttu-id="a2126-118">Modelowanie zagrożeń</span><span class="sxs-lookup"><span data-stu-id="a2126-118">Threat Modeling</span></span>  
 <span data-ttu-id="a2126-119">Modelowanie zagrożeń jest podstawowym składnikiem [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)]i jest używany do profilu systemu, aby określić potencjalnych luk w zabezpieczeniach.</span><span class="sxs-lookup"><span data-stu-id="a2126-119">Threat modeling is a core component of the [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], and is used to profile a system to determine potential security vulnerabilities.</span></span> <span data-ttu-id="a2126-120">Po zidentyfikowaniu luk w zabezpieczeniach modelowanie zagrożeń gwarantuje również, że zostały spełnione odpowiednie środki zaradcze.</span><span class="sxs-lookup"><span data-stu-id="a2126-120">Once the vulnerabilities are identified, threat modeling also ensures that appropriate mitigations are in place.</span></span>  
  
 <span data-ttu-id="a2126-121">Na wysokim poziomie modelowanie zagrożeń obejmuje następujące kroki klucza za pomocą magazynu spożywczych, na przykład:</span><span class="sxs-lookup"><span data-stu-id="a2126-121">At a high level, threat modeling involves the following key steps by using a grocery store as an example:</span></span>  
  
1.  <span data-ttu-id="a2126-122">**Identyfikowanie zasobów**.</span><span class="sxs-lookup"><span data-stu-id="a2126-122">**Identifying Assets**.</span></span> <span data-ttu-id="a2126-123">Zasoby magazynem spożywczych mogą obejmować pracowników, sejfie kasy i spisu.</span><span class="sxs-lookup"><span data-stu-id="a2126-123">A grocery store's assets might include employees, a safe, cash registers, and inventory.</span></span>  
  
2.  <span data-ttu-id="a2126-124">**Wyliczanie punktów wejścia**.</span><span class="sxs-lookup"><span data-stu-id="a2126-124">**Enumerating Entry Points**.</span></span> <span data-ttu-id="a2126-125">Punkty wejścia magazynem spożywczych może obejmować przodu i drzwi Wstecz, windows, dokowania ładowania i klimatyzacja jednostki.</span><span class="sxs-lookup"><span data-stu-id="a2126-125">A grocery store's entry points might include the front and back doors, windows, the loading dock, and air conditioning units.</span></span>  
  
3.  <span data-ttu-id="a2126-126">**Badanie ataków na zasoby przy użyciu punktów wejścia**.</span><span class="sxs-lookup"><span data-stu-id="a2126-126">**Investigating Attacks against Assets using Entry Points**.</span></span> <span data-ttu-id="a2126-127">Jeden możliwości ataku jest przeznaczona magazynem spożywczych *bezpieczne* zasobów za pomocą *klimatyzacja* punktu wejścia; klimatyzacja jednostką może być unscrewed umożliwia bezpiecznie rama przy jego użyciu i z Magazyn.</span><span class="sxs-lookup"><span data-stu-id="a2126-127">One possible attack could target a grocery store's *safe* asset through the *air conditioning* entry point; the air conditioning unit could be unscrewed to allow the safe to be pulled up through it and out of the store.</span></span>  
  
 <span data-ttu-id="a2126-128">Modelowanie zagrożeń jest stosowana w całym [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] i obejmuje następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="a2126-128">Threat modeling is applied throughout [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] and includes the following:</span></span>  
  
-   <span data-ttu-id="a2126-129">Jak [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] analizator odczytuje pliki mapuje tekstu do odpowiedniej klasy modelu obiektów i tworzy rzeczywisty kod.</span><span class="sxs-lookup"><span data-stu-id="a2126-129">How the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] parser reads files, maps text to corresponding object model classes, and creates the actual code.</span></span>  
  
-   <span data-ttu-id="a2126-130">Jak uchwyt okna (hWnd) jest tworzony, wysyła komunikaty i jest używany do renderowania zawartości okna.</span><span class="sxs-lookup"><span data-stu-id="a2126-130">How a window handle (hWnd) is created, sends messages, and is used for rendering the contents of a window.</span></span>  
  
-   <span data-ttu-id="a2126-131">Sposób powiązania danych uzyskuje zasobów i współdziała z systemu.</span><span class="sxs-lookup"><span data-stu-id="a2126-131">How data binding obtains resources and interacts with the system.</span></span>  
  
 <span data-ttu-id="a2126-132">Modele te zagrożenia są ważne w przypadku identyfikowania wymagań dotyczących projektowania zabezpieczeń i środki zaradcze zagrożeń podczas procesu projektowania.</span><span class="sxs-lookup"><span data-stu-id="a2126-132">These threat models are important for identifying security design requirements and threat mitigations during the development process.</span></span>  
  
<a name="tools"></a>   
### <a name="source-analysis-and-editing-tools"></a><span data-ttu-id="a2126-133">Źródło analizy i narzędzia do edycji</span><span class="sxs-lookup"><span data-stu-id="a2126-133">Source Analysis and Editing Tools</span></span>  
 <span data-ttu-id="a2126-134">Oprócz kodu zabezpieczeń ręczne przeglądu elementów [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] zespół używa kilka narzędzi do analizy źródła i zmiany skojarzone zmniejszyć luk w zabezpieczeniach.</span><span class="sxs-lookup"><span data-stu-id="a2126-134">In addition to the manual security code review elements of the [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] team uses several tools for source analysis and associated edits to decrease security vulnerabilities.</span></span> <span data-ttu-id="a2126-135">Szeroką gamę narzędzi źródła są używane i są następujące:</span><span class="sxs-lookup"><span data-stu-id="a2126-135">A wide range of source tools are used, and include the following:</span></span>  
  
-   <span data-ttu-id="a2126-136">**FXCop**: umożliwia znalezienie typowych problemów z zabezpieczeniami w kodzie zarządzanym od reguł dziedziczenia z użyciem zabezpieczeń dostępu kodu, jak bezpiecznie współdziałanie z kodem niezarządzanym.</span><span class="sxs-lookup"><span data-stu-id="a2126-136">**FXCop**: Finds common security issues in managed code ranging from inheritance rules to code access security usage to how to safely interoperate with unmanaged code.</span></span> <span data-ttu-id="a2126-137">Zobacz [FXCop](http://www.gotdotnet.com/team/fxcop/).</span><span class="sxs-lookup"><span data-stu-id="a2126-137">See [FXCop](http://www.gotdotnet.com/team/fxcop/).</span></span>  
  
-   <span data-ttu-id="a2126-138">**Prefiks/Prefast**: luki w zabezpieczeniach znajduje i typowych problemów z zabezpieczeniami za pomocą kodu niezarządzanego, takie jak przepełnienia buforu formatu ciągu problemów i sprawdzania błędów.</span><span class="sxs-lookup"><span data-stu-id="a2126-138">**Prefix/Prefast**: Finds security vulnerabilities and common security issues in unmanaged code such as buffer overruns, format string issues, and error checking.</span></span>  
  
-   <span data-ttu-id="a2126-139">**Interfejsy API zakazane**: Wyszukiwanie źródła kodu, aby zidentyfikować przypadkowego funkcje, które są dobrze znanego powoduje problemy z zabezpieczeniami, takich jak `strcpy`.</span><span class="sxs-lookup"><span data-stu-id="a2126-139">**Banned APIs**: Searches source code to identify accidental usage of functions that are well-known for causing security issues, such as `strcpy`.</span></span> <span data-ttu-id="a2126-140">Po zidentyfikowaniu te funkcje są zastępowane rozwiązań alternatywnych, które są większe bezpieczeństwo.</span><span class="sxs-lookup"><span data-stu-id="a2126-140">Once identified, these functions are replaced with alternatives that are more security.</span></span>  
  
<a name="techniques"></a>   
### <a name="testing-techniques"></a><span data-ttu-id="a2126-141">Techniki testowania</span><span class="sxs-lookup"><span data-stu-id="a2126-141">Testing Techniques</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="a2126-142">używa różnorodnych narzędzi zabezpieczeń testowania techniki, które obejmują:</span><span class="sxs-lookup"><span data-stu-id="a2126-142"> uses a variety of security testing techniques that include:</span></span>  
  
-   <span data-ttu-id="a2126-143">**Testowanie Whitebox**: testerów wyświetlić kodu źródłowego i późniejszego kompilowania wykorzystać testów</span><span class="sxs-lookup"><span data-stu-id="a2126-143">**Whitebox Testing**: Testers view source code, and then build exploit tests</span></span>  
  
-   <span data-ttu-id="a2126-144">**Testowanie Blackbox**: testerów prób znalezienia zabezpieczeń wykorzystuje, sprawdzając interfejsu API i funkcje, a następnie spróbuj na ataki produktu.</span><span class="sxs-lookup"><span data-stu-id="a2126-144">**Blackbox Testing**: Testers try to find security exploits by examining the API and features, and then try to attack the product.</span></span>  
  
-   <span data-ttu-id="a2126-145">**Regresję problemy dotyczące zabezpieczeń z innymi produktami**: stosownych sprawdzane są problemy z zabezpieczeniami z pokrewnych produktów.</span><span class="sxs-lookup"><span data-stu-id="a2126-145">**Regressing Security Issues from other Products**: Where relevant, security issues from related products are tested.</span></span> <span data-ttu-id="a2126-146">Na przykład odpowiednie wariantów około sześćdziesiąt problemy z bezpieczeństwem dotyczące [!INCLUDE[TLA2#tla_ie](../../../includes/tla2sharptla-ie-md.md)] zostały zidentyfikowane i nastąpiła dla możliwości ich zastosowania do [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2126-146">For example, appropriate variants of approximately sixty security issues for [!INCLUDE[TLA2#tla_ie](../../../includes/tla2sharptla-ie-md.md)] have been identified and tried for their applicability to [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
-   <span data-ttu-id="a2126-147">**Na podstawie narzędzia penetracji testowanie za pomocą pliku Fuzzing**: plik fuzzing jest wykorzystanie czytnik plików wejściowych zakresu za pomocą różnych danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="a2126-147">**Tools-Based Penetration Testing through File Fuzzing**: File fuzzing is the exploitation of a file reader's input range through a variety of inputs.</span></span> <span data-ttu-id="a2126-148">Jednym z przykładów w [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] gdy ta metoda jest używana jest sprawdzenie niepowodzenia w obrazie dekodowania kodu.</span><span class="sxs-lookup"><span data-stu-id="a2126-148">One example in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] where this technique is used is to check for failure in image decoding code.</span></span>  
  
<a name="critical_code"></a>   
### <a name="critical-code-management"></a><span data-ttu-id="a2126-149">Kod krytyczny dla zarządzania</span><span class="sxs-lookup"><span data-stu-id="a2126-149">Critical Code Management</span></span>  
 <span data-ttu-id="a2126-150">Dla [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] tworzy piaskownicy zabezpieczeń przy użyciu [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)] obsługę oznaczenie i śledzenia kod krytyczny dla zabezpieczeń, który zostanie uprawnień (zobacz **krytyczny dla zabezpieczeń metodologii** w [ Strategia zabezpieczeń WPF - zabezpieczeń platformy](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)).</span><span class="sxs-lookup"><span data-stu-id="a2126-150">For [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] builds a security sandbox by using [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)] support for marking and tracking security-critical code that elevates privileges (see **Security-Critical Methodology** in [WPF Security Strategy - Platform Security](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)).</span></span> <span data-ttu-id="a2126-151">Taki kod na kod krytyczny dla zabezpieczeń ze względu na wymagania jakości wysokiego poziomu zabezpieczeń, otrzymuje dodatkowego poziomu inspekcji zabezpieczeń i kontroli zarządzania źródła.</span><span class="sxs-lookup"><span data-stu-id="a2126-151">Given the high security quality requirements on security critical code, such code receives an additional level of source management control and security audit.</span></span> <span data-ttu-id="a2126-152">Około 5 – 10% z [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] składa się z kod krytyczny dla zabezpieczeń, który jest rozpatrywana przez dedykowany zespół recenzowania.</span><span class="sxs-lookup"><span data-stu-id="a2126-152">Approximately 5% to 10% of [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] consists of security-critical code, which is reviewed by a dedicated reviewing team.</span></span> <span data-ttu-id="a2126-153">Kod źródłowy i sprawdzanie w trakcie zarządza śledzenia kodu krytycznego dla zabezpieczeń i mapowanie każdej jednostki krytyczne (np. metody, która zawiera kod krytyczny) do jego Zaloguj się w stanie wyłączonym.</span><span class="sxs-lookup"><span data-stu-id="a2126-153">The source code and check-in process is managed by tracking security critical code and mapping each critical entity (i.e. a method that contains critical code) to its sign off state.</span></span> <span data-ttu-id="a2126-154">Zaloguj się w stanie wyłączonym zawiera nazwy jednego lub więcej recenzentów.</span><span class="sxs-lookup"><span data-stu-id="a2126-154">The sign off state includes the names of one or more reviewers.</span></span> <span data-ttu-id="a2126-155">Każdy codzienne kompilacji [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] porównuje kod krytyczny w tym w wcześniejsze kompilacje, aby sprawdzić niezatwierdzone zmiany.</span><span class="sxs-lookup"><span data-stu-id="a2126-155">Each daily build of [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] compares the critical code to that in previous builds to check for unapproved changes.</span></span> <span data-ttu-id="a2126-156">Jeżeli inżyniera modyfikuje kodu krytycznego bez zatwierdzenia od zespołu recenzowania, zidentyfikowane i natychmiast stałej.</span><span class="sxs-lookup"><span data-stu-id="a2126-156">If an engineer modifies critical code without approval from the reviewing team, it is identified and fixed immediately.</span></span> <span data-ttu-id="a2126-157">Ten proces umożliwia aplikacji i konserwacji szczególnie wysoki poziom kontroli nad [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] kodu piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="a2126-157">This process enables the application and maintenance of an especially high level of scrutiny over [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] sandbox code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2126-158">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a2126-158">See Also</span></span>  
 [<span data-ttu-id="a2126-159">Zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="a2126-159">Security</span></span>](../../../docs/framework/wpf/security-wpf.md)  
 [<span data-ttu-id="a2126-160">WPF częściowej relacji zaufania zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="a2126-160">WPF Partial Trust Security</span></span>](../../../docs/framework/wpf/wpf-partial-trust-security.md)  
 [<span data-ttu-id="a2126-161">Strategia zabezpieczeń WPF - zabezpieczeń platformy</span><span class="sxs-lookup"><span data-stu-id="a2126-161">WPF Security Strategy - Platform Security</span></span>](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)  
 [<span data-ttu-id="a2126-162">Wiarygodne technologie komputerowe</span><span class="sxs-lookup"><span data-stu-id="a2126-162">Trustworthy Computing</span></span>](http://www.microsoft.com/mscorp/twc/default.mspx)  
 [<span data-ttu-id="a2126-163">Modelowanie zagrożeń aplikacji</span><span class="sxs-lookup"><span data-stu-id="a2126-163">Application Threat Modeling</span></span>](http://msdn.microsoft.com/security/securecode/threatmodeling/acetm/)  
 [<span data-ttu-id="a2126-164">Wytyczne dotyczące zabezpieczeń: .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="a2126-164">Security Guidelines: .NET Framework 2.0</span></span>](http://msdn.microsoft.com/library/default.asp?url=/library/dnpag2/html/PAGGuidelines0003.asp)