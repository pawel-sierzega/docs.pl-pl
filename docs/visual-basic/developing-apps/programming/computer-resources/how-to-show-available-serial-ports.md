---
title: "Porady: wyświetlanie dostępnych portów seryjnych w Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- serial ports, availability
- My.Computer.Ports.SerialPortNames property
- My.Computer.Ports object
- ports, serial port availability
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1dc12d8ad4c27eff346ccb6a7f5fd2ae3bd76701
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-show-available-serial-ports-in-visual-basic"></a>Porady: wyświetlanie dostępnych portów seryjnych w Visual Basic
W tym temacie opisano sposób użycia `My.Computer.Ports` Aby wyświetlić dostępne porty szeregowe komputera w [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
 Umożliwia użytkownikowi wybranie port, który można użyć nazwy porty szeregowe są umieszczane w <xref:System.Windows.Forms.ListBox> formantu.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie pętli wszystkie ciągi który `My.Computer.Ports.SerialPortNames` zwraca właściwości. Te parametry są nazwami dostępne porty szeregowe na komputerze.  
  
 Zazwyczaj użytkownik wybiera które portu szeregowego należy używać aplikacji z listy dostępnych portów. W tym przykładzie nazwy portu szeregowego są przechowywane w <xref:System.Windows.Forms.ListBox> formantu. Aby uzyskać więcej informacji, zobacz [kontrolki ListBox](../../../../framework/winforms/controls/listbox-control-windows-forms.md).  
  
 [!code-vb[VbVbalrMyComputer#45](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-show-available-serial-ports_1.vb)]  
  
 W tym przykładzie kodu jest również dostępny jako fragmentu kodu IntelliSense. Selektor wstawek kodu, znajduje się się w **sieć i łączność**. Aby uzyskać więcej informacji, zobacz [wstawki kodu](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Ten przykład wymaga:  
  
-   Odwołanie projektu do System.Windows.Forms.dll.  
  
-   Dostęp do elementów członkowskich <xref:System.Windows.Forms> przestrzeni nazw. Dodaj `Imports` instrukcję, jeśli użytkownik jest całkowicie niekwalifikujących nazwy elementów członkowskich w kodzie. Aby uzyskać więcej informacji, zobacz [Importy — instrukcja (.NET Namespace i Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
-   Formularz zainstalowanego <xref:System.Windows.Forms.ListBox> formantu o nazwie `ListBox1`.  
  
## <a name="robust-programming"></a>Niezawodne programowanie  
 Nie trzeba używać <xref:System.Windows.Forms.ListBox> formantu, aby wyświetlić nazwy dostępnego portu szeregowego. Zamiast tego można użyć <xref:System.Windows.Forms.ComboBox> lub inny formant. Jeśli aplikacja nie wymaga odpowiedzi od użytkownika, możesz użyć <xref:System.Windows.Forms.TextBox> formantu, aby wyświetlić informacje.  
  
> [!NOTE]
>  Nazwy portów zwrócony przez `My.Computer.Ports.SerialPortNames` może być niepoprawna uruchomienia w systemach Windows 98. Aby zapobiec błędom aplikacji, użyj obsługi wyjątków, takich jak `Try...Catch...Finally` instrukcji lub `Using` instrukcji, gdy używane są nazwy portu otworzyć porty.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:Microsoft.VisualBasic.Devices.Ports>  
 [Porady: modemy dostępowe powiązane z portami seryjnymi](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)  
 [Porady: wysyłanie ciągów do portów seryjnych](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)  
 [Porady: odbieranie ciągów z portów seryjnych](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)
