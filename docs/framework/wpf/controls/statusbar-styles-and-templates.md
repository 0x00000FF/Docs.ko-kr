---
title: StatusBar 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
ms.openlocfilehash: ee3bd060268d5ab6f713a74f871d7de0dd77782b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660465"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="46c42-102">StatusBar 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="46c42-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="46c42-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.Primitives.StatusBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c42-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="46c42-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46c42-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="46c42-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46c42-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="46c42-106">상태 표시줄 파트</span><span class="sxs-lookup"><span data-stu-id="46c42-106">StatusBar Parts</span></span>  
 <span data-ttu-id="46c42-107"><xref:System.Windows.Controls.Primitives.StatusBar> 컨트롤에 명명된 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46c42-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="46c42-108">상태 표시줄 상태</span><span class="sxs-lookup"><span data-stu-id="46c42-108">StatusBar States</span></span>  
 <span data-ttu-id="46c42-109">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.Primitives.StatusBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c42-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="46c42-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="46c42-110">VisualState Name</span></span>|<span data-ttu-id="46c42-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="46c42-111">VisualStateGroup Name</span></span>|<span data-ttu-id="46c42-112">설명</span><span class="sxs-lookup"><span data-stu-id="46c42-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="46c42-113">유효</span><span class="sxs-lookup"><span data-stu-id="46c42-113">Valid</span></span>|<span data-ttu-id="46c42-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="46c42-114">ValidationStates</span></span>|<span data-ttu-id="46c42-115">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="46c42-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="46c42-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="46c42-116">InvalidFocused</span></span>|<span data-ttu-id="46c42-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="46c42-117">ValidationStates</span></span>|<span data-ttu-id="46c42-118">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46c42-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="46c42-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="46c42-119">InvalidUnfocused</span></span>|<span data-ttu-id="46c42-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="46c42-120">ValidationStates</span></span>|<span data-ttu-id="46c42-121">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c42-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="46c42-122">StatusBarItem 파트</span><span class="sxs-lookup"><span data-stu-id="46c42-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="46c42-123"><xref:System.Windows.Controls.Primitives.StatusBarItem> 컨트롤에 명명된 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46c42-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="46c42-124">상태 표시줄 상태</span><span class="sxs-lookup"><span data-stu-id="46c42-124">StatusBar States</span></span>  
 <span data-ttu-id="46c42-125">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.Primitives.StatusBarItem> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c42-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="46c42-126">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="46c42-126">VisualState Name</span></span>|<span data-ttu-id="46c42-127">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="46c42-127">VisualStateGroup Name</span></span>|<span data-ttu-id="46c42-128">설명</span><span class="sxs-lookup"><span data-stu-id="46c42-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="46c42-129">유효</span><span class="sxs-lookup"><span data-stu-id="46c42-129">Valid</span></span>|<span data-ttu-id="46c42-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="46c42-130">ValidationStates</span></span>|<span data-ttu-id="46c42-131">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="46c42-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="46c42-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="46c42-132">InvalidFocused</span></span>|<span data-ttu-id="46c42-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="46c42-133">ValidationStates</span></span>|<span data-ttu-id="46c42-134">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46c42-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="46c42-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="46c42-135">InvalidUnfocused</span></span>|<span data-ttu-id="46c42-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="46c42-136">ValidationStates</span></span>|<span data-ttu-id="46c42-137">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c42-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="46c42-138">StatusBar ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="46c42-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="46c42-139">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Primitives.StatusBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c42-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="46c42-140"><xref:System.Windows.Controls.ControlTemplate> 다음 리소스 중 하나 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c42-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="46c42-141">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46c42-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c42-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="46c42-142">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="46c42-143">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="46c42-143">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="46c42-144">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="46c42-144">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="46c42-145">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="46c42-145">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="46c42-146">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="46c42-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
