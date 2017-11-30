---
title: "CorDebugJITCompilerFlags — Wyliczenie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugJITCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugJITCompilerFlags
helpviewer_keywords: CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d7eb8421dcd68c67536e0de038f7038500556c47
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="62b39-102">CorDebugJITCompilerFlags — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="62b39-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="62b39-103">Zawiera wartości, które wpływają na zachowanie zarządzanych kompilatora just in time (JIT).</span><span class="sxs-lookup"><span data-stu-id="62b39-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62b39-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="62b39-104">Syntax</span></span>  
  
```  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="62b39-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="62b39-105">Members</span></span>  
  
|<span data-ttu-id="62b39-106">Element członkowski</span><span class="sxs-lookup"><span data-stu-id="62b39-106">Member</span></span>|<span data-ttu-id="62b39-107">Opis</span><span class="sxs-lookup"><span data-stu-id="62b39-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="62b39-108">Określa, czy kompilator powinien śledzą dane dotyczące kompilacji i umożliwia optymalizacji.</span><span class="sxs-lookup"><span data-stu-id="62b39-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="62b39-109">Określa, czy kompilator powinien śledzenia danych kompilacji, ale wyłącza optymalizacje.</span><span class="sxs-lookup"><span data-stu-id="62b39-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="62b39-110">Określa, że kompilator powinien śledzenia danych kompilacji, wyłącza optymalizacje, i umożliwia Edytuj i Kontynuuj technologii.</span><span class="sxs-lookup"><span data-stu-id="62b39-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="62b39-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="62b39-111">Requirements</span></span>  
 <span data-ttu-id="62b39-112">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62b39-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62b39-113">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62b39-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62b39-114">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62b39-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62b39-115">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62b39-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62b39-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="62b39-116">See Also</span></span>  
 [<span data-ttu-id="62b39-117">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="62b39-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)