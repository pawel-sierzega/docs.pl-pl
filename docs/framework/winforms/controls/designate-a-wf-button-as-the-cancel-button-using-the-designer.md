---
title: "Porady: wyznaczanie przycisku formularzy systemu Windows na przycisk Anuluj przy użyciu narzędzia Projektant"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 28e1667d086f26759e0129fc62d94ea79c68d880
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="3f031-102">Porady: wyznaczanie przycisku formularzy systemu Windows na przycisk Anuluj przy użyciu narzędzia Projektant</span><span class="sxs-lookup"><span data-stu-id="3f031-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="3f031-103">Na każdym formularzy systemu Windows, możesz wyznaczyć <xref:System.Windows.Forms.Button> formantu przycisku Anuluj.</span><span class="sxs-lookup"><span data-stu-id="3f031-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="3f031-104">Kliknięto przycisk Anuluj przy każdym naciśnięciu klawisza ESC, niezależnie od tego, który inny formant w formularzu ma fokus.</span><span class="sxs-lookup"><span data-stu-id="3f031-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="3f031-105">Aby umożliwić użytkownikowi szybkie zakończyć operację bez zatwierdzania jakiegokolwiek działania, zwykle zaplanowano taki przycisk.</span><span class="sxs-lookup"><span data-stu-id="3f031-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f031-106">Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania.</span><span class="sxs-lookup"><span data-stu-id="3f031-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3f031-107">Aby zmienić ustawienia, wybierz **Import i eksport ustawień** na **narzędzia** menu.</span><span class="sxs-lookup"><span data-stu-id="3f031-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3f031-108">Aby uzyskać więcej informacji, zobacz [Dostosowywanie ustawień środowiska w programie Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="3f031-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="3f031-109">Aby wyznaczyć przycisku Anuluj</span><span class="sxs-lookup"><span data-stu-id="3f031-109">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="3f031-110">Wybierz formularz, na którym znajduje się przycisk.</span><span class="sxs-lookup"><span data-stu-id="3f031-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="3f031-111">W **właściwości** Ustaw formularza <xref:System.Windows.Forms.Form.CancelButton%2A> właściwości <xref:System.Windows.Forms.Button> nazwy formantu.</span><span class="sxs-lookup"><span data-stu-id="3f031-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f031-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3f031-112">See Also</span></span>  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [<span data-ttu-id="3f031-113">Informacje o kontrolce przycisku</span><span class="sxs-lookup"><span data-stu-id="3f031-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="3f031-114">Sposoby wyboru formantu przycisku formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="3f031-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="3f031-115">Porady: odpowiadanie na kliknięcia przycisków formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="3f031-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="3f031-116">Porady: wyznaczanie przycisku formularzy systemu Windows na przycisk Akceptuj przy użyciu narzędzia Projektant</span><span class="sxs-lookup"><span data-stu-id="3f031-116">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [<span data-ttu-id="3f031-117">Button — formant</span><span class="sxs-lookup"><span data-stu-id="3f031-117">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)