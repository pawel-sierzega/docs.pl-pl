---
title: "CorDebugRegister — Wyliczenie"
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
- CorDebugRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugRegister
helpviewer_keywords:
- CorDebugRegister enumeration [.NET Framework debugging]
ms.assetid: 003bb138-7960-4291-ac88-0d87e470ff70
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f168e686a127b2763099d2cfaea7ff396c4e734
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugregister-enumeration"></a>CorDebugRegister — Wyliczenie
Określa, rejestruje skojarzony z danym procesor.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef enum CorDebugRegister {  
  
    REGISTER_INSTRUCTION_POINTER = 0,  
    REGISTER_STACK_POINTER,  
    REGISTER_FRAME_POINTER,  
  
    REGISTER_X86_EIP = 0,  
    REGISTER_X86_ESP,  
    REGISTER_X86_EBP,  
  
    REGISTER_X86_EAX,  
    REGISTER_X86_ECX,  
    REGISTER_X86_EDX,  
    REGISTER_X86_EBX,  
  
    REGISTER_X86_ESI,  
    REGISTER_X86_EDI,  
  
    REGISTER_X86_FPSTACK_0,  
    REGISTER_X86_FPSTACK_1,  
    REGISTER_X86_FPSTACK_2,  
    REGISTER_X86_FPSTACK_3,  
    REGISTER_X86_FPSTACK_4,  
    REGISTER_X86_FPSTACK_5,  
    REGISTER_X86_FPSTACK_6,  
    REGISTER_X86_FPSTACK_7,  
  
    REGISTER_AMD64_RIP = 0,  
    REGISTER_AMD64_RSP,  
    REGISTER_AMD64_RBP,  
    REGISTER_AMD64_RAX,  
    REGISTER_AMD64_RCX,  
    REGISTER_AMD64_RDX,  
    REGISTER_AMD64_RBX,  
    REGISTER_AMD64_RSI,  
    REGISTER_AMD64_RDI,  
    REGISTER_AMD64_R8,  
    REGISTER_AMD64_R9,  
    REGISTER_AMD64_R10,  
    REGISTER_AMD64_R11,  
    REGISTER_AMD64_R12,  
    REGISTER_AMD64_R13,  
    REGISTER_AMD64_R14,  
    REGISTER_AMD64_R15,  
  
    REGISTER_AMD64_XMM0,  
    REGISTER_AMD64_XMM1,  
    REGISTER_AMD64_XMM2,  
    REGISTER_AMD64_XMM3,  
    REGISTER_AMD64_XMM4,  
    REGISTER_AMD64_XMM5,  
    REGISTER_AMD64_XMM6,  
    REGISTER_AMD64_XMM7,  
    REGISTER_AMD64_XMM8,  
    REGISTER_AMD64_XMM9,  
    REGISTER_AMD64_XMM10,  
    REGISTER_AMD64_XMM11,  
    REGISTER_AMD64_XMM12,  
    REGISTER_AMD64_XMM13,  
    REGISTER_AMD64_XMM14,  
    REGISTER_AMD64_XMM15,  
  
    REGISTER_IA64_BSP = REGISTER_FRAME_POINTER,  
    REGISTER_IA64_R0  = REGISTER_IA64_BSP + 1,  
    REGISTER_IA64_F0  = REGISTER_IA64_R0  + 128,  
    REGISTER_ARM_PC = 0,  
    REGISTER_ARM_SP,  
    REGISTER_ARM_R0,  
    REGISTER_ARM_R1,  
    REGISTER_ARM_R2,  
    REGISTER_ARM_R3,  
    REGISTER_ARM_R4,  
    REGISTER_ARM_R5,  
    REGISTER_ARM_R6,  
    REGISTER_ARM_R7,  
    REGISTER_ARM_R8,  
    REGISTER_ARM_R9,  
    REGISTER_ARM_R10,  
    REGISTER_ARM_R11,  
    REGISTER_ARM_R12,  
    REGISTER_ARM_LR,  
  
} CorDebugRegister;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|`REGISTER_INSTRUCTION_POINTER`|Wskaźnik instrukcji zarejestrować dowolnego procesora.|  
|`REGISTER_STACK_POINTER`|Wskaźnik stosu zarejestrować dowolnego procesora.|  
|`REGISTER_FRAME_POINTER`|Rejestr wskaźnika ramki za dowolnego procesora.|  
|`REGISTER_X86_EIP`|Rejestr wskaźnika instrukcji na x86 procesora.|  
|`REGISTER_X86_ESP`|Rejestr wskaźnika stosu na x86 procesora.|  
|`REGISTER_X86_EBP`|Rejestr podstawowego wskaźnika na x86 procesora.|  
|`REGISTER_X86_EAX`|Rejestr danych A na x86 procesora.|  
|`REGISTER_X86_ECX`|Rejestr danych C na x86 procesora.|  
|`REGISTER_X86_EDX`|Rejestr danych D na x86 procesora.|  
|`REGISTER_X86_EBX`|Rejestr danych B na x86 procesora.|  
|`REGISTER_X86_ESI`|Źródło indeks rejestru w x86 procesora.|  
|`REGISTER_X86_EDI`|Rejestr indeksu docelowego na x86 procesora.|  
|`REGISTER_X86_FPSTACK_0`|Procesor rejestru 0 na x86 liczb zmiennoprzecinkowych (FP) stosu.|  
|`REGISTER_X86_FPSTACK_1`|Stos #1 zarejestrować x86 FP procesora.|  
|`REGISTER_X86_FPSTACK_2`|Stos #2 zarejestrować x86 FP procesora.|  
|`REGISTER_X86_FPSTACK_3`|Stos #3 zarejestrować x86 FP procesora.|  
|`REGISTER_X86_FPSTACK_4`|Stos #4 zarejestrować x86 FP procesora.|  
|`REGISTER_X86_FPSTACK_5`|Stos #5 zarejestrować x86 FP procesora.|  
|`REGISTER_X86_FPSTACK_6`|Stos #6 zarejestrować x86 FP procesora.|  
|`REGISTER_X86_FPSTACK_7`|Stos #7 zarejestrować x86 FP procesora.|  
|`REGISTER_AMD64_RIP`|Wskaźnik instrukcji zarejestrować na procesorem AMD64.|  
|`REGISTER_AMD64_RSP`|Wskaźnik stosu zarejestrować na procesorem AMD64.|  
|`REGISTER_AMD64_RBP`|Rejestr podstawowego wskaźnika na procesorem AMD64.|  
|`REGISTER_AMD64_RAX`|Rejestr danych A na procesorem AMD64.|  
|`REGISTER_AMD64_RCX`|Zarejestruj dane C na procesorem AMD64.|  
|`REGISTER_AMD64_RDX`|Zarejestruj dane D na procesorem AMD64.|  
|`REGISTER_AMD64_RBX`|Zarejestruj dane B na procesorem AMD64.|  
|`REGISTER_AMD64_RSI`|Indeks źródła zarejestrować na procesorem AMD64.|  
|`REGISTER_AMD64_RDI`|Indeksu docelowego zarejestrować na procesorem AMD64.|  
|`REGISTER_AMD64_R8`|Zarejestruj dane #8 na procesorem AMD64.|  
|`REGISTER_AMD64_R9`|Zarejestruj dane #9 na procesorem AMD64.|  
|`REGISTER_AMD64_R10`|Zarejestruj dane #10 na procesorem AMD64.|  
|`REGISTER_AMD64_R11`|Zarejestruj dane #11 na procesorem AMD64.|  
|`REGISTER_AMD64_R12`|Zarejestruj dane #12 na procesorem AMD64.|  
|`REGISTER_AMD64_R13`|Zarejestruj dane #13 na procesorem AMD64.|  
|`REGISTER_AMD64_R14`|Zarejestruj dane #14 na procesorem AMD64.|  
|`REGISTER_AMD64_R15`|Zarejestruj dane #15 na procesorem AMD64.|  
|`REGISTER_AMD64_XMM0`|Zarejestruj #0 multimediów na procesorem AMD64.|  
|`REGISTER_AMD64_XMM1`|Zarejestruj #1 multimedialnych na procesorem AMD64.|  
|`REGISTER_AMD64_XMM2`|Zarejestruj #2 multimedialnych na procesorem AMD64.|  
|`REGISTER_AMD64_XMM3`|Zarejestruj #3 multimedialnych na procesorem AMD64.|  
|`REGISTER_AMD64_XMM4`|Zarejestruj #4 multimedialnych na procesorem AMD64.|  
|`REGISTER_AMD64_XMM5`|Zarejestruj #5 multimedialnych na procesorem AMD64.|  
|`REGISTER_AMD64_XMM6`|Zarejestruj #6 multimedialnych na procesorem AMD64.|  
|`REGISTER_AMD64_XMM7`|Zarejestruj #7 multimedialnych na procesorem AMD64.|  
|`REGISTER_AMD64_XMM8`|Zarejestruj #8 multimedialnych na procesorem AMD64.|  
|`REGISTER_AMD64_XMM9`|Zarejestruj #9 multimedialnych na procesorem AMD64.|  
|`REGISTER_AMD64_XMM10`|Zarejestruj #10 multimedialnych na procesorem AMD64.|  
|`REGISTER_AMD64_XMM11`|Zarejestruj #11 multimedialnych na procesorem AMD64.|  
|`REGISTER_AMD64_XMM12`|Zarejestruj #12 multimedialnych na procesorem AMD64.|  
|`REGISTER_AMD64_XMM13`|Zarejestruj #13 multimedialnych na procesorem AMD64.|  
|`REGISTER_AMD64_XMM14`|Zarejestruj #14 multimedialnych na procesorem AMD64.|  
|`REGISTER_AMD64_XMM15`|Zarejestruj #15 multimedialnych na procesorem AMD64.|  
|`REGISTER_IA64_BSP`|Wskaźnik stosu zarejestrować w procesorze IA-64.|  
|`REGISTER_IA64_R0`|Zarejestruj dane #0 na procesorze IA-64.|  
|`REGISTER_IA64_F0`|Zarejestruj dane FP #0 na procesorze IA-64.|  
|`REGISTER_ARM_PC`|Licznik programu Zarejestruj (R15) w procesorze ARM.|  
|`REGISTER_ARM_SP`|Wskaźnik stosu Zarejestruj (R13) w procesorze ARM.|  
|`REGISTER_ARM_R0`|Dane rejestru R0 na procesor ARM.|  
|`REGISTER_ARM_R1`|Dane rejestru R1 na procesor ARM.|  
|`REGISTER_ARM_R2`|Dane rejestru R2 na procesor ARM.|  
|`REGISTER_ARM_R3`|Dane rejestru R3 na procesor ARM.|  
|`REGISTER_ARM_R4`|Zarejestruj R4 na procesor ARM.|  
|`REGISTER_ARM_R5`|Zarejestruj R5 na procesor ARM.|  
|`REGISTER_ARM_R6`|Zarejestruj R6 na procesor ARM.|  
|`REGISTER_ARM_R7`|Zarejestruj R7 (MINIATURA wskaźnika ramki) na procesor ARM.|  
|`REGISTER_ARM_R8`|Zarejestruj R8 na procesor ARM.|  
|`REGISTER_ARM_R9`|Zarejestruj R9 na procesor ARM.|  
|`REGISTER_ARM_R10`|Zarejestruj R10 na procesor ARM.|  
|`REGISTER_ARM_R11`|Wskaźnik ramki na procesor ARM.|  
|`REGISTER_ARM_R12`|Zarejestruj R12 na procesor ARM.|  
|`REGISTER_ARM_LR`|Rejestr łącza (R14) w procesorze ARM.|  
  
## <a name="remarks"></a>Uwagi  
 Rejestruje 128 danych ogólnego przeznaczenia i 128 rejestrów zmiennoprzecinkowych danych na procesor IA-64, ale tylko wartości `REGISTER_IA64_R0` i `REGISTER_IA64_F0` są udostępniane. Inne wartości mogą być określane w następujący sposób:  
  
-   Dodaj numer rejestru `REGISTER_IA64_R0` wartości `REGISTER_IA64_R1` za pośrednictwem `REGISTER_IA64_R127`, które odpowiadają rejestru #1 danych za pomocą rejestru #127 danych w procesorze IA-64.  
  
-   Dodaj numer rejestru `REGISTER_IA64_F0` wartości `REGISTER_IA64_F1` za pośrednictwem `REGISTER_IA64_F127`, która odpowiada Rejestr danych FP #1 do #127 rejestr FP danych w procesorze IA-64.  
  
 Na przykład, jeśli należy określić rejestr #83 danych w procesorze IA-64, użyj `REGISTER_IA64_R0` + 83.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [Debugowanie, wyliczenia](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
