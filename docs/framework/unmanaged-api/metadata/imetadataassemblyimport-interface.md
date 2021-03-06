---
title: "IMetaDataAssemblyImport — Interfejs"
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
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 992b588d16bc221f6b72044da40d09fbb6894511
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimport-interface"></a>IMetaDataAssemblyImport — Interfejs
Udostępnia metody dostępu i sprawdź zawartość manifest zestawu.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[CloseEnum, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|Zwalnia dojścia do określonego modułu wyliczającego.|  
|[EnumAssemblyRefs, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|Pobiera wskaźnika interfejsu, aby moduł wyliczający, który zawiera `mdAssemblyRef` tokeny zestawów odwołuje się zestaw w bieżącym zakresie metadanych.|  
|[EnumExportedTypes, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|Pobiera wskaźnika interfejsu, aby moduł wyliczający, który zawiera `mdExportedType` tokeny typów COM odwołuje się zestaw w bieżącym zakresie metadanych.|  
|[EnumFiles, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|Pobiera wskaźnika interfejsu, aby moduł wyliczający, który zawiera `mdFile` tokeny plików odwołuje się zestaw w bieżącym zakresie metadanych.|  
|[EnumManifestResources, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|Pobiera wskaźnika interfejsu, aby moduł wyliczający, który zawiera `mdManifestResource` tokenów zasobów odwołuje się zestaw w bieżącym zakresie metadanych.|  
|[FindAssembliesByName, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|Pobiera tablicę `mdAssemblyRef` tokeny dla zestawów o określonej nazwie.|  
|[FindExportedTypeByName, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|Pobiera `mdExportedType` tokenu dla typu modelu COM o określonej nazwie.|  
|[FindManifestResourceByName, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|Pobiera `mdManifestResource` tokenu dla zasobu o określonej nazwie.|  
|[GetAssemblyFromScope, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|Pobiera token dla zestawu w bieżącym zakresie metadanych.|  
|[GetAssemblyProps, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|Pobiera ustawienia właściwości określonego zestawu.|  
|[GetAssemblyRefProps, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|Pobiera ustawienia właściwości określonego `mdAssemblyRef` tokenu.|  
|[GetExportedTypeProps, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|Pobiera ustawienia właściwości określonego typu modelu COM.|  
|[GetFileProps, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|Pobiera ustawienia właściwości określonego pliku.|  
|[GetManifestResourceProps, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|Pobiera ustawienia właściwości określonego zasobu manifestu.|  
  
## <a name="requirements"></a>Wymagania  
 **Platforma:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** Cor.h  
  
 **Biblioteka:** używany jako zasób w MsCorEE.dll  
  
 **Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [Interfejsy metadanych](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataAssemblyEmit, interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
