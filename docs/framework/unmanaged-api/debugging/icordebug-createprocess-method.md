---
title: "ICorDebug::CreateProcess — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.CreateProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a05bb8d8486f5ae12910d51e3717c4c91ef09cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="c8dd2-102">ICorDebug::CreateProcess — Metoda</span><span class="sxs-lookup"><span data-stu-id="c8dd2-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="c8dd2-103">Uruchamia proces i jego podstawowym wątku pod kontrolą debugera.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8dd2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c8dd2-104">Syntax</span></span>  
  
```  
HRESULT CreateProcess (  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess            **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8dd2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c8dd2-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="c8dd2-106">[in] Wskaźnik do zerem ciąg, który określa moduł, który ma być wykonane przez uruchomionego procesu.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="c8dd2-107">Moduł jest wykonywany w kontekście zabezpieczeń procesu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="c8dd2-108">[in] Wskaźnik do zerem ciąg, który określa wiersz polecenia ma być wykonane przez uruchomionego procesu.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="c8dd2-109">Nazwa aplikacji (na przykład "SomeApp.exe") musi być pierwszym argumentem.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="c8dd2-110">[in] Wskaźnik do Win32 `SECURITY_ATTRIBUTES` strukturę, która określa deskryptora zabezpieczeń dla procesu.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="c8dd2-111">Jeśli `lpProcessAttributes` jest wartość null, proces pobiera domyślnego deskryptora zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="c8dd2-112">[in] Wskaźnik do Win32 `SECURITY_ATTRIBUTES` strukturę, która określa deskryptora zabezpieczeń dla podstawowego wątków procesu.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="c8dd2-113">Jeśli `lpThreadAttributes` jest wartość null, wątek pobiera domyślnego deskryptora zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="c8dd2-114">[in] Ustaw `true` aby wskazać, że każdego dziedziczne uchwytu procesu wywołującego jest dziedziczona przez uruchomionego procesu lub `false` aby wskazać, że uchwyty nie są dziedziczone.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="c8dd2-115">Uchwyty odziedziczone mają te same prawa dostępu i wartość jako oryginalnego uchwytów.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="c8dd2-116">[in] Bitowe połączenie [flagi tworzenia procesu Win32](http://go.microsoft.com/fwlink/?linkid=69981) umożliwiające sterowanie priorytet i działanie uruchomionego procesu.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-116">[in] A bitwise combination of the [Win32 Process Creation Flags](http://go.microsoft.com/fwlink/?linkid=69981) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="c8dd2-117">[in] Wskaźnik do bloku środowiska dla nowego procesu.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="c8dd2-118">[in] Wskaźnik do zerem ciąg, który określa pełną ścieżkę do katalogu bieżącego procesu.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="c8dd2-119">Jeśli ten parametr ma wartość null, nowy proces będzie mieć tego samego bieżącego dysku i katalogu jako proces wywoływania.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="c8dd2-120">[in] Wskaźnik do Win32 `STARTUPINFOW` strukturę, która określa stacja pulpitu, standardowe dojść i wyglądu głównego okna procesu uruchomionego.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="c8dd2-121">[in] Wskaźnik do Win32 `PROCESS_INFORMATION` strukturę, która określa informacje identyfikacyjne dotyczące procesu, które mają zostać uruchomione.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="c8dd2-122">[in] Wartość wyliczenia CorDebugCreateProcessFlags, która określa opcje debugowania.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="c8dd2-123">[out] Wskaźnik do adres obiektu ICorDebugProcess, który reprezentuje procesu.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8dd2-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c8dd2-124">Remarks</span></span>  
 <span data-ttu-id="c8dd2-125">Parametry tej metody są takie same jak Win32 `CreateProcess` metody.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="c8dd2-126">Aby włączyć debugowanie w trybie mieszanym niezarządzane, ustaw `dwCreationFlags` DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="c8dd2-127">Jeśli chcesz używać, tylko debugowanie zarządzane nie należy ustawiać te flagi.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="c8dd2-128">Jeśli debugera i procesu, aby było debugowania (dołączony proces) udostępnianie jednej konsoli, a jeśli używany jest debugowania międzyoperacyjnego, istnieje możliwość dołączony proces do przechowywania blokad konsoli i zatrzymać w zdarzeniu debugowania.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="c8dd2-129">Debuger następnie blokuje wszelkie próby korzystania z konsoli.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="c8dd2-130">Aby uniknąć tego problemu, należy ustawić flagę CREATE_NEW_CONSOLE `dwCreationFlags` parametru.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="c8dd2-131">Debugowanie międzyoperacyjne nie jest obsługiwane na platformach Win9x i z systemem innym niż x86, takich jak IA-64 i procesorem AMD64 platformy.</span><span class="sxs-lookup"><span data-stu-id="c8dd2-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8dd2-132">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c8dd2-132">Requirements</span></span>  
 <span data-ttu-id="c8dd2-133">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8dd2-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8dd2-134">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8dd2-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8dd2-135">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8dd2-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8dd2-136">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8dd2-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8dd2-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c8dd2-137">See Also</span></span>  
 [<span data-ttu-id="c8dd2-138">ICorDebug — interfejs</span><span class="sxs-lookup"><span data-stu-id="c8dd2-138">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)