---
title: 'Porady: dziedziczenie z klasy UserControl'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fbeb2712742ae4c500ccd14a19c397d5d411c73a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a><span data-ttu-id="2f866-102">Porady: dziedziczenie z klasy UserControl</span><span class="sxs-lookup"><span data-stu-id="2f866-102">How to: Inherit from the UserControl Class</span></span>
<span data-ttu-id="2f866-103">Aby połączyć funkcji formanty formularzy systemu Windows co najmniej jeden z kodu niestandardowego, można utworzyć *kontrolki użytkownika*.</span><span class="sxs-lookup"><span data-stu-id="2f866-103">To combine the functionality of one or more Windows Forms controls with custom code, you can create a *user control*.</span></span> <span data-ttu-id="2f866-104">Formanty użytkownika Scalaj programowanie szybkiej kontroli, standardowych formularzy systemu Windows kontrolować funkcjonalność i wszechstronność niestandardowe właściwości i metod.</span><span class="sxs-lookup"><span data-stu-id="2f866-104">User controls combine rapid control development, standard Windows Forms control functionality, and the versatility of custom properties and methods.</span></span> <span data-ttu-id="2f866-105">Po rozpoczęciu tworzenia kontrolki użytkownika, są prezentowane w Projektancie widoczne, na której można umieścić standardowe formanty formularzy systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="2f866-105">When you begin creating a user control, you are presented with a visible designer, upon which you can place standard Windows Forms controls.</span></span> <span data-ttu-id="2f866-106">Formanty zachować wszystkie ich związanego z używaniem funkcji, a także wygląd i zachowanie (wygląd i działanie) standardowych kontrolek.</span><span class="sxs-lookup"><span data-stu-id="2f866-106">These controls retain all of their inherent functionality, as well as the appearance and behavior (look and feel) of standard controls.</span></span> <span data-ttu-id="2f866-107">Po tych kontrolek są wbudowane w formancie użytkownika, jednak nie są one dostępne za pośrednictwem kodu.</span><span class="sxs-lookup"><span data-stu-id="2f866-107">Once these controls are built into the user control, however, they are no longer available to you through code.</span></span> <span data-ttu-id="2f866-108">Kontrola użytkownika nie własną rysowania i również obsługuje wszystkie podstawowe funkcje związane z formantami.</span><span class="sxs-lookup"><span data-stu-id="2f866-108">The user control does its own painting and also handles all of the basic functionality associated with controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f866-109">Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania.</span><span class="sxs-lookup"><span data-stu-id="2f866-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2f866-110">Aby zmienić ustawienia, wybierz **Import i eksport ustawień** na **narzędzia** menu.</span><span class="sxs-lookup"><span data-stu-id="2f866-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2f866-111">Aby uzyskać więcej informacji, zobacz [Dostosowywanie ustawień środowiska w programie Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="2f866-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-user-control"></a><span data-ttu-id="2f866-112">Aby utworzyć kontrolkę użytkownika</span><span class="sxs-lookup"><span data-stu-id="2f866-112">To create a user control</span></span>  
  
1.  <span data-ttu-id="2f866-113">Utwórz nową **Biblioteka formantów systemu Windows** projektu.</span><span class="sxs-lookup"><span data-stu-id="2f866-113">Create a new **Windows Control Library** project.</span></span>  
  
     <span data-ttu-id="2f866-114">Nowy projekt zostanie utworzona z kontrola pustego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2f866-114">A new project is created with a blank user control.</span></span>  
  
2.  <span data-ttu-id="2f866-115">Przeciągnij formanty z **formularzy systemu Windows** karcie **przybornika** na z projektantem.</span><span class="sxs-lookup"><span data-stu-id="2f866-115">Drag controls from the **Windows Forms** tab of the **Toolbox** onto your designer.</span></span>  
  
3.  <span data-ttu-id="2f866-116">Formanty należy znajduje się i zaprojektowane jak mają być wyświetlane w formancie użytkownika końcowego.</span><span class="sxs-lookup"><span data-stu-id="2f866-116">These controls should be positioned and designed as you want them to appear in the final user control.</span></span> <span data-ttu-id="2f866-117">Umożliwia deweloperom korzystanie formanty składników, musi zadeklarować je jako public lub selektywnie ujawnić właściwości formantu składników.</span><span class="sxs-lookup"><span data-stu-id="2f866-117">If you want to allow developers to access the constituent controls, you must declare them as public, or selectively expose properties of the constituent control.</span></span> <span data-ttu-id="2f866-118">Aby uzyskać więcej informacji, zobacz [porady: udostępnianie właściwości formantów składnika](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md).</span><span class="sxs-lookup"><span data-stu-id="2f866-118">For details, see [How to: Expose Properties of Constituent Controls](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md).</span></span>  
  
4.  <span data-ttu-id="2f866-119">Implementowanie niestandardowych metod ani właściwości zawierające formantu.</span><span class="sxs-lookup"><span data-stu-id="2f866-119">Implement any custom methods or properties that your control will incorporate.</span></span>  
  
5.  <span data-ttu-id="2f866-120">Naciśnij klawisz F5, aby skompilować projekt i uruchomić kontrolę w **kontener testu UserControl**.</span><span class="sxs-lookup"><span data-stu-id="2f866-120">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="2f866-121">Aby uzyskać więcej informacji, zobacz [porady: testowanie zachowania UserControl w czasie wykonywania](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="2f866-121">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f866-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2f866-122">See Also</span></span>  
 [<span data-ttu-id="2f866-123">Różne typy formantów niestandardowych</span><span class="sxs-lookup"><span data-stu-id="2f866-123">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="2f866-124">Porady: dziedziczenie z klasy formantów</span><span class="sxs-lookup"><span data-stu-id="2f866-124">How to: Inherit from the Control Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [<span data-ttu-id="2f866-125">Porady: dziedziczyć Windows istniejących formantów formularzy</span><span class="sxs-lookup"><span data-stu-id="2f866-125">How to: Inherit from Existing Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [<span data-ttu-id="2f866-126">Porady: formanty autoryzacji dla formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="2f866-126">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="2f866-127">Rozwiązywanie problemów z odziedziczonymi programami obsługi zdarzeń w języku Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2f866-127">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [<span data-ttu-id="2f866-128">Porady: testowanie zachowania UserControl w czasie wykonywania</span><span class="sxs-lookup"><span data-stu-id="2f866-128">How to: Test the Run-Time Behavior of a UserControl</span></span>](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)