---
title: dirtyCastAndCallOnInterface MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed debugging assistants (MDAs), early bound calls AutoDispatch
- dispatch-only mode
- dirtyCastAndCallOnInterface
- early-bound managed classes
- early bound calls on AutoDispatch
- MDAs (managed debugging assistants), early bound calls AutoDispatch
- EarlyBoundCallOnAutorDispatchClassInteface MDA
ms.assetid: aa388ed3-7e3d-48ea-a0b5-c47ae19cec38
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: eebbf48f084a0c0125bf40e5e14b8c71c1b0a6ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="dirtycastandcalloninterface-mda"></a><span data-ttu-id="646a5-102">dirtyCastAndCallOnInterface MDA</span><span class="sxs-lookup"><span data-stu-id="646a5-102">dirtyCastAndCallOnInterface MDA</span></span>
<span data-ttu-id="646a5-103">`dirtyCastAndCallOnInterface` Zarządzany Asystent debugowania (MDA) jest aktywowany, gdy w interfejsie klasy, która została oznaczona jako późnym wiązaniem tylko podejmowane są próby wywołania z wczesnym wiązaniem vtable.</span><span class="sxs-lookup"><span data-stu-id="646a5-103">The `dirtyCastAndCallOnInterface` managed debugging assistant (MDA) is activated when an early-bound call through a vtable is attempted on a class interface that has been marked late-bound only.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="646a5-104">Symptomy</span><span class="sxs-lookup"><span data-stu-id="646a5-104">Symptoms</span></span>  
 <span data-ttu-id="646a5-105">Aplikacja zgłasza naruszenie zasad dostępu lub ma nieoczekiwanego zachowania podczas umieszczania wywołania z wczesnym wiązaniem za pośrednictwem modelu COM do środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="646a5-105">An application throws an access violation or has unexpected behavior when placing an early-bound call via COM into the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="646a5-106">Przyczyna</span><span class="sxs-lookup"><span data-stu-id="646a5-106">Cause</span></span>  
 <span data-ttu-id="646a5-107">Kod jest próba wywołania z wczesnym wiązaniem vtable za pośrednictwem interfejsu klasy, które są tylko późnym wiązaniem.</span><span class="sxs-lookup"><span data-stu-id="646a5-107">Code is attempting an early-bound call through a vtable via a class interface that is late-bound only.</span></span> <span data-ttu-id="646a5-108">Należy pamiętać, że przez domyślną klasę interfejsy są identyfikowane jako trwa późnym wiązaniem tylko.</span><span class="sxs-lookup"><span data-stu-id="646a5-108">Note that by default class interfaces are identified as being late-bound only.</span></span> <span data-ttu-id="646a5-109">Można również zidentyfikować je jako późnym wiązaniem z <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> atrybutem <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> wartość (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).</span><span class="sxs-lookup"><span data-stu-id="646a5-109">They can also be identified as late-bound with the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute with an <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> value (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="646a5-110">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="646a5-110">Resolution</span></span>  
 <span data-ttu-id="646a5-111">Zalecane rozwiązanie jest zdefiniować jawnego interfejsu do użycia przez model COM, a wywołania klientów modelu COM za pośrednictwem tego interfejsu zamiast za pomocą interfejsu automatycznie wygenerowana klasa.</span><span class="sxs-lookup"><span data-stu-id="646a5-111">The recommended resolution is to define an explicit interface for use by COM and have the COM clients call through this interface instead of through the automatically generated class interface.</span></span> <span data-ttu-id="646a5-112">Alternatywnie wywołania z modelu COM może służyć za pośrednictwem wywołania późnym wiązaniem `IDispatch`.</span><span class="sxs-lookup"><span data-stu-id="646a5-112">Alternatively, the call from COM can be transformed into a late-bound call via `IDispatch`.</span></span>  
  
 <span data-ttu-id="646a5-113">Ponadto istnieje możliwość identyfikowania klasy jako <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) umożliwia wywołania z wczesnym wiązaniem do umieszczenia z modelu COM; jednak za pomocą <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> jest zalecane z powodu ograniczeń versioning opisanego w <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span><span class="sxs-lookup"><span data-stu-id="646a5-113">Finally, it is possible to identify the class as <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) to allow early bound calls to be placed from COM; however, using <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> is strongly discouraged because of the versioning limitations described in <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="646a5-114">Wpływ na środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="646a5-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="646a5-115">To zdarzenie MDA nie ma wpływu na środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="646a5-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="646a5-116">Zwraca tylko dane o wywołania z wczesnym wiązaniem dla interfejsów z późnym wiązaniem.</span><span class="sxs-lookup"><span data-stu-id="646a5-116">It only reports data about early-bound calls on late-bound interfaces.</span></span>  
  
## <a name="output"></a><span data-ttu-id="646a5-117">Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="646a5-117">Output</span></span>  
 <span data-ttu-id="646a5-118">Nazwa metody lub nazwę pola, do której uzyskuje dostęp z wczesnym wiązaniem.</span><span class="sxs-lookup"><span data-stu-id="646a5-118">The name of the method or name of the field being accessed early-bound.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="646a5-119">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="646a5-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dirtyCastAndCallOnInterface />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="646a5-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="646a5-120">See Also</span></span>  
 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>  
 [<span data-ttu-id="646a5-121">Diagnozowanie błędów przy użyciu Asystenci zarządzanego debugowania</span><span class="sxs-lookup"><span data-stu-id="646a5-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)