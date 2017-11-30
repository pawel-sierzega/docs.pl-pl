---
title: "Nieprawidłowa wartość sumy kontrolnej, cyfry nieszesnastkowe lub nieparzysta liczba cyfr szesnastkowych"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords: BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1158742c8eaa51bcbb5607795f16ae6c2b570db4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a><span data-ttu-id="e4f74-102">Nieprawidłowa wartość sumy kontrolnej, cyfry nieszesnastkowe lub nieparzysta liczba cyfr szesnastkowych</span><span class="sxs-lookup"><span data-stu-id="e4f74-102">Bad checksum value, non hex digits or odd number of hex digits</span></span>
<span data-ttu-id="e4f74-103">Wartość sumy kontrolnej zawiera nieprawidłowe cyfry szesnastkowe lub ma nieparzystą liczbę cyfr.</span><span class="sxs-lookup"><span data-stu-id="e4f74-103">A checksum value contains invalid hexadecimal digits or has an odd number of digits.</span></span>  
  
 <span data-ttu-id="e4f74-104">Gdy program ASP.NET wygeneruje plik źródłowy języka Visual Basic (.vb rozszerzenia), oblicza sumę kontrolną i umieszcza je w pliku źródłowym ukryte identyfikowane przez `#externalchecksum`.</span><span class="sxs-lookup"><span data-stu-id="e4f74-104">When ASP.NET generates a Visual Basic source file (extension .vb), it calculates a checksum and places it in a hidden source file identified by `#externalchecksum`.</span></span> <span data-ttu-id="e4f74-105">Istnieje możliwość, że użytkownik Generowanie pliku .vb, w tym również, ale ten proces jest najlepszym od lewej do użytku wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="e4f74-105">It is possible for a user generating a .vb file to do this also, but this process is best left to internal use.</span></span>  
  
 <span data-ttu-id="e4f74-106">Domyślnie ten komunikat jest ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="e4f74-106">By default, this message is a warning.</span></span> <span data-ttu-id="e4f74-107">Aby uzyskać informacje na ukrywanie ostrzeżenia lub traktowanie ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e4f74-107">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e4f74-108">**Identyfikator błędu:** BC42033</span><span class="sxs-lookup"><span data-stu-id="e4f74-108">**Error ID:** BC42033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e4f74-109">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="e4f74-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="e4f74-110">Jeśli program ASP.NET jest generowany plik źródłowy języka Visual Basic, uruchom ponownie kompilacji projektu.</span><span class="sxs-lookup"><span data-stu-id="e4f74-110">If ASP.NET is generating the Visual Basic source file, restart the project build.</span></span>  
  
2.  <span data-ttu-id="e4f74-111">Jeśli to ostrzeżenie będzie nadal występował po ponownym uruchomieniu, ponownej instalacji programu ASP.NET i spróbuj ponownie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="e4f74-111">If this warning persists after restarting, reinstall ASP.NET and try the build again.</span></span>  
  
3.  <span data-ttu-id="e4f74-112">Jeśli to ostrzeżenie będzie nadal występować lub jeśli nie używasz programu ASP.NET, zebrać informacje dotyczące okoliczności i powiadomić pomocy technicznej firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4f74-112">If the warning still persists, or if you are not using ASP.NET, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4f74-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e4f74-113">See Also</span></span>  
 [<span data-ttu-id="e4f74-114">Omówienie programu ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e4f74-114">ASP.NET Overview</span></span>](https://msdn.microsoft.com/library/4w3ex9c2.aspx)  
 [<span data-ttu-id="e4f74-115">Porozmawiaj z nami</span><span class="sxs-lookup"><span data-stu-id="e4f74-115">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)