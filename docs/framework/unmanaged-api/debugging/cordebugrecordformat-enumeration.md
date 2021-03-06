---
title: Wyliczenie CorDebugRecordFormat
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
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eaf962250d97f031eaa60b7cc0b15622897aad3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugrecordformat-enumeration"></a>Wyliczenie CorDebugRecordFormat
Opisuje format danych w tablicy bajtów, który zawiera informacje dotyczące zdarzenia debugowania natywnego wyjątek.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|Dane są rekord wyjątek 32-bitowego systemu Windows.|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|Dane są rekord wyjątek 64-bitowego systemu Windows.|  
  
## <a name="remarks"></a>Uwagi  
 Członek `CorDebugRecordFormat` wyliczenie jest przekazywana do [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) metody, aby wskazać format tablicy bajtów w jego `pRecord` argumentu.  
  
> [!NOTE]
>  To wyliczenie jest przeznaczona do użycia w platformę .NET Native tylko w scenariuszach debugowania.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [Debugowanie, wyliczenia](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
