---
title: "Przegląd Masek krycia"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- brushes [WPF], opacity masks
- masks [WPF], opacity
- opacity [WPF], masks
ms.assetid: 22367fab-5f59-4583-abfd-db2bf86eaef7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6cd077d1e24fa50dc42a2169b45fe38930cc76c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="opacity-masks-overview"></a><span data-ttu-id="5dca4-102">Przegląd Masek krycia</span><span class="sxs-lookup"><span data-stu-id="5dca4-102">Opacity Masks Overview</span></span>
<span data-ttu-id="5dca4-103">Nieprzezroczystość maski umożliwiają upewnij części elementu lub visual przezroczystego lub częściowo przezroczysty.</span><span class="sxs-lookup"><span data-stu-id="5dca4-103">Opacity masks enable you to make portions of an element or visual either transparent or partially transparent.</span></span> <span data-ttu-id="5dca4-104">Aby utworzyć maskę przezroczystości, należy zastosować <xref:System.Windows.Media.Brush> do <xref:System.Windows.UIElement.OpacityMask%2A> właściwości elementu lub <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="5dca4-104">To create an opacity mask, you apply a <xref:System.Windows.Media.Brush> to the <xref:System.Windows.UIElement.OpacityMask%2A> property of an element or <xref:System.Windows.Media.Visual>.</span></span>  <span data-ttu-id="5dca4-105">Pędzel jest mapowana do elementu lub visual, a wartość nieprzezroczystości każdego piksela pędzla służy do określania wynikowy nieprzezroczystość każdego piksela odpowiedniego elementu lub visual.</span><span class="sxs-lookup"><span data-stu-id="5dca4-105">The brush is mapped to the element or visual, and the opacity value of each brush pixel is used to determine the resulting opacity of each corresponding pixel of the element or visual.</span></span>  
  
<a name="prereqs"></a>   
## <a name="prerequisites"></a><span data-ttu-id="5dca4-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="5dca4-106">Prerequisites</span></span>  
 <span data-ttu-id="5dca4-107">To omówienie przyjęto założenie, że czytelnik zna <xref:System.Windows.Media.Brush> obiektów.</span><span class="sxs-lookup"><span data-stu-id="5dca4-107">This overview assumes that you are familiar with <xref:System.Windows.Media.Brush> objects.</span></span> <span data-ttu-id="5dca4-108">Aby obejrzeć wprowadzenie do przy użyciu pędzle, zobacz [Malowanie z kolorami i przegląd gradienty](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5dca4-108">For an introduction to using brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span> <span data-ttu-id="5dca4-109">Aby uzyskać informacje o <xref:System.Windows.Media.ImageBrush> i <xref:System.Windows.Media.DrawingBrush>, zobacz [malowanie obrazów, rysunki i elementy wizualne](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="5dca4-109">For information about <xref:System.Windows.Media.ImageBrush> and <xref:System.Windows.Media.DrawingBrush>, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
<a name="opacitymasks"></a>   
## <a name="creating-visual-effects-with-opacity-masks"></a><span data-ttu-id="5dca4-110">Tworzenie efektów wizualnych za pomocą maski przezroczystości</span><span class="sxs-lookup"><span data-stu-id="5dca4-110">Creating Visual Effects with Opacity Masks</span></span>  
 <span data-ttu-id="5dca4-111">Maskę przezroczystości działa przez mapowanie jego zawartość do elementu lub visual.</span><span class="sxs-lookup"><span data-stu-id="5dca4-111">An opacity mask works by mapping its contents to the element or visual.</span></span> <span data-ttu-id="5dca4-112">Kanał alfa każdego pikseli pędzla następnie są używane do określania wynikowy nieprzezroczystość elementu lub jego visual odpowiedniego pikseli; rzeczywiste kolor pędzla jest ignorowana.</span><span class="sxs-lookup"><span data-stu-id="5dca4-112">The alpha channel of each of the brush's pixels are then used to determine the resulting opacity of the element or visual's corresponding pixels; the actual color of the brush is ignored.</span></span> <span data-ttu-id="5dca4-113">Jeśli dany część pędzla jest niewidoczny, odpowiednich części elementu lub visual staje się przezroczysty.</span><span class="sxs-lookup"><span data-stu-id="5dca4-113">If a given portion of the brush is transparent, the corresponding portion of the element or visual becomes transparent.</span></span> <span data-ttu-id="5dca4-114">W przypadku nieprzezroczyste danej części pędzla nieprzezroczystość odpowiednich części elementu lub visual pozostaje niezmieniona.</span><span class="sxs-lookup"><span data-stu-id="5dca4-114">If a given portion of the brush is opaque, the opacity of the corresponding portion of the element or visual is unchanged.</span></span> <span data-ttu-id="5dca4-115">Nieprzezroczystość określony przez maskę przezroczystości w połączeniu z ustawienia nieprzezroczystość w elemencie lub visual.</span><span class="sxs-lookup"><span data-stu-id="5dca4-115">The opacity specified by the opacity mask is combined with any opacity settings present in the element or visual.</span></span> <span data-ttu-id="5dca4-116">Na przykład jeśli element jest 25 procent nieprzezroczystych i zastosowanej maskę przezroczystości przejścia z całkowicie nieprzezroczyste, aby w pełni przezroczyste, wynik jest element, który przechodzi z nieprzezroczystość 25 procent w pełni przezroczyste.</span><span class="sxs-lookup"><span data-stu-id="5dca4-116">For example, if an element is 25 percent opaque and an opacity mask is applied that transitions from fully opaque to fully transparent, the result is an element that transitions from 25 percent opacity to fully transparent.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5dca4-117">Mimo że przykłady w tym omówieniu przedstawiają sposób używania masek nieprzezroczystości dla elementów obrazu, maskę przezroczystości mogą być stosowane do dowolnego elementu lub <xref:System.Windows.Media.Visual>, w tym paneli i kontrolek.</span><span class="sxs-lookup"><span data-stu-id="5dca4-117">Although the examples in this overview demonstrate the use of opacity masks on image elements, an opacity mask may be applied to any element or <xref:System.Windows.Media.Visual>, including panels and controls.</span></span>  
  
 <span data-ttu-id="5dca4-118">Nieprzezroczystość maski służą do utworzyć interesujące efekty wizualne, takie jak obrazy lub stopniowe przycisków z widoku, aby dodać tekstury elementów lub połączyć gradientów do produkcji szkła przypominającej powierzchni.</span><span class="sxs-lookup"><span data-stu-id="5dca4-118">Opacity masks are used to create interesting visual effects, such as to create images or buttons that fade from view, to add textures to elements, or to combine gradients to produce glass-like surfaces.</span></span> <span data-ttu-id="5dca4-119">Poniższa ilustracja przedstawia użycie maskę przezroczystości.</span><span class="sxs-lookup"><span data-stu-id="5dca4-119">The following illustration demonstrates the use of an opacity mask.</span></span> <span data-ttu-id="5dca4-120">Tle specjalną służy do wyświetlenia przezroczyste obiekty maski.</span><span class="sxs-lookup"><span data-stu-id="5dca4-120">A checkered background is used to show the transparent portions of the mask.</span></span>  
  
 <span data-ttu-id="5dca4-121">![Obiekt z maską nieprzezroczystości LinearGradientBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-opacitymask-imageexample.png "wcpsdk_graphicsmm_opacitymask_imageexample")</span><span class="sxs-lookup"><span data-stu-id="5dca4-121">![Object with a LinearGradientBrush opacity mask](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-opacitymask-imageexample.png "wcpsdk_graphicsmm_opacitymask_imageexample")</span></span>  
<span data-ttu-id="5dca4-122">Przykład maskowania nieprzezroczystość.</span><span class="sxs-lookup"><span data-stu-id="5dca4-122">Opacity masking example</span></span>  
  
<a name="creatingopacitymasks"></a>   
## <a name="creating-an-opacity-mask"></a><span data-ttu-id="5dca4-123">Tworzenie maskę przezroczystości</span><span class="sxs-lookup"><span data-stu-id="5dca4-123">Creating an Opacity Mask</span></span>  
 <span data-ttu-id="5dca4-124">Aby utworzyć maskę przezroczystości, należy utworzyć <xref:System.Windows.Media.Brush> i zastosować je do <xref:System.Windows.UIElement.OpacityMask%2A> właściwości elementu lub visual.</span><span class="sxs-lookup"><span data-stu-id="5dca4-124">To create an opacity mask, you create a <xref:System.Windows.Media.Brush> and apply it to the <xref:System.Windows.UIElement.OpacityMask%2A> property of an element or visual.</span></span> <span data-ttu-id="5dca4-125">Można użyć dowolnego typu <xref:System.Windows.Media.Brush> jak maskę przezroczystości.</span><span class="sxs-lookup"><span data-stu-id="5dca4-125">You can use any type of <xref:System.Windows.Media.Brush> as an opacity mask.</span></span>  
  
-   <span data-ttu-id="5dca4-126"><xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>: Umożliwia pokazanie element lub visual zanikania z widoku.</span><span class="sxs-lookup"><span data-stu-id="5dca4-126"><xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>: Used to make an element or visual fade from view.</span></span>  
  
     <span data-ttu-id="5dca4-127">Poniższy obraz przedstawia <xref:System.Windows.Media.LinearGradientBrush> używany jak maskę przezroczystości.</span><span class="sxs-lookup"><span data-stu-id="5dca4-127">The following image shows a <xref:System.Windows.Media.LinearGradientBrush> used as an opacity mask.</span></span>  
  
     <span data-ttu-id="5dca4-128">![Obiekt o nieprzezroczystości LinearGradientBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-brushes-lineagradientopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_lineagradientopacitymasksingle")</span><span class="sxs-lookup"><span data-stu-id="5dca4-128">![An object with an LinearGradientBrush opacity mask](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-brushes-lineagradientopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_lineagradientopacitymasksingle")</span></span>  
<span data-ttu-id="5dca4-129">Przykład maskowania nieprzezroczystości LinearGradientBrush</span><span class="sxs-lookup"><span data-stu-id="5dca4-129">LinearGradientBrush Opacity Masking Example</span></span>  
  
-   <span data-ttu-id="5dca4-130"><xref:System.Windows.Media.ImageBrush>: Używany do tworzenia tekstury i nietrwałego lub przerwana efekty krawędzi.</span><span class="sxs-lookup"><span data-stu-id="5dca4-130"><xref:System.Windows.Media.ImageBrush>: Used to create texture and soft or torn edge effects.</span></span>  
  
     <span data-ttu-id="5dca4-131">Poniższy obraz przedstawia <xref:System.Windows.Media.ImageBrush> używany jak maskę przezroczystości.</span><span class="sxs-lookup"><span data-stu-id="5dca4-131">The following image shows an <xref:System.Windows.Media.ImageBrush> used as an opacity mask.</span></span>  
  
     <span data-ttu-id="5dca4-132">![Obiekt, który ma nieprzezroczystości ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-brushes-imageasopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_imageasopacitymasksingle")</span><span class="sxs-lookup"><span data-stu-id="5dca4-132">![Object that has an ImageBrush opacity mask](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-brushes-imageasopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_imageasopacitymasksingle")</span></span>  
<span data-ttu-id="5dca4-133">Przykład maskowania nieprzezroczystości LinearGradientBrush</span><span class="sxs-lookup"><span data-stu-id="5dca4-133">LinearGradientBrush opacity masking example</span></span>  
  
-   <span data-ttu-id="5dca4-134"><xref:System.Windows.Media.DrawingBrush>: Używany do tworzenia złożonych nieprzezroczystość maski z wzorców kształtów, obrazy i gradienty.</span><span class="sxs-lookup"><span data-stu-id="5dca4-134"><xref:System.Windows.Media.DrawingBrush>: Used to create complex opacity masks from patterns of shapes, images, and gradients.</span></span>  
  
     <span data-ttu-id="5dca4-135">Poniższy obraz przedstawia <xref:System.Windows.Media.DrawingBrush> używany jak maskę przezroczystości.</span><span class="sxs-lookup"><span data-stu-id="5dca4-135">The following image shows a <xref:System.Windows.Media.DrawingBrush> used as an opacity mask.</span></span>  
  
     <span data-ttu-id="5dca4-136">![Obiekt z maską przezroczystość pędzla](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-drawingbrushasopacitymask-single.jpg "wcpsdk_drawingbrushasopacitymask_single")</span><span class="sxs-lookup"><span data-stu-id="5dca4-136">![Object with a DrawingBrush opacity mask](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-drawingbrushasopacitymask-single.jpg "wcpsdk_drawingbrushasopacitymask_single")</span></span>  
<span data-ttu-id="5dca4-137">Przykład maskowania przezroczystość pędzla</span><span class="sxs-lookup"><span data-stu-id="5dca4-137">DrawingBrush opacity masking example</span></span>  
  
 <span data-ttu-id="5dca4-138">Pędzle gradientów (<xref:System.Windows.Media.LinearGradientBrush> i <xref:System.Windows.Media.RadialGradientBrush>) są szczególnie odpowiednie do użycia jako maskę przezroczystości.</span><span class="sxs-lookup"><span data-stu-id="5dca4-138">The gradient brushes (<xref:System.Windows.Media.LinearGradientBrush> and <xref:System.Windows.Media.RadialGradientBrush>) are particularly well-suited for use as an opacity mask.</span></span> <span data-ttu-id="5dca4-139">Ponieważ <xref:System.Windows.Media.SolidColorBrush> wypełnienia jako obszar kolorem jednolite, należy niską nieprzezroczystość maski; przy użyciu <xref:System.Windows.Media.SolidColorBrush> jest równoznaczne z ustawieniem elementu lub jego visual <xref:System.Windows.UIElement.OpacityMask%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="5dca4-139">Because a <xref:System.Windows.Media.SolidColorBrush> fills an area with a uniform color, they make poor opacity masks; using a <xref:System.Windows.Media.SolidColorBrush> is equivalent to setting the element's or visual's <xref:System.Windows.UIElement.OpacityMask%2A> property.</span></span>  
  
<a name="creatingopacitymaskswithgradients"></a>   
## <a name="using-a-gradient-as-an-opacity-mask"></a><span data-ttu-id="5dca4-140">Przy użyciu gradientu jak maskę przezroczystości</span><span class="sxs-lookup"><span data-stu-id="5dca4-140">Using a Gradient as an Opacity Mask</span></span>  
 <span data-ttu-id="5dca4-141">Aby utworzyć wypełnienia gradientowego, należy określić co najmniej dwa gradientu.</span><span class="sxs-lookup"><span data-stu-id="5dca4-141">To create a gradient fill, you specify two or more gradient stops.</span></span> <span data-ttu-id="5dca4-142">Zawiera każdego gradientu opisano kolorów i pozycji (zobacz [Malowanie z kolorami i przegląd gradienty](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) Aby uzyskać więcej informacji na temat tworzenia i używania gradienty).</span><span class="sxs-lookup"><span data-stu-id="5dca4-142">Each gradient stop contains describes a color and a position (see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) for more information about creating and using gradients).</span></span> <span data-ttu-id="5dca4-143">Proces jest taki sam, używając gradientu jak maskę przezroczystości z tą różnicą, że zamiast mieszania kolorów, gradientu maskę przezroczystości miesza wartości kanału alfa.</span><span class="sxs-lookup"><span data-stu-id="5dca4-143">The process is the same when using a gradient as an opacity mask, except that, instead of blending colors, the opacity mask gradient blends alpha channel values.</span></span> <span data-ttu-id="5dca4-144">Tak rzeczywiste kolor gradientu treści nie ma znaczenia; ma znaczenie tylko kanału alfa lub przezroczystość poszczególnych kolorów.</span><span class="sxs-lookup"><span data-stu-id="5dca4-144">So the actual color of the gradient's contents do not matter; only the alpha channel, or opacity, of each color matters.</span></span> <span data-ttu-id="5dca4-145">Poniżej przedstawiono przykład.</span><span class="sxs-lookup"><span data-stu-id="5dca4-145">The following is an example.</span></span>  
  
 [!code-xaml[OpacityMasksSnippet#LinearGradientOpacityMaskonImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/GradientBrushExample.xaml#lineargradientopacitymaskonimage)]  
  
<a name="specifyinggradientcolors"></a>   
## <a name="specifying-gradient-stops-for-an-opacity-mask"></a><span data-ttu-id="5dca4-146">Określanie gradientu maskę przezroczystości</span><span class="sxs-lookup"><span data-stu-id="5dca4-146">Specifying Gradient Stops for an Opacity Mask</span></span>  
 <span data-ttu-id="5dca4-147">W poprzednim przykładzie, kolor zdefiniowany przez system <xref:System.Windows.Media.Colors.Black%2A> jest używany jako kolor początkowy gradientu.</span><span class="sxs-lookup"><span data-stu-id="5dca4-147">In the previous example, the system-defined color <xref:System.Windows.Media.Colors.Black%2A> is used as the starting color of the gradient.</span></span> <span data-ttu-id="5dca4-148">Ponieważ wszystkie kolory w <xref:System.Windows.Media.Colors> klasy, z wyjątkiem <xref:System.Windows.Media.Colors.Transparent%2A>, są całkowicie nieprzezroczyste, może służyć do definiowania po prostu początkowy kolor gradientu nieprzezroczystość maski.</span><span class="sxs-lookup"><span data-stu-id="5dca4-148">Because all of the colors in the <xref:System.Windows.Media.Colors> class, except <xref:System.Windows.Media.Colors.Transparent%2A>, are fully opaque, they can be used to simply define a starting color for a gradient opacity mask.</span></span>  
  
 <span data-ttu-id="5dca4-149">Dodatkową kontrolę nad wartości alfa podczas definiowania maskę przezroczystości, można określić dla kanału alfa kolorów przy użyciu [!INCLUDE[TLA#tla_argb](../../../../includes/tlasharptla-argb-md.md)] szesnastkowym znaczników lub przy użyciu <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="5dca4-149">For additional control over alpha values when defining an opacity mask, you can specify the alpha channel of colors using [!INCLUDE[TLA#tla_argb](../../../../includes/tlasharptla-argb-md.md)] hexadecimal notation in markup or using the <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=nameWithType> method.</span></span>  
  
<a name="argbsyntax"></a>   
### <a name="specifying-color-opacity-in-xaml"></a><span data-ttu-id="5dca4-150">Określanie Przezroczystość koloru w "XAML"</span><span class="sxs-lookup"><span data-stu-id="5dca4-150">Specifying Color Opacity in "XAML"</span></span>  
 <span data-ttu-id="5dca4-151">W [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], możesz użyć [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] szesnastkowym, aby określić przezroczystość poszczególnych kolorów.</span><span class="sxs-lookup"><span data-stu-id="5dca4-151">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you use  [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] hexadecimal notation to specify the opacity of individual colors.</span></span> [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)]<span data-ttu-id="5dca4-152">szesnastkowym używa następującej składni:</span><span class="sxs-lookup"><span data-stu-id="5dca4-152"> hexadecimal notation uses the following syntax:</span></span>  
  
 <span data-ttu-id="5dca4-153">`#`**aa** *rrggbb*</span><span class="sxs-lookup"><span data-stu-id="5dca4-153">`#` **aa** *rrggbb*</span></span>  
  
 <span data-ttu-id="5dca4-154">*Aa* w poprzednim wierszu reprezentuje wartość szesnastkowa dwucyfrowe używany do określenia Przezroczystość koloru.</span><span class="sxs-lookup"><span data-stu-id="5dca4-154">The *aa* in the previous line represents a two-digit hexadecimal value used to specify the opacity of the color.</span></span> <span data-ttu-id="5dca4-155">*Rr*, *gg*, i *bb* każdy reprezentuje wartość szesnastkowa dwóch cyfr używana do określania ilości czerwony, zielony i niebieski w kolor.</span><span class="sxs-lookup"><span data-stu-id="5dca4-155">The *rr*, *gg*, and *bb* each represent a two digit hexadecimal value used to specify the amount of red, green, and blue in the color.</span></span> <span data-ttu-id="5dca4-156">Każdy szesnastkową wartością cyfrową może mieć wartość z zakresu od 0 – 9 lub A-F.</span><span class="sxs-lookup"><span data-stu-id="5dca4-156">Each hexadecimal digit may have a value from 0-9 or A-F.</span></span> <span data-ttu-id="5dca4-157">najmniejsza wartość to 0, a F jest większa.</span><span class="sxs-lookup"><span data-stu-id="5dca4-157">0 is the smallest value, and F is the greatest.</span></span> <span data-ttu-id="5dca4-158">Wartości alfa 00 Określa kolor, który jest całkowicie niewidoczne, gdy wartość alfa FF tworzy kolor jest całkowicie nieprzezroczyste.</span><span class="sxs-lookup"><span data-stu-id="5dca4-158">An alpha value of 00 specifies a color that is completely transparent, while an alpha value of FF creates a color that is fully opaque.</span></span>  <span data-ttu-id="5dca4-159">W poniższym przykładzie szesnastkową [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] notacji służy do określania dwóch kolorów.</span><span class="sxs-lookup"><span data-stu-id="5dca4-159">In the following example, hexadecimal [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] notation is used to specify two colors.</span></span> <span data-ttu-id="5dca4-160">Pierwsza to całkowicie nieprzezroczyste, podczas gdy druga jest całkowicie niewidoczne.</span><span class="sxs-lookup"><span data-stu-id="5dca4-160">The first is fully opaque, while the second is completely transparent.</span></span>  
  
 [!code-xaml[OpacityMasksSnippet#AARRGGBBValueonOpacityMask](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/GradientBrushExample.xaml#aarrggbbvalueonopacitymask)]  
  
<a name="usingimageasopacitymask"></a>   
## <a name="using-an-image-as-an-opacity-mask"></a><span data-ttu-id="5dca4-161">Przy użyciu obrazu jak maskę przezroczystości</span><span class="sxs-lookup"><span data-stu-id="5dca4-161">Using an Image as an Opacity Mask</span></span>  
 <span data-ttu-id="5dca4-162">Obrazy można również jak maskę przezroczystości.</span><span class="sxs-lookup"><span data-stu-id="5dca4-162">Images can also be used as an opacity mask.</span></span> <span data-ttu-id="5dca4-163">Na poniższej ilustracji przedstawiono przykład.</span><span class="sxs-lookup"><span data-stu-id="5dca4-163">The following image shows an example.</span></span> <span data-ttu-id="5dca4-164">Tle specjalną służy do wyświetlenia przezroczyste obiekty maski.</span><span class="sxs-lookup"><span data-stu-id="5dca4-164">A checkered background is used to show the transparent portions of the mask.</span></span>  
  
 <span data-ttu-id="5dca4-165">![Obiekt z maską nieprzezroczystości ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-imageasopacitymask.png "wcpsdk_graphicsmm_imageasopacitymask")</span><span class="sxs-lookup"><span data-stu-id="5dca4-165">![An object with an ImageBrush opacity mask](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-imageasopacitymask.png "wcpsdk_graphicsmm_imageasopacitymask")</span></span>  
<span data-ttu-id="5dca4-166">Przykład maskowania nieprzezroczystość.</span><span class="sxs-lookup"><span data-stu-id="5dca4-166">Opacity masking example</span></span>  
  
 <span data-ttu-id="5dca4-167">Aby użyć obrazu jak maskę przezroczystości, użyj <xref:System.Windows.Media.ImageBrush> zawiera obraz.</span><span class="sxs-lookup"><span data-stu-id="5dca4-167">To use an image as an opacity mask, use an <xref:System.Windows.Media.ImageBrush> to contain the image.</span></span> <span data-ttu-id="5dca4-168">Podczas tworzenia obrazu do użycia jak maskę przezroczystości, zapisania obrazu w formacie, który obsługuje wiele poziomów przezroczystości, takich jak [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dca4-168">When creating an image to be used as an opacity mask, save the image in a format that supports multiple levels of transparency, such as [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)].</span></span> <span data-ttu-id="5dca4-169">Poniższy przykład przedstawia kod używany do utworzenia na poprzedniej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="5dca4-169">The following example shows the code used to create the previous illustration.</span></span>  
  
 [!code-xaml[OpacityMasksSnippet#UIElementOpacityMask](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/ImageBrushExample.xaml#uielementopacitymask)]  
  
<a name="tilingimageopacitymask"></a>   
### <a name="using-a-tiled-image-as-an-opacity-mask"></a><span data-ttu-id="5dca4-170">Przy użyciu obrazu sąsiadującym jak maskę przezroczystości</span><span class="sxs-lookup"><span data-stu-id="5dca4-170">Using a Tiled Image as an Opacity Mask</span></span>  
 <span data-ttu-id="5dca4-171">W poniższym przykładzie ten sam obraz jest używana z inną <xref:System.Windows.Media.ImageBrush>, ale pędzla kafelków funkcje są używane do tworzenia Kafelki kwadratu obrazu 50 pikseli.</span><span class="sxs-lookup"><span data-stu-id="5dca4-171">In the following example, the same image is used with another <xref:System.Windows.Media.ImageBrush>, but the brush's tiling features are used to produce tiles of the image 50 pixels square.</span></span>  
  
 [!code-xaml[OpacityMasksSnippet#TiledImageasOpacityMask](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/ImageBrushExample.xaml#tiledimageasopacitymask)]  
  
<a name="drawingbrushasopacitymask"></a>   
## <a name="creating-an-opacity-mask-from-a-drawing"></a><span data-ttu-id="5dca4-172">Tworzenie z rysunku maskę przezroczystości</span><span class="sxs-lookup"><span data-stu-id="5dca4-172">Creating an Opacity Mask from a Drawing</span></span>  
 <span data-ttu-id="5dca4-173">Rysunki mogą być używane maskę przezroczystości.</span><span class="sxs-lookup"><span data-stu-id="5dca4-173">Drawings can be used an opacity mask.</span></span> <span data-ttu-id="5dca4-174">Kształty znajdujących się na rysunku się można podać gradientów, pełne kolory, obrazy lub nawet inne rysunki.</span><span class="sxs-lookup"><span data-stu-id="5dca4-174">The shapes contained within the drawing can themselves be filled with gradients, solid colors, images, or even other drawings.</span></span> <span data-ttu-id="5dca4-175">Na poniższej ilustracji przedstawiono przykład rysunku używany jak maskę przezroczystości.</span><span class="sxs-lookup"><span data-stu-id="5dca4-175">The following image shows an example of a drawing used as an opacity mask.</span></span> <span data-ttu-id="5dca4-176">Tle specjalną służy do wyświetlenia przezroczyste obiekty maski.</span><span class="sxs-lookup"><span data-stu-id="5dca4-176">A checkered background is used to show the transparent portions of the mask.</span></span>  
  
 <span data-ttu-id="5dca4-177">![Obiekt z maską przezroczystość pędzla](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-drawingbrushasopacitymask.png "wcpsdk_drawingbrushasopacitymask")</span><span class="sxs-lookup"><span data-stu-id="5dca4-177">![An object with a DrawingBrush opacity mask](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-drawingbrushasopacitymask.png "wcpsdk_drawingbrushasopacitymask")</span></span>  
<span data-ttu-id="5dca4-178">Przykład maskowania przezroczystość pędzla</span><span class="sxs-lookup"><span data-stu-id="5dca4-178">DrawingBrush opacity masking example</span></span>  
  
 <span data-ttu-id="5dca4-179">Aby użyć rysunku jak maskę przezroczystości, użyj <xref:System.Windows.Media.DrawingBrush> zawiera rysunku.</span><span class="sxs-lookup"><span data-stu-id="5dca4-179">To use a drawing as an opacity mask, use a <xref:System.Windows.Media.DrawingBrush> to contain the drawing.</span></span> <span data-ttu-id="5dca4-180">W poniższym przykładzie pokazano kod, który został użyty do utworzenia na poprzedniej ilustracji:</span><span class="sxs-lookup"><span data-stu-id="5dca4-180">The following example shows the code used to create the previous illustration:</span></span>  
  
 [!code-xaml[OpacityMasksSnippet#OpacityMaskfromDrawing](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/DrawingBrushExample.xaml#opacitymaskfromdrawing)]  
  
<a name="tileddrawingbrush"></a>   
### <a name="using-a-tiled-drawing-as-an-opacity-mask"></a><span data-ttu-id="5dca4-181">Za pomocą rysowania sąsiadującym jak maskę przezroczystości</span><span class="sxs-lookup"><span data-stu-id="5dca4-181">Using a Tiled Drawing as an Opacity Mask</span></span>  
 <span data-ttu-id="5dca4-182">Podobnie jak <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> można wprowadzić na kafelku jej rysowania.</span><span class="sxs-lookup"><span data-stu-id="5dca4-182">Like the <xref:System.Windows.Media.ImageBrush>, the <xref:System.Windows.Media.DrawingBrush> can be made to tile its drawing.</span></span> <span data-ttu-id="5dca4-183">W poniższym przykładzie pędzla do rysowania służy do tworzenia maskę przezroczystości sąsiadującym.</span><span class="sxs-lookup"><span data-stu-id="5dca4-183">In the following example, a drawing brush is used to create a tiled opacity mask.</span></span>  
  
 [!code-xaml[OpacityMasksSnippet#TiledDrawingasOpacityMask](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/DrawingBrushExample.xaml#tileddrawingasopacitymask)]  
  
## <a name="see-also"></a><span data-ttu-id="5dca4-184">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5dca4-184">See Also</span></span>  
 [<span data-ttu-id="5dca4-185">Malowanie obrazów, rysunki i elementy wizualne</span><span class="sxs-lookup"><span data-stu-id="5dca4-185">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [<span data-ttu-id="5dca4-186">Malowanie pełnych kolorów i gradientów — omówienie</span><span class="sxs-lookup"><span data-stu-id="5dca4-186">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)