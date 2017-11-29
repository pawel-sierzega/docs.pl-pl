---
title: "Korzystając ze zmiennych z zestaw reguł .NET Framework 3.5"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e9b5cc982aaad92258102b313d8fc19a9ff1521a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="using-variables-with-a-net-framework-35-ruleset"></a><span data-ttu-id="e13b3-102">Korzystając ze zmiennych z zestaw reguł .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="e13b3-102">Using Variables with a .NET Framework 3.5 Ruleset</span></span>
<span data-ttu-id="e13b3-103">Ten przykład przedstawia sposób tworzenia przepływu pracy korzystającego z <xref:System.Activities.Statements.Interop> działania integracji działań niestandardowych w [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] używającej zasad i reguł.</span><span class="sxs-lookup"><span data-stu-id="e13b3-103">This sample demonstrates how to create a workflow that uses the <xref:System.Activities.Statements.Interop> activity to integrate a custom activity written in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] that uses policy and rules.</span></span> <span data-ttu-id="e13b3-104">Przepływ pracy przekazuje dane do działania niestandardowego przez powiązanie zmiennych, właściwości zależności udostępnianych przez działania niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="e13b3-104">The workflow passes data to the custom activity by binding variables to the dependency properties exposed by the custom activity.</span></span>  
  
## <a name="sample-walkthrough"></a><span data-ttu-id="e13b3-105">Przykładowe wskazówki</span><span class="sxs-lookup"><span data-stu-id="e13b3-105">Sample walkthrough</span></span>  
  
#### <a name="to-examine-travelrulelibrary"></a><span data-ttu-id="e13b3-106">Aby sprawdzić TravelRuleLibrary</span><span class="sxs-lookup"><span data-stu-id="e13b3-106">To examine TravelRuleLibrary</span></span>  
  
1.  <span data-ttu-id="e13b3-107">Przy użyciu [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], otwórz plik rozwiązania InteropWith35RuleSet.sln.</span><span class="sxs-lookup"><span data-stu-id="e13b3-107">Using [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="e13b3-108">Otwórz TravelRuleSet.cs w Projektancie przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="e13b3-108">Open the TravelRuleSet.cs in the workflow designer.</span></span>  
  
     <span data-ttu-id="e13b3-109">Niestandardowe działania sekwencyjnego, który zawiera <xref:System.Workflow.Activities.PolicyActivity> jest wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="e13b3-109">A custom sequential activity that contains a <xref:System.Workflow.Activities.PolicyActivity> is displayed.</span></span>  
  
3.  <span data-ttu-id="e13b3-110">Kliknij dwukrotnie działanie zasad DiscountPolicy do sprawdzenia zasad.</span><span class="sxs-lookup"><span data-stu-id="e13b3-110">Double-click the DiscountPolicy policy activity to examine the rules.</span></span>  
  
     <span data-ttu-id="e13b3-111">Edytor reguł pojawia się, aby wyświetlić zasady.</span><span class="sxs-lookup"><span data-stu-id="e13b3-111">The Rules editor pops up to show the rules.</span></span>  
  
4.  <span data-ttu-id="e13b3-112">Kliknij prawym przyciskiem myszy `DiscountPolicy` i wybierz **kod widoku** opcję, aby sprawdzić kod obok kodu C# dla działania.</span><span class="sxs-lookup"><span data-stu-id="e13b3-112">Right click the `DiscountPolicy` and select the **View Code** option to examine the code beside C# code for the activity.</span></span>  
  
     <span data-ttu-id="e13b3-113">Sprawdź ustawienie właściwości zależności `DiscountLevel`.</span><span class="sxs-lookup"><span data-stu-id="e13b3-113">Observe the dependency property setting for `DiscountLevel`.</span></span> <span data-ttu-id="e13b3-114">Jest to równoważne argumentów [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e13b3-114">This is equivalent to arguments in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e13b3-115">argumenty, zobacz [zmiennych i argumenty](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="e13b3-115"> arguments, see [Variables and Arguments](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span></span>  
  
## <a name="interopwith35ruleset"></a><span data-ttu-id="e13b3-116">InteropWith35RuleSet</span><span class="sxs-lookup"><span data-stu-id="e13b3-116">InteropWith35RuleSet</span></span>  
 <span data-ttu-id="e13b3-117">Jest to projekt sekwencyjnego przepływu pracy, który używa <xref:System.Activities.Statements.Interop> działania integracji z niestandardowego zestawu reguł utworzonych w `TravelRuleLibrary` projektu.</span><span class="sxs-lookup"><span data-stu-id="e13b3-117">This is a sequential workflow project that uses the <xref:System.Activities.Statements.Interop> activity to integrate with the custom Rule set created in the `TravelRuleLibrary` project.</span></span> <span data-ttu-id="e13b3-118">Zmienne utworzone na najwyższym poziomie <xref:System.Activities.Statements.Sequence> działania.</span><span class="sxs-lookup"><span data-stu-id="e13b3-118">Variables are created on the top level <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="e13b3-119"><xref:System.Activities.Statements.Interop> To działanie służy do integracji z `TravelRuleSet` działania.</span><span class="sxs-lookup"><span data-stu-id="e13b3-119">The <xref:System.Activities.Statements.Interop> activity is used to integrate with the `TravelRuleSet` activity.</span></span> <span data-ttu-id="e13b3-120">Zmienne, które są zadeklarowane na <xref:System.Activities.Statements.Sequence> są używane w celu powiązania właściwości zależności.</span><span class="sxs-lookup"><span data-stu-id="e13b3-120">The variables that are declared on the <xref:System.Activities.Statements.Sequence> are used to bind to the dependency properties.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="e13b3-121">Aby użyć tego przykładu</span><span class="sxs-lookup"><span data-stu-id="e13b3-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="e13b3-122">Przy użyciu [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], otwórz plik rozwiązania InteropWith35RuleSet.sln.</span><span class="sxs-lookup"><span data-stu-id="e13b3-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="e13b3-123">Aby tworzyć rozwiązania, naciśnij kombinację klawiszy CTRL + SHIFT + B.</span><span class="sxs-lookup"><span data-stu-id="e13b3-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="e13b3-124">Aby uruchomić rozwiązanie, naciśnij klawisze CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="e13b3-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e13b3-125">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="e13b3-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e13b3-126">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="e13b3-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e13b3-127">Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="e13b3-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e13b3-128">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="e13b3-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`  
  
## <a name="see-also"></a><span data-ttu-id="e13b3-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e13b3-129">See Also</span></span>