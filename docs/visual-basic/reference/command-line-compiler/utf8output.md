---
title: /utf8output (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 23c7c308865a6b6afb07443a42090fff3d9e2efb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="utf8output-visual-basic"></a><span data-ttu-id="787e2-102">/utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="787e2-102">/utf8output (Visual Basic)</span></span>
<span data-ttu-id="787e2-103">Wyświetla kompilatora, dane wyjściowe przy użyciu kodowania UTF-8.</span><span class="sxs-lookup"><span data-stu-id="787e2-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="787e2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="787e2-104">Syntax</span></span>  
  
```  
/utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="787e2-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="787e2-105">Arguments</span></span>  
 <span data-ttu-id="787e2-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="787e2-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="787e2-107">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="787e2-107">Optional.</span></span> <span data-ttu-id="787e2-108">Wartość domyślna dla tej opcji to `/utf8output-`, co oznacza, że dane wyjściowe kompilatora nie używa kodowania UTF-8.</span><span class="sxs-lookup"><span data-stu-id="787e2-108">The default for this option is `/utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="787e2-109">Określanie `/utf8output` jest taka sama jak określanie `/utf8output+`.</span><span class="sxs-lookup"><span data-stu-id="787e2-109">Specifying `/utf8output` is the same as specifying `/utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="787e2-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="787e2-110">Remarks</span></span>  
 <span data-ttu-id="787e2-111">W niektórych konfiguracjach międzynarodowe dane wyjściowe kompilatora nie można wyświetlić poprawnie w konsoli.</span><span class="sxs-lookup"><span data-stu-id="787e2-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="787e2-112">W takiej sytuacji należy używać `/utf8output` i Przekieruj dane wyjściowe kompilatora do pliku.</span><span class="sxs-lookup"><span data-stu-id="787e2-112">In such situations, use `/utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="787e2-113">`/utf8output` Opcja nie jest dostępne w środowisku programowania Visual Studio; jest dostępna tylko podczas kompilowania kodu w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="787e2-113">The `/utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="787e2-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="787e2-114">Example</span></span>  
 <span data-ttu-id="787e2-115">Poniższy kod kompiluje `In.vb` i kieruje kompilatora, aby wyświetlić dane wyjściowe przy użyciu kodowania UTF-8.</span><span class="sxs-lookup"><span data-stu-id="787e2-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```  
vbc /utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="787e2-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="787e2-116">See Also</span></span>  
 [<span data-ttu-id="787e2-117">Kompilator w wierszu polecenia programu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="787e2-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="787e2-118">Kompilacja przykładów — wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="787e2-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)