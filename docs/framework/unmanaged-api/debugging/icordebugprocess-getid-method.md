---
title: "ICorDebugProcess::GetID — Metoda"
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
- ICorDebugProcess.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetID
helpviewer_keywords:
- GetID method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetID method [.NET Framework debugging]
ms.assetid: b0ba8453-fa7e-4c14-93e5-335409cd4a47
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d09888434048c312bd78dddf29d39a45f023695e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessgetid-method"></a>ICorDebugProcess::GetID — Metoda
Pobiera identyfikator systemu operacyjnego (OS) procesu.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwProcessId`  
 [out] Unikatowy identyfikator procesu.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
