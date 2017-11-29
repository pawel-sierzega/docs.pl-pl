---
title: "Architektura programowania aplikacji usług"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceController components, programming architecture
- ServiceBase class, service states
- Windows Service applications, code model
- services, programming architecture
- ServiceController class
- services, states
- ServiceProcessInstaller class, service application code model
- Windows Service applications, states
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: e9c16f2e603a3ce9bbc59be4e01aa492239d2c63
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="service-application-programming-architecture"></a><span data-ttu-id="333ee-102">Architektura programowania aplikacji usług</span><span class="sxs-lookup"><span data-stu-id="333ee-102">Service Application Programming Architecture</span></span>
<span data-ttu-id="333ee-103">Aplikacje usług systemu Windows są oparte na klasę, która dziedziczy <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> klasy.</span><span class="sxs-lookup"><span data-stu-id="333ee-103">Windows Service applications are based on a class that inherits from the <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="333ee-104">Przesłaniaj metody z tej klasy i zdefiniuj funkcji je, aby określić sposób działania usługi.</span><span class="sxs-lookup"><span data-stu-id="333ee-104">You override methods from this class and define functionality for them to determine how your service behaves.</span></span>  
  
 <span data-ttu-id="333ee-105">Klasy głównym zaangażowane w tworzenie usług są:</span><span class="sxs-lookup"><span data-stu-id="333ee-105">The main classes involved in service creation are:</span></span>  
  
-   <span data-ttu-id="333ee-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>— Można zastąpić metody z <xref:System.ServiceProcess.ServiceBase> klasy podczas tworzenia usługi i definiują kod, aby określić, jak Usługa funkcji w tym dziedziczone klasy.</span><span class="sxs-lookup"><span data-stu-id="333ee-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> — You override methods from the <xref:System.ServiceProcess.ServiceBase> class when creating a service and define the code to determine how your service functions in this inherited class.</span></span>  
  
-   <span data-ttu-id="333ee-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType>i <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> — te klasy służą do instalowania i odinstalowywania usługi.</span><span class="sxs-lookup"><span data-stu-id="333ee-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType> and <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> —You use these classes to install and uninstall your service.</span></span>  
  
 <span data-ttu-id="333ee-108">Ponadto klasa o nazwie <xref:System.ServiceProcess.ServiceController> może służyć do operowania samą usługę.</span><span class="sxs-lookup"><span data-stu-id="333ee-108">In addition, a class named <xref:System.ServiceProcess.ServiceController> can be used to manipulate the service itself.</span></span> <span data-ttu-id="333ee-109">Ta klasa nie jest do utworzenia usługi, ale może służyć do uruchamiania i Zatrzymaj usługę, Przekaż do niego poleceń i zwracać szereg wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="333ee-109">This class is not involved in the creation of a service, but can be used to start and stop the service, pass commands to it, and return a series of enumerations.</span></span>  
  
## <a name="defining-your-services-behavior"></a><span data-ttu-id="333ee-110">Definiowanie zachowania usługi</span><span class="sxs-lookup"><span data-stu-id="333ee-110">Defining Your Service's Behavior</span></span>  
 <span data-ttu-id="333ee-111">W klasie usługi należy zastąpić funkcje klasy podstawowej, które określają, co się dzieje, gdy stan usługi zostanie zmieniona w Menedżerze sterowania usługami.</span><span class="sxs-lookup"><span data-stu-id="333ee-111">In your service class, you override base class functions that determine what happens when the state of your service is changed in the Services Control Manager.</span></span> <span data-ttu-id="333ee-112"><xref:System.ServiceProcess.ServiceBase> Klasa udostępnia następujące metody, które można zmienić, aby dodać niestandardowe zachowanie.</span><span class="sxs-lookup"><span data-stu-id="333ee-112">The <xref:System.ServiceProcess.ServiceBase> class exposes the following methods, which you can override to add custom behavior.</span></span>  
  
|<span data-ttu-id="333ee-113">Metoda</span><span class="sxs-lookup"><span data-stu-id="333ee-113">Method</span></span>|<span data-ttu-id="333ee-114">Zastąpienie</span><span class="sxs-lookup"><span data-stu-id="333ee-114">Override to</span></span>|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|<span data-ttu-id="333ee-115">Wskazuje, jakie działania należy podjąć, podczas uruchamiania usługi.</span><span class="sxs-lookup"><span data-stu-id="333ee-115">Indicate what actions should be taken when your service starts running.</span></span> <span data-ttu-id="333ee-116">W tej procedurze usługi do wykonywania pracy przydatne należy napisać kod.</span><span class="sxs-lookup"><span data-stu-id="333ee-116">You must write code in this procedure for your service to perform useful work.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|<span data-ttu-id="333ee-117">Wskazuje, co powinno się zdarzyć, gdy usługa jest wstrzymana.</span><span class="sxs-lookup"><span data-stu-id="333ee-117">Indicate what should happen when your service is paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|<span data-ttu-id="333ee-118">Wskazuje, co powinno się zdarzyć, gdy usługa przestanie działać.</span><span class="sxs-lookup"><span data-stu-id="333ee-118">Indicate what should happen when your service stops running.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|<span data-ttu-id="333ee-119">Wskazuje, co powinno się zdarzyć, gdy usługa wznawia normalne działanie po wstrzymaniu.</span><span class="sxs-lookup"><span data-stu-id="333ee-119">Indicate what should happen when your service resumes normal functioning after being paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|<span data-ttu-id="333ee-120">Wskazuje, co powinno się stać wcześniejszy niż system zamykana, jeśli usługa jest uruchomiona w tym czasie.</span><span class="sxs-lookup"><span data-stu-id="333ee-120">Indicate what should happen just prior to your system shutting down, if your service is running at that time.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|<span data-ttu-id="333ee-121">Wskazuje, co powinno się stać z usługą odebrania polecenia niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="333ee-121">Indicate what should happen when your service receives a custom command.</span></span> <span data-ttu-id="333ee-122">Aby uzyskać więcej informacji o niestandardowych poleceń Zobacz MSDN online.</span><span class="sxs-lookup"><span data-stu-id="333ee-122">For more information on custom commands, see MSDN online.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|<span data-ttu-id="333ee-123">Wskazuje, jak usługa powinna odpowiadać po odebraniu zdarzenie zarządzania energią, takich jak niskim poziomie naładowania baterii lub wstrzymane operacji.</span><span class="sxs-lookup"><span data-stu-id="333ee-123">Indicate how the service should respond when a power management event is received, such as a low battery or suspended operation.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="333ee-124">Te metody reprezentują stanów, które usługa przechodzi przez w jego trwania. Usługa przejść z jednego stanu do następnej.</span><span class="sxs-lookup"><span data-stu-id="333ee-124">These methods represent states that the service moves through in its lifetime; the service transitions from one state to the next.</span></span> <span data-ttu-id="333ee-125">Na przykład, nigdy nie otrzymasz usługi odpowiedzieć na <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> polecenia przed <xref:System.ServiceProcess.ServiceBase.OnStart%2A> została wywołana.</span><span class="sxs-lookup"><span data-stu-id="333ee-125">For example, you will never get the service to respond to an <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> command before <xref:System.ServiceProcess.ServiceBase.OnStart%2A> has been called.</span></span>  
  
 <span data-ttu-id="333ee-126">Istnieje kilka innych właściwości i metod, które mogą być przydatne.</span><span class="sxs-lookup"><span data-stu-id="333ee-126">There are several other properties and methods that are of interest.</span></span> <span data-ttu-id="333ee-127">Należą do nich następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="333ee-127">These include:</span></span>  
  
-   <span data-ttu-id="333ee-128"><xref:System.ServiceProcess.ServiceBase.Run%2A> Metoda <xref:System.ServiceProcess.ServiceBase> klasy.</span><span class="sxs-lookup"><span data-stu-id="333ee-128">The <xref:System.ServiceProcess.ServiceBase.Run%2A> method on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="333ee-129">To jest główny punkt wejścia dla usługi.</span><span class="sxs-lookup"><span data-stu-id="333ee-129">This is the main entry point for the service.</span></span> <span data-ttu-id="333ee-130">Podczas tworzenia usługi przy użyciu szablonu usług systemu Windows, kod jest wstawiany do aplikacji `Main` metody w celu uruchomienia usługi.</span><span class="sxs-lookup"><span data-stu-id="333ee-130">When you create a service using the Windows Service template, code is inserted in your application's `Main` method to run the service.</span></span> <span data-ttu-id="333ee-131">Ten kod wygląda następująco:</span><span class="sxs-lookup"><span data-stu-id="333ee-131">This code looks like this:</span></span>  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  <span data-ttu-id="333ee-132">Poniższe przykłady Użyj tablicy typu <xref:System.ServiceProcess.ServiceBase>, do którego można dodać poszczególnych usług aplikacji i wszystkich usług można uruchomić jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="333ee-132">These examples use an array of type <xref:System.ServiceProcess.ServiceBase>, into which each service your application contains can be added, and then all of the services can be run together.</span></span> <span data-ttu-id="333ee-133">Jeśli tworzysz tylko jednej usługi, jednak warto nie używają tablicy i po prostu zadeklarować nowy obiekt dziedziczenie z <xref:System.ServiceProcess.ServiceBase> , a następnie uruchom go.</span><span class="sxs-lookup"><span data-stu-id="333ee-133">If you are only creating a single service, however, you might choose not to use the array and simply declare a new object inheriting from <xref:System.ServiceProcess.ServiceBase> and then run it.</span></span> <span data-ttu-id="333ee-134">Na przykład zobacz [porady: programowane pisanie usług](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="333ee-134">For an example, see [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span></span>  
  
-   <span data-ttu-id="333ee-135">Szereg właściwości <xref:System.ServiceProcess.ServiceBase> klasy.</span><span class="sxs-lookup"><span data-stu-id="333ee-135">A series of properties on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="333ee-136">Te określają, jakie metody można wywołać w usłudze.</span><span class="sxs-lookup"><span data-stu-id="333ee-136">These determine what methods can be called on your service.</span></span> <span data-ttu-id="333ee-137">Na przykład, jeśli <xref:System.ServiceProcess.ServiceBase.CanStop%2A> właściwość jest ustawiona na `true`, <xref:System.ServiceProcess.ServiceBase.OnStop%2A> można wywołać metody w usłudze.</span><span class="sxs-lookup"><span data-stu-id="333ee-137">For example, when the <xref:System.ServiceProcess.ServiceBase.CanStop%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method on your service can be called.</span></span> <span data-ttu-id="333ee-138">Gdy <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> właściwość jest ustawiona na `true`, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> i <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> można wywołać metody.</span><span class="sxs-lookup"><span data-stu-id="333ee-138">When the <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnPause%2A> and <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> methods can be called.</span></span> <span data-ttu-id="333ee-139">Po określeniu jednej z tych właściwości na `true`, należy zastąpić i zdefiniuj przetwarzania dla metod skojarzone.</span><span class="sxs-lookup"><span data-stu-id="333ee-139">When you set one of these properties to `true`, you should then override and define processing for the associated methods.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="333ee-140">Co najmniej przesłonięcie usługi <xref:System.ServiceProcess.ServiceBase.OnStart%2A> i <xref:System.ServiceProcess.ServiceBase.OnStop%2A> użyteczne.</span><span class="sxs-lookup"><span data-stu-id="333ee-140">Your service must override at least <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> to be useful.</span></span>  
  
 <span data-ttu-id="333ee-141">Można również użyć składnik o nazwie <xref:System.ServiceProcess.ServiceController> do komunikacji z i kontrolują zachowanie istniejącą usługę.</span><span class="sxs-lookup"><span data-stu-id="333ee-141">You can also use a component called the <xref:System.ServiceProcess.ServiceController> to communicate with and control the behavior of an existing service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="333ee-142">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="333ee-142">See Also</span></span>  
 [<span data-ttu-id="333ee-143">Wprowadzenie do aplikacji usług systemu Windows</span><span class="sxs-lookup"><span data-stu-id="333ee-143">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="333ee-144">Porady: tworzenie usług systemu Windows</span><span class="sxs-lookup"><span data-stu-id="333ee-144">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)