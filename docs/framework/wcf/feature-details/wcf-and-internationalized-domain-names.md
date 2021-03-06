---
title: "Architektura WCF i międzynarodowe nazwy domen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a0a6cd2a809648aadfba9bac2c4ab35c26b4c65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-and-internationalized-domain-names"></a>Architektura WCF i międzynarodowe nazwy domen
Dodano obsługę umożliwiające usługi WCF z domeny nazwy (IDN). Międzynarodowych nazw domen jest nazwą domeny, który zawiera znaki spoza zestawu ASCII. Ta obsługa obejmuje to możliwość hostowanie usługi WCF z nazwą IDN i klienta WCF do komunikowania się z usługą sieci web z nazwą IDN.  
  
## <a name="systemuri-and-idn"></a>System.Uri i IDN  
 <xref:System.Uri>ma dwie właściwości <xref:System.Uri.Host%2A> i <xref:System.Uri.DnsSafeHost%2A>. Te właściwości zawierają wartości Unicode lub ciąg Punycode, w zależności od ustawień konfiguracji IDN.  
  
 IDN jest włączone w pliku konfiguracji aplikacji przy użyciu następującego kodu XML  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 \<Idn > element zawiera włączony atrybut, który może być ustawione na jedną z następujących wartości:  
  
1.  "None"  
  
2.  "AllExceptIntranet"  
  
3.  "Wszystkie"  
  
 Ustawienie IDN ma wartość "None", ma konwersji są wykonywane przez Uri.Host lub Uri.DnsSafeHost. Gdy ustawienie IDN ma wartość "Wszystkie", identyfikator uri. Host pozostaje Unicode i identyfikatora uri. DnsSafeHost jest konwertowana na ciąg Punycode. Jeśli ustawienie IDN jest równa "AllExceptIntranet", identyfikator uri. DnsSafeHost jest konwertowana na ciąg Punycode w przypadku adresów internetowych i pozostaje Unicode intranetowe adresy. To ustawienie jest ważne w przypadku poprawne rozpoznawanie nazwy DNS. Uwaga: to ustawienie nie jest wymagane do skonfigurowania dla systemu Windows 8 i nowszych wersji.  
  
> [!WARNING]
>  Należy nigdy nie kodowane adresu przy użyciu Punycode. Usługi WCF przekonwertuje go na podstawie ustawień konfiguracji, które należy zastosować.  
  
> [!WARNING]
>  Podczas dodawania znaków Unicode do applicationHost.exe.config, Zapisz plik przy użyciu kodowania UTF-8.  
  
## <a name="see-also"></a>Zobacz też  
 [System.Uri](http://msdn.microsoft.com/library/system.uri.aspx)
