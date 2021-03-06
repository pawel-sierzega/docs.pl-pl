---
title: "ICorDebugFunction2::GetVersionNumber — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 16902d1a50f691ae555fdbc964bb9a1c6bf563c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunction2getversionnumber-method"></a>ICorDebugFunction2::GetVersionNumber — Metoda
Pobiera wersję tej funkcji Edytuj i Kontynuuj.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pnVersion`  
 [out] Wskaźnik do wartości całkowitej, numer wersji reprezentowanego przez ten obiekt ICorDebugFunction2 funkcji.  
  
## <a name="remarks"></a>Uwagi  
 Środowisko uruchomieniowe przechowuje informacje o liczbę zmian, które miały miejsce do poszczególnych modułów podczas sesji debugowania. Numer wersji funkcji jest jednym więcej niż liczba edycji, który wprowadzono funkcję. Funkcja oryginalnej wersji jest w wersji 1. Numer jest zwiększany modułu zawsze [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) zostanie wywołany dla tego modułu. W związku z tym jeśli treść funkcji został zastąpiony w wywołaniu pierwszy i trzeci `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` może zwrócić w wersji 1, 2 lub 4 dla tej funkcji, ale nie w wersji 3. (Ta funkcja będzie miała nie w wersji 3.)  
  
 Numer wersji jest osobno dla każdego modułu. Tak po wykonaniu czterech zmiany w Module 1 i żaden moduł 2 dalej edycji w Module 1 przypisze numer wersji 6 wszystkie funkcje edycji w Module 1. Jeśli takie same edytować poprawki modułu 2, funkcji w Module 2 otrzyma numer wersji 2.  
  
 Numer wersji uzyskany przez `GetVersionNumber` metoda może być mniejszy niż uzyskany przez [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).  
  
 [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) metoda wykonuje tę samą operację jako `ICorDebugFunction2::GetVersionNumber`.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
