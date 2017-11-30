---
title: Wbudowane konfiguracji
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 34e85c9b-088d-4347-816c-0f77cb73ef2f
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7dc11c19025393ffb1ce8e10cbfa637f38a867fd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="built-in-configuration"></a><span data-ttu-id="faae7-102">Wbudowane konfiguracji</span><span class="sxs-lookup"><span data-stu-id="faae7-102">Built-in Configuration</span></span>
<span data-ttu-id="faae7-103">W przykładzie pokazano, używania i konfiguracji w magazynie wystąpień przepływu pracy SQL.</span><span class="sxs-lookup"><span data-stu-id="faae7-103">This sample demonstrates the use and configuration of the SQL workflow instance store.</span></span> <span data-ttu-id="faae7-104">W magazynie wystąpień przepływu pracy SQL jest implementacją SQL na podstawie wystąpienia magazynu.</span><span class="sxs-lookup"><span data-stu-id="faae7-104">The SQL workflow instance store is a SQL-based implementation of an instance store.</span></span> <span data-ttu-id="faae7-105">Umożliwia on do zapisywania i ładowania stanu z bazy danych programu SQL Server lub SQL Server Express i wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="faae7-105">It allows an instance to save and load its state to and from a SQL Server or SQL Server Express database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="faae7-106">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="faae7-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="faae7-107">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="faae7-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="faae7-108">Jeśli ten katalog nie istnieje, przejdź do (stronę pobierania), aby pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="faae7-108">If this directory does not exist, go to (download page) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="faae7-109">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="faae7-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\BuiltInConfiguration`  
  
## <a name="sample-details"></a><span data-ttu-id="faae7-110">Szczegóły próbki</span><span class="sxs-lookup"><span data-stu-id="faae7-110">Sample Details</span></span>  
 <span data-ttu-id="faae7-111">W tym przykładzie składa się z przepływu pracy, który implementuje usługi zliczania.</span><span class="sxs-lookup"><span data-stu-id="faae7-111">This sample consists of a workflow that implements a counting service.</span></span> <span data-ttu-id="faae7-112">Po wywołaniu metody uruchamiania usługi, usługi liczby z zakresu od 0 do 59.</span><span class="sxs-lookup"><span data-stu-id="faae7-112">Once the service's start method is invoked, the service counts from 0 to 59.</span></span> <span data-ttu-id="faae7-113">Licznik jest zwiększany co 2 sekundy.</span><span class="sxs-lookup"><span data-stu-id="faae7-113">The counter is incremented once every 2 seconds.</span></span> <span data-ttu-id="faae7-114">Po każdej liczby utrzymuje przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="faae7-114">After each count, the workflow persists.</span></span>  
  
 <span data-ttu-id="faae7-115">Zliczania przepływu pracy jest samodzielnie hostowana przez hosta usługi przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="faae7-115">The counting workflow is self-hosted by a workflow service host.</span></span> <span data-ttu-id="faae7-116">Program `Main` metoda tworzy wystąpienie hosta usługi przepływu pracy obsługującego zliczania przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="faae7-116">The program's `Main` method creates an instance of the workflow service host that hosts the counting workflow.</span></span> <span data-ttu-id="faae7-117">Definiuje punkty końcowe, zgodnie z którymi zliczania przepływu pracy jest osiągalna.</span><span class="sxs-lookup"><span data-stu-id="faae7-117">It defines the endpoints under which the counting workflow can be reached.</span></span> <span data-ttu-id="faae7-118">Po wykonaniu tej definiuje SQL zachowanie magazynu wystąpienia przepływu pracy, który służy do konfigurowania w magazynie wystąpień przepływu pracy programu SQL.</span><span class="sxs-lookup"><span data-stu-id="faae7-118">After that, it defines a SQL workflow instance store behavior, which is used to configure the SQL workflow instance store.</span></span> <span data-ttu-id="faae7-119">Następnie program tworzy klienta, który wywołuje metodę start zliczania przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="faae7-119">Next, the program creates a client that calls the start method of the counting workflow.</span></span>  
  
 <span data-ttu-id="faae7-120">Po uruchomieniu programu licznik uruchamia się automatycznie zliczania.</span><span class="sxs-lookup"><span data-stu-id="faae7-120">Once the program is started, the counter automatically starts counting.</span></span> <span data-ttu-id="faae7-121">Należy pamiętać, że może zająć kilka sekund, aby załadować wystąpienie i skonfigurować Magazyn wystąpienia przepływu pracy programu SQL.</span><span class="sxs-lookup"><span data-stu-id="faae7-121">Note that it might take a few seconds to load the instance and configure the SQL workflow instance store.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="faae7-122">w magazynie wystąpień przepływu pracy, zobacz [magazyn wystąpienia przepływu pracy SQL](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="faae7-122"> the workflow instance store, see [SQL Workflow Instance Store](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span></span>  
  
 <span data-ttu-id="faae7-123">Próbka składa się z dwóch części:</span><span class="sxs-lookup"><span data-stu-id="faae7-123">The sample consists of two parts:</span></span>  
  
1.  <span data-ttu-id="faae7-124">Pokazuje InstanceStore1 jak <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> jest konfigurowana przy użyciu kodu C# (zobacz Program.cs).</span><span class="sxs-lookup"><span data-stu-id="faae7-124">InstanceStore1 shows how <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> is configured using C# code (see Program.cs).</span></span>  
  
2.  <span data-ttu-id="faae7-125">Pokazuje InstanceStore2 jak <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> jest skonfigurowany za pomocą XML (zobacz App.config).</span><span class="sxs-lookup"><span data-stu-id="faae7-125">InstanceStore2 shows how <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> is configured using XML (see App.config).</span></span>  
  
 <span data-ttu-id="faae7-126">Można konfigurować zachowanie magazynu wystąpienia przepływu pracy SQL są następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="faae7-126">The following settings are available to configure the SQL Workflow Instance Store behavior:</span></span>  
  
-   <span data-ttu-id="faae7-127">Ustaw `HostLockRenewalPeriod`.</span><span class="sxs-lookup"><span data-stu-id="faae7-127">Set the `HostLockRenewalPeriod`.</span></span> <span data-ttu-id="faae7-128">Teraz Określa interwał, z którym host odnawia blokady własność wystąpień, jego uruchomienie.</span><span class="sxs-lookup"><span data-stu-id="faae7-128">This time defines the interval with which the host renews the ownership lock of the instances it runs.</span></span> <span data-ttu-id="faae7-129">Informacje blokady są przechowywane w magazynie wystąpień.</span><span class="sxs-lookup"><span data-stu-id="faae7-129">The lock information is stored in the Instance Store.</span></span> <span data-ttu-id="faae7-130">Jeśli nie zostanie odnowiony własności dla dwóch odstępach czasu zdefiniowanych w `HostLockRenewalPeriod`, wystąpienie jest uznawany za porzucone.</span><span class="sxs-lookup"><span data-stu-id="faae7-130">If the ownership is not renewed for two of the intervals defined in `HostLockRenewalPeriod`, the instance is considered abandoned.</span></span> <span data-ttu-id="faae7-131">Jeśli inny <xref:System.ServiceModel.Activities.WorkflowServiceHost> jest uruchomiona na tym samym przepływie pracy i połączony z tym samym magazynie wystąpienia (albo w tym samym komputerze lub na innym komputerze), odzyskuje tego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="faae7-131">If another <xref:System.ServiceModel.Activities.WorkflowServiceHost> is running the same workflow and connected to the same instance store (either on the same computer or a different computer), it recovers that instance.</span></span> <span data-ttu-id="faae7-132">(Wystąpienie odzyskiwania jest poza zakresem dla tego przykładu).</span><span class="sxs-lookup"><span data-stu-id="faae7-132">(Instance Recovery is out of scope for this sample.)</span></span>  
  
-   <span data-ttu-id="faae7-133">Ustaw `RunnableInstancesDetectionPeriod`.</span><span class="sxs-lookup"><span data-stu-id="faae7-133">Set the `RunnableInstancesDetectionPeriod`.</span></span> <span data-ttu-id="faae7-134">Ten okres Określa interwał, w którym host sonduje dla wystąpień, które stały się do uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="faae7-134">This period defines the interval in which the host polls for instances that have become runnable.</span></span> <span data-ttu-id="faae7-135">Wystąpień, mogą stać się do uruchomienia, jeśli wystąpienia któregokolwiek z następujących zdarzeń:</span><span class="sxs-lookup"><span data-stu-id="faae7-135">Instances may become runnable if any of the following events occur:</span></span>  
  
    -   <span data-ttu-id="faae7-136">Trwałe czasomierza (<xref:System.Activities.Statements.Delay>) wygaśnie.</span><span class="sxs-lookup"><span data-stu-id="faae7-136">A Durable Timer (<xref:System.Activities.Statements.Delay>) expires.</span></span>  
  
    -   <span data-ttu-id="faae7-137">Chybienia hosta innego jego `HostLockRenewal` pulsu (na przykład z powodu awarii komputera) i wystąpienia są odzyskiwane.</span><span class="sxs-lookup"><span data-stu-id="faae7-137">Another host misses its `HostLockRenewal` heartbeat (for example, due to a computer crash) and the instance is recovered.</span></span>  
  
-   <span data-ttu-id="faae7-138">Ustaw `InstanceCompletionAction`.</span><span class="sxs-lookup"><span data-stu-id="faae7-138">Set the `InstanceCompletionAction`.</span></span> <span data-ttu-id="faae7-139">Tę właściwość, jeśli ustawiono `DeleteNothing`, wystąpień przechowuje ukończone w magazynie wystąpień; w przypadku ustawienia `DeleteAll`, wystąpienia zostaną usunięte z magazynu po zakończeniu.</span><span class="sxs-lookup"><span data-stu-id="faae7-139">This property, if set to `DeleteNothing`, keeps completed instances in the Instance Store; if set to `DeleteAll`, instances are deleted from the store upon completion.</span></span> <span data-ttu-id="faae7-140">Należy pamiętać, że</span><span class="sxs-lookup"><span data-stu-id="faae7-140">Note that</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="faae7-141">Przerywanie hosta, naciskając klawisz ENTER, zanim liczenie została zakończona, nie zostanie zakończone wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="faae7-141">Terminating the host by pressing ENTER before the counting has completed does not complete the workflow instance.</span></span>  
  
-   <span data-ttu-id="faae7-142">Ustaw `InstanceLockedExceptionAction`.</span><span class="sxs-lookup"><span data-stu-id="faae7-142">Set the `InstanceLockedExceptionAction`.</span></span> <span data-ttu-id="faae7-143">To ustawienie określa, co hosta zrobić, jeśli chce się załadować wystąpienia, który jest zablokowany przez innego hosta.</span><span class="sxs-lookup"><span data-stu-id="faae7-143">This setting defines what a host should do if it wants to load an instance that is locked by another host.</span></span> <span data-ttu-id="faae7-144">Istnieją następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="faae7-144">The following options exist:</span></span>  
  
    -   <span data-ttu-id="faae7-145">Jeśli ustawiono `NoRetry`: ponów obciążenia i nie zwraca `InstanceLockedException` do hosta.</span><span class="sxs-lookup"><span data-stu-id="faae7-145">If set to `NoRetry`: Do not retry the load and return an `InstanceLockedException` to the host.</span></span>  
  
    -   <span data-ttu-id="faae7-146">Jeśli ustawiono `BasicRetry`: podejmować dalsze próby załadowania wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="faae7-146">If set to `BasicRetry`: Keep retrying to load the instance.</span></span> <span data-ttu-id="faae7-147">Ponowne próby są planowane zgodnie z prosty algorytm liniową (na przykład, spróbuj co 5 sekund).</span><span class="sxs-lookup"><span data-stu-id="faae7-147">The retries are scheduled according to a simple linear algorithm (for example, retry every 5 seconds).</span></span>  
  
    -   <span data-ttu-id="faae7-148">Jeśli ustawiono `AggressiveRetry`: podejmować dalsze próby załadowania wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="faae7-148">If set to `AggressiveRetry`: Keep retrying to load the instance.</span></span> <span data-ttu-id="faae7-149">Ponowne próby są planowane zgodnie agresywne wykładniczego wycofywania algorytmu.</span><span class="sxs-lookup"><span data-stu-id="faae7-149">The retries are scheduled according to an aggressive exponential back-off algorithm.</span></span>  
  
-   <span data-ttu-id="faae7-150">Ustawianie opcji kodowania.</span><span class="sxs-lookup"><span data-stu-id="faae7-150">Set the Encoding option.</span></span> <span data-ttu-id="faae7-151">To ustawienie określa, jak stan wystąpienia jest przechowywany w magazynie wystąpień przepływu pracy programu SQL.</span><span class="sxs-lookup"><span data-stu-id="faae7-151">This setting defines how the instance state is stored in the SQL Workflow Instance Store.</span></span> <span data-ttu-id="faae7-152">Istnieją następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="faae7-152">The following options exist:</span></span>  
  
    -   <span data-ttu-id="faae7-153">Stan wystąpienia jest skompresowany, przy użyciu algorytmu kompresji GZip.</span><span class="sxs-lookup"><span data-stu-id="faae7-153">The instance state is compressed using the GZip compression algorithm.</span></span>  
  
    -   <span data-ttu-id="faae7-154">Stan wystąpienia nie jest kompresowany.</span><span class="sxs-lookup"><span data-stu-id="faae7-154">The instance state is not compressed.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="faae7-155">Aby użyć tego przykładu</span><span class="sxs-lookup"><span data-stu-id="faae7-155">To use this sample</span></span>  
  
1.  <span data-ttu-id="faae7-156">Otwórz [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] wiersz polecenia jako Administrator, jeśli są dostępne uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="faae7-156">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt as an Administrator if permissions are available.</span></span>  
  
2.  <span data-ttu-id="faae7-157">Przejdź do katalogu próbki (\WF\Basic\Persistence\BuiltInConfiguration\CS), a następnie uruchom CreateInstanceStore.cmd.</span><span class="sxs-lookup"><span data-stu-id="faae7-157">Navigate to the sample directory (\WF\Basic\Persistence\BuiltInConfiguration\CS) and run CreateInstanceStore.cmd.</span></span>  
  
3.  <span data-ttu-id="faae7-158">Jeśli uprawnienia administratora nie są dostępne, logowania programu SQL Server Utwórz.</span><span class="sxs-lookup"><span data-stu-id="faae7-158">If Administrator privileges are not available, Create SQL Server login.</span></span> <span data-ttu-id="faae7-159">Przejdź do `Security`, **logowania**.</span><span class="sxs-lookup"><span data-stu-id="faae7-159">Go to `Security`, **Logins**.</span></span> <span data-ttu-id="faae7-160">Kliknij prawym przyciskiem myszy **logowania** i Utwórz nowe dane logowania.</span><span class="sxs-lookup"><span data-stu-id="faae7-160">Right-click **Logins** and create a new login.</span></span>  
  
4.  <span data-ttu-id="faae7-161">Dodaj listę kontroli dostępu użytkownika do roli programu SQL.</span><span class="sxs-lookup"><span data-stu-id="faae7-161">Add your ACL user to SQL role.</span></span> <span data-ttu-id="faae7-162">Otwórz **baz danych**, **InstanceStore**, **zabezpieczeń**.</span><span class="sxs-lookup"><span data-stu-id="faae7-162">Open **Databases**, **InstanceStore**, **Security**.</span></span> <span data-ttu-id="faae7-163">Kliknij prawym przyciskiem myszy **użytkowników** i wybierz **nowych użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="faae7-163">Right-click **Users** and select **New users**.</span></span> <span data-ttu-id="faae7-164">Ustaw **nazwa logowania** użytkownikowi utworzony w poprzednim kroku.</span><span class="sxs-lookup"><span data-stu-id="faae7-164">Set the **Login name** to the user created in the previous step.</span></span> <span data-ttu-id="faae7-165">Dodaj użytkownika do członkostwo roli bazy danych **System.Activities.DurableInstancing.InstanceStoreUsers** (i inne).</span><span class="sxs-lookup"><span data-stu-id="faae7-165">Add the user to the Database role membership **System.Activities.DurableInstancing.InstanceStoreUsers** (and others).</span></span> <span data-ttu-id="faae7-166">Należy pamiętać, że użytkownik może istnieć już (na przykład użytkownika dbo).</span><span class="sxs-lookup"><span data-stu-id="faae7-166">Note that the user might exist already (for example, user dbo).</span></span>  
  
5.  <span data-ttu-id="faae7-167">Otwórz plik InstanceStore.sln w [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] i Skompiluj rozwiązanie, naciskając klawisze CTRL + SHIFT + B.</span><span class="sxs-lookup"><span data-stu-id="faae7-167">Open the InstanceStore.sln file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="faae7-168">W [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], przejdź do katalogu bin\debug odpowiednie próbki (\WF\Basic\Persistence\BuiltInConfiguration\cs\InstanceStore(1 or 2)\bin\debug), kliknij prawym przyciskiem myszy InstanceStore.exe i wybierz **Uruchom jako administrator**.</span><span class="sxs-lookup"><span data-stu-id="faae7-168">In [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], navigate to the sample’s appropriate bin\debug directory (\WF\Basic\Persistence\BuiltInConfiguration\cs\InstanceStore(1 or 2)\bin\debug), right click InstanceStore.exe and select **Run as administrator**.</span></span> <span data-ttu-id="faae7-169">W tym przykładzie należy uruchomić z uprawnieniami administracyjnymi, ponieważ spowoduje to otwarcie odbiornika kanałów.</span><span class="sxs-lookup"><span data-stu-id="faae7-169">This sample must be run with administrative privileges because it opens a channel listener.</span></span>  
  
7.  <span data-ttu-id="faae7-170">Jeśli w bazie danych innych niż lokalnej instalacji programu SQL Server Express został utworzony w magazynie wystąpień, należy zaktualizować parametry połączenia bazy danych (`const string ConnectionString` w pliku Program.cs projektu InstanceStore1 i `connectionString` atrybutu w pliku App.config programu Projekt InstanceStore2) w przykładowych i skompiluj ponownie próbki.</span><span class="sxs-lookup"><span data-stu-id="faae7-170">If you created the instance store in a database other than a local installation of SQL Server Express you must update the database connection string (`const string ConnectionString` in Program.cs of the InstanceStore1 project, and the `connectionString` attribute in App.config of the InstanceStore2 project) in the sample and recompile the sample.</span></span>  
  
#### <a name="to-verify-the-sample-is-running-correctly"></a><span data-ttu-id="faae7-171">Aby zweryfikować próbki działa poprawnie</span><span class="sxs-lookup"><span data-stu-id="faae7-171">To verify the sample is running correctly</span></span>  
  
1.  <span data-ttu-id="faae7-172">Próbki jest uruchomiona, uruchom program SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="faae7-172">While the sample is running, start SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="faae7-173">W **Eksplorator obiektów**, wybierz pozycję **baz danych**, **InstanceStore**, **tabel**, a następnie  **System.Activities.DurableInstancing.InstanceTable**.</span><span class="sxs-lookup"><span data-stu-id="faae7-173">In the **Object Explorer**, select **Databases**, **InstanceStore**, **Tables**, and then **System.Activities.DurableInstancing.InstanceTable**.</span></span>  
  
3.  <span data-ttu-id="faae7-174">Kliknij prawym przyciskiem myszy **InstanceTable** i wybierz **zaznacz 1000 pierwszych wierszy**.</span><span class="sxs-lookup"><span data-stu-id="faae7-174">Right click **InstanceTable** and select **Select Top 1000 Rows**.</span></span>  
  
4.  <span data-ttu-id="faae7-175">Sprawdź, czy znajduje się nowy wpis, a **okresu ważności blokady** zmienia co 5 sekund (kliknij przycisk paska zadań **Execute** przycisk, aby odświeżyć zapytanie).</span><span class="sxs-lookup"><span data-stu-id="faae7-175">Observe that there is a new entry and that the **Lock Expiration** changes every 5 seconds, (click the taskbar’s **Execute** button to refresh the query).</span></span> <span data-ttu-id="faae7-176">Jest to konsekwencją ustawienie **okres odnawiania blokady hosta** do 5.</span><span class="sxs-lookup"><span data-stu-id="faae7-176">This is a consequence of setting the **Host Lock Renewal Period** to 5.</span></span>  
  
5.  <span data-ttu-id="faae7-177">Obserwować po zakończeniu inwentaryzacji, że wpis w tabeli wystąpienie zostanie usunięty.</span><span class="sxs-lookup"><span data-stu-id="faae7-177">Observe after the counting completes, that the entry in the instance table is removed.</span></span> <span data-ttu-id="faae7-178">Jest to konsekwencją ustawienie **wystąpienia ukończenia akcji** do **DeleteAll**.</span><span class="sxs-lookup"><span data-stu-id="faae7-178">This is a consequence of setting **Instance Completion Action** to **DeleteAll**.</span></span>  
  
6.  <span data-ttu-id="faae7-179">Naciśnij klawisz ENTER, aby zakończyć tę aplikację hosta przepływu pracy i że **LockOwnersTable** zostaną usunięte.</span><span class="sxs-lookup"><span data-stu-id="faae7-179">Press ENTER to terminate the workflow host application and observe that the **LockOwnersTable** is deleted.</span></span>  
  
#### <a name="to-uninstall-the-sample"></a><span data-ttu-id="faae7-180">Aby odinstalować próbki</span><span class="sxs-lookup"><span data-stu-id="faae7-180">To uninstall the sample</span></span>  
  
1.  <span data-ttu-id="faae7-181">Uruchom RemoveInstanceStore.cmd w katalogu próbki (\WF\Basic\Persistence\BuiltInConfiguration).</span><span class="sxs-lookup"><span data-stu-id="faae7-181">Run RemoveInstanceStore.cmd in the sample directory (\WF\Basic\Persistence\BuiltInConfiguration).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="faae7-182">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="faae7-182">The samples may already be installed on your computer.</span></span> <span data-ttu-id="faae7-183">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="faae7-183">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="faae7-184">Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="faae7-184">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="faae7-185">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="faae7-185">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\BuiltInConfiguration`  
  
## <a name="see-also"></a><span data-ttu-id="faae7-186">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="faae7-186">See Also</span></span>  
 [<span data-ttu-id="faae7-187">Przykłady trwałości i hostingu AppFabric</span><span class="sxs-lookup"><span data-stu-id="faae7-187">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)