---
title: 'Porady: wyznaczanie przycisku formularzy systemu Windows na przycisk Anuluj'
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
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3bbdf2ec4f2353662f1077b9d95966e0a2ebd316
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="ba212-102">Porady: wyznaczanie przycisku formularzy systemu Windows na przycisk Anuluj</span><span class="sxs-lookup"><span data-stu-id="ba212-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="ba212-103">Na każdym formularzy systemu Windows, możesz wyznaczyć <xref:System.Windows.Forms.Button> formantu przycisku Anuluj.</span><span class="sxs-lookup"><span data-stu-id="ba212-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="ba212-104">Kliknięto przycisk Anuluj przy każdym naciśnięciu klawisza ESC, niezależnie od tego, który inny formant w formularzu ma fokus.</span><span class="sxs-lookup"><span data-stu-id="ba212-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="ba212-105">Aby umożliwić użytkownikowi szybkie zakończyć operację bez zatwierdzania jakiegokolwiek działania, zwykle zaplanowano taki przycisk.</span><span class="sxs-lookup"><span data-stu-id="ba212-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="ba212-106">Aby wyznaczyć przycisku Anuluj</span><span class="sxs-lookup"><span data-stu-id="ba212-106">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="ba212-107">Ustaw formularza <xref:System.Windows.Forms.Form.CancelButton%2A> właściwości do odpowiedniego <xref:System.Windows.Forms.Button> formantu.</span><span class="sxs-lookup"><span data-stu-id="ba212-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ba212-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ba212-108">See Also</span></span>  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [<span data-ttu-id="ba212-109">Informacje o kontrolce przycisku</span><span class="sxs-lookup"><span data-stu-id="ba212-109">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="ba212-110">Sposoby wyboru formantu przycisku formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="ba212-110">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="ba212-111">Porady: odpowiadanie na kliknięcia przycisków formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="ba212-111">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="ba212-112">Porady: wyznaczanie przycisku formularzy systemu Windows na przycisk Akceptuj</span><span class="sxs-lookup"><span data-stu-id="ba212-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)  
 [<span data-ttu-id="ba212-113">Button — formant</span><span class="sxs-lookup"><span data-stu-id="ba212-113">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)