---
title: "ICorDebugEval::CreateValue — Metoda"
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
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64d55a951795cc5efc1bfc624dbe07575be153aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalcreatevalue-method"></a>ICorDebugEval::CreateValue — Metoda
Tworzy wartość określonego typu o wartości początkowej zero lub wartość null.  
  
 Ta metoda jest przestarzała w programie .NET Framework w wersji 2.0. Użyj [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) zamiast tego.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `elementType`  
 [in] Wartość [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) wyliczenia, która określa typ wartości.  
  
 `pElementClass`  
 [in] Wskaźnik do [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) obiekt, który określa klasę wartości, jeśli typ nie jest typem pierwotnym.  
  
 `ppValue`  
 [out] Wskaźnik do obiektu "ICorDebugValue", który reprezentuje wartość adresu.  
  
## <a name="remarks"></a>Uwagi  
 `CreateValue`Tworzy `ICorDebugValue` obiekt danego typu wyłącznie w celu używania go w obliczania funkcji. Ten obiekt wartość może służyć do przekazywania stałe użytkownika jako parametry.  
  
 Jeśli typ wartości jest typu pierwotnego, jego wartość początkowa to zero lub wartość null. Użyj [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) można ustawić wartości typu pierwotnego.  
  
 Jeśli wartość `elementType` jest po elemencie ELEMENT_TYPE_CLASS, możesz uzyskać "ICorDebugReferenceValue" (zwracane w `ppValue`) reprezentujący odwołanie do obiektu o wartości null. Ten obiekt służy do przekazania wartości null do obliczania funkcji z parametrami odwołanie do obiektu. Nie można ustawić `ICorDebugValue` na niczego; zawsze pozostaje wartości null.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Zobacz też  
    
 [CreateValueForType, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)  
 ICorDebugValue
