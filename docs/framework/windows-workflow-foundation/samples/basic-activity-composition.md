---
title: "Podstawowe działanie kompozycji"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6f1c94a276cf2e76d595a22c5c930614818bbf2b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="basic-activity-composition"></a><span data-ttu-id="84d71-102">Podstawowe działanie kompozycji</span><span class="sxs-lookup"><span data-stu-id="84d71-102">Basic Activity Composition</span></span>
<span data-ttu-id="84d71-103">W tym przykładzie pokazano, jak utworzyć niestandardowe działania i działania dostarczane przez system do tworzenia działań niestandardowych więcej.</span><span class="sxs-lookup"><span data-stu-id="84d71-103">This sample demonstrates how to compose custom activities and system-provided activities to build more custom activities.</span></span>  
  
 <span data-ttu-id="84d71-104">Przepływ pracy korzystający z działania przeglądu planuje listę pytania ankiety, a następnie wyprowadza odpowiedzi otrzymywanych.</span><span class="sxs-lookup"><span data-stu-id="84d71-104">The workflow using the Survey activity schedules the Survey with a list of questions, and then outputs the responses received.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="84d71-105">Szczegóły próbki</span><span class="sxs-lookup"><span data-stu-id="84d71-105">Sample Details</span></span>  
 <span data-ttu-id="84d71-106">W tym przykładzie używa trzech działań niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="84d71-106">This sample uses three custom activities.</span></span> <span data-ttu-id="84d71-107">`ReadLine`jest prostą <xref:System.Activities.NativeActivity> \<ciąg > tworzącą <xref:System.Activities.Bookmark> podczas zaplanowane, a następnie ustawia `Return` <xref:System.Activities.OutArgument%601> wartości, z którym <xref:System.Activities.Bookmark> zostanie wznowione.</span><span class="sxs-lookup"><span data-stu-id="84d71-107">`ReadLine` is a simple <xref:System.Activities.NativeActivity>\<string> that creates a <xref:System.Activities.Bookmark> when scheduled, and then sets the `Return`<xref:System.Activities.OutArgument%601> to the value with which the <xref:System.Activities.Bookmark> is resumed.</span></span> <span data-ttu-id="84d71-108">`Prompt`jest <xref:System.Activities.Activity%601> \<ciąg > pobierającej <xref:System.Activities.InArgument%601>< ciąg\> o nazwie `Text` i zwraca użytkowników odpowiedzi w `Result` <xref:System.Activities.OutArgument%601> \<ciąg >.</span><span class="sxs-lookup"><span data-stu-id="84d71-108">`Prompt` is an <xref:System.Activities.Activity%601>\<string> that takes an <xref:System.Activities.InArgument%601><string\> named `Text` and returns the users response in the `Result`<xref:System.Activities.OutArgument%601>\<string>.</span></span> <span data-ttu-id="84d71-109">`Prompt` Używa działania <xref:System.Activities.Statements.Sequence> i <xref:System.Activities.Statements.WriteLine> działania, które jest dostarczane jako część programu .NET Framework i zawiera też niestandardowa `ReadLine` działania dotyczące pobierania danych wejściowych użytkownika.</span><span class="sxs-lookup"><span data-stu-id="84d71-109">The `Prompt` activity uses the <xref:System.Activities.Statements.Sequence> and <xref:System.Activities.Statements.WriteLine> activities that ship as part of the .NET Framework, and also incorporates the custom `ReadLine` activity for getting user input.</span></span> <span data-ttu-id="84d71-110">Ostatnie niestandardowe działanie jest `Survey` działania.</span><span class="sxs-lookup"><span data-stu-id="84d71-110">The last custom activity is the `Survey` activity.</span></span> <span data-ttu-id="84d71-111">Jest <xref:System.Activities.Activity>< ICollection\<ciąg >>.</span><span class="sxs-lookup"><span data-stu-id="84d71-111">It is an <xref:System.Activities.Activity><ICollection\<string>>.</span></span>  <span data-ttu-id="84d71-112">To działanie ma <xref:System.Activities.InArgument%601>< IEnumerable < ciąg\>> o nazwie `Questions` i wypełnia `Result` limit argumentu z odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="84d71-112">This activity takes an <xref:System.Activities.InArgument%601><IEnumerable<string\>> named `Questions` and populates the `Result` out argument with the responses.</span></span> <span data-ttu-id="84d71-113">`Survey` Używa działania <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> i <xref:System.Activities.Statements.AddToCollection%601> z programu .NET Framework i wymaga `Prompt` działania udzielenia odpowiedzi na pytania ankiety i uzyskiwanie odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="84d71-113">The `Survey` activity uses <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> and <xref:System.Activities.Statements.AddToCollection%601> from the .NET Framework and employs the `Prompt` activity for asking the survey questions and getting responses.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="84d71-114">Aby skonfigurować, kompilacji, a następnie uruchom próbki</span><span class="sxs-lookup"><span data-stu-id="84d71-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="84d71-115">Otwórz **BasicActivityComposition.sln** przykładowe rozwiązanie w [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84d71-115">Open the **BasicActivityComposition.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="84d71-116">Tworzenie i uruchamianie rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="84d71-116">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="84d71-117">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="84d71-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="84d71-118">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="84d71-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="84d71-119">Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="84d71-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="84d71-120">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="84d71-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`  
  
## <a name="see-also"></a><span data-ttu-id="84d71-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="84d71-121">See Also</span></span>