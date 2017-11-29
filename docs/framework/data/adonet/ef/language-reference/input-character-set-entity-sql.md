---
title: "Zestaw znaków (jednostka SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 691f29a04b1b1f997be501330ec887d6815d7531
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="input-character-set-entity-sql"></a><span data-ttu-id="037b9-102">Zestaw znaków (jednostka SQL)</span><span class="sxs-lookup"><span data-stu-id="037b9-102">Input Character Set (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="037b9-103">akceptuje zakodowane w formacie UTF-16 znaków UNICODE.</span><span class="sxs-lookup"><span data-stu-id="037b9-103"> accepts UNICODE characters encoded in UTF-16.</span></span>  
  
 <span data-ttu-id="037b9-104">Literały ciągu może zawierać dowolne znaki UTF-16, ujęta w apostrofy.</span><span class="sxs-lookup"><span data-stu-id="037b9-104">String literals can contain any UTF-16 character enclosed in single quotes.</span></span> <span data-ttu-id="037b9-105">Na przykład N "文字列リテラル".</span><span class="sxs-lookup"><span data-stu-id="037b9-105">For example, N'文字列リテラル'.</span></span> <span data-ttu-id="037b9-106">Porównaniu literałów ciągów są używane oryginalnych wartości UTF-16.</span><span class="sxs-lookup"><span data-stu-id="037b9-106">When string literals are compared, the original UTF-16 values are used.</span></span> <span data-ttu-id="037b9-107">Na przykład N'ABC "różni się w języku japońskim i Latin strony kodowe.</span><span class="sxs-lookup"><span data-stu-id="037b9-107">For example, N'ABC' is different in Japanese and Latin codepages.</span></span>  
  
 <span data-ttu-id="037b9-108">Komentarze mogą zawierać dowolne znaki UTF-16.</span><span class="sxs-lookup"><span data-stu-id="037b9-108">Comments can contain any UTF-16 character.</span></span>  
  
 <span data-ttu-id="037b9-109">Identyfikatory o zmienionym znaczeniu może zawierać dowolne znaki UTF-16, w nawiasach kwadratowych.</span><span class="sxs-lookup"><span data-stu-id="037b9-109">Escaped identifiers can contain any UTF-16 character enclosed in square brackets.</span></span> <span data-ttu-id="037b9-110">Na przykład [エスケープされた識別子].</span><span class="sxs-lookup"><span data-stu-id="037b9-110">For example, [エスケープされた識別子].</span></span> <span data-ttu-id="037b9-111">Porównanie identyfikatory UTF-16, znaki ucieczki nie uwzględnia wielkości liter.</span><span class="sxs-lookup"><span data-stu-id="037b9-111">The comparison of UTF-16 escaped identifiers is case insensitive.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="037b9-112">traktuje wersji liter wyglądają tak samo, które pochodzą z różnych kodowe jako różne znaki.</span><span class="sxs-lookup"><span data-stu-id="037b9-112"> treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="037b9-113">Na przykład [ABC] jest odpowiednikiem [abc], jeśli odpowiedni znak z tej samej strony kodowej.</span><span class="sxs-lookup"><span data-stu-id="037b9-113">For example, [ABC] is equivalent to [abc] if the corresponding characters are from the same code page.</span></span> <span data-ttu-id="037b9-114">Jednak w przypadku tego samego dwóch identyfikatorów z innej strony kodowe, nie są równoważne.</span><span class="sxs-lookup"><span data-stu-id="037b9-114">However, if the same two identifiers are from different code pages, they are not equivalent.</span></span>  
  
 <span data-ttu-id="037b9-115">Biały znak jest dowolny znak odstępu UTF-16.</span><span class="sxs-lookup"><span data-stu-id="037b9-115">White space is any UTF-16 white space character.</span></span>  
  
 <span data-ttu-id="037b9-116">Nowy wiersz jest znakiem nowego wiersza znormalizowane UTF-16.</span><span class="sxs-lookup"><span data-stu-id="037b9-116">A newline is any normalized UTF-16 newline character.</span></span> <span data-ttu-id="037b9-117">Na przykład "\n" i "\r\n" są traktowane jako znaki nowego wiersza, ale "\r" nie jest znakiem nowego wiersza.</span><span class="sxs-lookup"><span data-stu-id="037b9-117">For example, '\n' and '\r\n' are considered newline characters, but '\r' is not a newline character.</span></span>  
  
 <span data-ttu-id="037b9-118">Słowa kluczowe, wyrażenia i znaków interpunkcyjnych może być dowolny znak UTF-16, który normalizuje do Latin.</span><span class="sxs-lookup"><span data-stu-id="037b9-118">Keywords, expressions, and punctuation can be any UTF-16 character that normalizes to Latin.</span></span> <span data-ttu-id="037b9-119">Na przykład wybierz w japońskich strony kodowej jest nieprawidłowy — słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="037b9-119">For example, SELECT in a Japanese codepage is a valid keyword.</span></span>  
  
 <span data-ttu-id="037b9-120">Słowa kluczowe, wyrażenia i znaków interpunkcyjnych może być tylko znaki alfabetu łacińskiego.</span><span class="sxs-lookup"><span data-stu-id="037b9-120">Keywords, expressions, and punctuation can only be Latin characters.</span></span> <span data-ttu-id="037b9-121">`SELECT`w japońskich strona kodowa nie jest słowem kluczowym.</span><span class="sxs-lookup"><span data-stu-id="037b9-121">`SELECT` in a Japanese codepage is not a keyword.</span></span> <span data-ttu-id="037b9-122">+,-, *, /, =, (,), ", [,] i innych konstrukcji języka nie podane w tym polu może być tylko znaki alfabetu łacińskiego.</span><span class="sxs-lookup"><span data-stu-id="037b9-122">+, -, *, /, =, (, ), ‘, [, ] and any other language construct not quoted here can only be Latin characters.</span></span>  
  
 <span data-ttu-id="037b9-123">Proste identyfikatory mogą być tylko znaki alfabetu łacińskiego.</span><span class="sxs-lookup"><span data-stu-id="037b9-123">Simple identifiers can only be Latin characters.</span></span> <span data-ttu-id="037b9-124">Dzięki temu można uniknąć niejednoznaczności podczas porównywania, ponieważ oryginalne wartości są porównywane.</span><span class="sxs-lookup"><span data-stu-id="037b9-124">This avoids ambiguity during comparison, because original values are compared.</span></span> <span data-ttu-id="037b9-125">Na przykład ABC może być różna w w języku japońskim i Latin strony kodowe.</span><span class="sxs-lookup"><span data-stu-id="037b9-125">For example, ABC would be different in in Japanese and Latin codepages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="037b9-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="037b9-126">See Also</span></span>  
 [<span data-ttu-id="037b9-127">Omówienie SQL jednostki</span><span class="sxs-lookup"><span data-stu-id="037b9-127">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)