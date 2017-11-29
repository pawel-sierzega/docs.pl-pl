---
title: 'Porady: wykazywanie stref czasowych na komputerze'
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f77afc8a0f2e6c110f4dc037c12ecc8b06908e60
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a><span data-ttu-id="696dc-102">Porady: wykazywanie stref czasowych na komputerze</span><span class="sxs-lookup"><span data-stu-id="696dc-102">How to: Enumerate time zones present on a computer</span></span>

<span data-ttu-id="696dc-103">Pomyślnie Praca z wyznaczonych strefy czasowej wymaga, aby dowiedzieć się, że strefa czasowa dostępna w systemie.</span><span class="sxs-lookup"><span data-stu-id="696dc-103">Successfully working with a designated time zone requires that information about that time zone be available to the system.</span></span> <span data-ttu-id="696dc-104">Systemów operacyjnych Windows XP i Windows Vista te informacje są przechowywane w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="696dc-104">The Windows XP and Windows Vista operating systems store this information in the registry.</span></span> <span data-ttu-id="696dc-105">Jednak mimo że duża liczba stref czasowych, które istnieją na całym świecie rejestru zawiera informacje o tylko podzestaw z nich.</span><span class="sxs-lookup"><span data-stu-id="696dc-105">However, although the total number of time zones that exist throughout the world is large, the registry contains information about only a subset of them.</span></span> <span data-ttu-id="696dc-106">Ponadto rejestr sam jest struktury dynamiczne, których zawartość mogą ulec zmianie zarówno zamierzonego i przypadkowe.</span><span class="sxs-lookup"><span data-stu-id="696dc-106">In addition, the registry itself is a dynamic structure whose contents are subject to both deliberate and accidental change.</span></span> <span data-ttu-id="696dc-107">W związku z tym aplikacja nie zawsze przyjęto, że daną strefę czasową zostało zdefiniowane i dostępne w systemie.</span><span class="sxs-lookup"><span data-stu-id="696dc-107">As a result, an application cannot always assume that a particular time zone is defined and available on a system.</span></span> <span data-ttu-id="696dc-108">Pierwszym krokiem w wielu aplikacjach, które korzystają z aplikacji informacje o strefie czasowej jest ustalenie, czy wymagane stref czasowych są dostępne w systemie lokalnym lub udzielenia lista stref czasowych, z którego można wybrać użytkownika.</span><span class="sxs-lookup"><span data-stu-id="696dc-108">The first step for many applications that use time zone information applications is to determine whether required time zones are available on the local system, or to give the user a list of time zones from which to select.</span></span> <span data-ttu-id="696dc-109">Wymaga to, że aplikacja wyliczanie stref czasowych zdefiniowanych w systemie lokalnym.</span><span class="sxs-lookup"><span data-stu-id="696dc-109">This requires that an application enumerate the time zones defined on a local system.</span></span>

> [!NOTE]
> <span data-ttu-id="696dc-110">Jeśli aplikacja zależy od obecności daną strefę czasową, która nie może być zdefiniowana w systemie lokalnym, aplikacja zapewnia jego obecność serializację i deserializację informacji o strefie czasowej.</span><span class="sxs-lookup"><span data-stu-id="696dc-110">If an application relies on the presence of a particular time zone that may not be defined on a local system, the application can ensure its presence by serializing and deserializing information about the time zone.</span></span> <span data-ttu-id="696dc-111">Następnie można dodać strefę czasową formant listy, aby go wybrać użytkowników aplikacji.</span><span class="sxs-lookup"><span data-stu-id="696dc-111">The time zone can then be added to a list control so that the application user can select it.</span></span> <span data-ttu-id="696dc-112">Aby uzyskać więcej informacji, zobacz [porady: zapisywanie stref czasowych w zasobie osadzonym](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) i [porady: Przywracanie stref czasowych z zasobu osadzonego](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="696dc-112">For details, see [How to: Save Time Zones to an Embedded Resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) and [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span></span>

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a><span data-ttu-id="696dc-113">Aby wyliczyć obecne w systemie lokalnym stref czasowych</span><span class="sxs-lookup"><span data-stu-id="696dc-113">To enumerate the time zones present on the local system</span></span>

1. <span data-ttu-id="696dc-114">Wywołanie <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="696dc-114">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="696dc-115">Metoda zwraca ogólnego <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Kolekcja <xref:System.TimeZoneInfo> obiektów.</span><span class="sxs-lookup"><span data-stu-id="696dc-115">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span> <span data-ttu-id="696dc-116">Wpisy w kolekcji są sortowane według ich <xref:System.TimeZoneInfo.DisplayName%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="696dc-116">The entries in the collection are sorted by their <xref:System.TimeZoneInfo.DisplayName%2A> property.</span></span> <span data-ttu-id="696dc-117">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="696dc-117">For example:</span></span>

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. <span data-ttu-id="696dc-118">Wyliczanie poszczególne <xref:System.TimeZoneInfo> obiektów z kolekcji przy użyciu `foreach` pętli (w języku C#) lub `For Each`...`Next`</span><span class="sxs-lookup"><span data-stu-id="696dc-118">Enumerate the individual <xref:System.TimeZoneInfo> objects in the collection by using a `foreach` loop (in C#) or a `For Each`…`Next`</span></span> <span data-ttu-id="696dc-119">Pętla (w języku Visual Basic), a niezbędne przetwarzania dla każdego obiektu.</span><span class="sxs-lookup"><span data-stu-id="696dc-119">loop (in Visual Basic), and perform any necessary processing on each object.</span></span> <span data-ttu-id="696dc-120">Na przykład następujący kod wylicza <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Kolekcja <xref:System.TimeZoneInfo> list nazwę wyświetlaną w każdej strefie czasowej w konsoli i obiektów zwróconych w kroku 1.</span><span class="sxs-lookup"><span data-stu-id="696dc-120">For example, the following code enumerates the <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects returned in step 1 and lists the display name of each time zone on the console.</span></span>

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a><span data-ttu-id="696dc-121">Do zaoferowania użytkownikowi lista stref czasowych obecne w systemie lokalnym</span><span class="sxs-lookup"><span data-stu-id="696dc-121">To present the user with a list of time zones present on the local system</span></span>

1. <span data-ttu-id="696dc-122">Wywołanie <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="696dc-122">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="696dc-123">Metoda zwraca ogólnego <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Kolekcja <xref:System.TimeZoneInfo> obiektów.</span><span class="sxs-lookup"><span data-stu-id="696dc-123">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span>

2. <span data-ttu-id="696dc-124">Kolekcja zwracana w kroku 1, aby przypisać `DataSource` właściwości systemu Windows forms lub ASP.NET formant listy.</span><span class="sxs-lookup"><span data-stu-id="696dc-124">Assign the collection returned in step 1 to the `DataSource` property of a Windows forms or ASP.NET list control.</span></span>

3. <span data-ttu-id="696dc-125">Pobrać <xref:System.TimeZoneInfo> obiektu, który został wybrany przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="696dc-125">Retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span>

<span data-ttu-id="696dc-126">W przykładzie przedstawiono ilustracja dla aplikacji systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="696dc-126">The example provides an illustration for a Windows application.</span></span>

## <a name="example"></a><span data-ttu-id="696dc-127">Przykład</span><span class="sxs-lookup"><span data-stu-id="696dc-127">Example</span></span>

<span data-ttu-id="696dc-128">W przykładzie uruchomiono aplikacji systemu Windows, który wyświetla stref czasowych zdefiniowanych w systemie, w polu listy.</span><span class="sxs-lookup"><span data-stu-id="696dc-128">The example starts a Windows application that displays the time zones defined on a system in a list box.</span></span> <span data-ttu-id="696dc-129">Przykład następnie wyświetla okno dialogowe, który zawiera wartość <xref:System.TimeZoneInfo.DisplayName%2A> właściwości obiektu strefy czasowej wybrane przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="696dc-129">The example then displays a dialog box that contains the value of the <xref:System.TimeZoneInfo.DisplayName%2A> property of the time zone object selected by the user.</span></span>

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

<span data-ttu-id="696dc-130">Najbardziej listy formantów (takie jak <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> lub <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> kontroli) można przypisać kolekcję zmiennych obiektu do ich `DataSource` tak długo, jak implementuje kolekcji właściwości <xref:System.Collections.IEnumerable> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="696dc-130">Most list controls (such as the <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> or <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> control) allow you to assign a collection of object variables to their `DataSource` property as long as that collection implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="696dc-131">(Ogólnego <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> klasy robi to.) Do wyświetlania pojedynczego obiektu w kolekcji, kontrolka wywołuje ten obiekt `ToString` metodę, aby wyodrębnić ciąg, który jest używany do reprezentowania obiektu.</span><span class="sxs-lookup"><span data-stu-id="696dc-131">(The generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class does this.) To display an individual object in the collection, the control calls that object's `ToString` method to extract the string that is used to represent the object.</span></span> <span data-ttu-id="696dc-132">W przypadku programu <xref:System.TimeZoneInfo> obiektów, `ToString` metoda zwraca <xref:System.TimeZoneInfo> nazwę wyświetlaną obiektu (wartość jego <xref:System.TimeZoneInfo.DisplayName%2A> właściwości).</span><span class="sxs-lookup"><span data-stu-id="696dc-132">In the case of <xref:System.TimeZoneInfo> objects, the `ToString` method returns the <xref:System.TimeZoneInfo> object's display name (the value of its <xref:System.TimeZoneInfo.DisplayName%2A> property).</span></span>

> [!NOTE]
> <span data-ttu-id="696dc-133">Ponieważ kontrolki listy wywołać obiektu `ToString` metody, można przypisać kolekcję <xref:System.TimeZoneInfo> obiekty do kontrolki, mają kontroli Wyświetl nazwę opisową dla każdego obiektu i pobrać <xref:System.TimeZoneInfo> obiektu, który został wybrany przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="696dc-133">Because list controls call an object's `ToString` method, you can assign a collection of <xref:System.TimeZoneInfo> objects to the control, have the control display a meaningful name for each object, and retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span> <span data-ttu-id="696dc-134">Eliminuje to potrzebę extract ciąg dla każdego obiektu w kolekcji, przypisz ciąg do kolekcji, która z kolei jest przypisany do formantu `DataSource` właściwości, użytkownik wybrał parametry, a następnie użyć tego ciągu do wyodrębnienia obiektu Ten opis.</span><span class="sxs-lookup"><span data-stu-id="696dc-134">This eliminates the need to extract a string for each object in the collection, assign the string to a collection that is in turn assigned to the control's `DataSource` property, retrieve the string the user has selected, and then use this string to extract the object that it describes.</span></span> 

## <a name="compiling-the-code"></a><span data-ttu-id="696dc-135">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="696dc-135">Compiling the code</span></span>

<span data-ttu-id="696dc-136">Ten przykład wymaga:</span><span class="sxs-lookup"><span data-stu-id="696dc-136">This example requires:</span></span>

* <span data-ttu-id="696dc-137">Odwołania do System.Core.dll dodania do projektu.</span><span class="sxs-lookup"><span data-stu-id="696dc-137">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="696dc-138">Czy następujących przestrzeni nazw można importować:</span><span class="sxs-lookup"><span data-stu-id="696dc-138">That the following namespaces be imported:</span></span>

  <span data-ttu-id="696dc-139"><xref:System>(w kodzie języka C#)</span><span class="sxs-lookup"><span data-stu-id="696dc-139"><xref:System> (in C# code)</span></span>

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a><span data-ttu-id="696dc-140">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="696dc-140">See also</span></span>

<span data-ttu-id="696dc-141">[Daty, godziny i strefy czasowe](../../../docs/standard/datetime/index.md)
[porady: zapisywanie stref czasowych w zasobie osadzonym](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[porady: Przywracanie stref czasowych z zasobu osadzonego](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span><span class="sxs-lookup"><span data-stu-id="696dc-141">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span></span>