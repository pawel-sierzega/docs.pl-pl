---
title: "Porady: analizowanie ścieżek pliku w Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- file names [Visual Basic], parsing [Visual Basic]
- parsing, file paths [Visual Basic]
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 913fe45cf6fc7afdc6e0f31e028bc18808cecf89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-parse-file-paths-in-visual-basic"></a><span data-ttu-id="5f6bc-102">Porady: analizowanie ścieżek pliku w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5f6bc-102">How to: Parse File Paths in Visual Basic</span></span>
<span data-ttu-id="5f6bc-103"><xref:Microsoft.VisualBasic.FileIO.FileSystem> Obiekt oferuje wiele metod przydatne podczas analizowania ścieżki do pliku.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem> object offers a number of useful methods when parsing file paths.</span></span>  
  
-   <span data-ttu-id="5f6bc-104"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> Metoda ma dwie ścieżki i zwraca poprawnie sformatowana połączone ścieżki.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-104">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> method takes two paths and returns a properly formatted combined path.</span></span>  
  
-   <span data-ttu-id="5f6bc-105"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> — Metoda zwraca ścieżkę bezwzględną elementu nadrzędnego podana ścieżka.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-105">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> method returns the absolute path of the parent of the provided path.</span></span>  
  
-   <span data-ttu-id="5f6bc-106"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> Metoda zwraca <xref:System.IO.FileInfo> obiekt, który można wykonać zapytania, aby określić właściwości pliku, takie jak jego nazwa i ścieżka.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-106">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method returns a <xref:System.IO.FileInfo> object that can be queried to determine the file's properties, such as its name and path.</span></span>  
  
 <span data-ttu-id="5f6bc-107">Nie należy wprowadzać decyzje dotyczące zawartości pliku, na podstawie rozszerzenia nazwy pliku.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-107">Do not make decisions about the contents of the file based on the file name extension.</span></span> <span data-ttu-id="5f6bc-108">Na przykład plik Form1.vb nie może być plik źródłowy języka Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-108">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
### <a name="to-determine-a-files-name-and-path"></a><span data-ttu-id="5f6bc-109">Aby określić nazwę pliku i ścieżkę</span><span class="sxs-lookup"><span data-stu-id="5f6bc-109">To determine a file's name and path</span></span>  
  
-   <span data-ttu-id="5f6bc-110">Użyj <xref:System.IO.FileInfo.DirectoryName%2A> i <xref:System.IO.FileInfo.Name%2A> właściwości <xref:System.IO.FileInfo> obiektem, aby określić nazwę pliku i ścieżkę.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-110">Use the <xref:System.IO.FileInfo.DirectoryName%2A> and <xref:System.IO.FileInfo.Name%2A> properties of the <xref:System.IO.FileInfo> object to determine a file's name and path.</span></span> <span data-ttu-id="5f6bc-111">W tym przykładzie określa nazwę i ścieżkę i wyświetla je.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-111">This example determines the name and path and displays them.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#54](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_1.vb)]  
  
### <a name="to-combine-a-files-name-and-directory-to-create-the-full-path"></a><span data-ttu-id="5f6bc-112">Aby połączyć nazwy i katalog, aby utworzyć pełną ścieżkę pliku</span><span class="sxs-lookup"><span data-stu-id="5f6bc-112">To combine a file's name and directory to create the full path</span></span>  
  
-   <span data-ttu-id="5f6bc-113">Użyj `CombinePath` metody dostarczania katalogu i nazwę.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-113">Use the `CombinePath` method, supplying the directory and name.</span></span> <span data-ttu-id="5f6bc-114">W tym przykładzie przyjmuje ciągi `folderPath` i `fileName` utworzony w poprzednim przykładzie, łączy je i wyświetla wyniki.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-114">This example takes the strings `folderPath` and `fileName` created in the previous example, combines them, and displays the result.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#55](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5f6bc-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5f6bc-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>  
 <xref:System.IO.FileInfo>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>  
 [<span data-ttu-id="5f6bc-116">Porady: pobieranie kolekcji plików z katalogu</span><span class="sxs-lookup"><span data-stu-id="5f6bc-116">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)