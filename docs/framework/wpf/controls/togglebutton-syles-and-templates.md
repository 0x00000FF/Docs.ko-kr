---
title: "ToggleButton 스타일 및 템플릿"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c143717b691e79771fbaa55724d9d9748259e3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="togglebutton-syles-and-templates"></a><span data-ttu-id="96bcf-102">ToggleButton 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="96bcf-102">ToggleButton Syles and Templates</span></span>
<span data-ttu-id="96bcf-103">이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.Primitives.ToggleButton> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="96bcf-104">기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="96bcf-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96bcf-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="togglebutton-parts"></a><span data-ttu-id="96bcf-106">ToggleButton 부분</span><span class="sxs-lookup"><span data-stu-id="96bcf-106">ToggleButton Parts</span></span>  
 <span data-ttu-id="96bcf-107"><xref:System.Windows.Controls.Primitives.ToggleButton> 컨트롤에는 명명된 된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>  
  
## <a name="togglebutton-states"></a><span data-ttu-id="96bcf-108">토글 단추 상태</span><span class="sxs-lookup"><span data-stu-id="96bcf-108">ToggleButton States</span></span>  
 <span data-ttu-id="96bcf-109">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.Primitives.ToggleButton> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>  
  
|<span data-ttu-id="96bcf-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="96bcf-110">VisualState Name</span></span>|<span data-ttu-id="96bcf-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="96bcf-111">VisualStateGroup Name</span></span>|<span data-ttu-id="96bcf-112">설명</span><span class="sxs-lookup"><span data-stu-id="96bcf-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="96bcf-113">보통</span><span class="sxs-lookup"><span data-stu-id="96bcf-113">Normal</span></span>|<span data-ttu-id="96bcf-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="96bcf-114">CommonStates</span></span>|<span data-ttu-id="96bcf-115">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-115">The default state.</span></span>|  
|<span data-ttu-id="96bcf-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="96bcf-116">MouseOver</span></span>|<span data-ttu-id="96bcf-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="96bcf-117">CommonStates</span></span>|<span data-ttu-id="96bcf-118">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="96bcf-119">누름</span><span class="sxs-lookup"><span data-stu-id="96bcf-119">Pressed</span></span>|<span data-ttu-id="96bcf-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="96bcf-120">CommonStates</span></span>|<span data-ttu-id="96bcf-121">컨트롤을 눌렀습니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-121">The control is pressed.</span></span>|  
|<span data-ttu-id="96bcf-122">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="96bcf-122">Disabled</span></span>|<span data-ttu-id="96bcf-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="96bcf-123">CommonStates</span></span>|<span data-ttu-id="96bcf-124">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-124">The control is disabled.</span></span>|  
|<span data-ttu-id="96bcf-125">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="96bcf-125">Focused</span></span>|<span data-ttu-id="96bcf-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="96bcf-126">FocusStates</span></span>|<span data-ttu-id="96bcf-127">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-127">The control has focus.</span></span>|  
|<span data-ttu-id="96bcf-128">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="96bcf-128">Unfocused</span></span>|<span data-ttu-id="96bcf-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="96bcf-129">FocusStates</span></span>|<span data-ttu-id="96bcf-130">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="96bcf-131">선택한 상태</span><span class="sxs-lookup"><span data-stu-id="96bcf-131">Checked</span></span>|<span data-ttu-id="96bcf-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="96bcf-132">CheckStates</span></span>|<span data-ttu-id="96bcf-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>가 `true`인 경우</span><span class="sxs-lookup"><span data-stu-id="96bcf-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="96bcf-134">선택 취소 되어 있음</span><span class="sxs-lookup"><span data-stu-id="96bcf-134">Unchecked</span></span>|<span data-ttu-id="96bcf-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="96bcf-135">CheckStates</span></span>|<span data-ttu-id="96bcf-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>가 `false`인 경우</span><span class="sxs-lookup"><span data-stu-id="96bcf-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="96bcf-137">비활성화 상태</span><span class="sxs-lookup"><span data-stu-id="96bcf-137">Indeterminate</span></span>|<span data-ttu-id="96bcf-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="96bcf-138">CheckStates</span></span>|<span data-ttu-id="96bcf-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>`true`, 및 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 은 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="96bcf-140">유효</span><span class="sxs-lookup"><span data-stu-id="96bcf-140">Valid</span></span>|<span data-ttu-id="96bcf-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="96bcf-141">ValidationStates</span></span>|<span data-ttu-id="96bcf-142">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="96bcf-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="96bcf-143">InvalidFocused</span></span>|<span data-ttu-id="96bcf-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="96bcf-144">ValidationStates</span></span>|<span data-ttu-id="96bcf-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="96bcf-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="96bcf-146">InvalidUnfocused</span></span>|<span data-ttu-id="96bcf-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="96bcf-147">ValidationStates</span></span>|<span data-ttu-id="96bcf-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="96bcf-149">비활성화 된 시각적 상태 컨트롤 서식 파일에 없는 경우 확인 되지 않은 시각적 상태 시각적 상태를 기본으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>  
  
## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="96bcf-150">토글 단추 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="96bcf-150">ToggleButton ControlTemplate Example</span></span>  
 <span data-ttu-id="96bcf-151">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Primitives.ToggleButton> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToggleButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]  
  
 <span data-ttu-id="96bcf-152">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96bcf-152">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="96bcf-153">전체 샘플을 보려면 [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96bcf-153">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96bcf-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96bcf-154">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="96bcf-155">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="96bcf-155">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="96bcf-156">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="96bcf-156">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="96bcf-157">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="96bcf-157">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="96bcf-158">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="96bcf-158">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
