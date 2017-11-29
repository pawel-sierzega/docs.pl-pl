---
title: "107 — BookmarkResumptionRecord"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa2d37ed-2bfa-439b-89e8-a9354027f155
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 247a439dcbe566e74fd0157fbd92b9cb6c96e375
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="107----bookmarkresumptionrecord"></a><span data-ttu-id="5d953-102">107 — BookmarkResumptionRecord</span><span class="sxs-lookup"><span data-stu-id="5d953-102">107 -- BookmarkResumptionRecord</span></span>
## <a name="properties"></a><span data-ttu-id="5d953-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="5d953-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d953-104">Identyfikator</span><span class="sxs-lookup"><span data-stu-id="5d953-104">Id</span></span>|<span data-ttu-id="5d953-105">107</span><span class="sxs-lookup"><span data-stu-id="5d953-105">107</span></span>|  
|<span data-ttu-id="5d953-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="5d953-106">Keywords</span></span>|<span data-ttu-id="5d953-107">EndToEndMonitoring rozwiązywania problemów, HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="5d953-107">EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="5d953-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="5d953-108">Level</span></span>|<span data-ttu-id="5d953-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="5d953-109">Information</span></span>|  
|<span data-ttu-id="5d953-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="5d953-110">Channel</span></span>|<span data-ttu-id="5d953-111">Microsoft-Windows aplikacji Server aplikacje/analityczne</span><span class="sxs-lookup"><span data-stu-id="5d953-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5d953-112">Opis</span><span class="sxs-lookup"><span data-stu-id="5d953-112">Description</span></span>  
 <span data-ttu-id="5d953-113">To zdarzenie jest emitowane przez uczestnika śledzenia zdarzeń systemu Windows, gdy BookmarkResumptionRecord emituje wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="5d953-113">This event is emitted by the ETW tracking participant when a workflow instance emits a BookmarkResumptionRecord.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5d953-114">Komunikat</span><span class="sxs-lookup"><span data-stu-id="5d953-114">Message</span></span>  
 <span data-ttu-id="5d953-115">TrackRecord = BookmarkResumptionRecord, identyfikator wystąpienia = %1, RecordNumber = %2, EventTime = %3, nazwa = %4, SubInstanceID = %5, OwnerActivityName = %6, OwnerActivityId = %7 OwnerActivityInstanceId = %8, OwnerActivityTypeName = %9 adnotacje = % 10 ProfileName = % 11</span><span class="sxs-lookup"><span data-stu-id="5d953-115">TrackRecord = BookmarkResumptionRecord, InstanceID=%1, RecordNumber=%2,EventTime=%3, Name=%4, SubInstanceID=%5,  OwnerActivityName=%6, OwnerActivityId =%7, OwnerActivityInstanceId=%8, OwnerActivityTypeName=%9, Annotations=%10, ProfileName = %11</span></span>  
  
## <a name="details"></a><span data-ttu-id="5d953-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="5d953-116">Details</span></span>  
  
|<span data-ttu-id="5d953-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="5d953-117">Data Item Name</span></span>|<span data-ttu-id="5d953-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="5d953-118">Data Item Type</span></span>|<span data-ttu-id="5d953-119">Opis</span><span class="sxs-lookup"><span data-stu-id="5d953-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5d953-120">Identyfikator wystąpienia</span><span class="sxs-lookup"><span data-stu-id="5d953-120">InstanceId</span></span>|<span data-ttu-id="5d953-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="5d953-121">xs:GUID</span></span>|<span data-ttu-id="5d953-122">Identyfikator wystąpienia przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="5d953-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="5d953-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="5d953-123">RecordNumber</span></span>|<span data-ttu-id="5d953-124">xs:Long</span><span class="sxs-lookup"><span data-stu-id="5d953-124">xs:long</span></span>|<span data-ttu-id="5d953-125">Numer sekwencyjny emitowany rekordu</span><span class="sxs-lookup"><span data-stu-id="5d953-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="5d953-126">eventTime</span><span class="sxs-lookup"><span data-stu-id="5d953-126">EventTime</span></span>|<span data-ttu-id="5d953-127">xs: DateTime</span><span class="sxs-lookup"><span data-stu-id="5d953-127">xs:dateTime</span></span>|<span data-ttu-id="5d953-128">Godzina w formacie UTC podczas zdarzenia zostały wyemitowane</span><span class="sxs-lookup"><span data-stu-id="5d953-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="5d953-129">Nazwa</span><span class="sxs-lookup"><span data-stu-id="5d953-129">Name</span></span>|<span data-ttu-id="5d953-130">xs:String</span><span class="sxs-lookup"><span data-stu-id="5d953-130">xs:string</span></span>|<span data-ttu-id="5d953-131">Nazwa zakładki, która zostało wznowione</span><span class="sxs-lookup"><span data-stu-id="5d953-131">The name of the bookmark that was resumed</span></span>|  
|<span data-ttu-id="5d953-132">SubInstanceID</span><span class="sxs-lookup"><span data-stu-id="5d953-132">SubInstanceID</span></span>|<span data-ttu-id="5d953-133">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="5d953-133">xs:GUID</span></span>|<span data-ttu-id="5d953-134">Identyfikator zakresu zakładek</span><span class="sxs-lookup"><span data-stu-id="5d953-134">The id of the bookmark scope</span></span>|  
|<span data-ttu-id="5d953-135">Właściwość OwnerActivityName</span><span class="sxs-lookup"><span data-stu-id="5d953-135">OwnerActivityName</span></span>|<span data-ttu-id="5d953-136">xs:String</span><span class="sxs-lookup"><span data-stu-id="5d953-136">xs:string</span></span>|<span data-ttu-id="5d953-137">Nazwa działania zakładki</span><span class="sxs-lookup"><span data-stu-id="5d953-137">The name of the bookmark activity</span></span>|  
|<span data-ttu-id="5d953-138">OwnerActivityId</span><span class="sxs-lookup"><span data-stu-id="5d953-138">OwnerActivityId</span></span>|<span data-ttu-id="5d953-139">xs:String</span><span class="sxs-lookup"><span data-stu-id="5d953-139">xs:string</span></span>|<span data-ttu-id="5d953-140">Identyfikator działania zakładki</span><span class="sxs-lookup"><span data-stu-id="5d953-140">The id of the bookmark activity</span></span>|  
|<span data-ttu-id="5d953-141">OwnerActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="5d953-141">OwnerActivityInstanceId</span></span>|<span data-ttu-id="5d953-142">xs:String</span><span class="sxs-lookup"><span data-stu-id="5d953-142">xs:string</span></span>|<span data-ttu-id="5d953-143">Identyfikator wystąpienia działania zakładki</span><span class="sxs-lookup"><span data-stu-id="5d953-143">The instance id of the bookmark activity</span></span>|  
|<span data-ttu-id="5d953-144">OwnerActivityTypeName</span><span class="sxs-lookup"><span data-stu-id="5d953-144">OwnerActivityTypeName</span></span>|<span data-ttu-id="5d953-145">xs:String</span><span class="sxs-lookup"><span data-stu-id="5d953-145">xs:string</span></span>|<span data-ttu-id="5d953-146">Typ działania zakładki</span><span class="sxs-lookup"><span data-stu-id="5d953-146">The type of the bookmark activity</span></span>|  
|<span data-ttu-id="5d953-147">Adnotacje</span><span class="sxs-lookup"><span data-stu-id="5d953-147">Annotations</span></span>|<span data-ttu-id="5d953-148">xs:String</span><span class="sxs-lookup"><span data-stu-id="5d953-148">xs:string</span></span>|<span data-ttu-id="5d953-149">Adnotacje, które zostały dodane do tego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="5d953-149">The annotations that were added to this event.</span></span>  <span data-ttu-id="5d953-150">Wartości są przechowywane w elemencie xml w formacie \<elementy >\< nazwa elementu = "annotationName" type="System.String" > annotationValue\</elementu > \< /elementy >.</span><span class="sxs-lookup"><span data-stu-id="5d953-150">The values are stored in an xml element in the format \<items>\< item  name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span>  <span data-ttu-id="5d953-151">Jeśli nie określono bez adnotacji, a następnie ciąg zawiera \<elementów / >.</span><span class="sxs-lookup"><span data-stu-id="5d953-151">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="5d953-152">Rozmiar zdarzenia ETW jest ograniczona przez rozmiar bufora ETW lub max ładunku zdarzenia ETW.</span><span class="sxs-lookup"><span data-stu-id="5d953-152">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="5d953-153">Jeśli limity ETW przekracza rozmiar zdarzenia, a następnie zdarzenia został obcięty przez usunięcie adnotacje i zastąpienie wartości adnotacji z \<elementy >...  \< /elementy >.</span><span class="sxs-lookup"><span data-stu-id="5d953-153">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="5d953-154">ProfileName</span><span class="sxs-lookup"><span data-stu-id="5d953-154">ProfileName</span></span>|<span data-ttu-id="5d953-155">xs:String</span><span class="sxs-lookup"><span data-stu-id="5d953-155">xs:string</span></span>|<span data-ttu-id="5d953-156">Nazwa lub profilu śledzenia, które spowodowały to zdarzenie jest emitowany</span><span class="sxs-lookup"><span data-stu-id="5d953-156">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="5d953-157">HostReference</span><span class="sxs-lookup"><span data-stu-id="5d953-157">HostReference</span></span>|<span data-ttu-id="5d953-158">xs:String</span><span class="sxs-lookup"><span data-stu-id="5d953-158">xs:string</span></span>|<span data-ttu-id="5d953-159">Dla usług sieci web hostowanych w tym polu unikatowo identyfikuje usługę w hierarchii sieci web.</span><span class="sxs-lookup"><span data-stu-id="5d953-159">For web hosted services, this field uniquely identifies the service in the web hierarchy.</span></span>  <span data-ttu-id="5d953-160">Jego format jest zdefiniowany jako "Ścieżka wirtualna aplikacji Nazwa witryny sieci Web &#124; Ścieżka wirtualna usługi &#124; ServiceName "przykład:" Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService "</span><span class="sxs-lookup"><span data-stu-id="5d953-160">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName' Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'</span></span>|  
|<span data-ttu-id="5d953-161">Domeny aplikacji</span><span class="sxs-lookup"><span data-stu-id="5d953-161">AppDomain</span></span>|<span data-ttu-id="5d953-162">xs:String</span><span class="sxs-lookup"><span data-stu-id="5d953-162">xs:string</span></span>|<span data-ttu-id="5d953-163">Długość ciągu zwróconego przez AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5d953-163">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|