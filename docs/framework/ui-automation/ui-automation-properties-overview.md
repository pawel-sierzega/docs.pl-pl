---
title: "Przegląd właściwości automatyzacji interfejsu użytkownika"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, properties
- properties, UI Automation
ms.assetid: a6c31d7b-b33e-49b3-b5c1-31a345f9b7c8
caps.latest.revision: "17"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: a6fec422e235413bd76d86cdcb5a72a351bb3f97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-properties-overview"></a><span data-ttu-id="e27b7-102">Przegląd właściwości automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="e27b7-102">UI Automation Properties Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="e27b7-103">Ta dokumentacja jest przeznaczony dla deweloperów .NET Framework, które chcą korzystać zarządzanej [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="e27b7-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e27b7-104">Aby uzyskać najnowsze informacje o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], zobacz [interfejsu API systemu Windows automatyzacji: automatyzacji interfejsu użytkownika](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="e27b7-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="e27b7-105">Dostawcy automatyzacji interfejsu użytkownika udostępniają właściwości na [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elementów.</span><span class="sxs-lookup"><span data-stu-id="e27b7-105">UI Automation providers expose properties on [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements.</span></span> <span data-ttu-id="e27b7-106">Te właściwości umożliwić aplikacjom klienckim automatyzacji interfejsu użytkownika informacji o części [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], szczególnie kontrolki, w tym danych statycznych i dynamicznych.</span><span class="sxs-lookup"><span data-stu-id="e27b7-106">These properties enable UI Automation client applications to discover information about pieces of the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], especially controls, including both static and dynamic data.</span></span>  
  
 <span data-ttu-id="e27b7-107">W tej sekcji przedstawiono ogólne omówienie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] właściwości.</span><span class="sxs-lookup"><span data-stu-id="e27b7-107">This section gives a broad overview of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] properties.</span></span> <span data-ttu-id="e27b7-108">Więcej informacji znajduje się w następujących tematach:</span><span class="sxs-lookup"><span data-stu-id="e27b7-108">More specific information is given in the following topics:</span></span>  
  
-   [<span data-ttu-id="e27b7-109">Właściwości automatyzacji interfejsu użytkownika dla klientów</span><span class="sxs-lookup"><span data-stu-id="e27b7-109">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
  
-   [<span data-ttu-id="e27b7-110">Implementacja dostawcy automatyzacji interfejsu użytkownika po stronie serwera</span><span class="sxs-lookup"><span data-stu-id="e27b7-110">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)  
  
<a name="Property_Identifiers"></a>   
## <a name="property-identifiers"></a><span data-ttu-id="e27b7-111">Identyfikatory właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-111">Property Identifiers</span></span>  
 <span data-ttu-id="e27b7-112">Dla każdej właściwości jest identyfikowany przez numer i nazwę.</span><span class="sxs-lookup"><span data-stu-id="e27b7-112">Every property is identified by a number and a name.</span></span> <span data-ttu-id="e27b7-113">Nazwy właściwości są używane tylko w przypadku debugowania i diagnostyki.</span><span class="sxs-lookup"><span data-stu-id="e27b7-113">The names of properties are used only for debugging and diagnosis.</span></span> <span data-ttu-id="e27b7-114">Dostawcy używają numeryczne [!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)] do identyfikowania przychodzące żądania właściwości.</span><span class="sxs-lookup"><span data-stu-id="e27b7-114">Providers use the numeric [!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)] to identify incoming property requests.</span></span> <span data-ttu-id="e27b7-115">Aplikacje klienckie, jednak używać tylko <xref:System.Windows.Automation.AutomationProperty>, który hermetyzuje numeru i nazwy, aby zidentyfikować właściwości chcesz pobrać.</span><span class="sxs-lookup"><span data-stu-id="e27b7-115">Client applications, however, only use <xref:System.Windows.Automation.AutomationProperty>, which encapsulates the number and name, to identify properties they wish to retrieve.</span></span>  
  
 <span data-ttu-id="e27b7-116"><xref:System.Windows.Automation.AutomationProperty>obiekty reprezentujące określonej właściwości są dostępne jako pola w różnych klas.</span><span class="sxs-lookup"><span data-stu-id="e27b7-116"><xref:System.Windows.Automation.AutomationProperty> objects representing particular properties are available as fields in various classes.</span></span> <span data-ttu-id="e27b7-117">Ze względów bezpieczeństwa dostawców automatyzacji interfejsu użytkownika, należy uzyskać te obiekty z osobny zestaw klas, które są zawarte w Uiautomationtypes.dll.</span><span class="sxs-lookup"><span data-stu-id="e27b7-117">For security reasons, UI Automation providers obtain these objects from a separate set of classes that are contained in Uiautomationtypes.dll.</span></span>  
  
 <span data-ttu-id="e27b7-118">Poniższa tabela kategoryzuje właściwości według klasy, które zawierają <xref:System.Windows.Automation.AutomationProperty> [!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e27b7-118">The following table categorizes properties by the classes that contain the <xref:System.Windows.Automation.AutomationProperty>[!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)].</span></span>  
  
|<span data-ttu-id="e27b7-119">Typy właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-119">Kinds of properties</span></span>|<span data-ttu-id="e27b7-120">Klienci uzyskują identyfikatory z</span><span class="sxs-lookup"><span data-stu-id="e27b7-120">Clients get IDs from</span></span>|<span data-ttu-id="e27b7-121">Identyfikatory z pobrać dostawców</span><span class="sxs-lookup"><span data-stu-id="e27b7-121">Providers get IDs from</span></span>|  
|-------------------------|--------------------------|----------------------------|  
|<span data-ttu-id="e27b7-122">Właściwości wspólne dla wszystkich elementów (zobacz poniższy tabele)</span><span class="sxs-lookup"><span data-stu-id="e27b7-122">Properties common to all elements (see following tables)</span></span>|<xref:System.Windows.Automation.AutomationElement>|<xref:System.Windows.Automation.AutomationElementIdentifiers>|  
|<span data-ttu-id="e27b7-123">Pozycja okna dokującego.</span><span class="sxs-lookup"><span data-stu-id="e27b7-123">Position of a docking window</span></span>|<xref:System.Windows.Automation.DockPattern>|<xref:System.Windows.Automation.DockPatternIdentifiers>|  
|<span data-ttu-id="e27b7-124">Stan elementu, który można zwijać i rozwijać</span><span class="sxs-lookup"><span data-stu-id="e27b7-124">State of an element that can expand and collapse</span></span>|<xref:System.Windows.Automation.ExpandCollapsePattern>|<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers>|  
|<span data-ttu-id="e27b7-125">Właściwości elementu w siatce</span><span class="sxs-lookup"><span data-stu-id="e27b7-125">Properties of an item in a grid</span></span>|<xref:System.Windows.Automation.GridItemPattern>|<xref:System.Windows.Automation.GridItemPatternIdentifiers>|  
|<span data-ttu-id="e27b7-126">Właściwości siatki</span><span class="sxs-lookup"><span data-stu-id="e27b7-126">Properties of a grid</span></span>|<xref:System.Windows.Automation.GridPattern>|<xref:System.Windows.Automation.GridPatternIdentifiers>|  
|<span data-ttu-id="e27b7-127">Wyświetl bieżące i obsługiwane elementu, który ma wiele widoków</span><span class="sxs-lookup"><span data-stu-id="e27b7-127">Current and supported view of an element that has multiple views</span></span>|<xref:System.Windows.Automation.MultipleViewPattern>|<xref:System.Windows.Automation.MultipleViewPatternIdentifiers>|  
|<span data-ttu-id="e27b7-128">Właściwości elementu, który przechodzi przez zakres wartości, takich jak suwaka</span><span class="sxs-lookup"><span data-stu-id="e27b7-128">Properties of an element that moves over a range of values, such as a slider</span></span>|<xref:System.Windows.Automation.RangeValuePattern>|<xref:System.Windows.Automation.RangeValuePatternIdentifiers>|  
|<span data-ttu-id="e27b7-129">Właściwości przewijania okna</span><span class="sxs-lookup"><span data-stu-id="e27b7-129">Properties of a scrolling window</span></span>|<xref:System.Windows.Automation.ScrollPattern>|<xref:System.Windows.Automation.ScrollPatternIdentifiers>|  
|<span data-ttu-id="e27b7-130">Stan i kontener elementu, który można wybrać, jak listy</span><span class="sxs-lookup"><span data-stu-id="e27b7-130">Status and container of an item that can be selected, as in a list</span></span>|<xref:System.Windows.Automation.SelectionItemPattern>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers>|  
|<span data-ttu-id="e27b7-131">Właściwości formantu, który zawiera elementy zaznaczenia</span><span class="sxs-lookup"><span data-stu-id="e27b7-131">Properties of a control that contains selection items</span></span>|<xref:System.Windows.Automation.SelectionPattern>|<xref:System.Windows.Automation.SelectionPatternIdentifiers>|  
|<span data-ttu-id="e27b7-132">Nagłówki wierszy i kolumn elementu w tabeli</span><span class="sxs-lookup"><span data-stu-id="e27b7-132">Column and row headers of an item in a table</span></span>|<xref:System.Windows.Automation.TableItemPattern>|<xref:System.Windows.Automation.TableItemPatternIdentifiers>|  
|<span data-ttu-id="e27b7-133">Nagłówki kolumn i wierszy i orientację tabeli</span><span class="sxs-lookup"><span data-stu-id="e27b7-133">Column and row headers, and orientation, of a table</span></span>|<xref:System.Windows.Automation.TablePattern>|<xref:System.Windows.Automation.TablePatternIdentifiers>|  
|<span data-ttu-id="e27b7-134">Stan formantu przełącznika</span><span class="sxs-lookup"><span data-stu-id="e27b7-134">State of a toggle control</span></span>|<xref:System.Windows.Automation.TogglePattern>|<xref:System.Windows.Automation.TogglePatternIdentifiers>|  
|<span data-ttu-id="e27b7-135">Możliwości element, który można przenosić, obracać lub zmiany rozmiaru</span><span class="sxs-lookup"><span data-stu-id="e27b7-135">Capabilities of an element that can be moved, rotated, or resized</span></span>|<xref:System.Windows.Automation.TransformPattern>|<xref:System.Windows.Automation.TransformPatternIdentifiers>|  
|<span data-ttu-id="e27b7-136">Element, który ma wartość możliwości wartość i odczytu/zapisu</span><span class="sxs-lookup"><span data-stu-id="e27b7-136">Value and read/write capabilities of an element that has a value</span></span>|<xref:System.Windows.Automation.ValuePattern>|<xref:System.Windows.Automation.ValuePatternIdentifiers>|  
|<span data-ttu-id="e27b7-137">Możliwości i stan okna</span><span class="sxs-lookup"><span data-stu-id="e27b7-137">Capabilities and state of a window</span></span>|<xref:System.Windows.Automation.WindowPattern>|<xref:System.Windows.Automation.WindowPatternIdentifiers>|  
  
<a name="Properties_by_Category"></a>   
## <a name="properties-by-category"></a><span data-ttu-id="e27b7-138">Właściwości według kategorii</span><span class="sxs-lookup"><span data-stu-id="e27b7-138">Properties by Category</span></span>  
 <span data-ttu-id="e27b7-139">Poniższe tabele kategoryzowanie właściwości którego [!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)] znajdują się w <xref:System.Windows.Automation.AutomationElement> i <xref:System.Windows.Automation.AutomationElementIdentifiers>.</span><span class="sxs-lookup"><span data-stu-id="e27b7-139">The following tables categorize the properties whose [!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)] are found in <xref:System.Windows.Automation.AutomationElement> and <xref:System.Windows.Automation.AutomationElementIdentifiers>.</span></span> <span data-ttu-id="e27b7-140">Te właściwości są wspólne dla wszystkich kontrolek.</span><span class="sxs-lookup"><span data-stu-id="e27b7-140">These properties are common to all controls.</span></span> <span data-ttu-id="e27b7-141">Wszystkie z wyjątkiem kilku z nich mogą zostać statycznego okresu istnienia aplikacji dostawcy; właściwości najbardziej dynamiczne są skojarzone z wzorców formantu.</span><span class="sxs-lookup"><span data-stu-id="e27b7-141">All but a few of them are likely to be static over the lifetime of the provider application; most dynamic properties are associated with control patterns.</span></span>  
  
 <span data-ttu-id="e27b7-142">**Dostępu do właściwości** kolumna zawiera inne metody dostępu dla każdej właściwości w uzupełnieniu do <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> i <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="e27b7-142">The **Property Access** column lists any other accessors for each property, in addition to <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> and <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>.</span></span> <span data-ttu-id="e27b7-143">Aby uzyskać więcej informacji na temat pobierania właściwości w aplikacji klienta, zobacz [właściwości automatyzacji interfejsu użytkownika dla klientów](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="e27b7-143">For more information on getting properties in a client application, see [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e27b7-144">Aby uzyskać szczegółowe informacje o każdej właściwości, kliknij link w **dostępu do właściwości** kolumny.</span><span class="sxs-lookup"><span data-stu-id="e27b7-144">For specific information about each property, follow the link in the **Property Access** column.</span></span>  
  
### <a name="display-characteristics"></a><span data-ttu-id="e27b7-145">Wyświetl właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-145">Display Characteristics</span></span>  
  
|<span data-ttu-id="e27b7-146">Identyfikator właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-146">Property identifier</span></span>|<span data-ttu-id="e27b7-147">Dostęp do właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-147">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>|  
|<xref:System.Windows.Automation.AutomationElement.CultureProperty>|<span data-ttu-id="e27b7-148">n/d</span><span class="sxs-lookup"><span data-stu-id="e27b7-148">n/a</span></span>|  
|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsOffscreen%2A>|  
|<xref:System.Windows.Automation.AutomationElement.OrientationProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Orientation%2A>|  
  
### <a name="element-type"></a><span data-ttu-id="e27b7-149">Typ elementu</span><span class="sxs-lookup"><span data-stu-id="e27b7-149">Element Type</span></span>  
  
|<span data-ttu-id="e27b7-150">Identyfikator właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-150">Property identifier</span></span>|<span data-ttu-id="e27b7-151">Dostęp do właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-151">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsContentElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsControlElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LocalizedControlType%2A>|  
  
### <a name="identification"></a><span data-ttu-id="e27b7-152">Identyfikacja</span><span class="sxs-lookup"><span data-stu-id="e27b7-152">Identification</span></span>  
  
|<span data-ttu-id="e27b7-153">Identyfikator właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-153">Property identifier</span></span>|<span data-ttu-id="e27b7-154">Dostęp do właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-154">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AutomationId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClassNameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ClassName%2A>|  
|<xref:System.Windows.Automation.AutomationElement.FrameworkIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.FrameworkId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LabeledByProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LabeledBy%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ProcessIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ProcessId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.RuntimeIdProperty>|<xref:System.Windows.Automation.AutomationElement.GetRuntimeId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NativeWindowHandleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.NativeWindowHandle%2A>|  
  
### <a name="interaction"></a><span data-ttu-id="e27b7-155">Interakcji</span><span class="sxs-lookup"><span data-stu-id="e27b7-155">Interaction</span></span>  
  
|<span data-ttu-id="e27b7-156">Identyfikator właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-156">Property identifier</span></span>|<span data-ttu-id="e27b7-157">Dostęp do właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-157">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AcceleratorKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AccessKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>|<xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>|  
|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HasKeyboardFocus%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsEnabled%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsKeyboardFocusable%2A>|  
  
### <a name="support-for-patterns"></a><span data-ttu-id="e27b7-158">Obsługa wzorców</span><span class="sxs-lookup"><span data-stu-id="e27b7-158">Support for Patterns</span></span>  
  
|<span data-ttu-id="e27b7-159">Identyfikator właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-159">Property identifier</span></span>|<span data-ttu-id="e27b7-160">Dostęp do właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-160">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsDockPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsExpandCollapsePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsInvokePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsMultipleViewPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsRangeValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTableItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTablePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTogglePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTransformPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsWindowPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
  
### <a name="miscellaneous"></a><span data-ttu-id="e27b7-161">Inne</span><span class="sxs-lookup"><span data-stu-id="e27b7-161">Miscellaneous</span></span>  
  
|<span data-ttu-id="e27b7-162">Identyfikator właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-162">Property identifier</span></span>|<span data-ttu-id="e27b7-163">Dostęp do właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-163">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsRequiredForFormProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsRequiredForForm%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsPassword%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemStatusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemStatus%2A>|  
  
<a name="Localization"></a>   
## <a name="localization"></a><span data-ttu-id="e27b7-164">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="e27b7-164">Localization</span></span>  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="e27b7-165">dostawcy powinni przedstawić następujących właściwości w języku systemu operacyjnego:</span><span class="sxs-lookup"><span data-stu-id="e27b7-165"> providers should present the following properties in the language of the operating system:</span></span>  
  
-   <xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>  
  
-   <xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>  
  
-   <xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>  
  
-   <xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>  
  
-   <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>  
  
<a name="Properties_and_Events"></a>   
## <a name="properties-and-events"></a><span data-ttu-id="e27b7-166">Właściwości i zdarzenia</span><span class="sxs-lookup"><span data-stu-id="e27b7-166">Properties and Events</span></span>  
 <span data-ttu-id="e27b7-167">Ściśle związany się przy użyciu właściwości w [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] to pojęcia zdarzenia zmiany właściwości.</span><span class="sxs-lookup"><span data-stu-id="e27b7-167">Closely tied in with the properties in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is the concept of property-changed events.</span></span> <span data-ttu-id="e27b7-168">Dla właściwości dynamicznych aplikacja kliencka musi mieć możliwość wiedzieć, że wartość właściwości została zmieniona, tak, aby go zaktualizować pamięci podręcznej informacji lub reagowania na nowe informacje w inny sposób.</span><span class="sxs-lookup"><span data-stu-id="e27b7-168">For dynamic properties, the client application needs a way to know that a property value has changed, so that it can update its cache of information or react to the new information in some other way.</span></span>  
  
 <span data-ttu-id="e27b7-169">Dostawców wywoływanie zdarzeń, gdy coś [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] zmiany.</span><span class="sxs-lookup"><span data-stu-id="e27b7-169">Providers raise events when something in the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] changes.</span></span> <span data-ttu-id="e27b7-170">Na przykład jeśli pole wyboru jest zaznaczone lub wyczyszczone, zdarzenie zmiany właściwości jest wywoływane przez implementację dostawcy wzorca przełącznika.</span><span class="sxs-lookup"><span data-stu-id="e27b7-170">For example, if a check box is selected or cleared, a property-changed event is raised by the provider's implementation of the Toggle pattern.</span></span> <span data-ttu-id="e27b7-171">Dostawców może wywoływać zdarzenia selektywnie, w zależności od tego, czy wszyscy klienci są nasłuchiwanie zdarzeń lub nasłuchiwania dla określonych zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="e27b7-171">Providers can raise events selectively, depending on whether any clients are listening for events, or listening for specific events.</span></span>  
  
 <span data-ttu-id="e27b7-172">Nie wszystkie zmiany właściwości wywoływanie zdarzeń; to jest całkowicie zależy implementacja dostawcy automatyzacji interfejsu użytkownika dla elementu.</span><span class="sxs-lookup"><span data-stu-id="e27b7-172">Not all property changes raise events; that is entirely up to the implementation of the UI Automation provider for the element.</span></span> <span data-ttu-id="e27b7-173">Na przykład proxy standardowych dostawców dla pola listy nie wygenerował zdarzenie po <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> zmiany.</span><span class="sxs-lookup"><span data-stu-id="e27b7-173">For example, the standard proxy providers for list boxes do not raise an event when the <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> changes.</span></span> <span data-ttu-id="e27b7-174">W takim przypadku aplikacji zamiast musi nasłuchiwać <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>.</span><span class="sxs-lookup"><span data-stu-id="e27b7-174">In this case, the application instead must listen for an <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>.</span></span>  
  
 <span data-ttu-id="e27b7-175">Klienci nasłuchiwania zdarzeń Subskrybuj je.</span><span class="sxs-lookup"><span data-stu-id="e27b7-175">Clients listen for events by subscribing to them.</span></span> <span data-ttu-id="e27b7-176">Subskrybowanie zdarzeń oznacza tworzenia metody delegata, jaką może obsłużyć zdarzenia, a następnie przekazywanie metody [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] wraz z określonych zdarzeń, które zostaną omówione w jednej z tych metod.</span><span class="sxs-lookup"><span data-stu-id="e27b7-176">Subscribing to events means creating delegate methods that can handle the events, and then passing the methods to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] along with the specific events that will be dealt with in those methods.</span></span> <span data-ttu-id="e27b7-177">Dla zdarzenia zmiany właściwości w szczególności, klienci muszą implementować <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="e27b7-177">For property-changed events in particular, clients must implement <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e27b7-178">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e27b7-178">See Also</span></span>  
 [<span data-ttu-id="e27b7-179">Buforowanie w klientach automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="e27b7-179">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)  
 [<span data-ttu-id="e27b7-180">Właściwości automatyzacji interfejsu użytkownika dla klientów</span><span class="sxs-lookup"><span data-stu-id="e27b7-180">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [<span data-ttu-id="e27b7-181">Implementacja dostawcy automatyzacji interfejsu użytkownika po stronie serwera</span><span class="sxs-lookup"><span data-stu-id="e27b7-181">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)  
 [<span data-ttu-id="e27b7-182">Znajdź Element automatyzacji interfejsu użytkownika na podstawie warunku właściwości</span><span class="sxs-lookup"><span data-stu-id="e27b7-182">Find a UI Automation Element Based on a Property Condition</span></span>](../../../docs/framework/ui-automation/find-a-ui-automation-element-based-on-a-property-condition.md)  
 [<span data-ttu-id="e27b7-183">Zwracanie właściwości od dostawcy automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="e27b7-183">Return Properties from a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/return-properties-from-a-ui-automation-provider.md)  
 [<span data-ttu-id="e27b7-184">Wywoływanie zdarzeń od dostawcy automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="e27b7-184">Raise Events from a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/raise-events-from-a-ui-automation-provider.md)