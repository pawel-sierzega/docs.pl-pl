---
title: "ICLRTask2::EndPreventAsyncAbort — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2.EndPreventAsyncAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c76a75004b4593e8e93aa4dd999c85c0fb7cf38a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="4cdc7-102">ICLRTask2::EndPreventAsyncAbort — Metoda</span><span class="sxs-lookup"><span data-stu-id="4cdc7-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="4cdc7-103">Zezwala na nowe lub oczekujące żądania przerwania wątku w wątku przerywa w bieżącym wątku.</span><span class="sxs-lookup"><span data-stu-id="4cdc7-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cdc7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4cdc7-104">Syntax</span></span>  
  
```  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4cdc7-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="4cdc7-105">Return Value</span></span>  
 <span data-ttu-id="4cdc7-106">Ta metoda zwraca następujące określonych wyników HRESULT, a także HRESULT błędów wskazujących Niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="4cdc7-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4cdc7-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4cdc7-107">HRESULT</span></span>|<span data-ttu-id="4cdc7-108">Opis</span><span class="sxs-lookup"><span data-stu-id="4cdc7-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4cdc7-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="4cdc7-109">S_OK</span></span>|<span data-ttu-id="4cdc7-110">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="4cdc7-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="4cdc7-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="4cdc7-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="4cdc7-112">Metoda została wywołana w wątku, który nie jest bieżący wątek.</span><span class="sxs-lookup"><span data-stu-id="4cdc7-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cdc7-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4cdc7-113">Remarks</span></span>  
 <span data-ttu-id="4cdc7-114">Ten licznik zmniejsza przerwania wątku opóźnienie — metoda podczas wywoływania bieżącego wątku o jeden.</span><span class="sxs-lookup"><span data-stu-id="4cdc7-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="4cdc7-115">Wywołuje się [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) i `EndPreventAsyncAbort` mogą być zagnieżdżone.</span><span class="sxs-lookup"><span data-stu-id="4cdc7-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="4cdc7-116">Tak długo, jak wartość licznika jest większa niż zero, opóźnienia przerwania wątku dla bieżącego wątku.</span><span class="sxs-lookup"><span data-stu-id="4cdc7-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="4cdc7-117">Funkcje, które jest udostępniane przez tę funkcję jest używana wewnętrznie przez maszynę wirtualną (VM).</span><span class="sxs-lookup"><span data-stu-id="4cdc7-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="4cdc7-118">Nieprawidłowe użycie tych metod może spowodować nieokreślony zachowanie w maszynie Wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="4cdc7-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="4cdc7-119">Na przykład wywołanie elementu `EndPreventAsyncAbort` bez wywoływania pierwszego elementu `BeginPreventAsyncAbort` można ustawić licznik do zera, gdy maszyna wirtualna wcześniej ma zwiększany.</span><span class="sxs-lookup"><span data-stu-id="4cdc7-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="4cdc7-120">Podobnie wewnętrzny licznik nie jest sprawdzany pod kątem przepełnienia.</span><span class="sxs-lookup"><span data-stu-id="4cdc7-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="4cdc7-121">W razie przekroczenia limitu całkowitej, ponieważ jest zwiększany przez hosta i maszyny Wirtualnej, efekty jest nieokreślony.</span><span class="sxs-lookup"><span data-stu-id="4cdc7-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cdc7-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4cdc7-122">Requirements</span></span>  
 <span data-ttu-id="4cdc7-123">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cdc7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cdc7-124">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4cdc7-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4cdc7-125">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4cdc7-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cdc7-126">**Wersje programu .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cdc7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cdc7-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4cdc7-127">See Also</span></span>  
 [<span data-ttu-id="4cdc7-128">BeginPreventAsyncAbort — metoda</span><span class="sxs-lookup"><span data-stu-id="4cdc7-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)  
 [<span data-ttu-id="4cdc7-129">ICLRTask2 — interfejs</span><span class="sxs-lookup"><span data-stu-id="4cdc7-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [<span data-ttu-id="4cdc7-130">ICLRTaskManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="4cdc7-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="4cdc7-131">IHostTask — interfejs</span><span class="sxs-lookup"><span data-stu-id="4cdc7-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="4cdc7-132">IHostTaskManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="4cdc7-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="4cdc7-133">Hosting — interfejsy</span><span class="sxs-lookup"><span data-stu-id="4cdc7-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)