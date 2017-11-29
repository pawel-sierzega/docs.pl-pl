---
title: "Porady: Debugowanie aplikacji obsługujących oświadczenia i usług za pomocą śledzenia WIF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d51ba59-3adb-4ca4-bd33-5027531af687
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 36cb961345cb724597d8e48ec3be6cbb84df4632
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-debug-claims-aware-applications-and-services-using-wif-tracing"></a><span data-ttu-id="4f04e-102">Porady: Debugowanie aplikacji obsługujących oświadczenia i usług za pomocą śledzenia WIF</span><span class="sxs-lookup"><span data-stu-id="4f04e-102">How To: Debug Claims-Aware Applications And Services Using WIF Tracing</span></span>
## <a name="applies-to"></a><span data-ttu-id="4f04e-103">Dotyczy:</span><span class="sxs-lookup"><span data-stu-id="4f04e-103">Applies To</span></span>  
  
-   <span data-ttu-id="4f04e-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="4f04e-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="4f04e-105">Narzędzie do przeglądania danych śledzenia usług (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="4f04e-105">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>  
  
-   <span data-ttu-id="4f04e-106">Rozwiązywanie problemów i debugowanie aplikacji WIF</span><span class="sxs-lookup"><span data-stu-id="4f04e-106">Troubleshooting and Debugging WIF Applications</span></span>  
  
## <a name="summary"></a><span data-ttu-id="4f04e-107">Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="4f04e-107">Summary</span></span>  
 <span data-ttu-id="4f04e-108">Ten instrukcje w tym artykule opisano czynności, jak skonfigurować śledzenie WIF, zbieranie dzienników śledzenia i sposobu analizowania śledzenia loguje się przy użyciu narzędzia podglądu śledzenia.</span><span class="sxs-lookup"><span data-stu-id="4f04e-108">This How-To describes required steps for how to configure WIF tracing, collect trace logs, and how to analyze the trace logs using Trace Viewer tool.</span></span> <span data-ttu-id="4f04e-109">Udostępnia ogólne mapowania dla śledzenia pozycje, aby rozwiązywać problemy związane z WIF akcje.</span><span class="sxs-lookup"><span data-stu-id="4f04e-109">It provides general mapping for trace entries to actions needed to troubleshoot issues related to WIF.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="4f04e-110">Spis treści</span><span class="sxs-lookup"><span data-stu-id="4f04e-110">Contents</span></span>  
  
-   <span data-ttu-id="4f04e-111">Cele</span><span class="sxs-lookup"><span data-stu-id="4f04e-111">Objectives</span></span>  
  
-   <span data-ttu-id="4f04e-112">Zestawienie czynności</span><span class="sxs-lookup"><span data-stu-id="4f04e-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="4f04e-113">Krok 1: Konfigurowanie śledzenia przy użyciu pliku konfiguracji Web.config WIF</span><span class="sxs-lookup"><span data-stu-id="4f04e-113">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
-   <span data-ttu-id="4f04e-114">Krok 2: analizowanie plików śledzenia WIF za pomocą narzędzia podglądu śledzenia</span><span class="sxs-lookup"><span data-stu-id="4f04e-114">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
-   <span data-ttu-id="4f04e-115">Krok 3: określenie rozwiązań, aby naprawić WIF problemy związane z</span><span class="sxs-lookup"><span data-stu-id="4f04e-115">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
-   <span data-ttu-id="4f04e-116">Elementy pokrewne</span><span class="sxs-lookup"><span data-stu-id="4f04e-116">Related Items</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="4f04e-117">Cele</span><span class="sxs-lookup"><span data-stu-id="4f04e-117">Objectives</span></span>  
  
-   <span data-ttu-id="4f04e-118">Konfiguruj śledzenie WIF.</span><span class="sxs-lookup"><span data-stu-id="4f04e-118">Configure WIF tracing.</span></span>  
  
-   <span data-ttu-id="4f04e-119">Wyświetl ślad Dzienniki narzędzia podglądu śledzenia.</span><span class="sxs-lookup"><span data-stu-id="4f04e-119">View trace logs in the Trace Viewer tool.</span></span>  
  
-   <span data-ttu-id="4f04e-120">Zidentyfikuj WIF związane problemy w dziennikach śledzenia.</span><span class="sxs-lookup"><span data-stu-id="4f04e-120">Identify WIF related issues in the trace logs.</span></span>  
  
-   <span data-ttu-id="4f04e-121">Zastosuj do WIF działania naprawcze związane problemy znalezione w dziennikach śledzenia.</span><span class="sxs-lookup"><span data-stu-id="4f04e-121">Apply corrective actions to WIF related issues found in the trace logs.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="4f04e-122">Zestawienie czynności</span><span class="sxs-lookup"><span data-stu-id="4f04e-122">Summary of Steps</span></span>  
  
-   <span data-ttu-id="4f04e-123">Krok 1: Konfigurowanie śledzenia przy użyciu pliku konfiguracji Web.config WIF</span><span class="sxs-lookup"><span data-stu-id="4f04e-123">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
-   <span data-ttu-id="4f04e-124">Krok 2: analizowanie plików śledzenia WIF za pomocą narzędzia podglądu śledzenia</span><span class="sxs-lookup"><span data-stu-id="4f04e-124">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
-   <span data-ttu-id="4f04e-125">Krok 3: określenie rozwiązań, aby naprawić WIF problemy związane z</span><span class="sxs-lookup"><span data-stu-id="4f04e-125">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
## <a name="step-1--configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="4f04e-126">Krok 1: Konfigurowanie śledzenia przy użyciu pliku konfiguracji Web.config WIF</span><span class="sxs-lookup"><span data-stu-id="4f04e-126">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
 <span data-ttu-id="4f04e-127">Zmiany w tym kroku zostaną dodane do sekcji konfiguracyjnych w *Web.config* pliku, które umożliwiają WIF do śledzenia jego zdarzeń i przechowywania ich w dzienniku śledzenia.</span><span class="sxs-lookup"><span data-stu-id="4f04e-127">In this step, you will add changes to configuration sections in the *Web.config* file that enable WIF to trace its events and store them in a trace log.</span></span>  
  
#### <a name="to-configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="4f04e-128">Aby skonfigurować śledzenie WIF przy użyciu pliku konfiguracji Web.config</span><span class="sxs-lookup"><span data-stu-id="4f04e-128">To configure WIF tracing using Web.config configuration file</span></span>  
  
1.  <span data-ttu-id="4f04e-129">Otwórz katalog główny **Web.config** lub **App.config** pliku konfiguracji w edytorze programu Visual Studio przez dwukrotne kliknięcie w **Eksploratora rozwiązań**.</span><span class="sxs-lookup"><span data-stu-id="4f04e-129">Open the root **Web.config** or **App.config** configuration file in the Visual Studio editor by double clicking on it in **Solution Explorer**.</span></span> <span data-ttu-id="4f04e-130">Jeśli nie ma rozwiązania **Web.config** lub **App.config** konfiguracji pliku, dodaj ją, klikając prawym przyciskiem myszy w ramach rozwiązania w **Eksploratora rozwiązań** i klikając  **Dodaj**, klikając **nowy element...** .</span><span class="sxs-lookup"><span data-stu-id="4f04e-130">If your solution does not have **Web.config** or **App.config** configuration file, add it by right clicking on the solution in the **Solution Explorer** and clicking **Add**, then clicking **New Item…**.</span></span> <span data-ttu-id="4f04e-131">Na **nowy element** zaznacz pozycję **pliku konfiguracji aplikacji** dla **App.config** lub **pliku konfiguracji sieci Web** dla **Web.config** na liście i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f04e-131">On the **New Item** dialog, Select **Application Configuration File** for **App.config** or **Web Configuration File** for **Web.config** from the list and click **OK**.</span></span>  
  
2.  <span data-ttu-id="4f04e-132">Dodania wpisów konfiguracji, podobny do następującego pliku konfiguracji wewnątrz  **\<konfiguracji >** węzeł w końcu pliku konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="4f04e-132">Add the configuration entries similar to the following to the configuration file inside **\<configuration>** node at the end of the configuration file:</span></span>  
  
    ```xml  
    <system.diagnostics>  
        <sources>  
            <source name="System.IdentityModel" switchValue="Verbose">  
                <listeners>  
                    <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="WIFTrace.e2e"/>  
                </listeners>  
            </source>  
        </sources>  
        <trace autoflush="true"/>  
    </system.diagnostics>  
    ```  
  
3.  <span data-ttu-id="4f04e-133">Powyższej konfiguracji powoduje, że WIF generowanie zdarzeń śledzenia pełne i zaloguj się do *WIFTrace.e2e* pliku.</span><span class="sxs-lookup"><span data-stu-id="4f04e-133">The above configuration instructs WIF to generate verbose trace events and log them into *WIFTrace.e2e* file.</span></span> <span data-ttu-id="4f04e-134">Aby uzyskać pełną listę wartości **switchValue** , zobacz tabelę poziom śledzenia w następującym temacie: [Konfigurowanie śledzenia](http://msdn.microsoft.com/library/ms733025.aspx).</span><span class="sxs-lookup"><span data-stu-id="4f04e-134">For a complete list of values for the **switchValue** switch, refer to the Trace Level table found in the following topic: [Configuring Tracing](http://msdn.microsoft.com/library/ms733025.aspx).</span></span>  
  
## <a name="step-2--analyze-wif-trace-files-using-trace-viewer-tool"></a><span data-ttu-id="4f04e-135">Krok 2: analizowanie plików śledzenia WIF za pomocą narzędzia podglądu śledzenia</span><span class="sxs-lookup"><span data-stu-id="4f04e-135">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
 <span data-ttu-id="4f04e-136">W tym kroku użyjesz Trace Viewer Tool (SvcTraceViewer.exe) do analizowania dzienników śledzenia WIF.</span><span class="sxs-lookup"><span data-stu-id="4f04e-136">In this step, you will use the Trace Viewer Tool (SvcTraceViewer.exe) to analyze WIF trace logs.</span></span>  
  
#### <a name="to-analyze-wif-trace-logs-using-trace-viewer-tool-svctraceviewerexe"></a><span data-ttu-id="4f04e-137">Do analizowania dzienników śledzenia WIF za pomocą narzędzia podglądu śledzenia (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="4f04e-137">To analyze WIF trace logs using Trace Viewer tool (SvcTraceViewer.exe)</span></span>  
  
1.  <span data-ttu-id="4f04e-138">Narzędzia podglądu śledzenia (SvcTraceViewer.exe) jest dostarczany jako część zestawu Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="4f04e-138">Trace Viewer tool (SvcTraceViewer.exe) ships as part of the Windows SDK.</span></span> <span data-ttu-id="4f04e-139">Jeśli nie został już zainstalowany zestaw Windows SDK, można go pobrać tutaj: [zestaw Windows SDK](http://www.microsoft.com/download/en/details.aspx?id=8279).</span><span class="sxs-lookup"><span data-stu-id="4f04e-139">If you haven’t already installed the Windows SDK, you can download it here: [Windows SDK](http://www.microsoft.com/download/en/details.aspx?id=8279).</span></span>  
  
2.  <span data-ttu-id="4f04e-140">Uruchom narzędzie przeglądarki śledzenia (SvcTraceViewer.exe).</span><span class="sxs-lookup"><span data-stu-id="4f04e-140">Run the Trace Viewer tool (SvcTraceViewer.exe).</span></span> <span data-ttu-id="4f04e-141">Jest ona zazwyczaj dostępna w **Bin** folderu ścieżki instalacji.</span><span class="sxs-lookup"><span data-stu-id="4f04e-141">It is typically available in the **Bin** folder of the installation path.</span></span>  
  
3.  <span data-ttu-id="4f04e-142">Otwórz plik dziennika śledzenia WIF, na przykład WIFTrace.e2e wybierając **pliku**, **Otwórz...**</span><span class="sxs-lookup"><span data-stu-id="4f04e-142">Open the WIF trace log file, for example, WIFTrace.e2e by selecting **File**, **Open…**</span></span> <span data-ttu-id="4f04e-143">Opcja menu lub przy użyciu **Ctrl + O** skrótów.</span><span class="sxs-lookup"><span data-stu-id="4f04e-143">option in the menu or using the **Ctrl+O** shortcut.</span></span> <span data-ttu-id="4f04e-144">Otwiera plik dziennika śledzenia w narzędziu Podgląd śledzenia.</span><span class="sxs-lookup"><span data-stu-id="4f04e-144">The trace log file opens in the Trace Viewer tool.</span></span>  
  
4.  <span data-ttu-id="4f04e-145">Przejrzyj wpisy w **działania** kartę. Każdy wpis powinien zawierać numer działania, Liczba śladów, które zostały zarejestrowane, czas trwania działania i jego znaczniki czasu rozpoczęcia i zakończenia.</span><span class="sxs-lookup"><span data-stu-id="4f04e-145">Review entries in the **Activity** tab. Each entry should contain an activity number, the number of traces that were logged, duration of the activity and its start and end timestamps.</span></span>  
  
5.  <span data-ttu-id="4f04e-146">Polecenie **działania** kartę. Należy również wyświetlić szczegółowe śledzenia wpisy w obszarze głównym narzędzia.</span><span class="sxs-lookup"><span data-stu-id="4f04e-146">Click on the **Activity** tab. You should see detailed trace entries in the main area of the tool.</span></span> <span data-ttu-id="4f04e-147">Użyj **poziom** listy rozwijanej w menu, aby filtrować określony poziom śledzenia, na przykład: **wszystkie**, **ostrzeżenie**, **błędy**, **Informacji**itp.</span><span class="sxs-lookup"><span data-stu-id="4f04e-147">Use the **Level** dropdown list on the menu to filter specific level of traces, for example: **All**, **Warning**, **Errors**, **Information**, etc.</span></span>  
  
6.  <span data-ttu-id="4f04e-148">Polecenie wpisów śledzenia określonych szczegółowych informacji w dolnym obszarze narzędzia.</span><span class="sxs-lookup"><span data-stu-id="4f04e-148">Click on specific trace entries to review the details in the lower area of the tool.</span></span> <span data-ttu-id="4f04e-149">Szczegółowe informacje można wyświetlać przy użyciu **sformatowany** i **XML** widoku, wybierając odpowiednie karty.</span><span class="sxs-lookup"><span data-stu-id="4f04e-149">The details can be viewed using **Formatted** and **XML** view by choosing corresponding tabs.</span></span>  
  
## <a name="step-3--identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="4f04e-150">Krok 3: określenie rozwiązań, aby naprawić WIF problemy związane z</span><span class="sxs-lookup"><span data-stu-id="4f04e-150">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
 <span data-ttu-id="4f04e-151">W tym kroku należy zidentyfikować rozwiązania problemów związanych z WIF oznaczona przy użyciu narzędzia podglądu śledzenia i WIF w dzienniku śledzenia.</span><span class="sxs-lookup"><span data-stu-id="4f04e-151">In this step, you can identify solutions for WIF-related issues identified by using the WIF trace log and Trace Viewer tool.</span></span> <span data-ttu-id="4f04e-152">Zawiera opis ogólnego mapowania WIF powiązane wyjątki potencjalne rozwiązania lub wymagane akcje w celu rozwiązania problemu.</span><span class="sxs-lookup"><span data-stu-id="4f04e-152">It outlines general mapping of WIF related exceptions to potential solutions or required actions to troubleshoot the issue.</span></span>  
  
#### <a name="to-identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="4f04e-153">Aby zidentyfikować rozwiązania, aby naprawić WIF problemy związane z</span><span class="sxs-lookup"><span data-stu-id="4f04e-153">To identify solutions to fix WIF related issues</span></span>  
  
1.  <span data-ttu-id="4f04e-154">Należy przejrzeć poniższą tabelę WIF wyjątków i wymagane akcje do rozwiązania problemów.</span><span class="sxs-lookup"><span data-stu-id="4f04e-154">Review the following table of WIF exceptions and the required actions to correct the issues.</span></span>  
  
|<span data-ttu-id="4f04e-155">**Identyfikator błędu**</span><span class="sxs-lookup"><span data-stu-id="4f04e-155">**Error ID**</span></span>|<span data-ttu-id="4f04e-156">**Komunikat o błędzie**</span><span class="sxs-lookup"><span data-stu-id="4f04e-156">**Error Message**</span></span>|<span data-ttu-id="4f04e-157">**Czynności, aby naprawić błąd**</span><span class="sxs-lookup"><span data-stu-id="4f04e-157">**Action needed to fix the error**</span></span>|  
|-|-|-|  
|<span data-ttu-id="4f04e-158">ID4175</span><span class="sxs-lookup"><span data-stu-id="4f04e-158">ID4175</span></span>|<span data-ttu-id="4f04e-159">Wystawca tokenu zabezpieczającego nie został rozpoznany przez IssuerNameRegistry.</span><span class="sxs-lookup"><span data-stu-id="4f04e-159">The issuer of the security token was not recognized by the IssuerNameRegistry.</span></span>  <span data-ttu-id="4f04e-160">Aby zaakceptować tokeny zabezpieczające z tym wystawcą, skonfiguruj IssuerNameRegistry, aby zwrócić prawidłową nazwę tego wystawcy.</span><span class="sxs-lookup"><span data-stu-id="4f04e-160">To accept security tokens from this issuer, configure the IssuerNameRegistry to return a valid name for this issuer.</span></span>|<span data-ttu-id="4f04e-161">Ten błąd może być spowodowany przez skopiowanie odcisk palca z przystawki programu MMC i wklejenie go do *Web.config* pliku.</span><span class="sxs-lookup"><span data-stu-id="4f04e-161">This error can be caused by copying a thumbprint from the MMC snap-in and pasting it into the *Web.config* file.</span></span> <span data-ttu-id="4f04e-162">W szczególności podczas kopiowania z okna właściwości certyfikatu można uzyskać bardzo niedrukowalne znaki w ciągu tekstowym.</span><span class="sxs-lookup"><span data-stu-id="4f04e-162">Specifically, you can get an extra non-printable character in the text string when copying from the certificate properties window.</span></span> <span data-ttu-id="4f04e-163">Ten dodatkowy znak powoduje niepowodzenie dopasowania odcisk palca. Procedurę poprawnie kopiowania odcisk palca można znaleźć tutaj: [http://msdn.microsoft.com/library/ff359102.aspx](http://msdn.microsoft.com/library/ff359102.aspx)</span><span class="sxs-lookup"><span data-stu-id="4f04e-163">This extra character causes the thumbprint match to fail.The procedure for correctly copying the thumbprint can be found here: [http://msdn.microsoft.com/library/ff359102.aspx](http://msdn.microsoft.com/library/ff359102.aspx)</span></span>|  
  
## <a name="related-items"></a><span data-ttu-id="4f04e-164">Elementy pokrewne</span><span class="sxs-lookup"><span data-stu-id="4f04e-164">Related Items</span></span>  
  
-   [<span data-ttu-id="4f04e-165">Przy użyciu przeglądarki śledzenia usługi do wyświetlania skorelowanych danych śledzenia i rozwiązywania problemów</span><span class="sxs-lookup"><span data-stu-id="4f04e-165">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](http://msdn.microsoft.com/library/aa751795.aspx)