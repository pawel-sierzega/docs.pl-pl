---
title: "IMetaDataImport::GetFieldProps — Metoda"
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
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7785ea6beaa882e72d200ef559ba75538224091d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetfieldprops-method"></a>IMetaDataImport::GetFieldProps — Metoda
Pobiera metadane skojarzone z polem odwołuje się określony FieldDef token.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,   
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `mb`  
 [in] Token FieldDef, który reprezentuje pole, aby pobrać skojarzone metadane.  
  
 `pClass`  
 [out] Wskaźnik do tokenu — TypeDef, który reprezentuje typ pola należącego do klasy.  
  
 `szField`  
 [out] Nazwa pola.  
  
 `cchField`  
 [in] Rozmiar w znaki dwubajtowe buforu dla *szField*.  
  
 `pchField`  
 [out] Rzeczywisty rozmiar buforu zwrócony.  
  
 `pdwAttr`  
 [out] Flagi skojarzone z metadanymi pola.  
  
 `ppvSigBlob`  
 [in] Wskaźnik do wartości binarne metadanych, opisujący pola.  
  
 `pcbSigBlob`  
 [out] Wyrażony w bajtach rozmiar `ppvSigBlob`.  
  
 `pdwCPlusTypeFlag`  
 [out] Flaga, która określa typ wartości pola.  
  
 `ppValue`  
 [out] Stała wartość dla pola.  
  
 `pcchValue`  
 [out] Rozmiar znaków z `ppValue`, lub zero, jeśli ciąg nie istnieje.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** Cor.h  
  
 **Biblioteka:** uwzględnione jako zasób w MsCorEE.dll  
  
 **Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [IMetaDataImport, interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2, interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
