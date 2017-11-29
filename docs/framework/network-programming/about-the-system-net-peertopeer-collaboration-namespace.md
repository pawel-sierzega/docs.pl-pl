---
title: "Namespace System.Net.PeerToPeer.Collaboration — informacje"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5d8c1c1-6844-4947-9759-c7f1b564bded
caps.latest.revision: "4"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 696b1d3dd7312b52c28f11f64f007c29fb8a94b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="about-the-systemnetpeertopeercollaboration-namespace"></a><span data-ttu-id="38f08-102">Namespace System.Net.PeerToPeer.Collaboration — informacje</span><span class="sxs-lookup"><span data-stu-id="38f08-102">About the System.Net.PeerToPeer.Collaboration Namespace</span></span>
<span data-ttu-id="38f08-103"><xref:System.Net.PeerToPeer.Collaboration> Przestrzeń nazw zawiera klasy i interfejsy API, które są używane do wykonywania działań współpracy elementów równorzędnych przy użyciu infrastruktury współpracy Peer-to-Peer.</span><span class="sxs-lookup"><span data-stu-id="38f08-103">The <xref:System.Net.PeerToPeer.Collaboration> namespace provides classes and APIs that are used to implement peer collaboration activities using the Peer-to-Peer Collaboration Infrastructure.</span></span>  
  
## <a name="classes"></a><span data-ttu-id="38f08-104">Klasy</span><span class="sxs-lookup"><span data-stu-id="38f08-104">Classes</span></span>  
 <span data-ttu-id="38f08-105">Klasy głównym zastosowany w implementacji działania współpracy Peer-to-Peer są:</span><span class="sxs-lookup"><span data-stu-id="38f08-105">The main classes used in the implementation of a Peer-to-Peer Collaboration activity are:</span></span>  
  
-   <span data-ttu-id="38f08-106"><xref:System.Net.PeerToPeer.Collaboration.ContactManager>, Które mogą służyć do przechowywania elementów równorzędnych kontaktów.</span><span class="sxs-lookup"><span data-stu-id="38f08-106">The <xref:System.Net.PeerToPeer.Collaboration.ContactManager>, which can be used to store peer contacts.</span></span>  
  
-   <span data-ttu-id="38f08-107"><xref:System.Net.PeerToPeer.Collaboration.PeerApplication> Umożliwiającym współpracę, takie jak gry, klient rozmów lub konferencji rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="38f08-107">The <xref:System.Net.PeerToPeer.Collaboration.PeerApplication> in which to collaborate, such as a game, chat client, or conferencing solution.</span></span>  
  
-   <span data-ttu-id="38f08-108">Elementów równorzędnych, które będą współpracować w działaniu.</span><span class="sxs-lookup"><span data-stu-id="38f08-108">The peers that will be collaborating in an activity.</span></span>  <span data-ttu-id="38f08-109">Tych elementów równorzędnych może być reprezentowana jako <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe>, lub <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint> obiektów.</span><span class="sxs-lookup"><span data-stu-id="38f08-109">These peers can be represented as <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe>, or <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint> objects.</span></span>  
  
-   <span data-ttu-id="38f08-110">Statycznych <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> klasy siebie, który określa, które aplikacje są dostępne i komputerów równorzędnych uczestniczą w nich.</span><span class="sxs-lookup"><span data-stu-id="38f08-110">The static <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> class itself, which specifies which applications are available and which peers are participating in them.</span></span>  
  
 <span data-ttu-id="38f08-111"><xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> Metody są używane z zaproszeniem dla elementów równorzędnych do sesji współpracy.</span><span class="sxs-lookup"><span data-stu-id="38f08-111">The <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> methods are used to invite peers to a collaboration session.</span></span>  <span data-ttu-id="38f08-112">Wywołanie elementu równorzędnego mogą subskrybować innego elementu równorzędnego dla zdarzeń, że aktualizacje sygnał do aplikacji, obiektów lub obecności informacji powiązane z sesją współpracy.</span><span class="sxs-lookup"><span data-stu-id="38f08-112">A calling peer can subscribe to another peer for events that signal updates to application, object, or presence information affiliated with the collaboration session.</span></span> <span data-ttu-id="38f08-113">Określ klasy obecności czy <xref:System.Net.PeerToPeer.Collaboration.Peer> jest dostępny do współpracy i <xref:System.Net.PeerToPeer.Collaboration.PeerScope> klasa jest używana do określania, ile udział jest dozwolone dla elementu równorzędnego: <xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet> (globalne) <xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe>, (podsieć) lub <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None>.</span><span class="sxs-lookup"><span data-stu-id="38f08-113">Presence classes specify whether a <xref:System.Net.PeerToPeer.Collaboration.Peer> is available for collaboration, and the <xref:System.Net.PeerToPeer.Collaboration.PeerScope> class is used to specify how much participation is allowed for a peer:  <xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet> (global), <xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe>, (subnet) or <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None>.</span></span>  
  
 <span data-ttu-id="38f08-114">Sesję współpracy składa się z czterech etapów:</span><span class="sxs-lookup"><span data-stu-id="38f08-114">A collaboration session is comprised of four steps:</span></span>  
  
-   <span data-ttu-id="38f08-115">Odnajdywanie.</span><span class="sxs-lookup"><span data-stu-id="38f08-115">Discovery.</span></span> <span data-ttu-id="38f08-116">Wykrywanie i publikowania aplikacji, elementów równorzędnych i informacji o obecności.</span><span class="sxs-lookup"><span data-stu-id="38f08-116">Discover or publish applications, peers, and presence information.</span></span>  <span data-ttu-id="38f08-117">Na przykład znaleźć inne osoby w podsieci lokalnej, który ma tego samego gier zainstalowanych.</span><span class="sxs-lookup"><span data-stu-id="38f08-117">For instance, find other people on the local subnet that have the same games installed.</span></span>  
  
-   <span data-ttu-id="38f08-118">Zaproszenia.</span><span class="sxs-lookup"><span data-stu-id="38f08-118">Invitation.</span></span> <span data-ttu-id="38f08-119">Wysyłanie i zaakceptować bezpiecznego zaproszeń do zdalnego peer(s) start lub dołączyć <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> sesji.</span><span class="sxs-lookup"><span data-stu-id="38f08-119">Send and accept secure invitations for remote peer(s) to start or join <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> sessions.</span></span>  
  
-   <span data-ttu-id="38f08-120">Skontaktuj się z zarządzania.</span><span class="sxs-lookup"><span data-stu-id="38f08-120">Contact Management.</span></span> <span data-ttu-id="38f08-121">Dodawanie odnalezionych elementów równorzędnych jako kontakt <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.</span><span class="sxs-lookup"><span data-stu-id="38f08-121">Add discovered peers as a contact to a <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.</span></span>  
  
-   <span data-ttu-id="38f08-122">Komunikacji.</span><span class="sxs-lookup"><span data-stu-id="38f08-122">Communication.</span></span> <span data-ttu-id="38f08-123">Po nawiązaniu komunikacji, użyj <xref:System.Net> interfejsów API, <xref:System.Net.PeerToPeer> interfejsu API lub klasy kanału równorzędnego Foundation komunikacji Windows wielopartyjnej komunikacji.</span><span class="sxs-lookup"><span data-stu-id="38f08-123">When communication is established, use the <xref:System.Net> APIs, the <xref:System.Net.PeerToPeer> API, or the Windows Communication Foundation Peer Channel classes for multiparty communications.</span></span>  
  
 <span data-ttu-id="38f08-124">Na przykład równorzędnej hosta uruchamia sesję współpracy i korzysta z <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> metody w celu dodania komputer zdalny, a jeden z jego elementów równorzędnych w lokalnej elementu równorzędnego hosta do menedżera kontaktu.</span><span class="sxs-lookup"><span data-stu-id="38f08-124">For example, the host peer starts a collaboration session, and utilizes the <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> method to add a remote peer and one of its local peers to the Contact Manager of the host peer.</span></span>  <span data-ttu-id="38f08-125">Trzech użytkowników będzie następnie uczestniczyć w sesji współpracy prywatnych.</span><span class="sxs-lookup"><span data-stu-id="38f08-125">The three users will then participate in their own private collaboration session.</span></span>  
  
 <span data-ttu-id="38f08-126">Typowe aplikacje P2P: konferencji współpracy notatek lub whiteboarding, aplikacji niekorzystającą rozmowy, interakcyjne anonsów i sesje gier online.</span><span class="sxs-lookup"><span data-stu-id="38f08-126">Typical P2P applications are: conference calls for collaborative note-taking or whiteboarding, serverless chat applications, interactive advertisements, and online gaming sessions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38f08-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="38f08-127">See Also</span></span>  
 <xref:System.Net.PeerToPeer.Collaboration>