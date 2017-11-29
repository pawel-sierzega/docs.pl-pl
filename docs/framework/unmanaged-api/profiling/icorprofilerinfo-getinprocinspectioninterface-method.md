---
title: "ICorProfilerInfo::GetInprocInspectionInterface — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetInprocInspectionInterface
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type: apiref
caps.latest.revision: "19"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be114784b0003e5f1540520fdbbef751b369f1da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="f0510-102">ICorProfilerInfo::GetInprocInspectionInterface — Metoda</span><span class="sxs-lookup"><span data-stu-id="f0510-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="f0510-103">Pobiera obiekt, który można wykonać zapytania dla interfejsu "ICorDebugProcess".</span><span class="sxs-lookup"><span data-stu-id="f0510-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="f0510-104">Ta metoda jest przestarzała w programie .NET Framework w wersji 2.0.</span><span class="sxs-lookup"><span data-stu-id="f0510-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0510-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="f0510-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0510-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="f0510-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="f0510-107">[limit](/cpp/atl/iunknown) obiekt, który można wykonać zapytania o `ICorDebugProcess` interfejsu.</span><span class="sxs-lookup"><span data-stu-id="f0510-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0510-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f0510-108">Remarks</span></span>  
 <span data-ttu-id="f0510-109">Środowisko uruchomieniowe języka wspólnego (CLR) API — debugowanie obsługiwane ograniczony w trakcie debugowania w programie .NET Framework w wersji 1.0.</span><span class="sxs-lookup"><span data-stu-id="f0510-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="f0510-110">Debugowanie w trakcie włączone profiler do używania kontroli części interfejsu API debugowania.</span><span class="sxs-lookup"><span data-stu-id="f0510-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="f0510-111">Wyniku opinie klientów w trakcie debugowania ma został usunięty z programu .NET Framework w wersji 2.0 i zastąpione zestaw funkcji, która jest zgodna z interfejsu API profilowania.</span><span class="sxs-lookup"><span data-stu-id="f0510-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0510-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f0510-112">Requirements</span></span>  
 <span data-ttu-id="f0510-113">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0510-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0510-114">**Nagłówek:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f0510-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f0510-115">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0510-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0510-116">**Wersja platformy .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="f0510-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0510-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f0510-117">See Also</span></span>  
 [<span data-ttu-id="f0510-118">ICorProfilerInfo — interfejs</span><span class="sxs-lookup"><span data-stu-id="f0510-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)