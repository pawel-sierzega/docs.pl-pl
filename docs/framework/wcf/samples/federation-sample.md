---
title: "Federacja — przykład"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e9da0ca-e925-4644-aa96-8bfaf649d4bb
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c87984b08a073f37dcf155a39fab0f5e580e985
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="federation-sample"></a>Federacja — przykład
W tym przykładzie przedstawiono zabezpieczeń.  
  
## <a name="sample-details"></a>Szczegóły próbki  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]zapewnia obsługę wdrażania architektury zabezpieczeń za pomocą `wsFederationHttpBinding`. `wsFederationHttpBinding` Udostępnia bezpieczne, niezawodne i interoperacyjne powiązanie, które polega na użyciu protokołu HTTP jako podstawowy mechanizm transportu dla komunikacji żądanie/odpowiedź, a Text/XML jako przewodowy format kodowania. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Federacji w [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], zobacz [federacyjnego](../../../../docs/framework/wcf/feature-details/federation.md).  
  
 Scenariusz składa się z 4 części:  
  
-   Usługa księgarni  
  
-   Księgarni STS  
  
-   HomeRealm usługi STS  
  
-   Księgarni klienta  
  
 Usługa księgarni obsługuje dwie operacje `BrowseBooks` i `BuyBook`. Zezwala na dostęp anonimowy do `BrowseBooks` operacji, ale wymaga dostępu uwierzytelnionego dostępu `BuyBooks` operacji. Uwierzytelnianie ma postać token wystawiony przez usługę STS księgarni. Wskazuje plik konfiguracji usługi księgarni klientów przy użyciu usługi STS księgarni `wsFederationHttpBinding`.  
  
```xml  
<wsFederationHttpBinding>  
<!-- This is the Service binding for the BuyBooks endpoint. It redirects clients to the BookStore STS -->  
    <binding name='BuyBookBinding'>  
        <security mode="Message">  
            <message>  
                <issuerMetadata  
  address='http://localhost/FederationSample/BookStoreSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='BookStoreSTS.com'/>  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 STS księgarni wymaga, aby klienci uwierzytelniania za pomocą token wystawiony przez usługę STS HomeRealm. Ponownie, pliku konfiguracji dla usługi STS księgarni wskazuje klientów przy użyciu usługi STS HomeRealm `wsFederationHttpBinding`.  
  
```xml  
<wsFederationHttpBinding>  
 <!-- This is the binding for the clients requesting tokens from this STS. It redirects clients to the HomeRealm STS -->  
    <binding name='BookStoreSTSBinding'>  
        <security mode='Message'>  
            <message>  
                <issuerMetadata  
 address='http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='HomeRealmSTS.com' />  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 Kolejność zdarzeń przy uzyskiwaniu dostępu do `BuyBook` operacji wygląda następująco:  
  
1.  Uwierzytelnia klienta do usługi STS HomeRealm przy użyciu poświadczeń systemu Windows.  
  
2.  HomeRealm STS wystawia token, który może służyć do uwierzytelniania usługi STS księgarni.  
  
3.  Klient przeprowadza uwierzytelnianie za pomocą tokenu wystawiony przez usługę STS HomeRealm usługi STS księgarni.  
  
4.  Usługa tokenu Zabezpieczającego księgarni wystawia token, który może służyć do uwierzytelniania w usłudze księgarni.  
  
5.  Klient przeprowadza uwierzytelnianie w usłudze księgarni przy użyciu token wystawiony przez usługę STS księgarni.  
  
6.  Klient uzyskuje dostęp do `BuyBook` operacji.  
  
 Zobacz następujące instrukcje dotyczące konfigurowania i uruchamiania tego przykładu.  
  
> [!NOTE]
>  Musi mieć uprawnienia do zapisu **wwwroot** katalogu, aby uruchomić ten przykład.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Aby skonfigurować, kompilacji, a następnie uruchom próbki  
  
1.  Otwórz okno polecenia zestawu SDK. W ścieżce próbki należy uruchomić pliku Setup.bat. Tworzy wymagane przykładowej katalogi wirtualne i instaluje wymagane certyfikaty z odpowiednimi uprawnieniami.  
  
    > [!NOTE]
    >  Plik wsadowy pliku Setup.bat jest przeznaczony do uruchamiania z wiersza polecenia systemu Windows SDK. Wymaga ona, że zmienna środowiskowa MSSDK odwołują się do katalogu, w którym jest zainstalowany zestaw SDK. Ta zmienna środowiskowa jest automatycznie ustawiana w wierszu polecenia systemu Windows SDK. Na [!INCLUDE[wv](../../../../includes/wv-md.md)], musi zapewnić, że zgodność z narzędziami zarządzania usług IIS 6.0 jest zainstalowany, ponieważ skrypty administratora usług IIS korzysta z konfiguracji. Uruchomienie skryptu konfiguracji [!INCLUDE[wv](../../../../includes/wv-md.md)] wymaga uprawnień administratora.  
  
2.  Otwórz FederationSample.sln w programie Visual Studio i wybierz **Kompiluj rozwiązanie** z **kompilacji** menu. Tworzy wspólne pliki projektu, księgarni usługi STS księgarni, HomeRealm STS i wdraża je w usługach IIS. To również kompilacje księgarni aplikacji klienckiej i umieszcza BookStoreClient.exe wykonywalny w folderze FederationSample\BookStoreClient\bin\Debug.  
  
3.  Kliknij dwukrotnie BookStoreClient.exe. Zostanie wyświetlone okno BookStoreClient.  
  
4.  Możesz przeglądać książki w księgarni dostępne klikając **Przeglądaj książek**.  
  
5.  Aby kupić wybranej książki, wybierz książkę na liście, a następnie kliknij przycisk **kupić książki**. Aplikacja jest uruchamiany i jest uwierzytelniany przy użyciu uwierzytelniania systemu Windows z usługi tokenu zabezpieczającego HomeRealm.  
  
     Próbka jest skonfigurowany, aby umożliwić użytkownikom kupowanie książek, których koszt $15 lub mniej. Próba kupowanie książek, które koszty były wyższe niż $15 wyniki w kliencie pobieranie komunikat o odmowie dostępu z książki usługi magazynu.  
  
    > [!NOTE]
    >  Próbki nie aktualizuje limit kredytu użytkownika po zakupu. Możesz kupić wielokrotnie książek w limicie środki (stałe) użytkownika.  
  
#### <a name="to-clean-up"></a>Aby wyczyścić  
  
1.  Uruchom Cleanup.bat. Usuwa katalogi wirtualne, które zostały utworzone podczas zestawu w górę, a spowoduje również usunięcie certyfikaty zainstalowane podczas instalacji.  
  
> [!IMPORTANT]
>  Próbki mogą być zainstalowane na tym komputerze. Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek. W tym przykładzie znajduje się w następującym katalogu.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Federation`  
  
## <a name="see-also"></a>Zobacz też
