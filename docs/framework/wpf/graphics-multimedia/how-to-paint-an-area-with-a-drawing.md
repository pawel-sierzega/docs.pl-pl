---
title: "Jak malować obszar za pomocą rysowania"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1db788ae0fabdfd27cf215bfcf466c41df19c637
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-paint-an-area-with-a-drawing"></a><span data-ttu-id="8e946-102">Jak malować obszar za pomocą rysowania</span><span class="sxs-lookup"><span data-stu-id="8e946-102">How to: Paint an Area with a Drawing</span></span>
<span data-ttu-id="8e946-103">W tym przykładzie pokazano, jak namalować obszar z rysunku.</span><span class="sxs-lookup"><span data-stu-id="8e946-103">This example shows how to paint an area with a drawing.</span></span> <span data-ttu-id="8e946-104">Malowanie obszaru z rysunkiem, należy użyć <xref:System.Windows.Media.DrawingBrush> i co najmniej jeden <xref:System.Windows.Media.Drawing> obiektów.</span><span class="sxs-lookup"><span data-stu-id="8e946-104">To paint an area with a drawing, you use a <xref:System.Windows.Media.DrawingBrush> and one or more <xref:System.Windows.Media.Drawing> objects.</span></span>   <span data-ttu-id="8e946-105">W poniższym przykładzie użyto <xref:System.Windows.Media.DrawingBrush> obiektu z rysunkiem dwie elipsy.</span><span class="sxs-lookup"><span data-stu-id="8e946-105">The following example uses a <xref:System.Windows.Media.DrawingBrush> to paint an object with a drawing of two ellipses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e946-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="8e946-106">Example</span></span>  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 <span data-ttu-id="8e946-107">Na poniższej ilustracji przedstawiono przykładowe dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="8e946-107">The following illustration shows the example's output.</span></span>  
  
 <span data-ttu-id="8e946-108">![Dane wyjściowe z DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span><span class="sxs-lookup"><span data-stu-id="8e946-108">![Output from a DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span></span>  
  
 <span data-ttu-id="8e946-109">(Centrum kształt jest białe powodów opisanych w [kontrolować wypełnienia kształtu złożonego](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-the-fill-of-a-composite-shape.md).)</span><span class="sxs-lookup"><span data-stu-id="8e946-109">(The center of the shape is white for reasons described in     [Control the Fill of a Composite Shape](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-the-fill-of-a-composite-shape.md).)</span></span>  
  
 <span data-ttu-id="8e946-110">Przez ustawienie <xref:System.Windows.Media.DrawingBrush> obiektu <xref:System.Windows.Media.TileBrush.Viewport%2A> i <xref:System.Windows.Media.TileBrush.TileMode%2A> właściwości, można utworzyć identycznych wzorca.</span><span class="sxs-lookup"><span data-stu-id="8e946-110">By setting a <xref:System.Windows.Media.DrawingBrush> object's <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties, you can create a repeating pattern.</span></span> <span data-ttu-id="8e946-111">Poniższy przykład umożliwia malowanie obiektu z wzorcem utworzone na podstawie Rysowanie elips dwa.</span><span class="sxs-lookup"><span data-stu-id="8e946-111">The following example paints an object with a pattern created from a drawing of two ellipses.</span></span>  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 <span data-ttu-id="8e946-112">Na poniższej ilustracji przedstawiono sąsiadującym <xref:System.Windows.Media.DrawingBrush> danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="8e946-112">The following illustration shows the tiled <xref:System.Windows.Media.DrawingBrush> output.</span></span>  
  
 <span data-ttu-id="8e946-113">![Dane wyjściowe z DrawingBrush rozmieszczany](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span><span class="sxs-lookup"><span data-stu-id="8e946-113">![Tiled output from a DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span></span>  
  
 <span data-ttu-id="8e946-114">Aby uzyskać więcej informacji na temat rysowania pędzle, zobacz [malowanie obrazów, rysunki i elementy wizualne](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="8e946-114">For more information about drawing brushes, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span> <span data-ttu-id="8e946-115">Aby uzyskać więcej informacji na temat <xref:System.Windows.Media.Drawing> obiekty, zobacz [Przegląd obiektów rysunku](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8e946-115">For more information about <xref:System.Windows.Media.Drawing> objects, see the [Drawing Objects Overview](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).</span></span>