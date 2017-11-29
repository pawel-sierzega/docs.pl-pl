---
title: Podstawowy element TransactionScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e22b76a-76de-43b4-9be7-7a86ed3d5a44
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d4f9d9e966a0a6d8fa48d195b17438b3d78b32a9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="basic-transactionscope"></a><span data-ttu-id="cb99b-102">Podstawowy element TransactionScope</span><span class="sxs-lookup"><span data-stu-id="cb99b-102">Basic TransactionScope</span></span>
<span data-ttu-id="cb99b-103">W tym przykładzie składa się z czterech scenariuszy uruchomienia przedstawiająca sposób zagnieździć <xref:System.Activities.Statements.TransactionScope> wystąpień.</span><span class="sxs-lookup"><span data-stu-id="cb99b-103">This sample consists of four scenarios that run showing how to nest <xref:System.Activities.Statements.TransactionScope> instances.</span></span> <span data-ttu-id="cb99b-104">Pierwszy scenariusz przedstawia zagnieżdżania 3 działania firm, które autor nie zna konstrukcji.</span><span class="sxs-lookup"><span data-stu-id="cb99b-104">The first scenario shows nesting a 3rd party activity of which the author has no knowledge of the construction.</span></span> <span data-ttu-id="cb99b-105">Scenariusze drugiego i trzeciego pokazują, jak są przestrzegane limity czasu i końcowe scenariuszu pokazano <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A> ustawienie.</span><span class="sxs-lookup"><span data-stu-id="cb99b-105">The second and third scenarios show how time-outs are respected and the final scenario shows the <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A> setting.</span></span>  
  
## <a name="nesting-of-transactionscopeactivity"></a><span data-ttu-id="cb99b-106">Zagnieżdżanie działania TransactionScopeActivity</span><span class="sxs-lookup"><span data-stu-id="cb99b-106">Nesting of TransactionScopeActivity</span></span>  
 <span data-ttu-id="cb99b-107">Przepływ pracy dla pierwszego scenariusza składa się z dwóch sekwencji <xref:System.Activities.Statements.WriteLine> działań i <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="cb99b-107">The workflow for the first scenario consists of a sequence of two <xref:System.Activities.Statements.WriteLine> activities and a <xref:System.Activities.Statements.TransactionScope>.</span></span> <span data-ttu-id="cb99b-108">Treść <xref:System.Activities.Statements.TransactionScope> sekwencja dwóch więcej <xref:System.Activities.Statements.WriteLine> działań, niestandardowe działanie, które wyświetla lokalny identyfikator transakcji i innej firmy działania.</span><span class="sxs-lookup"><span data-stu-id="cb99b-108">The body of the <xref:System.Activities.Statements.TransactionScope> is a sequence of two more <xref:System.Activities.Statements.WriteLine> activities, a custom activity that prints the local identifier of the transaction and a third party activity.</span></span> <span data-ttu-id="cb99b-109">Działanie innych firm `TransactionScopeTest` zawiera <xref:System.Activities.Statements.TransactionScope> mimo, że autor przepływu pracy nie ma możliwości wiedzy.</span><span class="sxs-lookup"><span data-stu-id="cb99b-109">The third party activity `TransactionScopeTest` contains a <xref:System.Activities.Statements.TransactionScope> although the workflow author has no way of knowing.</span></span> <span data-ttu-id="cb99b-110">W tym scenariuszu pokazano, że <xref:System.Activities.Statements.TransactionScope> działania mogą być zagnieżdżone.</span><span class="sxs-lookup"><span data-stu-id="cb99b-110">This scenario shows that <xref:System.Activities.Statements.TransactionScope> activities can be nested.</span></span>  
  
## <a name="time-outs"></a><span data-ttu-id="cb99b-111">Limity czasu</span><span class="sxs-lookup"><span data-stu-id="cb99b-111">Time-Outs</span></span>  
 <span data-ttu-id="cb99b-112">Drugi scenariusz przepływu pracy jest niemal identyczna jako pierwszy.</span><span class="sxs-lookup"><span data-stu-id="cb99b-112">The workflow for the second scenario is nearly identical to the first.</span></span> <span data-ttu-id="cb99b-113">`TransactionScopeTest` Zostało zastąpione <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="cb99b-113">The `TransactionScopeTest` has been replaced with a <xref:System.Activities.Statements.TransactionScope>.</span></span> <span data-ttu-id="cb99b-114">Treść <xref:System.Activities.Statements.TransactionScope> opóźnienia pięciu sekund i limit czasu dla transakcji jest ustawiony na dwóch sekund.</span><span class="sxs-lookup"><span data-stu-id="cb99b-114">The body of the <xref:System.Activities.Statements.TransactionScope> is a five-second delay and the time-out for the transaction is set to two seconds.</span></span> <span data-ttu-id="cb99b-115">Limit czasu dla zewnętrznego <xref:System.Activities.Statements.TransactionScope> jest ustawiony na 10 sekund.</span><span class="sxs-lookup"><span data-stu-id="cb99b-115">The time-out for the outer <xref:System.Activities.Statements.TransactionScope> is set to 10 seconds.</span></span> <span data-ttu-id="cb99b-116">Warto zauważyć, że wzięty pod uwagę najmniejszą limitu czasu w zakresie transakcji upłynie limit czasu.</span><span class="sxs-lookup"><span data-stu-id="cb99b-116">Note that the smallest time-out in scope is respected and the transaction times out.</span></span>  
  
 <span data-ttu-id="cb99b-117">Przepływ pracy dla trzeci scenariusz jest niemal identyczna z scenariusz dwa.</span><span class="sxs-lookup"><span data-stu-id="cb99b-117">The workflow for the third scenario is nearly identical to scenario two.</span></span> <span data-ttu-id="cb99b-118">Działanie opóźnienie została przeniesiona z treści wewnętrzny <xref:System.Activities.Statements.TransactionScope> natychmiast po nim w sekwencji, który jest treści zewnętrznego <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="cb99b-118">The delay activity has been moved from the body of the inner <xref:System.Activities.Statements.TransactionScope> to immediately after it in the sequence that is the body of the outer <xref:System.Activities.Statements.TransactionScope>.</span></span> <span data-ttu-id="cb99b-119">Transakcja nadal upłynie limit czasu, ale ponieważ dwa drugie limit wewnętrzny <xref:System.Activities.Statements.TransactionScope> nie ma zastosowania.</span><span class="sxs-lookup"><span data-stu-id="cb99b-119">The transaction still times out but because the two second time-out of the inner <xref:System.Activities.Statements.TransactionScope> no longer applies.</span></span> <span data-ttu-id="cb99b-120">Czasy transakcji out na 10 sekund po zewnętrznego <xref:System.Activities.Statements.TransactionScope> Przekroczono limit czasu.</span><span class="sxs-lookup"><span data-stu-id="cb99b-120">The transaction times out at 10 seconds when the outer <xref:System.Activities.Statements.TransactionScope> time-out is exceeded.</span></span>  
  
## <a name="aborting-on-transaction-failure"></a><span data-ttu-id="cb99b-121">Trwa przerywanie niepowodzeń transakcji</span><span class="sxs-lookup"><span data-stu-id="cb99b-121">Aborting on Transaction Failure</span></span>  
 <span data-ttu-id="cb99b-122">Ten przepływ pracy jest podobny do scenariusza trzy, z wyjątkiem limitów czasu zostały zastąpione przez <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="cb99b-122">This workflow is similar to scenario three except the time-outs have been replaced by the <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A> property.</span></span> <span data-ttu-id="cb99b-123">Należy pamiętać, że flagi wszystkie wewnętrzne elementy podrzędne, jeśli ustawiona, muszą być zgodne zewnętrznego <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="cb99b-123">Note that the flags of all inner children, if set, must match the outer <xref:System.Activities.Statements.TransactionScope>.</span></span> <span data-ttu-id="cb99b-124">W tym scenariuszu nie i po otwarciu przepływu pracy jest zgłaszany wyjątek.</span><span class="sxs-lookup"><span data-stu-id="cb99b-124">In this scenario, they do not and an exception is thrown when the workflow opens.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="cb99b-125">Aby uruchomić przykładowy</span><span class="sxs-lookup"><span data-stu-id="cb99b-125">To run the sample</span></span>  
  
1.  <span data-ttu-id="cb99b-126">Otwórz rozwiązanie BasicTransactionScopeSample.sln w [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb99b-126">Open the BasicTransactionScopeSample.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="cb99b-127">Skompiluj rozwiązanie, naciśnij kombinację klawiszy CTRL + SHIFT + B lub wybierz **Kompiluj rozwiązanie** z **kompilacji** menu.</span><span class="sxs-lookup"><span data-stu-id="cb99b-127">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="cb99b-128">Gdy kompilacja zakończyła się pomyślnie, naciśnij klawisz F5 lub wybierz **Rozpocznij debugowanie** z **debugowania** menu.</span><span class="sxs-lookup"><span data-stu-id="cb99b-128">Once the build has succeeded, press F5 or select **Start Debugging** from the **Debug** menu.</span></span> <span data-ttu-id="cb99b-129">Można również nacisnąć klawisze CTRL + F5 lub wybierz **uruchomić bez debugowania** z **debugowania** menu, aby uruchomić bez debugowania.</span><span class="sxs-lookup"><span data-stu-id="cb99b-129">Alternatively you can press CTRL+F5 or select **Start Without Debugging** from the **Debug** menu to run without debugging.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cb99b-130">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="cb99b-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cb99b-131">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="cb99b-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cb99b-132">Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="cb99b-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cb99b-133">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="cb99b-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\BasicTransactionScope`  
  
## <a name="see-also"></a><span data-ttu-id="cb99b-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cb99b-134">See Also</span></span>