---
title: "Jak ustawić wyrównanie TileBrush w poziomie i pionie"
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
- TileBrush [WPF], alignment of
- vertical alignment of TileBrushes [WPF]
- aligning [WPF], TileBrushes
- horizontal alignment of Tilebrushes [WPF]
ms.assetid: 65ae89bd-9246-4c9e-bde4-2fb991d4060d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3dcbf4715c80f72178295c0b6abdc1272a055a8a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-horizontal-and-vertical-alignment-of-a-tilebrush"></a>Jak ustawić wyrównanie TileBrush w poziomie i pionie
Ten przykład przedstawia sposób kontrolowania wyrównanie poziome i pionowe zawartości na kafelku. Aby kontrolować wyrównanie poziome i pionowe <xref:System.Windows.Media.TileBrush>, użyj jej <xref:System.Windows.Media.TileBrush.AlignmentX%2A> i <xref:System.Windows.Media.TileBrush.AlignmentY%2A> właściwości.  
  
 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> i <xref:System.Windows.Media.TileBrush.AlignmentY%2A> właściwości <xref:System.Windows.Media.TileBrush> są używane podczas jest spełniony jeden z następujących warunków:  
  
-   <xref:System.Windows.Media.TileBrush.Stretch%2A> Właściwość jest <xref:System.Windows.Media.Stretch.Uniform> lub <xref:System.Windows.Media.Stretch.UniformToFill> i <xref:System.Windows.Media.TileBrush.Viewbox%2A> i <xref:System.Windows.Media.TileBrush.Viewport%2A> mają różnych współczynników proporcji.  
  
-   <xref:System.Windows.Media.TileBrush.Stretch%2A> Właściwość jest <xref:System.Windows.Media.Stretch.None> i <xref:System.Windows.Media.TileBrush.Viewbox%2A> i <xref:System.Windows.Media.TileBrush.Viewport%2A> mają różne rozmiary.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład Wyrównuje zawartość <xref:System.Windows.Media.DrawingBrush>, który jest typem <xref:System.Windows.Media.TileBrush>, do górnego lewego rogu jego kafelka. Aby wyrównać zawartości, ustawia przykład <xref:System.Windows.Media.TileBrush.AlignmentX%2A> właściwość <xref:System.Windows.Media.DrawingBrush> do <xref:System.Windows.Media.AlignmentX.Left> i <xref:System.Windows.Media.TileBrush.AlignmentY%2A> właściwości <xref:System.Windows.Media.AlignmentY.Top>. W tym przykładzie tworzy następujące dane wyjściowe.  
  
 ![Element TileBrush z góry &#45; wyrównanie do lewej](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletopleft.png "graphicsmm_TileBrushAlignmentExampleTopLeft")  
TileBrush z zawartością wyrównany do lewego górnego rogu  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmentinline)]  
  
## <a name="example"></a>Przykład  
 Kolejnym przykładzie Wyrównuje zawartość <xref:System.Windows.Media.DrawingBrush> do prawym dolnym rogu jego kafelka przez ustawienie <xref:System.Windows.Media.TileBrush.AlignmentX%2A> właściwości <xref:System.Windows.Media.AlignmentX.Right> i <xref:System.Windows.Media.TileBrush.AlignmentY%2A> właściwości <xref:System.Windows.Media.AlignmentY.Bottom>. Przykład tworzy następujące dane wyjściowe.  
  
 ![Element TileBrush z dołu &#45; wyrównanie do prawej](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomright.png "graphicsmm_TileBrushAlignmentExampleBottomRight")  
TileBrush z zawartością wyrównywana prawym dolnym rogu  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
## <a name="example"></a>Przykład  
 Kolejnym przykładzie Wyrównuje zawartość <xref:System.Windows.Media.DrawingBrush> do górnego lewego rogu jego kafelka przez ustawienie <xref:System.Windows.Media.TileBrush.AlignmentX%2A> właściwości <xref:System.Windows.Media.AlignmentX.Left> i <xref:System.Windows.Media.TileBrush.AlignmentY%2A> właściwości <xref:System.Windows.Media.AlignmentY.Top>. Ustawia również <xref:System.Windows.Media.TileBrush.Viewport%2A> i <xref:System.Windows.Media.TileBrush.TileMode%2A> z <xref:System.Windows.Media.DrawingBrush> wygenerowało wzorzec kafelka. Przykład tworzy następujące dane wyjściowe.  
  
 ![Element TileBrush sąsiadującym z góry &#45; wyrównanie do lewej](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletoplefttiled.png "graphicsmm_TileBrushAlignmentExampleTopLeftTiled")  
Wzorzec kafelka z zawartością wyrównany do lewej górnej kafelku podstawowej  
  
 Ilustracja prezentuje bazy danyc kafelka, tak aby były widoczne wyrównanie jego zawartości. Zwróć uwagę, że <xref:System.Windows.Media.TileBrush.AlignmentX%2A> ustawienie nie obowiązuje, ponieważ zawartość <xref:System.Windows.Media.DrawingBrush> całkowicie wypełnia podstawowy Kafelek poziomo.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmenttiledinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmenttiledinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmenttiledinline)]  
  
## <a name="example"></a>Przykład  
 Końcowy przykład Wyrównuje zawartość sąsiadującym <xref:System.Windows.Media.DrawingBrush> do prawej dolnej jego podstawowy Kafelek przez ustawienie <xref:System.Windows.Media.TileBrush.AlignmentX%2A> właściwości <xref:System.Windows.Media.AlignmentX.Right> i <xref:System.Windows.Media.TileBrush.AlignmentY%2A> właściwości <xref:System.Windows.Media.AlignmentY.Bottom>. Przykład tworzy następujące dane wyjściowe.  
  
 ![A rozmieszczany TileBrush z dołu &#45; kliknij prawym przyciskiem myszy wyrównanie](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomrighttiled.png "graphicsmm_TileBrushAlignmentExampleBottomRightTiled")  
Wzorzec kafelka z zawartością wyrównany do prawej dolnej kafelku podstawowej  
  
 Ponownie <xref:System.Windows.Media.TileBrush.AlignmentX%2A> ustawienie nie obowiązuje, ponieważ zawartość <xref:System.Windows.Media.DrawingBrush> całkowicie wypełnia podstawowy Kafelek poziomo.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
 W przykładach użyto <xref:System.Windows.Media.DrawingBrush> obiektów, aby zademonstrować sposób <xref:System.Windows.Media.TileBrush.AlignmentX%2A> i <xref:System.Windows.Media.TileBrush.AlignmentY%2A> właściwości są używane. Te właściwości zachowują się tak samo dla wszystkich pędzle kafelka: <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.ImageBrush>, i <xref:System.Windows.Media.VisualBrush>. Aby uzyskać więcej informacji na temat pędzle kafelka, zobacz [malowanie obrazów, rysunki i elementy wizualne](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Media.DrawingBrush>  
 <xref:System.Windows.Media.ImageBrush>  
 <xref:System.Windows.Media.VisualBrush>  
 [Malowanie przy użyciu obrazów, rysowania i wizualizacji](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
