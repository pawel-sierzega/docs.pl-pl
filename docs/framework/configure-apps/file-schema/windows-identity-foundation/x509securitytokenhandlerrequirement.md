---
title: '&lt;x509SecurityTokenHandlerRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7cb9eb1e7e80837e8036a8241a3a6bd679ed5e11
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="ltx509securitytokenhandlerrequirementgt"></a>&lt;x509SecurityTokenHandlerRequirement&gt;
Zapewnia opcjonalne konfigurację <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> klasy lub klas pochodnych.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<Dodaj >  
\<x509SecurityTokenHandlerRequirement >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|tryb certificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode> Wartość, która określa tryb walidacji do użycia na potrzeby certyfikatów X.509. Wartość domyślna to "PeerOrChainTrust".|  
|mapToWindows|Określa, czy programu obsługi tokenów należy mapować sprawdzania poprawności tokenu konto systemu Windows przy użyciu nazwy UPN oświadczenia przychodzącego. Wartość domyślna to "false".|  
|revocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wartość, która określa tryb odwołania dla certyfikatu X.509. Wartość domyślna to "Online".|  
|trustedStoreLocation|A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> wartość, która określa magazynu certyfikatu X.509. Wartością domyślną jest "Komputer lokalny".|  
|certificateValidator|Typ niestandardowy, która jest pochodną <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Jeśli `certificateValidationMode` atrybutu jest "Custom", wystąpienie tego typu jest używany do sprawdzania poprawności wystawcy certyfikatu.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<Dodaj >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Dodaje określony zabezpieczenia programu obsługi tokenów do kolekcji programu obsługi tokenów.|  
  
## <a name="example"></a>Przykład  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
