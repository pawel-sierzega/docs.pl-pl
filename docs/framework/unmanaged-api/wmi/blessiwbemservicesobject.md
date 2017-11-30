---
title: "Funkcja BlessIWbemServicesObject (niezarządzany wykaz interfejsów API)"
description: "Funkcja BlessIWbemServicesObject wskazuje, czy poświadczenia użytkownika zezwolenie na dostęp do obiektu IWbemServices"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BlessIWbemServicesObject
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BlessIWbemServicesObject
helpviewer_keywords: BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ebba6df29b814315180e9c8e936e5e1ad175ecf8
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="e5b55-103">Funkcja BlessIWbemServicesObject</span><span class="sxs-lookup"><span data-stu-id="e5b55-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="e5b55-104">Wskazuje, czy poświadczenia użytkownika zezwolenie na dostęp do określonej [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) obiektu.</span><span class="sxs-lookup"><span data-stu-id="e5b55-104">Indicates whether the user credentials permit access to a specified [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="e5b55-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="e5b55-105">Syntax</span></span>  
  
```  
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="e5b55-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="e5b55-106">Parameters</span></span>

`pIWbemServices`  
<span data-ttu-id="e5b55-107">[in] Wskaźnik do obiektu usługi WMI.</span><span class="sxs-lookup"><span data-stu-id="e5b55-107">[in] A pointer to a WMI service object.</span></span>

`strUser`  
<span data-ttu-id="e5b55-108">[in] Nazwa użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e5b55-108">[in] The user name.</span></span>

`strPassword`  
<span data-ttu-id="e5b55-109">[in] Hasło skojarzone z `strUser`.</span><span class="sxs-lookup"><span data-stu-id="e5b55-109">[in] The password associated with `strUser`.</span></span>

<span data-ttu-id="e5b55-110">`strAuthority`[in] Nazwa domeny użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e5b55-110">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="e5b55-111">Zobacz [ConnectServerWmi](connectserverwmi.md) funkcji, aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="e5b55-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="e5b55-112">`impLevel`[in] Poziom personifikacji.</span><span class="sxs-lookup"><span data-stu-id="e5b55-112">`impLevel` [in] The impersonation level.</span></span>

<span data-ttu-id="e5b55-113">`authnLevel`[in] Poziom autoryzacji.</span><span class="sxs-lookup"><span data-stu-id="e5b55-113">`authnLevel` [in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="e5b55-114">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="e5b55-114">Return value</span></span>

<span data-ttu-id="e5b55-115">Następujące wartości zwracane przez tę funkcję są zdefiniowane w *pliku WinError.h* pliku nagłówka, lub należy je zdefiniować jako stałe w kodzie:</span><span class="sxs-lookup"><span data-stu-id="e5b55-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e5b55-116">Stała</span><span class="sxs-lookup"><span data-stu-id="e5b55-116">Constant</span></span>  |<span data-ttu-id="e5b55-117">Wartość</span><span class="sxs-lookup"><span data-stu-id="e5b55-117">Value</span></span>  |<span data-ttu-id="e5b55-118">Opis</span><span class="sxs-lookup"><span data-stu-id="e5b55-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="e5b55-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="e5b55-119">0x80070057</span></span> | <span data-ttu-id="e5b55-120">Jeden lub więcej argumentów są nieprawidłowe.</span><span class="sxs-lookup"><span data-stu-id="e5b55-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="e5b55-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="e5b55-121">0x80004003</span></span> | <span data-ttu-id="e5b55-122">`pIWbemServices`jest `null`.</span><span class="sxs-lookup"><span data-stu-id="e5b55-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="e5b55-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="e5b55-123">0x80000008</span></span> | <span data-ttu-id="e5b55-124">Wystąpił nieokreślony błąd.</span><span class="sxs-lookup"><span data-stu-id="e5b55-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="e5b55-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="e5b55-125">0x80000002</span></span> | <span data-ttu-id="e5b55-126">Ma wystarczającej ilości pamięci do wykonania tej operacji.</span><span class="sxs-lookup"><span data-stu-id="e5b55-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="e5b55-127">0</span><span class="sxs-lookup"><span data-stu-id="e5b55-127">0</span></span> | <span data-ttu-id="e5b55-128">Wywołanie funkcji zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="e5b55-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="e5b55-129">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e5b55-129">Requirements</span></span>  
 <span data-ttu-id="e5b55-130">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5b55-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5b55-131">**Nagłówek:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e5b55-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e5b55-132">**Wersje programu .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e5b55-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b55-133">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e5b55-133">See also</span></span>  
[<span data-ttu-id="e5b55-134">Liczniki wydajności (niezarządzany wykaz interfejsów API) i usługi WMI</span><span class="sxs-lookup"><span data-stu-id="e5b55-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)