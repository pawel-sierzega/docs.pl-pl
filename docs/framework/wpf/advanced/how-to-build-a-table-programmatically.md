---
title: "Jak tworzyć tabele za pomocą programowania"
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
helpviewer_keywords: tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ef961bb219f201cf5fe32a5b2bbdf70ef45e73b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-build-a-table-programmatically"></a><span data-ttu-id="2129a-102">Jak tworzyć tabele za pomocą programowania</span><span class="sxs-lookup"><span data-stu-id="2129a-102">How to: Build a Table Programmatically</span></span>
<span data-ttu-id="2129a-103">W poniższych przykładach pokazano, jak utworzyć programowo <xref:System.Windows.Documents.Table> i wypełnianie jej zawartości.</span><span class="sxs-lookup"><span data-stu-id="2129a-103">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="2129a-104">Zawartość tabeli są rozdzielone do pięciu wierszy (reprezentowane przez <xref:System.Windows.Documents.TableRow> obiektów zawartych w <xref:System.Windows.Documents.Table.RowGroups%2A> obiektu) i sześć kolumn (reprezentowane przez <xref:System.Windows.Documents.TableColumn> obiektów).</span><span class="sxs-lookup"><span data-stu-id="2129a-104">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="2129a-105">Wiersze są używane do przedstawienia różnych celów, w tym tytuł wiersz przeznaczony do title całą tabelę, wiersz nagłówka do opisywania kolumn danych w tabeli i wiersz stopki z podsumowaniem.</span><span class="sxs-lookup"><span data-stu-id="2129a-105">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="2129a-106">Należy pamiętać, że pojęcie "title", "header" i "stopka" wierszy nie są włączone do tabeli; są to po prostu wierszy o różnej charakterystyce.</span><span class="sxs-lookup"><span data-stu-id="2129a-106">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="2129a-107">Komórki tabeli zawierają rzeczywistej zawartości, może składać się z tekstu, obrazów lub niemal każdy inny [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] elementu.</span><span class="sxs-lookup"><span data-stu-id="2129a-107">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2129a-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="2129a-108">Example</span></span>  
 <span data-ttu-id="2129a-109">Najpierw <xref:System.Windows.Documents.FlowDocument> jest tworzony na hoście <xref:System.Windows.Documents.Table>i nowy <xref:System.Windows.Documents.Table> jest tworzony i dodawany do zawartości <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="2129a-109">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a><span data-ttu-id="2129a-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="2129a-110">Example</span></span>  
 <span data-ttu-id="2129a-111">Następnie sześciu <xref:System.Windows.Documents.TableColumn> obiekty są tworzone i dodawane do tabeli <xref:System.Windows.Documents.Table.Columns%2A> kolekcji z niektórych formatowanie zastosowane.</span><span class="sxs-lookup"><span data-stu-id="2129a-111">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2129a-112">Należy pamiętać, że tabeli <xref:System.Windows.Documents.Table.Columns%2A> kolekcja używa standardowych indeksowania liczony od zera.</span><span class="sxs-lookup"><span data-stu-id="2129a-112">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a><span data-ttu-id="2129a-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="2129a-113">Example</span></span>  
 <span data-ttu-id="2129a-114">Następnie wiersz tytuł jest utworzony i dodane do tabeli z niektórych formatowanie zastosowane.</span><span class="sxs-lookup"><span data-stu-id="2129a-114">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="2129a-115">Wiersz tytułu odbywa się zawiera jedną komórkę, które obejmuje wszystkie sześć kolumn w tabeli.</span><span class="sxs-lookup"><span data-stu-id="2129a-115">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a><span data-ttu-id="2129a-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="2129a-116">Example</span></span>  
 <span data-ttu-id="2129a-117">Następnie wiersz nagłówka jest tworzony i dodawany do tabeli i komórek w wierszu nagłówka są tworzone i wypełniane przy użyciu zawartości.</span><span class="sxs-lookup"><span data-stu-id="2129a-117">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a><span data-ttu-id="2129a-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="2129a-118">Example</span></span>  
 <span data-ttu-id="2129a-119">Następnie wiersz danych jest tworzony i dodawany do tabeli i komórek w tym wierszu są tworzone i wypełniane przy użyciu zawartości.</span><span class="sxs-lookup"><span data-stu-id="2129a-119">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="2129a-120">Tworzenie tego wiersza jest podobny do budowania wiersz nagłówka z zastosowanym formatowaniem nieco inne.</span><span class="sxs-lookup"><span data-stu-id="2129a-120">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a><span data-ttu-id="2129a-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="2129a-121">Example</span></span>  
 <span data-ttu-id="2129a-122">Na koniec wiersza stopki jest utworzony, dodane i sformatowany.</span><span class="sxs-lookup"><span data-stu-id="2129a-122">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="2129a-123">Podobnie jak wiersz tytuł stopki zawiera jedną komórkę, które obejmuje wszystkie sześć kolumn w tabeli.</span><span class="sxs-lookup"><span data-stu-id="2129a-123">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="2129a-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2129a-124">See Also</span></span>  
 [<span data-ttu-id="2129a-125">Przegląd tabeli</span><span class="sxs-lookup"><span data-stu-id="2129a-125">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)