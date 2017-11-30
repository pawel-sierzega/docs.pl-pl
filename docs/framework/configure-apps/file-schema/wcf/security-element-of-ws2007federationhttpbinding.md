---
title: '&lt;security&gt; w &lt;ws2007FederationHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 79976b015f35bdd71a5f95a018d85c0ba41ce0b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="5c1b5-102">&lt;security&gt; w &lt;ws2007FederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="5c1b5-102">&lt;security&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="5c1b5-103">Definiuje ustawienia zabezpieczeń [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="5c1b5-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5c1b5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5c1b5-105">\<powiązania ></span><span class="sxs-lookup"><span data-stu-id="5c1b5-105">\<bindings></span></span>  
<span data-ttu-id="5c1b5-106">\<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="5c1b5-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="5c1b5-107">\<Powiązanie ></span><span class="sxs-lookup"><span data-stu-id="5c1b5-107">\<binding></span></span>  
<span data-ttu-id="5c1b5-108">\<Zabezpieczenia ></span><span class="sxs-lookup"><span data-stu-id="5c1b5-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c1b5-109">Składnia</span><span class="sxs-lookup"><span data-stu-id="5c1b5-109">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>  
    <binding >  
        <security mode="None/Message/TransportWithMessageCredential">  
           <message negotiateServiceCredential="Boolean"  
                algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/ Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                defaultProtectionLevel="none/sign/EncryptAndSign"   
                issuedTokenType="string"   
                issuedKeyType="SymmetricKey/PublicKey"  
           </message>  
        </security>  
    </binding>  
</ws2007FederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c1b5-110">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="5c1b5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5c1b5-111">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c1b5-112">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="5c1b5-112">Attributes</span></span>  
  
|<span data-ttu-id="5c1b5-113">Atrybut</span><span class="sxs-lookup"><span data-stu-id="5c1b5-113">Attribute</span></span>|<span data-ttu-id="5c1b5-114">Opis</span><span class="sxs-lookup"><span data-stu-id="5c1b5-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="5c1b5-115">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-115">Optional.</span></span> <span data-ttu-id="5c1b5-116">Określa typ zabezpieczeń, która została zastosowana.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="5c1b5-117">Wartość domyślna to `Message`.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-117">The default value is `Message`.</span></span> <span data-ttu-id="5c1b5-118">Ten atrybut jest typu <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="5c1b5-119">Tryb atrybutu</span><span class="sxs-lookup"><span data-stu-id="5c1b5-119">mode Attribute</span></span>  
  
|<span data-ttu-id="5c1b5-120">Wartość</span><span class="sxs-lookup"><span data-stu-id="5c1b5-120">Value</span></span>|<span data-ttu-id="5c1b5-121">Opis</span><span class="sxs-lookup"><span data-stu-id="5c1b5-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5c1b5-122">Brak</span><span class="sxs-lookup"><span data-stu-id="5c1b5-122">None</span></span>|<span data-ttu-id="5c1b5-123">Komunikatu protokołu SOAP nie jest bezpieczne podczas przesyłania.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="5c1b5-124">Komunikat</span><span class="sxs-lookup"><span data-stu-id="5c1b5-124">Message</span></span>|<span data-ttu-id="5c1b5-125">Korzystanie z zabezpieczeń komunikatów SOAP są udostępniane integralności, poufność, uwierzytelnianie serwera i uwierzytelnianie klienta.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="5c1b5-126">Domyślnie treści zostaje zaszyfrowany i podpisany.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="5c1b5-127">Usługa musi być skonfigurowana przy użyciu certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="5c1b5-128">Uwierzytelnianie klienta jest oparta na token wystawiony do klienta przez usługę tokenu zabezpieczającego.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="5c1b5-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="5c1b5-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="5c1b5-130">Uwierzytelnianie integralności i poufności serwera są udostępniane przez protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="5c1b5-131">Usługa musi być skonfigurowana przy użyciu certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="5c1b5-132">Uwierzytelnianie klienta jest dostarczany za pomocą zabezpieczeń wiadomości SOAP i opierają się na token wystawiony do klienta przez usługę tokenu zabezpieczającego.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c1b5-133">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="5c1b5-133">Child Elements</span></span>  
  
|<span data-ttu-id="5c1b5-134">Element</span><span class="sxs-lookup"><span data-stu-id="5c1b5-134">Element</span></span>|<span data-ttu-id="5c1b5-135">Opis</span><span class="sxs-lookup"><span data-stu-id="5c1b5-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c1b5-136">\<komunikat ></span><span class="sxs-lookup"><span data-stu-id="5c1b5-136">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="5c1b5-137">Definiuje ustawienia zabezpieczeń na poziomie wiadomości.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="5c1b5-138">Ten element jest typu <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="5c1b5-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c1b5-139">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="5c1b5-139">Parent Elements</span></span>  
  
|<span data-ttu-id="5c1b5-140">Element</span><span class="sxs-lookup"><span data-stu-id="5c1b5-140">Element</span></span>|<span data-ttu-id="5c1b5-141">Opis</span><span class="sxs-lookup"><span data-stu-id="5c1b5-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c1b5-142">\<Powiązanie ></span><span class="sxs-lookup"><span data-stu-id="5c1b5-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="5c1b5-143">Definiuje wszystkie możliwości powiązania [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="5c1b5-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c1b5-144">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5c1b5-144">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="5c1b5-145">Porady: tworzenie WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="5c1b5-145">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="5c1b5-146">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="5c1b5-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="5c1b5-147">Wybieranie typu poświadczeń</span><span class="sxs-lookup"><span data-stu-id="5c1b5-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="5c1b5-148">Powiązania</span><span class="sxs-lookup"><span data-stu-id="5c1b5-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="5c1b5-149">Konfigurowanie powiązań dostarczanych przez System</span><span class="sxs-lookup"><span data-stu-id="5c1b5-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="5c1b5-150">Konfigurowanie usług Windows Communication Foundation i klientów za pomocą powiązań</span><span class="sxs-lookup"><span data-stu-id="5c1b5-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="5c1b5-151">\<Powiązanie ></span><span class="sxs-lookup"><span data-stu-id="5c1b5-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)