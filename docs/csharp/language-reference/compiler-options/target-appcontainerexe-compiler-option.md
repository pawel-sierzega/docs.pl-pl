---
title: '-docelowych: appcontainerexe (opcje kompilatora C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 61fc914b0d956bcca8e0d574296fa0723b0e1406
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/22/2018
---
# <a name="-targetappcontainerexe-c-compiler-options"></a>-docelowych: appcontainerexe (opcje kompilatora C#)
Jeśli używasz **-docelowych: appcontainerexe** — opcja kompilatora, kompilator tworzy plik wykonywalny (.exe) systemu Windows, które muszą być uruchamiane w kontenerze aplikacji. Ta opcja jest równoważna [-docelowych: winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) , ale jest przeznaczona dla [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] aplikacji.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-target:appcontainerexe  
```  
  
## <a name="remarks"></a>Uwagi  
 Aby wymagać aplikacji do uruchamiania w kontenerze aplikacji, ta opcja umożliwia ustawienie nieco [przenośny plik wykonywalny](https://msdn.microsoft.com/library/windows/desktop/ms680547(v=vs.85).aspx?id=19509) pliku (PE). Podczas tego bit jest ustawiony, jeśli metody CreateProcess podejmie próbę uruchomienia pliku wykonywalnego poza kontenerem aplikacji wystąpi błąd.  
  
 Tylko w przypadku [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) opcji Nazwa pliku wyjściowego przyjmuje nazwę pliku wejściowego, który zawiera [Main](../../../csharp/programming-guide/main-and-command-args/index.md) — metoda.  
  
 Po określeniu tej opcji w wierszu polecenia, wszystkie pliki, aż do następnego **-out** lub **-docelowego** opcji są używane do tworzenia pliku wykonywalnego.  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a>Aby ustawić tę opcję kompilatora w IDE  
  
1.  W **Eksploratora rozwiązań**, otwórz menu skrótów projektu, a następnie wybierz **właściwości**.  
  
2.  Na **aplikacji** karcie **Output typu** wybierz **aplikacji ze Sklepu Windows**.  
  
     Ta opcja jest dostępna tylko w przypadku [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] szablonów aplikacji.  
  
 Aby dowiedzieć się, jak ustawić tę opcję kompilatora programowo, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Przykład  
 Następujące polecenie kompiluje `filename.cs` do pliku wykonywalnego systemu Windows, która może działać tylko w kontenerze aplikacji.  
  
```console  
csc -target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a>Zobacz też  
 [-docelowego (opcje kompilatora C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [-docelowych: winexe (opcje kompilatora C#)](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 [Opcje kompilatora C#](../../../csharp/language-reference/compiler-options/index.md)
