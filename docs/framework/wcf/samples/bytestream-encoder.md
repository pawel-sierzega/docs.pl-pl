---
title: Koder elementu ByteStream
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: de6d5fd64046a72eb6a21b43dd977463f5619850
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="bytestream-encoder"></a>Koder elementu ByteStream
Ten przykład przedstawia sposób tworzenia `ByteStreamHttpBinding`, <xref:System.ServiceModel.Channels.Binding> który prezentuje działanie funkcji kodera strumienia bajtów.  
  
## <a name="discussion"></a>Omówienie  
 Ten przykład przedstawia sposób tworzenia standardowego <xref:System.ServiceModel.Channels.Binding> za pomocą elementów Powiązanie standardowe <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> i <xref:System.ServiceModel.Channels.HttpTransportBindingElement>. Ten przykład przedstawia sposób użycia kodera strumienia bajtów do przekazywania i pobierania obrazu. Funkcja kodera strumienia bajtów obsługuje tylko transportu HTTP i nie obsługuje funkcji, takich jak niezawodna obsługa komunikatów i zabezpieczeń. Jedynym <xref:System.ServiceModel.Channels.MessageVersion> jest obsługiwane <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.  
  
> [!IMPORTANT]
>  Jeśli używasz tego przykładu [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] lub [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)], upewnij się, że uruchamiasz [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] z podwyższonym poziomem uprawnień.  
  
> [!IMPORTANT]
>  Próbki mogą być zainstalowane na tym komputerze. Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek. W tym przykładzie znajduje się w następującym katalogu.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Aby skonfigurować, kompilacji, a następnie uruchom próbki  
  
1.  Otwórz plik ByteStreamHttpBinding.sln w [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Uruchom nowe wystąpienie klasy ByteStreamHttpBindingServer projektu prawym przyciskiem myszy projekt w Eksploratorze rozwiązań i wybierając polecenie **debugowania**, a następnie **Start nowe wystąpienie** z menu kontekstowego.  
  
3.  Uruchom nowe wystąpienie klasy ByteStreamHttpBindingClient projektu prawym przyciskiem myszy projekt w Eksploratorze rozwiązań i wybierając polecenie **debugowania**, **Start nowe wystąpienie** z menu kontekstowego.
