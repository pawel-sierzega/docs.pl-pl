---
title: "Przy użyciu gniazda synchroniczne klienta"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- synchronous client sockets
- Socket class, synchronous client sockets
- receiving data, sockets
- sockets, synchronous client sockets
- protocols, sockets
- Internet, sockets
- client sockets
ms.assetid: 945d00c6-7202-466c-9df9-140b84156d43
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 03595539d825f26251a24fce33ede2552b79b38b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="using-a-synchronous-client-socket"></a>Przy użyciu gniazda synchroniczne klienta
Gniazda synchroniczne klienta zawiesza program aplikacji podczas operacji sieciowej. Gniazda synchroniczne nie są odpowiednie dla aplikacji, które w znacznym stopniu wykorzystywane sieci dla ich działania, ale umożliwiają one proste dostęp do usług sieciowych dla innych aplikacji.  
  
 Aby wysłać dane, Przekaż tablica bajtów do jednego z <xref:System.Net.Sockets.Socket> metod wysyłania danych klasy (<xref:System.Net.Sockets.Socket.Send%2A> i <xref:System.Net.Sockets.Socket.SendTo%2A>). Poniższy przykład koduje ciąg w użyciu buforu tablicy bajtów <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType> właściwości, a następnie przesyła bufor do urządzenia sieciowego przy użyciu **wysyłania** metody. **Wysyłania** metoda zwraca liczbę bajtów wysłanych z urządzeniem sieciowym.  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 **Wysyłania** — metoda usuwa bajtów z buforu, a kolejki je z interfejsem sieciowym do wysłania do urządzenia sieciowego. Interfejs sieciowy nie może wysłać dane od razu, ale wysyła on po pewnym czasie tak długo, jak połączenie jest zamknięte zwykle z <xref:System.Net.Sockets.Socket.Shutdown%2A> metody.  
  
 Na odbieranie danych z urządzenia sieciowego, Przekaż bufor do jednego z **gniazda** metody odbierania danych klasy (<xref:System.Net.Sockets.Socket.Receive%2A> i <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>). Synchroniczne sockets zawiesi stosowanie, dopóki nie są odbierane z sieci, lub do czasu zamknięcia gniazda. Poniższy przykład odbiera dane z sieci i wyświetla je w konsoli. W przykładzie założono, że danych przesyłanych przez sieć jest kodowany w formacie ASCII tekstu. **Receive** metoda zwraca liczbę bajtów odebranych z sieci.  
  
```vb  
Dim bytes(1024) As Byte  
Dim bytesRec = s.Receive(bytes)  
Console.WriteLine("Echoed text = {0}", _  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec))  
```  
  
```csharp  
byte[] bytes = new byte[1024];  
int bytesRec = s.Receive(bytes);  
Console.WriteLine("Echoed text = {0}",  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec));  
```  
  
 Gniazda jest już potrzebne, musisz zwolnić go przez wywołanie metody <xref:System.Net.Sockets.Socket.Shutdown%2A> — metoda i wywołując **Zamknij** metody. Poniższy przykład zwalnia **gniazda**. <xref:System.Net.Sockets.SocketShutdown> Wyliczenie definiuje stałe, które wskazują, czy gniazda powinno zostać zamknięte do wysyłania do odbierania lub oba.  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Używanie asynchronicznego gniazda klienta](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)  
 [Nasłuchiwanie przy użyciu gniazd](../../../docs/framework/network-programming/listening-with-sockets.md)  
 [Przykład synchronicznego gniazda klienta](../../../docs/framework/network-programming/synchronous-client-socket-example.md)
