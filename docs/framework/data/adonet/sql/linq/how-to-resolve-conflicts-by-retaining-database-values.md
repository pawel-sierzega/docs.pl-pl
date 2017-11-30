---
title: "Porady: Rozwiązywanie konfliktów, zachowując wartości bazy danych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1c2abc3f5ddd2daf9befc93e4469bd0e785fa6f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-resolve-conflicts-by-retaining-database-values"></a><span data-ttu-id="13283-102">Porady: Rozwiązywanie konfliktów, zachowując wartości bazy danych</span><span class="sxs-lookup"><span data-stu-id="13283-102">How to: Resolve Conflicts by Retaining Database Values</span></span>
<span data-ttu-id="13283-103">Uzgadnianie różnic pomiędzy wartościami oczekiwanymi i rzeczywistymi bazy danych, aby spróbować ponownie przesłać zmiany, umożliwia <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> do zachowania na wartości znajdujące się w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="13283-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> to retain the values found in the database.</span></span> <span data-ttu-id="13283-104">Bieżące wartości w modelu obiektów następnie zostaną zastąpione.</span><span class="sxs-lookup"><span data-stu-id="13283-104">The current values in the object model are then overwritten.</span></span> <span data-ttu-id="13283-105">Aby uzyskać więcej informacji, zobacz [optymistycznej współbieżności: omówienie](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="13283-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13283-106">We wszystkich przypadkach rekord klienta jest najpierw odświeżyć pobierając zaktualizowane dane z bazy danych.</span><span class="sxs-lookup"><span data-stu-id="13283-106">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="13283-107">Ta akcja gwarantuje, że następnej próbie aktualizacji zakończy się niepowodzeniem na tym samym kontrolach współbieżności.</span><span class="sxs-lookup"><span data-stu-id="13283-107">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13283-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="13283-108">Example</span></span>  
 <span data-ttu-id="13283-109">W tym scenariuszu <xref:System.Data.Linq.ChangeConflictException> wyjątek próba Użytkownik1 przesyłanie zmian, ponieważ Użytkownik2 w tym samym czasie została zmieniona kolumny Asystenta i działu.</span><span class="sxs-lookup"><span data-stu-id="13283-109">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="13283-110">W poniższej tabeli przedstawiono tę sytuację.</span><span class="sxs-lookup"><span data-stu-id="13283-110">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="13283-111">Menedżer</span><span class="sxs-lookup"><span data-stu-id="13283-111">Manager</span></span>|<span data-ttu-id="13283-112">Asystent</span><span class="sxs-lookup"><span data-stu-id="13283-112">Assistant</span></span>|<span data-ttu-id="13283-113">Dział</span><span class="sxs-lookup"><span data-stu-id="13283-113">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="13283-114">Oryginalny stan bazy danych po otrzymaniu kwerendy od użytkownika Użytkownik1 i Użytkownik2.</span><span class="sxs-lookup"><span data-stu-id="13283-114">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="13283-115">Alfreds</span><span class="sxs-lookup"><span data-stu-id="13283-115">Alfreds</span></span>|<span data-ttu-id="13283-116">Maria</span><span class="sxs-lookup"><span data-stu-id="13283-116">Maria</span></span>|<span data-ttu-id="13283-117">Sprzedaży</span><span class="sxs-lookup"><span data-stu-id="13283-117">Sales</span></span>|  
|<span data-ttu-id="13283-118">Użytkownik1 przygotowuje się do przesyłania tych zmian.</span><span class="sxs-lookup"><span data-stu-id="13283-118">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="13283-119">Alfred</span><span class="sxs-lookup"><span data-stu-id="13283-119">Alfred</span></span>||<span data-ttu-id="13283-120">Marketing</span><span class="sxs-lookup"><span data-stu-id="13283-120">Marketing</span></span>|  
|<span data-ttu-id="13283-121">UŻYTKOWNIK2 zostało już przesłane tych zmian.</span><span class="sxs-lookup"><span data-stu-id="13283-121">User2 has already submitted these changes.</span></span>||<span data-ttu-id="13283-122">Joanna</span><span class="sxs-lookup"><span data-stu-id="13283-122">Mary</span></span>|<span data-ttu-id="13283-123">Usługa</span><span class="sxs-lookup"><span data-stu-id="13283-123">Service</span></span>|  
  
 <span data-ttu-id="13283-124">Użytkownik1 decyduje o tym rozwiązać ten konflikt przez nowszą wartościami bazy danych zastąpić bieżące wartości w modelu obiektów.</span><span class="sxs-lookup"><span data-stu-id="13283-124">User1 decides to resolve this conflict by having the newer database values overwrite the current values in the object model.</span></span>  
  
 <span data-ttu-id="13283-125">Gdy Użytkownik1 rozwiązuje konflikt przy użyciu <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, wynik w bazie danych jest następujący w tabeli:</span><span class="sxs-lookup"><span data-stu-id="13283-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, the result in the database is as follows in the table:</span></span>  
  
||<span data-ttu-id="13283-126">Menedżer</span><span class="sxs-lookup"><span data-stu-id="13283-126">Manager</span></span>|<span data-ttu-id="13283-127">Asystent</span><span class="sxs-lookup"><span data-stu-id="13283-127">Assistant</span></span>|<span data-ttu-id="13283-128">Dział</span><span class="sxs-lookup"><span data-stu-id="13283-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="13283-129">Nowy stan po rozwiązywania konfliktów.</span><span class="sxs-lookup"><span data-stu-id="13283-129">New state after conflict resolution.</span></span>|<span data-ttu-id="13283-130">Alfreds</span><span class="sxs-lookup"><span data-stu-id="13283-130">Alfreds</span></span><br /><br /> <span data-ttu-id="13283-131">(oryginalny)</span><span class="sxs-lookup"><span data-stu-id="13283-131">(original)</span></span>|<span data-ttu-id="13283-132">Joanna</span><span class="sxs-lookup"><span data-stu-id="13283-132">Mary</span></span><br /><br /> <span data-ttu-id="13283-133">(z Użytkownik2)</span><span class="sxs-lookup"><span data-stu-id="13283-133">(from User2)</span></span>|<span data-ttu-id="13283-134">Usługa</span><span class="sxs-lookup"><span data-stu-id="13283-134">Service</span></span><br /><br /> <span data-ttu-id="13283-135">(z Użytkownik2)</span><span class="sxs-lookup"><span data-stu-id="13283-135">(from User2)</span></span>|  
  
 <span data-ttu-id="13283-136">Poniższy przykład kodu pokazuje, jak zastąpić bieżące wartości w modelu obiektów z wartościami bazy danych.</span><span class="sxs-lookup"><span data-stu-id="13283-136">The following example code shows how to overwrite current values in the object model with the database values.</span></span> <span data-ttu-id="13283-137">(Nie inspekcji lub niestandardową obsługę wystąpił konflikt elementu członkowskiego poszczególnych występuje.)</span><span class="sxs-lookup"><span data-stu-id="13283-137">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="13283-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="13283-138">See Also</span></span>  
 [<span data-ttu-id="13283-139">Porady: Zarządzanie konfliktów zmian</span><span class="sxs-lookup"><span data-stu-id="13283-139">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)