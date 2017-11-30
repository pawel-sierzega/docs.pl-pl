---
title: Bezpieczne konwersacje i bezpieczne sesje
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 6647ef8124279e9fc0b3049beb5c87f887125dfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="secure-conversations-and-secure-sessions"></a><span data-ttu-id="329cc-102">Bezpieczne konwersacje i bezpieczne sesje</span><span class="sxs-lookup"><span data-stu-id="329cc-102">Secure Conversations and Secure Sessions</span></span>
<span data-ttu-id="329cc-103">Funkcja [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] jest możliwość nawiązywania bezpiecznej sesji między dwoma punktami końcowymi, które wzajemne uwierzytelnianie i uzgodnić proces podpisów cyfrowych i szyfrowania.</span><span class="sxs-lookup"><span data-stu-id="329cc-103">A feature of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is the ability to establish secure sessions between two endpoints that authenticate each other and agree upon an encryption and digital signature process.</span></span> <span data-ttu-id="329cc-104">Na przykład punkt końcowy usługi może wymagać punktu końcowego klienta do wysyłania tokenu zabezpieczającego ustalane na podstawie certyfikatu X.509 do uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="329cc-104">For example, the service endpoint might require a client endpoint to send a security token based upon an X.509 certificate for authentication.</span></span> <span data-ttu-id="329cc-105">Po uwierzytelnieniu klient punktu końcowego usługi zwraca token kontekstu zabezpieczeń (SCT) do klienta, który jest następnie używany do zabezpieczania wszystkich kolejnych komunikatów w ramach sesji.</span><span class="sxs-lookup"><span data-stu-id="329cc-105">Once the client is authenticated, the service endpoint returns a security context token (SCT) back to the client that is then used to secure all subsequent messages within the session.</span></span> <span data-ttu-id="329cc-106">Ustanawianie tego bezpiecznej sesji umożliwia zestaw komunikatów, które są wymieniane między dwoma punktami końcowymi będzie bardziej wydajne, ponieważ SCT ma klucz symetryczny.</span><span class="sxs-lookup"><span data-stu-id="329cc-106">Establishing this secure session enables the set of messages that are exchanged between the two endpoints to be more efficient, because the SCT has a symmetric key.</span></span> <span data-ttu-id="329cc-107">Klucze asymetryczne certyfikatów X.509, które są ustalane, wymagają moc obliczeniową znacznie więcej niż kluczy symetrycznych podczas generowania podpisu cyfrowego lub szyfrowania zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="329cc-107">Asymmetric keys, which X.509 certificates are based upon, require significantly more computational power than symmetric keys when generating a digital signature or encrypting a set of data.</span></span>  
  
 <span data-ttu-id="329cc-108">Zasady ładowania początkowego (zdefiniowany w sekcji pkt 6.2.7 [WS-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817) standardowe) zawiera komunikat potwierdzenia zabezpieczeń używany do bezpiecznego kanału i uwierzytelnienia klienta przed RST/SCT i odpowiedź RSTR/SCT wymiany.</span><span class="sxs-lookup"><span data-stu-id="329cc-108">The bootstrap policy (defined in section 6.2.7 of the [WS-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817) standard) contains the message security assertions used to secure the channel and authenticate the client prior to the RST/SCT and RSTR/SCT exchange.</span></span> <span data-ttu-id="329cc-109">Niektóre [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] standardowe powiązania ma `Security.Message.EstablishSecurityContext` które kontrolki czy secure konwersacji jest używana.</span><span class="sxs-lookup"><span data-stu-id="329cc-109">Certain [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] standard bindings have a `Security.Message.EstablishSecurityContext` property which controls whether secure conversation is used.</span></span> <span data-ttu-id="329cc-110">Gdy przy użyciu niestandardowych powiązań ładowania początkowego jest wskazywana przez zagnieżdżenia elementy powiązania zabezpieczeń, za pośrednictwem [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) w pliku konfiguracji lub poprzez wywołanie <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> w kodzie.</span><span class="sxs-lookup"><span data-stu-id="329cc-110">When using custom bindings the bootstrap is indicated by nesting security binding elements, either through [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) in the configuration file, or by calling <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> in code.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="329cc-111">sesje, zobacz [sesji przy użyciu](../../../../docs/framework/wcf/using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="329cc-111"> sessions, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="329cc-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="329cc-112">See Also</span></span>  
 [<span data-ttu-id="329cc-113">Sesje, tworzenie wystąpień i współbieżność</span><span class="sxs-lookup"><span data-stu-id="329cc-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [<span data-ttu-id="329cc-114">Porady: Tworzenie usługi wymagającej użycia sesji</span><span class="sxs-lookup"><span data-stu-id="329cc-114">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)