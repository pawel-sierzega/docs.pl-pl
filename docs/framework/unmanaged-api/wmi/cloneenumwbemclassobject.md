---
title: "Funkcja CloneEnumWbemClassObject (niezarządzany wykaz interfejsów API)"
description: "Funkcja CloneEnumWbemClassObject tworzy kopię logicznej moduł wyliczający."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CloneEnumWbemClassObject
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CloneEnumWbemClassObject
helpviewer_keywords: CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7a4103a0103a334a0e5eace32d8fcf1b365917b8
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="feab7-103">Funkcja CloneEnumWbemClassObject</span><span class="sxs-lookup"><span data-stu-id="feab7-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="feab7-104">Tworzy kopię logicznej moduł wyliczający, zachowując jego bieżącym położeniu w wyliczeniu.</span><span class="sxs-lookup"><span data-stu-id="feab7-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="feab7-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="feab7-105">Syntax</span></span>  
  
```  
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```  

## <a name="parameters"></a><span data-ttu-id="feab7-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="feab7-106">Parameters</span></span>

`ppEnum`  
<span data-ttu-id="feab7-107">[out] Odbiera Wskaźnik do nowego [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="feab7-107">[out] Receives a pointer to a new [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).</span></span>

`authLevel`  
<span data-ttu-id="feab7-108">[in] Poziom autoryzacji.</span><span class="sxs-lookup"><span data-stu-id="feab7-108">[in] The authorization level.</span></span>

<span data-ttu-id="feab7-109">`impLevel`[in] Poziom personifikacji.</span><span class="sxs-lookup"><span data-stu-id="feab7-109">`impLevel` [in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`  
<span data-ttu-id="feab7-110">[out] Wskaźnik do [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) wystąpienia w klonowania.</span><span class="sxs-lookup"><span data-stu-id="feab7-110">[out] A pointer to the [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) instance to be cloned.</span></span>

`strUser`   
<span data-ttu-id="feab7-111">[in] Nazwa użytkownika.</span><span class="sxs-lookup"><span data-stu-id="feab7-111">[in] The user name.</span></span> <span data-ttu-id="feab7-112">Zobacz [ConnectServerWmi](connectserverwmi.md) funkcji, aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="feab7-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="feab7-113">[in] Hasło.</span><span class="sxs-lookup"><span data-stu-id="feab7-113">[in] The password.</span></span> <span data-ttu-id="feab7-114">Zobacz [ConnectServerWmi](connectserverwmi.md) funkcji, aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="feab7-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="feab7-115">[in] Nazwa domeny użytkownika.</span><span class="sxs-lookup"><span data-stu-id="feab7-115">[in] The domain name of the user.</span></span> <span data-ttu-id="feab7-116">Zobacz [ConnectServerWmi](connectserverwmi.md) funkcji, aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="feab7-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="feab7-117">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="feab7-117">Return value</span></span>

<span data-ttu-id="feab7-118">Następujące wartości zwracane przez tę funkcję są zdefiniowane w *WbemCli.h* pliku nagłówka, lub należy je zdefiniować jako stałe w kodzie:</span><span class="sxs-lookup"><span data-stu-id="feab7-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="feab7-119">Stała</span><span class="sxs-lookup"><span data-stu-id="feab7-119">Constant</span></span>  |<span data-ttu-id="feab7-120">Wartość</span><span class="sxs-lookup"><span data-stu-id="feab7-120">Value</span></span>  |<span data-ttu-id="feab7-121">Opis</span><span class="sxs-lookup"><span data-stu-id="feab7-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="feab7-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="feab7-122">0x80041001</span></span> | <span data-ttu-id="feab7-123">Wystąpił błąd ogólny.</span><span class="sxs-lookup"><span data-stu-id="feab7-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="feab7-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="feab7-124">0x80041008</span></span> | <span data-ttu-id="feab7-125">Parametr jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="feab7-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="feab7-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="feab7-126">0x80041006</span></span> | <span data-ttu-id="feab7-127">Za mało pamięci ukończyć operacji.</span><span class="sxs-lookup"><span data-stu-id="feab7-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="feab7-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="feab7-128">0x80041015</span></span> | <span data-ttu-id="feab7-129">Procedury zdalnej łącze wywołań (procedur RPC) między bieżącym procesem a usługą WMI nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="feab7-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="feab7-130">0</span><span class="sxs-lookup"><span data-stu-id="feab7-130">0</span></span> | <span data-ttu-id="feab7-131">Wywołanie funkcji zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="feab7-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="feab7-132">Uwagi</span><span class="sxs-lookup"><span data-stu-id="feab7-132">Remarks</span></span>

<span data-ttu-id="feab7-133">Ta funkcja jest zawijana wywołanie [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) metody.</span><span class="sxs-lookup"><span data-stu-id="feab7-133">This function wraps a call to the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="feab7-134">Ta metoda powoduje, że tylko kopii "optymalne działania".</span><span class="sxs-lookup"><span data-stu-id="feab7-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="feab7-135">Ze względu na specyfikę dynamiczne wiele obiektów modelu wspólnych informacji jest to możliwe, że nowy moduł wyliczający nie wylicza ten sam zestaw obiektów jako modułu wyliczającego źródła.</span><span class="sxs-lookup"><span data-stu-id="feab7-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>  

<span data-ttu-id="feab7-136">Jeśli wystąpi błąd wywołania funkcji, można uzyskać dodatkowe informacje o błędzie przez wywołanie metody [GetErrorInfo](geterrorinfo.md) funkcji.</span><span class="sxs-lookup"><span data-stu-id="feab7-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="feab7-137">Przykład</span><span class="sxs-lookup"><span data-stu-id="feab7-137">Example</span></span>

<span data-ttu-id="feab7-138">Na przykład zobacz [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) metody.</span><span class="sxs-lookup"><span data-stu-id="feab7-138">For an example, see the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="feab7-139">Wymagania</span><span class="sxs-lookup"><span data-stu-id="feab7-139">Requirements</span></span>  
 <span data-ttu-id="feab7-140">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="feab7-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="feab7-141">**Nagłówek:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="feab7-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="feab7-142">**Wersje programu .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="feab7-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feab7-143">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="feab7-143">See also</span></span>  
[<span data-ttu-id="feab7-144">Liczniki wydajności (niezarządzany wykaz interfejsów API) i usługi WMI</span><span class="sxs-lookup"><span data-stu-id="feab7-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)