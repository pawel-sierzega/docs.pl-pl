---
title: "Porady: tworzenie siatek właściwości dla ustawień użytkownika w Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Settings object [Visual Basic], creating property grids for user settings
- user settings [Visual Basic], creating property grids
- property grids [Visual Basic], creating for user settings
- property grids
ms.assetid: b0bc737e-50d1-43d1-a6df-268db6e6f91c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 81a79945dfc0b1501134bc1b0197c18093a5dfae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-property-grids-for-user-settings-in-visual-basic"></a><span data-ttu-id="78dbb-102">Porady: tworzenie siatek właściwości dla ustawień użytkownika w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78dbb-102">How to: Create Property Grids for User Settings in Visual Basic</span></span>
<span data-ttu-id="78dbb-103">Siatki właściwości dla ustawień użytkownika można tworzyć przy wprowadzaniu <xref:System.Windows.Forms.PropertyGrid> formantu użytkownika ustawienie właściwości `My.Settings` obiektu.</span><span class="sxs-lookup"><span data-stu-id="78dbb-103">You can create a property grid for user settings by populating a <xref:System.Windows.Forms.PropertyGrid> control with the user setting properties of the `My.Settings` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78dbb-104">W kolejności, w tym przykładzie działała aplikacja musi mieć jego skonfigurowane ustawienia użytkownika.</span><span class="sxs-lookup"><span data-stu-id="78dbb-104">In order for this example to work, your application must have its user settings configured.</span></span> <span data-ttu-id="78dbb-105">Aby uzyskać więcej informacji, zobacz [Zarządzanie ustawieniami aplikacji (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="78dbb-105">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
 <span data-ttu-id="78dbb-106">`My.Settings` Obiekt ujawnia każdego ustawienia jako właściwość.</span><span class="sxs-lookup"><span data-stu-id="78dbb-106">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="78dbb-107">Nazwa właściwości jest taka sama jak nazwa ustawienia i typ właściwości jest taki sam jak typ ustawienia.</span><span class="sxs-lookup"><span data-stu-id="78dbb-107">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="78dbb-108">Ustawienie **zakresu** Określa, czy właściwość jest tylko do odczytu; właściwość **aplikacji**— ustawienie zakresu jest tylko do odczytu, podczas właściwość **użytkownika**-zakresu Ustawienie to odczytu i zapisu.</span><span class="sxs-lookup"><span data-stu-id="78dbb-108">The setting's **Scope** determines if the property is read-only; the property for an **Application**-scope setting is read-only, while the property for a **User**-scope setting is read-write.</span></span> <span data-ttu-id="78dbb-109">Aby uzyskać więcej informacji, zobacz [My.Settings — obiekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="78dbb-109">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78dbb-110">Nie można zmienić ani zapisać wartości ustawień zakresu aplikacji w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="78dbb-110">You cannot change or save the values of application-scope settings at run time.</span></span> <span data-ttu-id="78dbb-111">Ustawienia zakresu aplikacji można zmienić tylko wtedy, gdy tworzenie aplikacji (za pośrednictwem **projektanta projektu**) lub poprzez edycję pliku konfiguracyjnego aplikacji.</span><span class="sxs-lookup"><span data-stu-id="78dbb-111">Application-scope settings can be changed only when creating the application (through the **Project Designer**) or by editing the application's configuration file.</span></span> <span data-ttu-id="78dbb-112">Aby uzyskać więcej informacji, zobacz [Zarządzanie ustawieniami aplikacji (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="78dbb-112">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
 <span data-ttu-id="78dbb-113">W tym przykładzie użyto <xref:System.Windows.Forms.PropertyGrid> formantu, aby uzyskać dostęp do właściwości ustawienia użytkownika `My.Settings` obiektu.</span><span class="sxs-lookup"><span data-stu-id="78dbb-113">This example uses a <xref:System.Windows.Forms.PropertyGrid> control to access the user-setting properties of the `My.Settings` object.</span></span> <span data-ttu-id="78dbb-114">Domyślnie <xref:System.Windows.Forms.PropertyGrid> zawiera wszystkie właściwości `My.Settings` obiektu.</span><span class="sxs-lookup"><span data-stu-id="78dbb-114">By default, the <xref:System.Windows.Forms.PropertyGrid> shows all the properties of the `My.Settings` object.</span></span> <span data-ttu-id="78dbb-115">Jednak ustawienia użytkownika właściwości mają <xref:System.Configuration.UserScopedSettingAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="78dbb-115">However, the user-setting properties have the <xref:System.Configuration.UserScopedSettingAttribute> attribute.</span></span> <span data-ttu-id="78dbb-116">W tym przykładzie <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> właściwość <xref:System.Windows.Forms.PropertyGrid> do <xref:System.Configuration.UserScopedSettingAttribute> do wyświetlenia tylko właściwości ustawień użytkownika.</span><span class="sxs-lookup"><span data-stu-id="78dbb-116">This example sets the <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> property of the <xref:System.Windows.Forms.PropertyGrid> to <xref:System.Configuration.UserScopedSettingAttribute> to display only the user-setting properties.</span></span>  
  
### <a name="to-add-a-user-setting-property-grid"></a><span data-ttu-id="78dbb-117">Aby dodać siatki właściwości ustawienia użytkownika</span><span class="sxs-lookup"><span data-stu-id="78dbb-117">To add a user setting property grid</span></span>  
  
1.  <span data-ttu-id="78dbb-118">Dodaj **PropertyGrid** kontrolować z **przybornika** na powierzchnię projektu dla aplikacji, w tym miejscu zakłada się, że `Form1`.</span><span class="sxs-lookup"><span data-stu-id="78dbb-118">Add the **PropertyGrid** control from the **Toolbox** to the design surface for your application, assumed here to be `Form1`.</span></span>  
  
     <span data-ttu-id="78dbb-119">Domyślna nazwa formantu siatki właściwości to `PropertyGrid1`.</span><span class="sxs-lookup"><span data-stu-id="78dbb-119">The default name of the property-grid control is `PropertyGrid1`.</span></span>  
  
2.  <span data-ttu-id="78dbb-120">Kliknij dwukrotnie powierzchnię projektu dla `Form1` otworzyć kodu dla obsługi zdarzeń ładowania formularza.</span><span class="sxs-lookup"><span data-stu-id="78dbb-120">Double-click the design surface for `Form1` to open the code for the form-load event handler.</span></span>  
  
3.  <span data-ttu-id="78dbb-121">Ustaw `My.Settings` obiektu jako obiektu wybranego w siatce właściwości.</span><span class="sxs-lookup"><span data-stu-id="78dbb-121">Set the `My.Settings` object as the selected object for the property grid.</span></span>  
  
     [!code-vb[VbVbalrMyResources#11](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_1.vb)]  
  
4.  <span data-ttu-id="78dbb-122">Skonfiguruj siatki właściwości, aby wyświetlić tylko ustawienia użytkownika.</span><span class="sxs-lookup"><span data-stu-id="78dbb-122">Configure the property grid to show only the user settings.</span></span>  
  
     [!code-vb[VbVbalrMyResources#12](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_2.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="78dbb-123">Aby wyświetlić tylko ustawienia zakres aplikacji, należy użyć <xref:System.Configuration.ApplicationScopedSettingAttribute> atrybutu zamiast <xref:System.Configuration.UserScopedSettingAttribute>.</span><span class="sxs-lookup"><span data-stu-id="78dbb-123">To show only the application-scope settings, use the <xref:System.Configuration.ApplicationScopedSettingAttribute> attribute instead of  <xref:System.Configuration.UserScopedSettingAttribute>.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="78dbb-124">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="78dbb-124">Robust Programming</span></span>  
 <span data-ttu-id="78dbb-125">Aplikacja zapisuje ustawienia użytkownika podczas zamykania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="78dbb-125">The application saves the user settings when the application shuts down.</span></span> <span data-ttu-id="78dbb-126">Aby zapisać ustawienia natychmiast, należy wywołać `My.Settings.Save` metody.</span><span class="sxs-lookup"><span data-stu-id="78dbb-126">To save the settings immediately, call the `My.Settings.Save` method.</span></span> <span data-ttu-id="78dbb-127">Aby uzyskać więcej informacji, zobacz [porady: utrwalanie ustawień użytkownika w języku Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span><span class="sxs-lookup"><span data-stu-id="78dbb-127">For more information, see [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78dbb-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="78dbb-128">See Also</span></span>  
 [<span data-ttu-id="78dbb-129">My.Settings — obiekt</span><span class="sxs-lookup"><span data-stu-id="78dbb-129">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [<span data-ttu-id="78dbb-130">Porady: odczytywanie ustawień aplikacji w języku Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78dbb-130">How to: Read Application Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [<span data-ttu-id="78dbb-131">Porady: Zmienianie ustawień użytkownika w języku Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78dbb-131">How to: Change User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [<span data-ttu-id="78dbb-132">Porady: utrwalanie ustawień użytkownika w języku Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78dbb-132">How to: Persist User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [<span data-ttu-id="78dbb-133">Zarządzanie ustawieniami aplikacji (.NET)</span><span class="sxs-lookup"><span data-stu-id="78dbb-133">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)