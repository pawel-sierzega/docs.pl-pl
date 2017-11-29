---
title: "&lt;bypasslist —&gt; — Element (ustawienia sieciowe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3d349f14535de806e0b130ef64b58333e63f1b86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltbypasslistgt-element-network-settings"></a><span data-ttu-id="f6523-102">&lt;bypasslist —&gt; — Element (ustawienia sieciowe)</span><span class="sxs-lookup"><span data-stu-id="f6523-102">&lt;bypasslist&gt; Element (Network Settings)</span></span>
<span data-ttu-id="f6523-103">Zawiera zestaw wyrażeń regularnych, opisujących adresów, które nie korzystają z serwera proxy.</span><span class="sxs-lookup"><span data-stu-id="f6523-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="f6523-104">\<Konfiguracja ></span><span class="sxs-lookup"><span data-stu-id="f6523-104">\<configuration></span></span>  
<span data-ttu-id="f6523-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="f6523-105">\<system.net></span></span>  
<span data-ttu-id="f6523-106">\<defaultProxy — ></span><span class="sxs-lookup"><span data-stu-id="f6523-106">\<defaultProxy></span></span>  
<span data-ttu-id="f6523-107">\<bypasslist — ></span><span class="sxs-lookup"><span data-stu-id="f6523-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6523-108">Składnia</span><span class="sxs-lookup"><span data-stu-id="f6523-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6523-109">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="f6523-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f6523-110">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="f6523-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6523-111">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="f6523-111">Attributes</span></span>  
 <span data-ttu-id="f6523-112">Brak.</span><span class="sxs-lookup"><span data-stu-id="f6523-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f6523-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="f6523-113">Child Elements</span></span>  
  
|<span data-ttu-id="f6523-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="f6523-114">**Element**</span></span>|<span data-ttu-id="f6523-115">**Opis**</span><span class="sxs-lookup"><span data-stu-id="f6523-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f6523-116">Dodaj</span><span class="sxs-lookup"><span data-stu-id="f6523-116">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="f6523-117">Dodaje adres IP lub nazwa DNS do Lista obejść serwerów proxy.</span><span class="sxs-lookup"><span data-stu-id="f6523-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="f6523-118">Wyczyść</span><span class="sxs-lookup"><span data-stu-id="f6523-118">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="f6523-119">Czyści listę obejścia.</span><span class="sxs-lookup"><span data-stu-id="f6523-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="f6523-120">Usuń</span><span class="sxs-lookup"><span data-stu-id="f6523-120">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="f6523-121">Usuwa adres IP lub nazwa DNS lista obejść serwerów proxy.</span><span class="sxs-lookup"><span data-stu-id="f6523-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f6523-122">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="f6523-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f6523-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="f6523-123">**Element**</span></span>|<span data-ttu-id="f6523-124">**Opis**</span><span class="sxs-lookup"><span data-stu-id="f6523-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f6523-125">defaultProxy —</span><span class="sxs-lookup"><span data-stu-id="f6523-125">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="f6523-126">Umożliwia skonfigurowanie serwera proxy protokołu HTTP (Hypertext Transfer).</span><span class="sxs-lookup"><span data-stu-id="f6523-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6523-127">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f6523-127">Remarks</span></span>  
 <span data-ttu-id="f6523-128">Lista obejść zawiera wyrażenia regularne, które opisują identyfikatorów URI który <xref:System.Net.WebRequest> wystąpień dostęp bezpośrednio zamiast z za pośrednictwem serwera proxy.</span><span class="sxs-lookup"><span data-stu-id="f6523-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="f6523-129">Należy zachować ostrożność podczas określania wyrażenia regularnego dla tego elementu.</span><span class="sxs-lookup"><span data-stu-id="f6523-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="f6523-130">Wyrażenie regularne "[a-z] +\\.contoso\\.com" dopasowań żadnego hosta w domenie contoso.com, ale również zgodna każdego hosta w domenie contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="f6523-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="f6523-131">Aby dopasować tylko na hoście w domenie contoso.com, użyj elementu zakotwiczenia ("$"): "[a-z] +\\.contoso\\.com$".</span><span class="sxs-lookup"><span data-stu-id="f6523-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="f6523-132">Aby uzyskać więcej informacji na temat wyrażeń regularnych Zobacz. [Wyrażeń regularnych programu .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f6523-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f6523-133">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="f6523-133">Configuration Files</span></span>  
 <span data-ttu-id="f6523-134">Ten element może być użyty w pliku konfiguracji aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f6523-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6523-135">Przykład</span><span class="sxs-lookup"><span data-stu-id="f6523-135">Example</span></span>  
 <span data-ttu-id="f6523-136">W następującym przykładzie dodano dwa adresy do obejścia listy.</span><span class="sxs-lookup"><span data-stu-id="f6523-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="f6523-137">Pierwszy pomija serwera proxy dla wszystkich serwerów w domenie contoso.com. drugi pomija serwera proxy dla wszystkich serwerom rozpocząć których adresy IP 192.168.</span><span class="sxs-lookup"><span data-stu-id="f6523-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6523-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f6523-138">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="f6523-139">Schemat ustawień sieci</span><span class="sxs-lookup"><span data-stu-id="f6523-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)