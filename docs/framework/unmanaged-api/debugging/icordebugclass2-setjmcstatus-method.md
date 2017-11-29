---
title: "ICorDebugClass2::SetJMCStatus — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da9f61bd9a652b4c8e340ddecdee4b48bbdb086e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="25d1d-102">ICorDebugClass2::SetJMCStatus — Metoda</span><span class="sxs-lookup"><span data-stu-id="25d1d-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="25d1d-103">Ustawia wartość wskazującą, czy metoda jest zdefiniowane przez użytkownika kod dla każdej metody klasy.</span><span class="sxs-lookup"><span data-stu-id="25d1d-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25d1d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="25d1d-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25d1d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="25d1d-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="25d1d-106">[in] Ustaw `true` aby wskazać, że metoda jest zdefiniowane przez użytkownika kod; w przeciwnym razie wartość `false`.</span><span class="sxs-lookup"><span data-stu-id="25d1d-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25d1d-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="25d1d-107">Remarks</span></span>  
 <span data-ttu-id="25d1d-108">Stepper (JMC) just my kodu pominie zdefiniowane użytkownika kodu.</span><span class="sxs-lookup"><span data-stu-id="25d1d-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="25d1d-109">Kod użytkownika muszą być podzbiorem możliwością debugowania kodu.</span><span class="sxs-lookup"><span data-stu-id="25d1d-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="25d1d-110">`SetJMCStatus`Zwraca wartość HRESULT S_FALSE, jeśli nie można ustawić wartości dla dowolnej metody, nawet jeśli pomyślnie ustawia wartość dla wszystkich innych metod.</span><span class="sxs-lookup"><span data-stu-id="25d1d-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25d1d-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="25d1d-111">Requirements</span></span>  
 <span data-ttu-id="25d1d-112">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25d1d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25d1d-113">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25d1d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25d1d-114">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25d1d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25d1d-115">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25d1d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>