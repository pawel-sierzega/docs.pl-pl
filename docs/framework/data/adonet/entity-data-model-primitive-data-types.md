---
title: 'Modelu Entity Data Model: Typy danych pierwotnych'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7635168e-0566-4fdd-8391-7941b0d9f787
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0bfd6a1f2ab938468cc1aa02d6cf4b1eb4d7c530
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="entity-data-model-primitive-data-types"></a><span data-ttu-id="40577-102">Modelu Entity Data Model: Typy danych pierwotnych</span><span class="sxs-lookup"><span data-stu-id="40577-102">Entity Data Model: Primitive Data Types</span></span>
<span data-ttu-id="40577-103">Modelu danych jednostki (EDM) obsługuje zestaw typów danych pierwotnych abstrakcyjny (na przykład String, Boolean, Int32 i tak dalej), które są używane do definiowania [właściwości](../../../../docs/framework/data/adonet/property.md) w modelu koncepcyjnym.</span><span class="sxs-lookup"><span data-stu-id="40577-103">The Entity Data Model (EDM) supports a set of abstract primitive data types (such as String, Boolean, Int32, and so on) that are used to define [properties](../../../../docs/framework/data/adonet/property.md) in a conceptual model.</span></span> <span data-ttu-id="40577-104">Te typy danych pierwotnych są serwery proxy dla typów pierwotnych danych rzeczywistych, które są obsługiwane w środowisku macierzystym, takie jak bazy danych programu SQL Server lub środowisko uruchomieniowe języka wspólnego (CLR) lub magazynu.</span><span class="sxs-lookup"><span data-stu-id="40577-104">These primitive data types are proxies for actual primitive data types that are supported in the storage or hosting environment, such as a SQL Server database or the common language runtime (CLR).</span></span> <span data-ttu-id="40577-105">EDM nie definiuje semantykę operacje lub konwersji na typy pierwotne danych; Te semantyki są definiowane przez magazynu lub w środowisku macierzystym.</span><span class="sxs-lookup"><span data-stu-id="40577-105">The EDM does not define the semantics of operations or conversions over primitive data types; these semantics are defined by the storage or hosting environment.</span></span> <span data-ttu-id="40577-106">Zazwyczaj typów danych pierwotnych w EDM są mapowane odpowiednie typy pierwotne danych w pamięci masowej lub środowisku macierzystym.</span><span class="sxs-lookup"><span data-stu-id="40577-106">Typically, primitive data types in the EDM are mapped to corresponding primitive data types in the storage or hosting environment.</span></span> <span data-ttu-id="40577-107">Aby uzyskać informacje dotyczące sposobu mapowania programu Entity Framework typów pierwotnych w EDM do typów danych programu SQL Server, zobacz [SqlClient dla jednostki FrameworkTypes](../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span><span class="sxs-lookup"><span data-stu-id="40577-107">For information about how the Entity Framework maps primitive types in the EDM to SQL Server data types, see [SqlClient for Entity FrameworkTypes](../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40577-108">Nie obsługuje kolekcji typów danych pierwotnych EDM.</span><span class="sxs-lookup"><span data-stu-id="40577-108">The EDM does not support collections of primitive data types.</span></span>  
  
 <span data-ttu-id="40577-109">Aby uzyskać informacje o typach danych strukturalnych w EDM, zobacz [typu jednostki](../../../../docs/framework/data/adonet/entity-type.md) i [typu złożonego](../../../../docs/framework/data/adonet/complex-type.md).</span><span class="sxs-lookup"><span data-stu-id="40577-109">For information about structured data types in the EDM, see [entity type](../../../../docs/framework/data/adonet/entity-type.md) and [complex type](../../../../docs/framework/data/adonet/complex-type.md).</span></span>  
  
## <a name="primitive-data-types-supported-in-the-entity-data-model"></a><span data-ttu-id="40577-110">Typy pierwotne danych obsługiwane w modelu danych jednostki</span><span class="sxs-lookup"><span data-stu-id="40577-110">Primitive Data Types Supported in the Entity Data Model</span></span>  
 <span data-ttu-id="40577-111">W poniższej tabeli przedstawiono typy pierwotne danych obsługiwane przez EDM.</span><span class="sxs-lookup"><span data-stu-id="40577-111">The table below lists the primitive data types supported by the EDM.</span></span> <span data-ttu-id="40577-112">Podano również [aspekty](../../../../docs/framework/data/adonet/facet.md) który można zastosować do poszczególnych typów danych pierwotnych.</span><span class="sxs-lookup"><span data-stu-id="40577-112">The table also lists the [facets](../../../../docs/framework/data/adonet/facet.md) that can be applied to each primitive data type.</span></span>  
  
|<span data-ttu-id="40577-113">Typ danych pierwotnych</span><span class="sxs-lookup"><span data-stu-id="40577-113">Primitive Data Type</span></span>|<span data-ttu-id="40577-114">Opis</span><span class="sxs-lookup"><span data-stu-id="40577-114">Description</span></span>|<span data-ttu-id="40577-115">Zastosowanie aspektów</span><span class="sxs-lookup"><span data-stu-id="40577-115">Applicable Facets</span></span>|  
|-------------------------|-----------------|-----------------------|  
|<span data-ttu-id="40577-116">plików binarnych</span><span class="sxs-lookup"><span data-stu-id="40577-116">Binary</span></span>|<span data-ttu-id="40577-117">Zawiera dane binarne.</span><span class="sxs-lookup"><span data-stu-id="40577-117">Contains binary data.</span></span>|<span data-ttu-id="40577-118">Domyślna wartość parametru MaxLength, FixedLength wartości null,</span><span class="sxs-lookup"><span data-stu-id="40577-118">MaxLength, FixedLength, Nullable, Default</span></span>|  
|<span data-ttu-id="40577-119">Boolean</span><span class="sxs-lookup"><span data-stu-id="40577-119">Boolean</span></span>|<span data-ttu-id="40577-120">Zawiera wartość `true` lub `false`.</span><span class="sxs-lookup"><span data-stu-id="40577-120">Contains the value `true` or `false`.</span></span>|<span data-ttu-id="40577-121">Wartości null, domyślny</span><span class="sxs-lookup"><span data-stu-id="40577-121">Nullable, Default</span></span>|  
|<span data-ttu-id="40577-122">Byte</span><span class="sxs-lookup"><span data-stu-id="40577-122">Byte</span></span>|<span data-ttu-id="40577-123">Zawiera wartość bez znaku 8-bitową liczbą całkowitą.</span><span class="sxs-lookup"><span data-stu-id="40577-123">Contains an unsigned 8-bit integer value.</span></span>|<span data-ttu-id="40577-124">Dokładność wartości null, domyślny</span><span class="sxs-lookup"><span data-stu-id="40577-124">Precision, Nullable, Default</span></span>|  
|<span data-ttu-id="40577-125">DataGodzina</span><span class="sxs-lookup"><span data-stu-id="40577-125">DateTime</span></span>|<span data-ttu-id="40577-126">Reprezentuje datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="40577-126">Represents a date and time.</span></span>|<span data-ttu-id="40577-127">Dokładność wartości null, domyślny</span><span class="sxs-lookup"><span data-stu-id="40577-127">Precision, Nullable, Default</span></span>|  
|<span data-ttu-id="40577-128">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="40577-128">DateTimeOffset</span></span>|<span data-ttu-id="40577-129">Zawiera datę i godzinę jako przesunięcie w minutach od GMT.</span><span class="sxs-lookup"><span data-stu-id="40577-129">Contains a date and time as an offset in minutes from GMT.</span></span>|<span data-ttu-id="40577-130">Dokładność wartości null, domyślny</span><span class="sxs-lookup"><span data-stu-id="40577-130">Precision, Nullable, Default</span></span>|  
|<span data-ttu-id="40577-131">Wartość dziesiętna</span><span class="sxs-lookup"><span data-stu-id="40577-131">Decimal</span></span>|<span data-ttu-id="40577-132">Zawiera wartość liczbową ze stałym precyzję i skalę.</span><span class="sxs-lookup"><span data-stu-id="40577-132">Contains a numeric value with fixed precision and scale.</span></span>|<span data-ttu-id="40577-133">Dokładność wartości null, domyślny</span><span class="sxs-lookup"><span data-stu-id="40577-133">Precision, Nullable, Default</span></span>|  
|<span data-ttu-id="40577-134">Double</span><span class="sxs-lookup"><span data-stu-id="40577-134">Double</span></span>|<span data-ttu-id="40577-135">Zawiera zmiennoprzecinkowej numer z dokładnością do 15 cyfr.</span><span class="sxs-lookup"><span data-stu-id="40577-135">Contains a floating point number with 15 digit precision.</span></span>|<span data-ttu-id="40577-136">Dokładność wartości null, domyślny</span><span class="sxs-lookup"><span data-stu-id="40577-136">Precision, Nullable, Default</span></span>|  
|<span data-ttu-id="40577-137">Float</span><span class="sxs-lookup"><span data-stu-id="40577-137">Float</span></span>|<span data-ttu-id="40577-138">Zawiera zmiennoprzecinkowej numer dokładności 7 cyfr.</span><span class="sxs-lookup"><span data-stu-id="40577-138">Contains a floating point number with seven digit precision.</span></span>|<span data-ttu-id="40577-139">Dokładność wartości null, domyślny</span><span class="sxs-lookup"><span data-stu-id="40577-139">Precision, Nullable, Default</span></span>|  
|<span data-ttu-id="40577-140">Identyfikator GUID</span><span class="sxs-lookup"><span data-stu-id="40577-140">Guid</span></span>|<span data-ttu-id="40577-141">Zawiera unikatowy identyfikator 16 bajtów.</span><span class="sxs-lookup"><span data-stu-id="40577-141">Contains a 16-byte unique identifier.</span></span>|<span data-ttu-id="40577-142">Dokładność wartości null, domyślny</span><span class="sxs-lookup"><span data-stu-id="40577-142">Precision, Nullable, Default</span></span>|  
|<span data-ttu-id="40577-143">Int16</span><span class="sxs-lookup"><span data-stu-id="40577-143">Int16</span></span>|<span data-ttu-id="40577-144">Zawiera wartość całkowita 16-bitowych.</span><span class="sxs-lookup"><span data-stu-id="40577-144">Contains a signed 16-bit integer value.</span></span>|<span data-ttu-id="40577-145">Dokładność wartości null, domyślny</span><span class="sxs-lookup"><span data-stu-id="40577-145">Precision, Nullable, Default</span></span>|  
|<span data-ttu-id="40577-146">Int32</span><span class="sxs-lookup"><span data-stu-id="40577-146">Int32</span></span>|<span data-ttu-id="40577-147">Zawiera wartość całkowita 32-bitowa.</span><span class="sxs-lookup"><span data-stu-id="40577-147">Contains a signed 32-bit integer value.</span></span>|<span data-ttu-id="40577-148">Dokładność wartości null, domyślny</span><span class="sxs-lookup"><span data-stu-id="40577-148">Precision, Nullable, Default</span></span>|  
|<span data-ttu-id="40577-149">Int64</span><span class="sxs-lookup"><span data-stu-id="40577-149">Int64</span></span>|<span data-ttu-id="40577-150">Zawiera wartość całkowita 64-bitowa.</span><span class="sxs-lookup"><span data-stu-id="40577-150">Contains a signed 64-bit integer value.</span></span>|<span data-ttu-id="40577-151">Dokładność wartości null, domyślny</span><span class="sxs-lookup"><span data-stu-id="40577-151">Precision, Nullable, Default</span></span>|  
|<span data-ttu-id="40577-152">SByte</span><span class="sxs-lookup"><span data-stu-id="40577-152">SByte</span></span>|<span data-ttu-id="40577-153">Zawiera wartość całkowita 8-bitowa.</span><span class="sxs-lookup"><span data-stu-id="40577-153">Contains a signed 8-bit integer value.</span></span>|<span data-ttu-id="40577-154">Dokładność wartości null, domyślny</span><span class="sxs-lookup"><span data-stu-id="40577-154">Precision, Nullable, Default</span></span>|  
|<span data-ttu-id="40577-155">String</span><span class="sxs-lookup"><span data-stu-id="40577-155">String</span></span>|<span data-ttu-id="40577-156">Zawiera dane znaków.</span><span class="sxs-lookup"><span data-stu-id="40577-156">Contains character data.</span></span>|<span data-ttu-id="40577-157">Unicode, FixedLength, MaxLength, sortowania, dokładność, wartości null, domyślny</span><span class="sxs-lookup"><span data-stu-id="40577-157">Unicode, FixedLength, MaxLength, Collation, Precision, Nullable, Default</span></span>|  
|<span data-ttu-id="40577-158">Godzina</span><span class="sxs-lookup"><span data-stu-id="40577-158">Time</span></span>|<span data-ttu-id="40577-159">Zawiera pora dnia.</span><span class="sxs-lookup"><span data-stu-id="40577-159">Contains a time of day.</span></span>|<span data-ttu-id="40577-160">Dokładność wartości null, domyślny</span><span class="sxs-lookup"><span data-stu-id="40577-160">Precision, Nullable, Default</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40577-161">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="40577-161">See Also</span></span>  
 [<span data-ttu-id="40577-162">Kluczowe założenia modelu danych jednostki</span><span class="sxs-lookup"><span data-stu-id="40577-162">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="40577-163">Modelu danych jednostki</span><span class="sxs-lookup"><span data-stu-id="40577-163">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)