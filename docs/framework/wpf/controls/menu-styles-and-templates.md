---
title: "Menu 스타일 및 템플릿"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e007ae09e57353446feb13b3693e62c985f522d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="menu-styles-and-templates"></a><span data-ttu-id="02030-102">Menu 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="02030-102">Menu Styles and Templates</span></span>
<span data-ttu-id="02030-103">이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.Menu> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Menu> control.</span></span> <span data-ttu-id="02030-104">기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02030-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="02030-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02030-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="menu-parts"></a><span data-ttu-id="02030-106">메뉴 부분</span><span class="sxs-lookup"><span data-stu-id="02030-106">Menu Parts</span></span>  
 <span data-ttu-id="02030-107"><xref:System.Windows.Controls.Menu> 컨트롤에는 명명된 된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02030-107">The <xref:System.Windows.Controls.Menu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="02030-108">만들 때 한 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Menu>, 서식 파일에 포함 될 수 있습니다는 <xref:System.Windows.Controls.ItemsPresenter> 내는 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.Menu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="02030-109">(의 <xref:System.Windows.Controls.ItemsPresenter> 각 항목에 표시 됩니다는 <xref:System.Windows.Controls.Menu>; <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤할 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="02030-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.Menu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="02030-110">경우는 <xref:System.Windows.Controls.ItemsPresenter> 의 직계 자식이 없는 <xref:System.Windows.Controls.ScrollViewer>를 지정 해야 합니다는 <xref:System.Windows.Controls.ItemsPresenter> 이름, `ItemsPresenter`합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menu-states"></a><span data-ttu-id="02030-111">메뉴 상태</span><span class="sxs-lookup"><span data-stu-id="02030-111">Menu States</span></span>  
 <span data-ttu-id="02030-112">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.Menu> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-112">The following table lists the visual states for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="02030-113">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="02030-113">VisualState Name</span></span>|<span data-ttu-id="02030-114">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="02030-114">VisualStateGroup Name</span></span>|<span data-ttu-id="02030-115">설명</span><span class="sxs-lookup"><span data-stu-id="02030-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="02030-116">유효</span><span class="sxs-lookup"><span data-stu-id="02030-116">Valid</span></span>|<span data-ttu-id="02030-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="02030-117">ValidationStates</span></span>|<span data-ttu-id="02030-118">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="02030-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="02030-119">InvalidFocused</span></span>|<span data-ttu-id="02030-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="02030-120">ValidationStates</span></span>|<span data-ttu-id="02030-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02030-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="02030-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="02030-122">InvalidUnfocused</span></span>|<span data-ttu-id="02030-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="02030-123">ValidationStates</span></span>|<span data-ttu-id="02030-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menuitem-parts"></a><span data-ttu-id="02030-125">MenuItem 부분</span><span class="sxs-lookup"><span data-stu-id="02030-125">MenuItem Parts</span></span>  
 <span data-ttu-id="02030-126">다음 표에서 명명된 된 요소를 나열는 <xref:System.Windows.Controls.Menu> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-126">The following table lists the named parts for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="02030-127">파트</span><span class="sxs-lookup"><span data-stu-id="02030-127">Part</span></span>|<span data-ttu-id="02030-128">형식</span><span class="sxs-lookup"><span data-stu-id="02030-128">Type</span></span>|<span data-ttu-id="02030-129">설명</span><span class="sxs-lookup"><span data-stu-id="02030-129">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="02030-130">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="02030-130">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="02030-131">하위 메뉴에 대 한 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="02030-131">The area for the submenu.</span></span>|  
  
 <span data-ttu-id="02030-132">만들 때 한 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.MenuItem>, 서식 파일에 포함 될 수 있습니다는 <xref:System.Windows.Controls.ItemsPresenter> 내는 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-132">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.MenuItem>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="02030-133">(의 <xref:System.Windows.Controls.ItemsPresenter> 각 항목에 표시 됩니다는 <xref:System.Windows.Controls.MenuItem>; <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤할 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="02030-133">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.MenuItem>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="02030-134">경우는 <xref:System.Windows.Controls.ItemsPresenter> 의 직계 자식이 없는 <xref:System.Windows.Controls.ScrollViewer>를 지정 해야 합니다는 <xref:System.Windows.Controls.ItemsPresenter> 이름, `ItemsPresenter`합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-134">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menuitem-states"></a><span data-ttu-id="02030-135">MenuItem 상태</span><span class="sxs-lookup"><span data-stu-id="02030-135">MenuItem States</span></span>  
 <span data-ttu-id="02030-136">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.MenuItem> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-136">The following table lists the visual states for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
|<span data-ttu-id="02030-137">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="02030-137">VisualState Name</span></span>|<span data-ttu-id="02030-138">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="02030-138">VisualStateGroup Name</span></span>|<span data-ttu-id="02030-139">설명</span><span class="sxs-lookup"><span data-stu-id="02030-139">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="02030-140">유효</span><span class="sxs-lookup"><span data-stu-id="02030-140">Valid</span></span>|<span data-ttu-id="02030-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="02030-141">ValidationStates</span></span>|<span data-ttu-id="02030-142">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="02030-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="02030-143">InvalidFocused</span></span>|<span data-ttu-id="02030-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="02030-144">ValidationStates</span></span>|<span data-ttu-id="02030-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02030-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="02030-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="02030-146">InvalidUnfocused</span></span>|<span data-ttu-id="02030-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="02030-147">ValidationStates</span></span>|<span data-ttu-id="02030-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a><span data-ttu-id="02030-149">메뉴 및 메뉴 항목 ControlTemplate 예</span><span class="sxs-lookup"><span data-stu-id="02030-149">Menu and MenuItem ControlTemplate Example</span></span>  
 <span data-ttu-id="02030-150">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Menu> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Menu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 <span data-ttu-id="02030-151">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.MenuItem> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 <span data-ttu-id="02030-152">다음 예제에서는 정의 `MenuScrollViewer`, 이전 예제에서 사용 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-152">The following example defines the `MenuScrollViewer`, which is used in the previous example.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 <span data-ttu-id="02030-153"><xref:System.Windows.Controls.ControlTemplate> 예제는 다음 리소스 중 하나 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="02030-153">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="02030-154">전체 샘플을 보려면 [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02030-154">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02030-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02030-155">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="02030-156">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="02030-156">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="02030-157">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="02030-157">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="02030-158">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="02030-158">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="02030-159">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="02030-159">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
