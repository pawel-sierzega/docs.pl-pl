---
title: "Porady: skojarzenie właściwości ContextMenuStrip z formantem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7307af535dce39443b623e1fee4491dd48ffbd94
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a>Porady: skojarzenie właściwości ContextMenuStrip z formantem
Po utworzeniu sieci formantów i menu skrótów, umożliwia wyświetlenie menu skrótów danego po kliknięciu formantu poniższych procedur. Te procedury skojarzyć <xref:System.Windows.Forms.ContextMenuStrip> z formularza systemu Windows i <xref:System.Windows.Forms.ToolStrip> formantu.  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a>Skojarzenie właściwości ContextMenuStrip z formularza systemu Windows  
  
1.  Ustaw <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> właściwość na nazwę skojarzonego <xref:System.Windows.Forms.ContextMenuStrip>.  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a>Skojarzenie właściwości ContextMenuStrip z formantu ToolStrip  
  
1.  Ustawianie formantu <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> właściwość na nazwę skojarzonego <xref:System.Windows.Forms.ContextMenuStrip>.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu tworzy formularz systemu Windows i <xref:System.Windows.Forms.ToolStrip>i kojarzy innej <xref:System.Windows.Forms.ContextMenuStrip> kontroli z każdym z nich.  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Ten przykład wymaga:  
  
-   Odwołania do zestawów systemu, dane systemowe, System.Drawing i System.Windows.Forms.  
  
 Informacji dotyczących tworzenia tego przykładu z wiersza polecenia dla [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] lub [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], zobacz [tworzenie z wiersza polecenia](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) lub [kompilowania z wiersza polecenia csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Można także utworzyć tym przykładzie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] przez wklejenie kodu do nowego projektu.  Zobacz też [porady: kompilowanie i uruchamianie pełną Windows formularze kodu przykład za pomocą programu Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>  
 <xref:System.Windows.Forms.ToolStrip>  
 [Instrukcje: dodawanie elementów menu do kontrolki ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md)  
 [ContextMenuStrip, kontrolka](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
