---
title: "Porady: tworzenie obramowania wokoło formantu formularzy systemu Windows za pomocą wypełnienia"
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
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b8fc8774e1f861db989b05678235ea34e38318c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>Porady: tworzenie obramowania wokoło formantu formularzy systemu Windows za pomocą wypełnienia
W poniższym przykładzie pokazano, jak utworzyć obramowanie lub konspektu wokół <xref:System.Windows.Forms.RichTextBox> formantu. W przykładzie wartość <xref:System.Windows.Forms.Panel> formantu <xref:System.Windows.Forms.Padding> 5 i ustawia dla właściwości <xref:System.Windows.Forms.Control.Dock%2A> właściwości podrzędnej <xref:System.Windows.Forms.RichTextBox> formant <xref:System.Windows.Forms.DockStyle.Fill>. <xref:System.Windows.Forms.Control.BackColor%2A> z <xref:System.Windows.Forms.Panel> kontrola jest ustawiona na <xref:System.Drawing.Color.Blue%2A>, co powoduje niebieskie obramowanie wokół <xref:System.Windows.Forms.RichTextBox> formantu.  
  
## <a name="example"></a>Przykład  
 [!code-csharp[System.Windows.Forms.Padding#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Forms.Padding>  
 [Margines i wypełnienie w kontrolkach formularzy Windows Forms](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)
