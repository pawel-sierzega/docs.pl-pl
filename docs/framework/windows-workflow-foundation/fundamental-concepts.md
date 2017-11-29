---
title: "Windows podstawowych koncepcji przepływu pracy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e930e80-5060-45d2-8a7a-95c0690105d4
caps.latest.revision: "27"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9f13979c7d44b06a820e3524081457e1afef2b28
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="fundamental-windows-workflow-concepts"></a><span data-ttu-id="420f3-102">Windows podstawowych koncepcji przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="420f3-102">Fundamental Windows Workflow Concepts</span></span>
<span data-ttu-id="420f3-103">Programowanie przepływu pracy w [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] używa pojęcia, które mogą być nowe dla niektórych deweloperów.</span><span class="sxs-lookup"><span data-stu-id="420f3-103">Workflow development in the [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] uses concepts that may be new to some developers.</span></span> <span data-ttu-id="420f3-104">W tym temacie opisano niektóre z pojęć i ich implementacji.</span><span class="sxs-lookup"><span data-stu-id="420f3-104">This topic describes some of the concepts and how they are implemented.</span></span>  
  
## <a name="workflows-and-activities"></a><span data-ttu-id="420f3-105">Przepływy pracy i działań</span><span class="sxs-lookup"><span data-stu-id="420f3-105">Workflows and Activities</span></span>  
 <span data-ttu-id="420f3-106">Przepływ pracy jest strukturalnych kolekcję akcji, która modele procesu.</span><span class="sxs-lookup"><span data-stu-id="420f3-106">A workflow is a structured collection of actions that models a process.</span></span> <span data-ttu-id="420f3-107">Każdego działania w przepływie pracy jest modelowana jako działania.</span><span class="sxs-lookup"><span data-stu-id="420f3-107">Each action in the workflow is modeled as an activity.</span></span> <span data-ttu-id="420f3-108">Host współdziała z przepływu pracy przy użyciu <xref:System.Activities.WorkflowInvoker> do wywoływania przepływu pracy, tak jakby był on metodę, <xref:System.Activities.WorkflowApplication> jawne kontrolować wykonywanie wystąpienia przepływu pracy pojedynczego, i <xref:System.ServiceModel.WorkflowServiceHost> oparta na komunikatach interakcji w wielu wystąpieniach scenariusze.</span><span class="sxs-lookup"><span data-stu-id="420f3-108">A host interacts with a workflow by using <xref:System.Activities.WorkflowInvoker> for invoking a workflow as if it were a method,  <xref:System.Activities.WorkflowApplication> for explicit control over the execution of a single workflow instance, and <xref:System.ServiceModel.WorkflowServiceHost> for message-based interactions in multi-instance scenarios.</span></span> <span data-ttu-id="420f3-109">Ponieważ kroki przepływu pracy są zdefiniowane jako hierarchię działań, działanie najwyższego poziomu w hierarchii można powiedzieć do definiowania sam przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="420f3-109">Because steps of the workflow are defined as a hierarchy of activities, the topmost activity in the hierarchy can be said to define the workflow itself.</span></span> <span data-ttu-id="420f3-110">Ten model hierarchii ma miejsce jawne `SequentialWorkflow` i `StateMachineWorkflow` klasy z poprzedniej wersji.</span><span class="sxs-lookup"><span data-stu-id="420f3-110">This hierarchy model takes the place of the explicit `SequentialWorkflow` and `StateMachineWorkflow` classes from previous versions.</span></span> <span data-ttu-id="420f3-111">Działania sami są tworzone jako kolekcje innych działań (przy użyciu <xref:System.Activities.Activity> klasy jako podstawa, zazwyczaj definiowane przy użyciu języka XAML) lub są tworzone za pomocą niestandardowych <xref:System.Activities.CodeActivity> klasy, którego można użyć środowiska uruchomieniowego dla dostępu do danych lub za pomocą <xref:System.Activities.NativeActivity> klasy, która przedstawia szerokość określony przez autora działania środowiska uruchomieniowego przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="420f3-111">Activities themselves are developed as collections of other activities (using the <xref:System.Activities.Activity> class as a base, usually defined by using XAML) or are custom created by using the <xref:System.Activities.CodeActivity> class, which can use the runtime for data access, or by using the <xref:System.Activities.NativeActivity> class, which exposes the breadth of the workflow runtime to the activity author.</span></span> <span data-ttu-id="420f3-112">Działań utworzonych za pomocą <xref:System.Activities.CodeActivity> i <xref:System.Activities.NativeActivity> są tworzone za pomocą zgodne CLR języków, takich jak C#.</span><span class="sxs-lookup"><span data-stu-id="420f3-112">Activities developed by using <xref:System.Activities.CodeActivity> and <xref:System.Activities.NativeActivity> are created by using CLR-compliant languages such as C#.</span></span>  
  
## <a name="activity-data-model"></a><span data-ttu-id="420f3-113">Model danych działania</span><span class="sxs-lookup"><span data-stu-id="420f3-113">Activity Data Model</span></span>  
 <span data-ttu-id="420f3-114">Działania przechowywać i udostępniać dane przy użyciu typów pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="420f3-114">Activities store and share data by using the types shown in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="420f3-115">Zmienna</span><span class="sxs-lookup"><span data-stu-id="420f3-115">Variable</span></span>|<span data-ttu-id="420f3-116">Przechowuje dane w działaniu.</span><span class="sxs-lookup"><span data-stu-id="420f3-116">Stores data in an activity.</span></span>|  
|<span data-ttu-id="420f3-117">Argument</span><span class="sxs-lookup"><span data-stu-id="420f3-117">Argument</span></span>|<span data-ttu-id="420f3-118">Przenosi dane do i z działania.</span><span class="sxs-lookup"><span data-stu-id="420f3-118">Moves data into and out of an activity.</span></span>|  
|<span data-ttu-id="420f3-119">Wyrażenie</span><span class="sxs-lookup"><span data-stu-id="420f3-119">Expression</span></span>|<span data-ttu-id="420f3-120">Działanie z podwyższonym poziomem uprawnień, zwracając wartość używana w powiązaniach argumentu.</span><span class="sxs-lookup"><span data-stu-id="420f3-120">An activity with an elevated return value used in argument bindings.</span></span>|  
  
## <a name="workflow-runtime"></a><span data-ttu-id="420f3-121">Środowiska uruchomieniowego przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="420f3-121">Workflow Runtime</span></span>  
 <span data-ttu-id="420f3-122">Środowisko wykonawcze przepływu pracy jest środowisko, w którym wykonania przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="420f3-122">The workflow runtime is the environment in which workflows execute.</span></span> <span data-ttu-id="420f3-123"><xref:System.Activities.WorkflowInvoker>to najprostszy sposób wykonania przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="420f3-123"><xref:System.Activities.WorkflowInvoker> is the simplest way to execute a workflow.</span></span> <span data-ttu-id="420f3-124">Host używa <xref:System.Activities.WorkflowInvoker> dla następujących:</span><span class="sxs-lookup"><span data-stu-id="420f3-124">The host uses <xref:System.Activities.WorkflowInvoker> for the following:</span></span>  
  
-   <span data-ttu-id="420f3-125">Aby wywołać synchronicznie przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="420f3-125">To synchronously invoke a workflow.</span></span>  
  
-   <span data-ttu-id="420f3-126">Podaj dane wejściowe lub pobrać dane wyjściowe z przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="420f3-126">To provide input to, or retrieve output from a workflow.</span></span>  
  
-   <span data-ttu-id="420f3-127">Aby dodać rozszerzenia do użycia przez działania.</span><span class="sxs-lookup"><span data-stu-id="420f3-127">To add extensions to be used by activities.</span></span>  
  
 <span data-ttu-id="420f3-128"><xref:System.Activities.ActivityInstance>to proxy wątkowo, który hostów można użyć do interakcji z środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="420f3-128"><xref:System.Activities.ActivityInstance> is the thread-safe proxy that hosts can use to interact with the runtime.</span></span> <span data-ttu-id="420f3-129">Host używa <xref:System.Activities.ActivityInstance> dla następujących:</span><span class="sxs-lookup"><span data-stu-id="420f3-129">The host uses <xref:System.Activities.ActivityInstance> for the following:</span></span>  
  
-   <span data-ttu-id="420f3-130">Uzyskanie wystąpienia przez go utworzyć lub załadować go ze sklepu wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="420f3-130">To acquire an instance by creating it or loading it from an instance store.</span></span>  
  
-   <span data-ttu-id="420f3-131">Aby otrzymywać powiadomienia wystąpienia zdarzeń cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="420f3-131">To be notified of instance life-cycle events.</span></span>  
  
-   <span data-ttu-id="420f3-132">Aby kontrolować wykonywanie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="420f3-132">To control workflow execution.</span></span>  
  
-   <span data-ttu-id="420f3-133">Podaj dane wejściowe lub pobrać dane wyjściowe z przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="420f3-133">To provide input to, or retrieve output from a workflow.</span></span>  
  
-   <span data-ttu-id="420f3-134">Sygnał kontynuacji przepływu pracy i wartości przekazywane do przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="420f3-134">To signal a workflow continuation and pass values into the workflow.</span></span>  
  
-   <span data-ttu-id="420f3-135">Aby zachować dane przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="420f3-135">To persist workflow data.</span></span>  
  
-   <span data-ttu-id="420f3-136">Aby dodać rozszerzenia do użycia przez działania.</span><span class="sxs-lookup"><span data-stu-id="420f3-136">To add extensions to be used by activities.</span></span>  
  
 <span data-ttu-id="420f3-137">Działania uzyskania dostępu do środowiska uruchomieniowego przepływu pracy przy użyciu odpowiednich <xref:System.Activities.ActivityContext> pochodnej klasy, takich jak <xref:System.Activities.NativeActivityContext> lub <xref:System.Activities.CodeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="420f3-137">Activities gain access to the workflow runtime environment by using the appropriate <xref:System.Activities.ActivityContext> derived class, such as <xref:System.Activities.NativeActivityContext> or <xref:System.Activities.CodeActivityContext>.</span></span> <span data-ttu-id="420f3-138">Używają to rozpoznawania argumentów i zmienne, do planowania działań podrzędnych i do innych celów.</span><span class="sxs-lookup"><span data-stu-id="420f3-138">They use this for resolving arguments and variables, for scheduling child activities, and for many other purposes.</span></span>  
  
## <a name="services"></a><span data-ttu-id="420f3-139">Usługi</span><span class="sxs-lookup"><span data-stu-id="420f3-139">Services</span></span>  
 <span data-ttu-id="420f3-140">Przepływy pracy umożliwiają fizyczne do wdrożenia i uzyskiwać dostęp do usług luźno połączonych, przy użyciu działań komunikacji.</span><span class="sxs-lookup"><span data-stu-id="420f3-140">Workflows provide a natural way to implement and access loosely-coupled services, using messaging activities.</span></span> <span data-ttu-id="420f3-141">Działania obsługi komunikatów są tworzone [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] i to podstawowy mechanizm używany do pobierania danych do i z przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="420f3-141">Messaging activities are built on [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] and are the primary mechanism used to get data into and out of a workflow.</span></span> <span data-ttu-id="420f3-142">Można utworzyć działania obsługi wiadomości ze sobą w celu modelowania dowolnego rodzaju wymiany komunikatów, które mają.</span><span class="sxs-lookup"><span data-stu-id="420f3-142">You can compose messaging activities together to model any kind of message exchange pattern you wish.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="420f3-143">zobacz [wiadomości działania](../../../docs/framework/wcf/feature-details/messaging-activities.md).</span><span class="sxs-lookup"><span data-stu-id="420f3-143"> see [Messaging Activities](../../../docs/framework/wcf/feature-details/messaging-activities.md).</span></span> <span data-ttu-id="420f3-144">Usługi przepływu pracy są obsługiwane przy użyciu <xref:System.ServiceModel.Activities.WorkflowServiceHost> klasy.</span><span class="sxs-lookup"><span data-stu-id="420f3-144">Workflow services are hosted using the <xref:System.ServiceModel.Activities.WorkflowServiceHost> class.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="420f3-145">[Hosting przepływu pracy usługi — omówienie](../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md).</span><span class="sxs-lookup"><span data-stu-id="420f3-145"> [Hosting Workflow Services Overview](../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="420f3-146">przepływ pracy usług zobacz [usług przepływu pracy](../../../docs/framework/wcf/feature-details/workflow-services.md)</span><span class="sxs-lookup"><span data-stu-id="420f3-146"> workflow services see [Workflow Services](../../../docs/framework/wcf/feature-details/workflow-services.md)</span></span>  
  
## <a name="persistence-unloading-and-long-running-workflows"></a><span data-ttu-id="420f3-147">Przepływy pracy zwalniania i długotrwałe trwałości,</span><span class="sxs-lookup"><span data-stu-id="420f3-147">Persistence, Unloading, and Long-Running Workflows</span></span>  
 <span data-ttu-id="420f3-148">Windows Workflow upraszcza tworzenie programów czynnych długotrwałe zapewniając:</span><span class="sxs-lookup"><span data-stu-id="420f3-148">Windows Workflow simplifies the authoring of long-running reactive programs by providing:</span></span>  
  
-   <span data-ttu-id="420f3-149">Działania, które uzyskują dostęp do zewnętrznych danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="420f3-149">Activities that access external input.</span></span>  
  
-   <span data-ttu-id="420f3-150">Możliwość tworzenia <xref:System.Activities.Bookmark> obiektów, które można wznowić przez odbiornik hosta.</span><span class="sxs-lookup"><span data-stu-id="420f3-150">The ability to create <xref:System.Activities.Bookmark> objects that can be resumed by a host listener.</span></span>  
  
-   <span data-ttu-id="420f3-151">Zdolność do utrwalenia danych przepływu pracy i zwolnienia przepływu pracy, Załaduj ponownie i Uaktywnij ponownie przepływu pracy w odpowiedzi na wznowienie <xref:System.Activities.Bookmark> obiektów w szczególności przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="420f3-151">The ability to persist a workflow’s data and unload the workflow, and then reload and reactivate the workflow in response to the resumption of <xref:System.Activities.Bookmark> objects in a particular workflow.</span></span>  
  
 <span data-ttu-id="420f3-152">Przepływ pracy stale wykonuje działania, dopóki nie ma żadnych więcej działań do wykonania lub aż wszystkie aktualnie wykonywanego działania oczekuje na dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="420f3-152">A workflow continuously executes activities until there are no more activities to execute or until all currently executing activities are waiting for input.</span></span> <span data-ttu-id="420f3-153">W tym ostatnim stanie przepływu pracy jest w stanie bezczynności.</span><span class="sxs-lookup"><span data-stu-id="420f3-153">In this latter state, the workflow is idle.</span></span> <span data-ttu-id="420f3-154">Często hosta można zwolnić przepływów pracy, które przeszły bezczynności i załadować ponownie je, aby kontynuować wykonywanie, gdy komunikat dociera.</span><span class="sxs-lookup"><span data-stu-id="420f3-154">It is common for a host to unload workflows that have gone idle and to reload them to continue execution when a message arrives.</span></span> <span data-ttu-id="420f3-155"><xref:System.ServiceModel.Activities.WorkflowServiceHost>zapewnia funkcje dla tej funkcji i zawiera zasady rozszerzonego, zwolnienia.</span><span class="sxs-lookup"><span data-stu-id="420f3-155"><xref:System.ServiceModel.Activities.WorkflowServiceHost> provides functionality for this feature and provides an extensible unload policy.</span></span> <span data-ttu-id="420f3-156">Dla bloków wykonywania korzystających z danych o stanie volatile lub innych danych, która nie może zostać utrwalona, działanie może wskazywać na hoście że nie należy go utrwalone przy użyciu <xref:System.Activities.NoPersistHandle>.</span><span class="sxs-lookup"><span data-stu-id="420f3-156">For blocks of execution that use volatile state data or other data that cannot be persisted, an activity can indicate to a host that it should not be persisted by using the <xref:System.Activities.NoPersistHandle>.</span></span> <span data-ttu-id="420f3-157">Przepływ pracy można również jawnie utrwalić danych jego średni magazynu trwałego za pomocą <xref:System.Activities.Statements.Persist> działania.</span><span class="sxs-lookup"><span data-stu-id="420f3-157">A workflow can also explicitly persist its data to a durable storage medium by using the <xref:System.Activities.Statements.Persist> activity.</span></span>