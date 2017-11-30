---
title: "Ograniczniki tagów dokumentacji (Przewodnik programowania w języku C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- XML [C#], delimiters
- /** */ delimiters for C# documentation tags
- /// delimiter for C# documentation
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a6ab03d220d1ef71605b83c529595dd986ea922a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a><span data-ttu-id="6387d-102">Ograniczniki tagów dokumentacji (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="6387d-102">Delimiters for Documentation Tags (C# Programming Guide)</span></span>
<span data-ttu-id="6387d-103">Korzystanie z komentarze w dokumencie XML wymaga ograniczników, które wskazują w kompilatorze, gdzie komentarzy dokumentacji rozpoczęcia i zakończenia.</span><span class="sxs-lookup"><span data-stu-id="6387d-103">The use of XML doc comments requires delimiters, which indicate to the compiler where a documentation comment begins and ends.</span></span> <span data-ttu-id="6387d-104">Można użyć następujące rodzaje ograniczniki tagów dokumentacji XML:</span><span class="sxs-lookup"><span data-stu-id="6387d-104">You can use the following kinds of delimiters with the XML documentation tags:</span></span>  
  
 `///`  
 <span data-ttu-id="6387d-105">Ogranicznik jeden wiersz.</span><span class="sxs-lookup"><span data-stu-id="6387d-105">Single-line delimiter.</span></span> <span data-ttu-id="6387d-106">Jest to formularz, który jest wyświetlany w przykładach dokumentacji i używane przez Szablony projektów Visual C#.</span><span class="sxs-lookup"><span data-stu-id="6387d-106">This is the form that is shown in documentation examples and used by the Visual C# project templates.</span></span> <span data-ttu-id="6387d-107">W przypadku biały znak po znaku ograniczającym ten znak nie jest uwzględniony w danych wyjściowych XML.</span><span class="sxs-lookup"><span data-stu-id="6387d-107">If there is a white space character following the delimiter, that character is not included in the XML output.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6387d-108">Środowiska IDE programu Visual Studio ma funkcję inteligentne komentarz edycji automatycznie wstawiany \<podsumowania > i \</summary > Znaczniki i przesuwa kursor w ramach tych tagów po wpisaniu `///` ogranicznik w edytorze kodu .</span><span class="sxs-lookup"><span data-stu-id="6387d-108">The Visual Studio IDE has a feature called Smart Comment Editing that automatically inserts the \<summary> and \</summary> tags and moves your cursor within these tags after you type the `///` delimiter in the Code Editor.</span></span> <span data-ttu-id="6387d-109">Dostęp do tej funkcji w [opcje, Edytor tekstu, C#, formatowanie](/visualstudio/ide/reference/options-text-editor-csharp-formatting) na stronach właściwości projektu.</span><span class="sxs-lookup"><span data-stu-id="6387d-109">Access this feature from the [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting) in your project property pages.</span></span>  
  
 `/** */`  
 <span data-ttu-id="6387d-110">Wielowierszowy ograniczników.</span><span class="sxs-lookup"><span data-stu-id="6387d-110">Multiline delimiters.</span></span>  
  
 <span data-ttu-id="6387d-111">Brak niektórych reguł formatowania, które należy wykonać, korzystając z `/** */` ograniczników.</span><span class="sxs-lookup"><span data-stu-id="6387d-111">There are some formatting rules to follow when you use the `/** */` delimiters.</span></span>  
  
-   <span data-ttu-id="6387d-112">W wierszu, który zawiera `/**` ogranicznik, jeśli do końca wiersza jest białe, wiersz nie został przetworzony przeznaczone do komentarzy.</span><span class="sxs-lookup"><span data-stu-id="6387d-112">On the line that contains the `/**` delimiter, if the remainder of the line is white space, the line is not processed for comments.</span></span> <span data-ttu-id="6387d-113">Jeśli pierwszym znakiem po `/**` ogranicznik jest białe, czy biały znak jest ignorowane, a pozostałe wiersz jest przetwarzany.</span><span class="sxs-lookup"><span data-stu-id="6387d-113">If the first character after the `/**` delimiter is white space, that white space character is ignored and the rest of the line is processed.</span></span> <span data-ttu-id="6387d-114">W przeciwnym razie cały tekst wiersza po `/**` ogranicznik jest przetwarzany jako część komentarza.</span><span class="sxs-lookup"><span data-stu-id="6387d-114">Otherwise, the entire text of the line after the `/**` delimiter is processed as part of the comment.</span></span>  
  
-   <span data-ttu-id="6387d-115">W wierszu, który zawiera `*/` ogranicznik, jeśli istnieje tylko biały znak do `*/` ogranicznika wiersza jest ignorowana.</span><span class="sxs-lookup"><span data-stu-id="6387d-115">On the line that contains the `*/` delimiter, if there is only white space up to the `*/` delimiter, that line is ignored.</span></span> <span data-ttu-id="6387d-116">W przeciwnym razie tekst w wierszu do `*/` ogranicznik jest przetwarzany jako część komentarza, opisane w poniższych punktor zasadom dopasowywanie do wzorca.</span><span class="sxs-lookup"><span data-stu-id="6387d-116">Otherwise, the text on the line up to the `*/` delimiter is processed as part of the comment, subject to the pattern-matching rules described in the following bullet.</span></span>  
  
-   <span data-ttu-id="6387d-117">Po tym, który rozpoczyna się od linii `/**` ogranicznik, kompilator szuka wspólnego wzorca na początku każdego wiersza.</span><span class="sxs-lookup"><span data-stu-id="6387d-117">For the lines after the one that begins with the `/**` delimiter, the compiler looks for a common pattern at the beginning of each line.</span></span> <span data-ttu-id="6387d-118">Wzorzec może zawierać białych opcjonalne i znak gwiazdki (`*`), a następnie opcjonalnie biały znak.</span><span class="sxs-lookup"><span data-stu-id="6387d-118">The pattern can consist of optional white space and an asterisk (`*`), followed by more optional white space.</span></span> <span data-ttu-id="6387d-119">Jeśli kompilator znajdzie wspólnego wzorca na początku każdego wiersza, który nie zaczyna się od `/**` ogranicznik lub `*/` ogranicznika ignoruje tego wzorca dla każdego wiersza.</span><span class="sxs-lookup"><span data-stu-id="6387d-119">If the compiler finds a common pattern at the beginning of each line that does not begin with the `/**` delimiter or the `*/` delimiter, it ignores that pattern for each line.</span></span>  
  
 <span data-ttu-id="6387d-120">Poniższe przykłady przedstawiają te reguły.</span><span class="sxs-lookup"><span data-stu-id="6387d-120">The following examples illustrate these rules.</span></span>  
  
-   <span data-ttu-id="6387d-121">Tylko część następujące komentarz, który zostanie przetworzona jest wiersza, który rozpoczyna się od `<summary>`.</span><span class="sxs-lookup"><span data-stu-id="6387d-121">The only part of the following comment that will be processed is the line that begins with `<summary>`.</span></span> <span data-ttu-id="6387d-122">Trzy formaty utworzyć samą komentarze.</span><span class="sxs-lookup"><span data-stu-id="6387d-122">The three tag formats produce the same comments.</span></span>  
  
    ```  
    /** <summary>text</summary> */   
  
    /**   
    <summary>text</summary>   
    */   
  
    /**   
     * <summary>text</summary>   
    */  
    ```  
  
-   <span data-ttu-id="6387d-123">Kompilator identyfikuje typowe wzorzec "*" na początku linii drugiego i trzeciego.</span><span class="sxs-lookup"><span data-stu-id="6387d-123">The compiler identifies a common pattern of " * " at the beginning of the second and third lines.</span></span> <span data-ttu-id="6387d-124">Wzorzec nie jest uwzględniony w danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="6387d-124">The pattern is not included in the output.</span></span>  
  
    ```  
    /**   
     * <summary>   
     * text </summary>*/   
    ```  
  
-   <span data-ttu-id="6387d-125">Kompilator znajduje nie wspólnego wzorca w poniższy komentarz, ponieważ znak na trzeci wiersz nie jest znak gwiazdki.</span><span class="sxs-lookup"><span data-stu-id="6387d-125">The compiler finds no common pattern in the following comment because the second character on the third line is not an asterisk.</span></span> <span data-ttu-id="6387d-126">W związku z tym cały tekst w wierszach drugiego i trzeciego są przetwarzane w ramach komentarza.</span><span class="sxs-lookup"><span data-stu-id="6387d-126">Therefore, all text on the second and third lines is processed as part of the comment.</span></span>  
  
    ```  
    /**   
     * <summary>   
       text </summary>  
    */   
    ```  
  
-   <span data-ttu-id="6387d-127">Kompilator znajduje nie wzorca w komentarzu następujących dwóch powodów.</span><span class="sxs-lookup"><span data-stu-id="6387d-127">The compiler finds no pattern in the following comment for two reasons.</span></span> <span data-ttu-id="6387d-128">Po pierwsze liczbę spacji przed gwiazdka nie jest spójna.</span><span class="sxs-lookup"><span data-stu-id="6387d-128">First, the number of spaces before the asterisk is not consistent.</span></span> <span data-ttu-id="6387d-129">Drugie piątej wiersz rozpoczyna się od kartę, która jest niezgodna z spacji.</span><span class="sxs-lookup"><span data-stu-id="6387d-129">Second, the fifth line begins with a tab, which does not match spaces.</span></span> <span data-ttu-id="6387d-130">W związku z tym cały tekst z dwa wiersze, za pomocą pięciu są przetwarzane w ramach komentarza.</span><span class="sxs-lookup"><span data-stu-id="6387d-130">Therefore, all text from lines two through five is processed as part of the comment.</span></span>  
  
    ```  
    /**   
      * <summary>   
      * text   
     *  text2   
        *  </summary>   
    */   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6387d-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6387d-131">See Also</span></span>  
 [<span data-ttu-id="6387d-132">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="6387d-132">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6387d-133">Komentarze dokumentacji XML</span><span class="sxs-lookup"><span data-stu-id="6387d-133">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)  
 [<span data-ttu-id="6387d-134">/ doc (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="6387d-134">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [<span data-ttu-id="6387d-135">Komentarze dokumentacji XML</span><span class="sxs-lookup"><span data-stu-id="6387d-135">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)