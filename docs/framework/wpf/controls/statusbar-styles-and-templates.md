---
title: "StatusBar — Style i szablony"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 570edc023467fb6e95cdcba23b75ac53397797c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="47c22-102">StatusBar — Style i szablony</span><span class="sxs-lookup"><span data-stu-id="47c22-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="47c22-103">W tym temacie opisano, style i szablonów dla <xref:System.Windows.Controls.Primitives.StatusBar> formantu.</span><span class="sxs-lookup"><span data-stu-id="47c22-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="47c22-104">Można zmodyfikować domyślne <xref:System.Windows.Controls.ControlTemplate> umożliwiają unikatowego wyglądu formantu.</span><span class="sxs-lookup"><span data-stu-id="47c22-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="47c22-105">Aby uzyskać więcej informacji, zobacz [Dostosowywanie wyglądu formant tworząc ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="47c22-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="47c22-106">Części pasek stanu</span><span class="sxs-lookup"><span data-stu-id="47c22-106">StatusBar Parts</span></span>  
 <span data-ttu-id="47c22-107"><xref:System.Windows.Controls.Primitives.StatusBar> Formant nie ma żadnych części o nazwie.</span><span class="sxs-lookup"><span data-stu-id="47c22-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="47c22-108">Stany pasek stanu</span><span class="sxs-lookup"><span data-stu-id="47c22-108">StatusBar States</span></span>  
 <span data-ttu-id="47c22-109">W poniższej tabeli wymieniono stany wizualne dla <xref:System.Windows.Controls.Primitives.StatusBar> formantu.</span><span class="sxs-lookup"><span data-stu-id="47c22-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="47c22-110">Nazwa stanu wizualnego</span><span class="sxs-lookup"><span data-stu-id="47c22-110">VisualState Name</span></span>|<span data-ttu-id="47c22-111">Nazwa VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="47c22-111">VisualStateGroup Name</span></span>|<span data-ttu-id="47c22-112">Opis</span><span class="sxs-lookup"><span data-stu-id="47c22-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="47c22-113">Prawidłowe</span><span class="sxs-lookup"><span data-stu-id="47c22-113">Valid</span></span>|<span data-ttu-id="47c22-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="47c22-114">ValidationStates</span></span>|<span data-ttu-id="47c22-115">Używa kontrolki <xref:System.Windows.Controls.Validation> klasy i <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> jest dołączona właściwość `false`.</span><span class="sxs-lookup"><span data-stu-id="47c22-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="47c22-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="47c22-116">InvalidFocused</span></span>|<span data-ttu-id="47c22-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="47c22-117">ValidationStates</span></span>|<span data-ttu-id="47c22-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Jest dołączona właściwość `true` ma formant ma fokus.</span><span class="sxs-lookup"><span data-stu-id="47c22-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="47c22-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="47c22-119">InvalidUnfocused</span></span>|<span data-ttu-id="47c22-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="47c22-120">ValidationStates</span></span>|<span data-ttu-id="47c22-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Jest dołączona właściwość `true` ma formant nie ma fokusa.</span><span class="sxs-lookup"><span data-stu-id="47c22-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="47c22-122">Części StatusBarItem</span><span class="sxs-lookup"><span data-stu-id="47c22-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="47c22-123"><xref:System.Windows.Controls.Primitives.StatusBarItem> Formant nie ma żadnych części o nazwie.</span><span class="sxs-lookup"><span data-stu-id="47c22-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="47c22-124">Stany pasek stanu</span><span class="sxs-lookup"><span data-stu-id="47c22-124">StatusBar States</span></span>  
 <span data-ttu-id="47c22-125">W poniższej tabeli wymieniono stany wizualne dla <xref:System.Windows.Controls.Primitives.StatusBarItem> formantu.</span><span class="sxs-lookup"><span data-stu-id="47c22-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="47c22-126">Nazwa stanu wizualnego</span><span class="sxs-lookup"><span data-stu-id="47c22-126">VisualState Name</span></span>|<span data-ttu-id="47c22-127">Nazwa VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="47c22-127">VisualStateGroup Name</span></span>|<span data-ttu-id="47c22-128">Opis</span><span class="sxs-lookup"><span data-stu-id="47c22-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="47c22-129">Prawidłowe</span><span class="sxs-lookup"><span data-stu-id="47c22-129">Valid</span></span>|<span data-ttu-id="47c22-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="47c22-130">ValidationStates</span></span>|<span data-ttu-id="47c22-131">Używa kontrolki <xref:System.Windows.Controls.Validation> klasy i <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> jest dołączona właściwość `false`.</span><span class="sxs-lookup"><span data-stu-id="47c22-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="47c22-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="47c22-132">InvalidFocused</span></span>|<span data-ttu-id="47c22-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="47c22-133">ValidationStates</span></span>|<span data-ttu-id="47c22-134"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Jest dołączona właściwość `true` ma formant ma fokus.</span><span class="sxs-lookup"><span data-stu-id="47c22-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="47c22-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="47c22-135">InvalidUnfocused</span></span>|<span data-ttu-id="47c22-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="47c22-136">ValidationStates</span></span>|<span data-ttu-id="47c22-137"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Jest dołączona właściwość `true` ma formant nie ma fokusa.</span><span class="sxs-lookup"><span data-stu-id="47c22-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="47c22-138">Przykład ControlTemplate pasek stanu</span><span class="sxs-lookup"><span data-stu-id="47c22-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="47c22-139">Poniższy przykład przedstawia sposób definiowania <xref:System.Windows.Controls.ControlTemplate> dla <xref:System.Windows.Controls.Primitives.StatusBar> formantu.</span><span class="sxs-lookup"><span data-stu-id="47c22-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="47c22-140"><xref:System.Windows.Controls.ControlTemplate> Korzysta z co najmniej jeden z następujących zasobów.</span><span class="sxs-lookup"><span data-stu-id="47c22-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="47c22-141">Pełny przykład, zobacz [style próbki ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="47c22-141">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c22-142">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="47c22-142">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="47c22-143">Style formantu i szablony</span><span class="sxs-lookup"><span data-stu-id="47c22-143">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="47c22-144">Dostosowywanie formantu</span><span class="sxs-lookup"><span data-stu-id="47c22-144">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="47c22-145">Style i tworzenia szablonów</span><span class="sxs-lookup"><span data-stu-id="47c22-145">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="47c22-146">Dostosowywanie wyglądu formant tworząc ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="47c22-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)