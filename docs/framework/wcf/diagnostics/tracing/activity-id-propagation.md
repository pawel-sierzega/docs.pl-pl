---
title: "Propagacja identyfikatora działania"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd1c1ae5-cc8a-4f51-90c9-f7b476bcfe70
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6c61087102148688678d868ce25a9cb63315ed65
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="activity-id-propagation"></a><span data-ttu-id="e7d72-102">Propagacja identyfikatora działania</span><span class="sxs-lookup"><span data-stu-id="e7d72-102">Activity ID Propagation</span></span>
<span data-ttu-id="e7d72-103">Propagacja odbywa się podczas ServiceModel czynność śledzenia jest włączona (ServiceModel propagacji) lub wyłączona (propagowania działań użytkownika).</span><span class="sxs-lookup"><span data-stu-id="e7d72-103">Propagation happens when ServiceModel activity tracing is enabled (ServiceModel propagation) or disabled (User-to-User activity propagation).</span></span>  
  
## <a name="servicemodel-activity-tracing-is-enabled"></a><span data-ttu-id="e7d72-104">Jest włączone śledzenie działania ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e7d72-104">ServiceModel Activity Tracing is Enabled</span></span>  
 <span data-ttu-id="e7d72-105">Po włączeniu ServiceModel ActivityTracing propagacji odbywa się między działaniami ProcessAction.</span><span class="sxs-lookup"><span data-stu-id="e7d72-105">If ServiceModel ActivityTracing is enabled, propagation happens between ProcessAction activities.</span></span>  
  
### <a name="server"></a><span data-ttu-id="e7d72-106">Serwer</span><span class="sxs-lookup"><span data-stu-id="e7d72-106">Server</span></span>  
 <span data-ttu-id="e7d72-107">Gdy `propagateActivity` atrybut ma ustawioną `true` na kliencie i serwerze identyfikator `ProcessAction` działania na serwerze jest taki sam jak identyfikator w propagowany `ActivityId` nagłówek komunikatu.</span><span class="sxs-lookup"><span data-stu-id="e7d72-107">When the `propagateActivity` attribute is set to `true` on both the client and server, the ID of the `ProcessAction` activity in the server is identical to the ID in the propagated `ActivityId` message header.</span></span>  
  
 <span data-ttu-id="e7d72-108">Gdy nie `ActivityId` nagłówka znajduje się w komunikacie (to znaczy `propagateActivity` = `false` na kliencie), lub gdy `propagateActivity` = `false` na serwerze, serwer generuje nowy identyfikator działania.</span><span class="sxs-lookup"><span data-stu-id="e7d72-108">When no `ActivityId` header is present in the message (that is, `propagateActivity`=`false` on the client), or when `propagateActivity`=`false` on the server, the server generates a new activity ID.</span></span>  
  
### <a name="client"></a><span data-ttu-id="e7d72-109">Klient</span><span class="sxs-lookup"><span data-stu-id="e7d72-109">Client</span></span>  
 <span data-ttu-id="e7d72-110">Jeśli klient jest synchronicznie pojedynczego wątku, klient pomija wszelkie ustawienia `propagateActivity` na klienta lub serwera.</span><span class="sxs-lookup"><span data-stu-id="e7d72-110">If the client is synchronously single threaded, the client disregards any settings of `propagateActivity` at the client or server.</span></span> <span data-ttu-id="e7d72-111">Zamiast tego odpowiedzi jest obsługiwany w działaniu żądania.</span><span class="sxs-lookup"><span data-stu-id="e7d72-111">Instead, the response is handled in the request activity.</span></span> <span data-ttu-id="e7d72-112">Jeśli klient jest asynchroniczne i synchroniczne wielowątkowe, `propagateActivity` = `true` w kliencie i brak nagłówka Identyfikatora aktywności w komunikacie wysyłane przez serwer, klient pobiera identyfikator działania z komunikatu i przesyła do Działanie akcji procesu, który zawiera identyfikator propagowany działania.</span><span class="sxs-lookup"><span data-stu-id="e7d72-112">If the client is asynchronous or synchronous multithreaded, `propagateActivity`=`true` in the client, and there is an activity ID header in the message sent by the server, the client retrieves the activity ID from the message, and transfers to the Process Action activity that contains the propagated activity ID.</span></span> <span data-ttu-id="e7d72-113">W przeciwnym razie klient przesyła z działania procesu komunikatu do nowego działania procesu akcji.</span><span class="sxs-lookup"><span data-stu-id="e7d72-113">Otherwise, the client transfers from Process Message activity to a new Process Action activity.</span></span> <span data-ttu-id="e7d72-114">To dodatkowe przeniesienie do nowego działania procesu akcji odbywa się dla spójności.</span><span class="sxs-lookup"><span data-stu-id="e7d72-114">This extra transfer to a new Process Action activity is done for consistency.</span></span> <span data-ttu-id="e7d72-115">Wewnątrz tego działania klient pobiera identyfikator działania działania BeginCall w kontekście lokalnego wątku po wątek został przydzielony do przetwarzania komunikatów odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="e7d72-115">Inside this activity, the client retrieves the activity ID of the BeginCall activity from the local thread context, when the thread is allocated for response message processing.</span></span> <span data-ttu-id="e7d72-116">Następnie przesyła początkowej działania procesu akcji.</span><span class="sxs-lookup"><span data-stu-id="e7d72-116">It then transfers to the initial Process Action activity.</span></span>  
  
 <span data-ttu-id="e7d72-117">Jeśli klient jest dupleksowy, klient działa jako serwer po otrzymaniu komunikatu.</span><span class="sxs-lookup"><span data-stu-id="e7d72-117">If the client is duplex, the client acts as server on receiving the message.</span></span>  
  
### <a name="propagation-in-fault-messages"></a><span data-ttu-id="e7d72-118">Propagacją komunikatów "Fault"</span><span class="sxs-lookup"><span data-stu-id="e7d72-118">Propagation in Fault Messages</span></span>  
 <span data-ttu-id="e7d72-119">Nie ma żadnej różnicy w Obsługa prawidłowe i komunikaty o błędach.</span><span class="sxs-lookup"><span data-stu-id="e7d72-119">There is no difference in handling valid and fault messages.</span></span> <span data-ttu-id="e7d72-120">Jeśli `propagateActivity` = `true`, identyfikator działania ma nagłówki komunikatów SOAP błędów jest identyczna jak działanie otoczenia.</span><span class="sxs-lookup"><span data-stu-id="e7d72-120">If `propagateActivity`=`true`, the activity ID added to the SOAP fault message headers is identical to the ambient activity.</span></span>  
  
## <a name="servicemodel-activity-tracing-is-disabled"></a><span data-ttu-id="e7d72-121">Śledzenie działania ServiceModel jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="e7d72-121">ServiceModel Activity Tracing is Disabled</span></span>  
 <span data-ttu-id="e7d72-122">Po wyłączeniu ServiceModel ActivityTracing propagacji występuje między działaniami kodu użytkownika bezpośrednio, bez pośrednictwa ServiceModel działań.</span><span class="sxs-lookup"><span data-stu-id="e7d72-122">If ServiceModel ActivityTracing is disabled, propagation occurs between user code activities directly without going through ServiceModel activities.</span></span> <span data-ttu-id="e7d72-123">Identyfikator działania zdefiniowane przez użytkownika również są propagowane do nagłówka Identyfikatora aktywności wiadomości.</span><span class="sxs-lookup"><span data-stu-id="e7d72-123">A user-defined activity ID is also propagated through the message activity ID header.</span></span>  
  
 <span data-ttu-id="e7d72-124">Jeśli `propagateActivity` = `true` i `ActivityTracing` = `off` dla odbiornika śledzenia ServiceModel (niezależnie od tego, czy śledzenie jest włączone w modelu ServiceModel), następujące się zdarzyć, klienta lub serwera:</span><span class="sxs-lookup"><span data-stu-id="e7d72-124">If `propagateActivity`=`true` and `ActivityTracing`=`off` for a ServiceModel trace listener (regardless of whether tracing is enabled on ServiceModel), the following happen on either the client or server:</span></span>  
  
-   <span data-ttu-id="e7d72-125">Na żądanie operacji lub wysyłania odpowiedzi identyfikator działania w protokole TLS są propagowane z kodu użytkownika, dopóki nie jest sformatowany komunikat.</span><span class="sxs-lookup"><span data-stu-id="e7d72-125">On operation request or sending response, the activity ID in TLS is propagated out of user code until a message is formed.</span></span> <span data-ttu-id="e7d72-126">Nagłówka Identyfikatora aktywności również jest wstawiany komunikat przed ich wysłaniem.</span><span class="sxs-lookup"><span data-stu-id="e7d72-126">An activity ID header is also inserted into the message before it is sent.</span></span>  
  
-   <span data-ttu-id="e7d72-127">Na żądania odbierania lub odbieranie odpowiedzi, identyfikator działania są pobierane z nagłówka wiadomości natychmiast po utworzeniu obiektu odebranego komunikatu.</span><span class="sxs-lookup"><span data-stu-id="e7d72-127">On receiving request or receiving response, the activity ID is retrieved from the message header as soon as the received message object is created.</span></span> <span data-ttu-id="e7d72-128">Identyfikator działania w protokole TLS są propagowane jak komunikat zniknie z zakresu, aż do osiągnięcia kodu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e7d72-128">The activity ID in TLS is propagated as soon as the message disappears from scope until user code is reached.</span></span>  
  
 <span data-ttu-id="e7d72-129">Te akcje gwarantuje, że śladów użytkownika pojawi się w to samo działanie, jeśli propagację znajduje się na.</span><span class="sxs-lookup"><span data-stu-id="e7d72-129">These actions guarantee that user traces will appear in the same activity if propagation is on.</span></span> <span data-ttu-id="e7d72-130">Jej nie udostępnia jednak żadnej gwarancji na śladów ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="e7d72-130">However, it makes no guarantee on ServiceModel traces.</span></span> <span data-ttu-id="e7d72-131">Ślady ServiceModel wystąpić w działaniu kodu użytkownika tylko wtedy, gdy przetwarzanie tych danych śledzenia jest wykonywane na tym samym wątku, w którym działanie kodu użytkownika została ustawiona.</span><span class="sxs-lookup"><span data-stu-id="e7d72-131">ServiceModel traces occur in a user code activity only if the processing of those traces is executed on the same thread where the user code activity was set.</span></span>  
  
 <span data-ttu-id="e7d72-132">Ogólnie rzecz biorąc można zaobserwować śladów ServiceModel w następujących miejscach:</span><span class="sxs-lookup"><span data-stu-id="e7d72-132">In general, ServiceModel traces can be observed in the following places:</span></span>  
  
-   <span data-ttu-id="e7d72-133">Jeśli ServiceModel śledzenie jest wyłączone, wszystkie ślady emitowany wyświetlana działań użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e7d72-133">If ServiceModel tracing is disabled, all emitted traces appear in user activities.</span></span> <span data-ttu-id="e7d72-134">Po włączeniu serwera i klienta propagacji te operacje śledzenia będą w tym samym działaniu.</span><span class="sxs-lookup"><span data-stu-id="e7d72-134">If propagation is enabled at both the server and client, these traces will be in the same activity.</span></span>  
  
-   <span data-ttu-id="e7d72-135">Jeśli ServiceModel śledzenie jest włączone, ale ActivityTracing jest wyłączona, dane śledzenia użytkownika są wyświetlane w to samo działanie, jeśli Propagacja jest włączona po obu stronach.</span><span class="sxs-lookup"><span data-stu-id="e7d72-135">If ServiceModel tracing is enabled, but ActivityTracing is disabled, user traces appear in the same activity if propagation is enabled on both ends.</span></span> <span data-ttu-id="e7d72-136">Ślady ServiceModel wyświetlana domyślne działanie 0000, jeśli występują one w tym samym wątku, co przetwarzania kodu użytkownika, gdy działanie jest początkowo ustawiona.</span><span class="sxs-lookup"><span data-stu-id="e7d72-136">ServiceModel traces appear in the default 0000 activity, unless they occur in the same thread as the user code processing where the activity is initially set.</span></span>  
  
-   <span data-ttu-id="e7d72-137">Jeśli zarówno śledzenie ServiceModel i ActivityTracing są włączone, śledzenie użytkowników są wyświetlane w zdefiniowanych przez użytkownika działań i ślady ServiceModel pojawiają się w zdefiniowanych ServiceModel działań.</span><span class="sxs-lookup"><span data-stu-id="e7d72-137">If both ServiceModel tracing and ActivityTracing are enabled, user traces appear in user-defined activities, and ServiceModel traces appear in ServiceModel-defined activities.</span></span> <span data-ttu-id="e7d72-138">Propagacja odbywa się na poziomie modelu ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="e7d72-138">Propagation happens at ServiceModel level.</span></span>