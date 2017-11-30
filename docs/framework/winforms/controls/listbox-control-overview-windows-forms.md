---
title: "ListBox — Informacje o formancie [Formularze systemu Windows]"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6e73d76a2d9b31a87bf5a693b5ffa387d7ab5cef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="listbox-control-overview-windows-forms"></a><span data-ttu-id="729fa-102">ListBox — Informacje o formancie [Formularze systemu Windows]</span><span class="sxs-lookup"><span data-stu-id="729fa-102">ListBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="729fa-103">Formularze systemu Windows <xref:System.Windows.Forms.ListBox> kontrolka ma wyświetlać listę, z którego użytkownik może wybrać co najmniej jeden element.</span><span class="sxs-lookup"><span data-stu-id="729fa-103">A Windows Forms <xref:System.Windows.Forms.ListBox> control displays a list from which the user can select one or more items.</span></span> <span data-ttu-id="729fa-104">Jeśli całkowita liczba elementów przekracza liczbę, która może być wyświetlana, pasek przewijania jest automatycznie dodawany do <xref:System.Windows.Forms.ListBox> formantu.</span><span class="sxs-lookup"><span data-stu-id="729fa-104">If the total number of items exceeds the number that can be displayed, a scroll bar is automatically added to the <xref:System.Windows.Forms.ListBox> control.</span></span> <span data-ttu-id="729fa-105">Gdy <xref:System.Windows.Forms.ListBox.MultiColumn%2A> właściwość jest ustawiona na `true`, elementy w polu listy są wyświetlane w wielu kolumnach i zostanie wyświetlony pasek przewijania poziomego.</span><span class="sxs-lookup"><span data-stu-id="729fa-105">When the <xref:System.Windows.Forms.ListBox.MultiColumn%2A> property is set to `true`, the list box displays items in multiple columns and a horizontal scroll bar appears.</span></span> <span data-ttu-id="729fa-106">Gdy <xref:System.Windows.Forms.ListBox.MultiColumn%2A> właściwość jest ustawiona na `false`, elementy w polu listy są wyświetlane w jednej kolumnie i jest wyświetlany pionowy pasek przewijania.</span><span class="sxs-lookup"><span data-stu-id="729fa-106">When the <xref:System.Windows.Forms.ListBox.MultiColumn%2A> property is set to `false`, the list box displays items in a single column and a vertical scroll bar appears.</span></span> <span data-ttu-id="729fa-107">Gdy <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> ma ustawioną wartość `true`, zostanie wyświetlony pasek przewijania, niezależnie od liczby elementów.</span><span class="sxs-lookup"><span data-stu-id="729fa-107">When <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> is set to `true`, the scroll bar appears regardless of the number of items.</span></span> <span data-ttu-id="729fa-108"><xref:System.Windows.Forms.ListBox.SelectionMode%2A> Właściwość określa, ile elementów listy można wybrać w czasie.</span><span class="sxs-lookup"><span data-stu-id="729fa-108">The <xref:System.Windows.Forms.ListBox.SelectionMode%2A> property determines how many list items can be selected at a time.</span></span>  
  
## <a name="ways-to-change-the-listbox-control"></a><span data-ttu-id="729fa-109">Sposoby zmiany ListBox — formant</span><span class="sxs-lookup"><span data-stu-id="729fa-109">Ways to Change the ListBox Control</span></span>  
 <span data-ttu-id="729fa-110"><xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Właściwość zwraca wartość całkowitą, która odpowiada do pierwszego elementu zaznaczonego w polu listy.</span><span class="sxs-lookup"><span data-stu-id="729fa-110">The <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> property returns an integer value that corresponds to the first selected item in the list box.</span></span> <span data-ttu-id="729fa-111">Wybrany element można programowo zmienić, zmieniając <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> wartości w kodzie; odpowiadający mu element na liście będą wyświetlane wyróżnione na formularzu systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="729fa-111">You can programmatically change the selected item by changing the <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> value in code; the corresponding item in the list will appear highlighted on the Windows Form.</span></span> <span data-ttu-id="729fa-112">Jeśli nie wybrano elementów, <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> wartość wynosi -1.</span><span class="sxs-lookup"><span data-stu-id="729fa-112">If no item is selected, the <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> value is -1.</span></span> <span data-ttu-id="729fa-113">Jeśli wybrano pierwszy element na liście, <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> wartość jest równa 0.</span><span class="sxs-lookup"><span data-stu-id="729fa-113">If the first item in the list is selected, the <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> value is 0.</span></span> <span data-ttu-id="729fa-114">Po wybraniu wielu elementów <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> wartość odzwierciedla wybranego elementu, który znajduje się na liście.</span><span class="sxs-lookup"><span data-stu-id="729fa-114">When multiple items are selected, the <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> value reflects the selected item that appears first in the list.</span></span> <span data-ttu-id="729fa-115"><xref:System.Windows.Forms.ListBox.SelectedItem%2A> Jest podobna do właściwości <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, ale zwraca sam element zwykle wartość ciągu.</span><span class="sxs-lookup"><span data-stu-id="729fa-115">The <xref:System.Windows.Forms.ListBox.SelectedItem%2A> property is similar to <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, but returns the item itself, usually a string value.</span></span> <span data-ttu-id="729fa-116"><xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> Właściwość odzwierciedla liczbę elementów na liście, a wartość <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> właściwości jest zawsze jeden więcej niż największa możliwa <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> wartości, ponieważ <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> jest liczony od zera.</span><span class="sxs-lookup"><span data-stu-id="729fa-116">The <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> property reflects the number of items in the list, and the value of the <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> property is always one more than the largest possible <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> value because <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> is zero-based.</span></span>  
  
 <span data-ttu-id="729fa-117">Aby dodać lub usunąć elementy <xref:System.Windows.Forms.ListBox> kontrolować, użyj <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> lub <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="729fa-117">To add or delete items in a <xref:System.Windows.Forms.ListBox> control, use the <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> or <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A> method.</span></span> <span data-ttu-id="729fa-118">Można również dodać elementy do listy przy użyciu <xref:System.Windows.Forms.ListBox.Items%2A> właściwości w czasie projektowania.</span><span class="sxs-lookup"><span data-stu-id="729fa-118">Alternatively, you can add items to the list by using the <xref:System.Windows.Forms.ListBox.Items%2A> property at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="729fa-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="729fa-119">See Also</span></span>  
 <xref:System.Windows.Forms.ListBox>  
 [<span data-ttu-id="729fa-120">Porady: Dodawanie i usuwanie elementów z systemu Windows formularzy ComboBox, ListBox lub CheckedListBox — formant</span><span class="sxs-lookup"><span data-stu-id="729fa-120">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [<span data-ttu-id="729fa-121">Porady: sortowanie zawartości systemu Windows ComboBox, ListBox lub CheckedListBox formularzy</span><span class="sxs-lookup"><span data-stu-id="729fa-121">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [<span data-ttu-id="729fa-122">Porady: powiązanie formantu ComboBox formularzy systemu Windows lub kontrolki ListBox z danymi</span><span class="sxs-lookup"><span data-stu-id="729fa-122">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 [<span data-ttu-id="729fa-123">Informacje o formancie ComboBox</span><span class="sxs-lookup"><span data-stu-id="729fa-123">ComboBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 [<span data-ttu-id="729fa-124">CheckedListBox — informacje o formancie</span><span class="sxs-lookup"><span data-stu-id="729fa-124">CheckedListBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="729fa-125">Formanty używane do obsługi opcji List formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="729fa-125">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)  
 [<span data-ttu-id="729fa-126">Porady: Tworzenie tabeli wyszukiwania dla formantu ComboBox, ListBox lub CheckedListBox formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="729fa-126">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)