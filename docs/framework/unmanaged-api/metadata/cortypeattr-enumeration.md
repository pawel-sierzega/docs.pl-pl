---
title: "CorTypeAttr — Wyliczenie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorTypeAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorTypeAttr
helpviewer_keywords: CorTypeAttr enumeration [.NET Framework metadata]
ms.assetid: 9bede0ec-5fdf-42a2-b5b7-bee64056acb6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ab9ce555406dfeb16f99601e6b88af2395c91ae0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="cortypeattr-enumeration"></a><span data-ttu-id="54bc1-102">CorTypeAttr — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="54bc1-102">CorTypeAttr Enumeration</span></span>
<span data-ttu-id="54bc1-103">Zawiera wartości, które wskazuje typ metadanych.</span><span class="sxs-lookup"><span data-stu-id="54bc1-103">Contains values that indicate type metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54bc1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="54bc1-104">Syntax</span></span>  
  
```  
typedef enum CorTypeAttr {  
  
    tdVisibilityMask        =   0x00000007,  
    tdNotPublic             =   0x00000000,  
    tdPublic                =   0x00000001,  
    tdNestedPublic          =   0x00000002,  
    tdNestedPrivate         =   0x00000003,  
    tdNestedFamily          =   0x00000004,  
    tdNestedAssembly        =   0x00000005,  
    tdNestedFamANDAssem     =   0x00000006,  
    tdNestedFamORAssem      =   0x00000007,  
  
    tdLayoutMask            =   0x00000018,  
    tdAutoLayout            =   0x00000000,  
    tdSequentialLayout      =   0x00000008,  
    tdExplicitLayout        =   0x00000010,  
  
    tdClassSemanticsMask    =   0x00000020,  
    tdClass                 =   0x00000000,  
    tdInterface             =   0x00000020,  
  
    tdAbstract              =   0x00000080,  
    tdSealed                =   0x00000100,  
    tdSpecialName           =   0x00000400,  
  
    tdImport                =   0x00001000,  
    tdSerializable          =   0x00002000,  
    tdWindowsRuntime        =   0x00004000,  
  
    tdStringFormatMask      =   0x00030000,  
    tdAnsiClass             =   0x00000000,  
    tdUnicodeClass          =   0x00010000,  
    tdAutoClass             =   0x00020000,  
    tdCustomFormatClass     =   0x00030000,  
    tdCustomFormatMask      =   0x00C00000,  
  
    tdBeforeFieldInit       =   0x00100000,  
    tdForwarder             =   0x00200000,  
  
    tdReservedMask          =   0x00040800,  
    tdRTSpecialName         =   0x00000800,  
    tdHasSecurity           =   0x00040000,  
  
} CorTypeAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="54bc1-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="54bc1-105">Members</span></span>  
  
|<span data-ttu-id="54bc1-106">Element członkowski</span><span class="sxs-lookup"><span data-stu-id="54bc1-106">Member</span></span>|<span data-ttu-id="54bc1-107">Opis</span><span class="sxs-lookup"><span data-stu-id="54bc1-107">Description</span></span>|  
|------------|-----------------|  
|`tdVisibilityMask`|<span data-ttu-id="54bc1-108">Używać dla informacji o typie widoczności.</span><span class="sxs-lookup"><span data-stu-id="54bc1-108">Used for type visibility information.</span></span>|  
|`tdNotPublic`|<span data-ttu-id="54bc1-109">Określa, że typ nie jest w zakresie publicznego.</span><span class="sxs-lookup"><span data-stu-id="54bc1-109">Specifies that the type is not in public scope.</span></span>|  
|`tdPublic`|<span data-ttu-id="54bc1-110">Określa, czy ten typ jest publiczny zakresu.</span><span class="sxs-lookup"><span data-stu-id="54bc1-110">Specifies that the type is in public scope.</span></span>|  
|`tdNestedPublic`|<span data-ttu-id="54bc1-111">Określa, że typ jest zagnieżdżony z widoczności publicznej.</span><span class="sxs-lookup"><span data-stu-id="54bc1-111">Specifies that the type is nested with public visibility.</span></span>|  
|`tdNestedPrivate`|<span data-ttu-id="54bc1-112">Określa, że typ jest zagnieżdżony z widoczności prywatnej.</span><span class="sxs-lookup"><span data-stu-id="54bc1-112">Specifies that the type is nested with private visibility.</span></span>|  
|`tdNestedFamily`|<span data-ttu-id="54bc1-113">Określa, że typ jest zagnieżdżony z rodziny widoczności.</span><span class="sxs-lookup"><span data-stu-id="54bc1-113">Specifies that the type is nested with family visibility.</span></span>|  
|`tdNestedAssembly`|<span data-ttu-id="54bc1-114">Określa, że typ jest zagnieżdżony z widoczność zestawu.</span><span class="sxs-lookup"><span data-stu-id="54bc1-114">Specifies that the type is nested with assembly visibility.</span></span>|  
|`tdNestedFamANDAssem`|<span data-ttu-id="54bc1-115">Określa, że typ jest zagnieżdżony z widocznością rodziny i zestawu.</span><span class="sxs-lookup"><span data-stu-id="54bc1-115">Specifies that the type is nested with family and assembly visibility.</span></span>|  
|`tdNestedFamORAssem`|<span data-ttu-id="54bc1-116">Określa, że typ jest zagnieżdżony z widocznością rodziny lub zestawu.</span><span class="sxs-lookup"><span data-stu-id="54bc1-116">Specifies that the type is nested with family or assembly visibility.</span></span>|  
|`tdLayoutMask`|<span data-ttu-id="54bc1-117">Pobiera informacje o układzie dla typu.</span><span class="sxs-lookup"><span data-stu-id="54bc1-117">Gets layout information for the type.</span></span>|  
|`tdAutoLayout`|<span data-ttu-id="54bc1-118">Określa, że pola tego typu są automatycznie układu.</span><span class="sxs-lookup"><span data-stu-id="54bc1-118">Specifies that the fields of this type are laid out automatically.</span></span>|  
|`tdSequentialLayout`|<span data-ttu-id="54bc1-119">Określa, że pola tego typu układ sekwencyjnie.</span><span class="sxs-lookup"><span data-stu-id="54bc1-119">Specifies that the fields of this type are laid out sequentially.</span></span>|  
|`tdExplicitLayout`|<span data-ttu-id="54bc1-120">Określa, że jest dostarczana układ tego pola.</span><span class="sxs-lookup"><span data-stu-id="54bc1-120">Specifies that field layout is supplied explicitly.</span></span>|  
|`tdClassSemanticsMask`|<span data-ttu-id="54bc1-121">Pobiera informacje semantyczne o typie.</span><span class="sxs-lookup"><span data-stu-id="54bc1-121">Gets semantic information about the type.</span></span>|  
|`tdClass`|<span data-ttu-id="54bc1-122">Określa, że typ jest klasą.</span><span class="sxs-lookup"><span data-stu-id="54bc1-122">Specifies that the type is a class.</span></span>|  
|`tdInterface`|<span data-ttu-id="54bc1-123">Określa, czy ten typ jest interfejsem.</span><span class="sxs-lookup"><span data-stu-id="54bc1-123">Specifies that the type is an interface.</span></span>|  
|`tdAbstract`|<span data-ttu-id="54bc1-124">Określa, że typ jest abstrakcyjny.</span><span class="sxs-lookup"><span data-stu-id="54bc1-124">Specifies that the type is abstract.</span></span>|  
|`tdSealed`|<span data-ttu-id="54bc1-125">Określa, że typ nie może zostać rozszerzony.</span><span class="sxs-lookup"><span data-stu-id="54bc1-125">Specifies that the type cannot be extended.</span></span>|  
|`tdSpecialName`|<span data-ttu-id="54bc1-126">Określa, że nazwa klasy jest specjalne.</span><span class="sxs-lookup"><span data-stu-id="54bc1-126">Specifies that the class name is special.</span></span> <span data-ttu-id="54bc1-127">Jego nazwa opisuje sposób.</span><span class="sxs-lookup"><span data-stu-id="54bc1-127">Its name describes how.</span></span>|  
|`tdImport`|<span data-ttu-id="54bc1-128">Określa, że typ jest zaimportowany.</span><span class="sxs-lookup"><span data-stu-id="54bc1-128">Specifies that the type is imported.</span></span>|  
|`tdSerializable`|<span data-ttu-id="54bc1-129">Określa, czy ten typ jest możliwy do serializacji.</span><span class="sxs-lookup"><span data-stu-id="54bc1-129">Specifies that the type is serializable.</span></span>|  
|`tdWindowsRuntime`|<span data-ttu-id="54bc1-130">Określa, że ten typ jest [!INCLUDE[wrt](../../../../includes/wrt-md.md)] typu.</span><span class="sxs-lookup"><span data-stu-id="54bc1-130">Specifies that this type is a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`tdStringFormatMask`|<span data-ttu-id="54bc1-131">Pobiera informacje o sposób kodowania i sformatowany ciągów.</span><span class="sxs-lookup"><span data-stu-id="54bc1-131">Gets information about how strings are encoded and formatted.</span></span>|  
|`tdAnsiClass`|<span data-ttu-id="54bc1-132">Określa, że ten typ interpretacji LPTSTR jako ANSI.</span><span class="sxs-lookup"><span data-stu-id="54bc1-132">Specifies that this type interprets an LPTSTR as ANSI.</span></span>|  
|`tdUnicodeClass`|<span data-ttu-id="54bc1-133">Określa, że ten typ interpretacji LPTSTR jako Unicode.</span><span class="sxs-lookup"><span data-stu-id="54bc1-133">Specifies that this type interprets an LPTSTR as Unicode.</span></span>|  
|`tdAutoClass`|<span data-ttu-id="54bc1-134">Określa, że ten typ interpretacji LPTSTR automatycznie.</span><span class="sxs-lookup"><span data-stu-id="54bc1-134">Specifies that this type interprets an LPTSTR automatically.</span></span>|  
|`tdCustomFormatClass`|<span data-ttu-id="54bc1-135">Określa, że typ ma niestandardowy kodowania, zgodnie z określonym `CustomFormatMask`.</span><span class="sxs-lookup"><span data-stu-id="54bc1-135">Specifies that the type has a non-standard encoding, as specified by `CustomFormatMask`.</span></span>|  
|`tdCustomFormatMask`|<span data-ttu-id="54bc1-136">Użyj tę maskę, aby pobrać niestandardowych informacji kodowania dla międzyoperacyjności z modelem natywnego.</span><span class="sxs-lookup"><span data-stu-id="54bc1-136">Use this mask to get non-standard encoding information for native interop.</span></span> <span data-ttu-id="54bc1-137">Znaczenie tej wartości te dwie usługi BITS jest nieokreślony.</span><span class="sxs-lookup"><span data-stu-id="54bc1-137">The meaning of the values of these two bits is unspecified.</span></span>|  
|`tdBeforeFieldInit`|<span data-ttu-id="54bc1-138">Określa, że typ musi zostać zainicjowany przed pierwsza próba uzyskania dostępu do statycznego pola.</span><span class="sxs-lookup"><span data-stu-id="54bc1-138">Specifies that the type must be initialized before the first attempt to access a static field.</span></span>|  
|`tdForwarder`|<span data-ttu-id="54bc1-139">Określa, że typ jest eksportowany, a usługi przesyłania dalej typu.</span><span class="sxs-lookup"><span data-stu-id="54bc1-139">Specifies that the type is exported, and a type forwarder.</span></span>|  
|`tdReservedMask`|<span data-ttu-id="54bc1-140">Ta flaga i flagi poniżej są używane wewnętrznie przez środowisko uruchomieniowe języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="54bc1-140">This flag and the flags below are used internally by the common language runtime.</span></span>|  
|`tdRTSpecialName`|<span data-ttu-id="54bc1-141">Określa, że środowisko uruchomieniowe języka wspólnego ma sprawdzać kodowanie nazwy.</span><span class="sxs-lookup"><span data-stu-id="54bc1-141">Specifies that the common language runtime should check the name encoding.</span></span>|  
|`tdHasSecurity`|<span data-ttu-id="54bc1-142">Określa, że typ ma zabezpieczeń skojarzonych z nim.</span><span class="sxs-lookup"><span data-stu-id="54bc1-142">Specifies that the type has security associated with it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="54bc1-143">Wymagania</span><span class="sxs-lookup"><span data-stu-id="54bc1-143">Requirements</span></span>  
 <span data-ttu-id="54bc1-144">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54bc1-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54bc1-145">**Nagłówek:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="54bc1-145">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="54bc1-146">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54bc1-146">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54bc1-147">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="54bc1-147">See Also</span></span>  
 [<span data-ttu-id="54bc1-148">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="54bc1-148">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)