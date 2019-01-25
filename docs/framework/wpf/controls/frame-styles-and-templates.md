---
title: Frame 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
ms.openlocfilehash: fbe49ae98e0fe281500ae37d53a3d47ff1d0b03a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700272"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="3d4bd-102">Frame 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="3d4bd-102">Frame Styles and Templates</span></span>
<span data-ttu-id="3d4bd-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.Frame> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d4bd-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="3d4bd-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d4bd-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3d4bd-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d4bd-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="3d4bd-106">프레임 부분</span><span class="sxs-lookup"><span data-stu-id="3d4bd-106">Frame Parts</span></span>  
 <span data-ttu-id="3d4bd-107">다음 표에서 대 한 명명된 된 파트를 <xref:System.Windows.Controls.Frame> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d4bd-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="3d4bd-108">파트</span><span class="sxs-lookup"><span data-stu-id="3d4bd-108">Part</span></span>|<span data-ttu-id="3d4bd-109">형식</span><span class="sxs-lookup"><span data-stu-id="3d4bd-109">Type</span></span>|<span data-ttu-id="3d4bd-110">설명</span><span class="sxs-lookup"><span data-stu-id="3d4bd-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3d4bd-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="3d4bd-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="3d4bd-112">콘텐츠 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="3d4bd-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="3d4bd-113">프레임 상태</span><span class="sxs-lookup"><span data-stu-id="3d4bd-113">Frame States</span></span>  
 <span data-ttu-id="3d4bd-114">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.Frame> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d4bd-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="3d4bd-115">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="3d4bd-115">VisualState Name</span></span>|<span data-ttu-id="3d4bd-116">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="3d4bd-116">VisualStateGroup Name</span></span>|<span data-ttu-id="3d4bd-117">설명</span><span class="sxs-lookup"><span data-stu-id="3d4bd-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3d4bd-118">유효</span><span class="sxs-lookup"><span data-stu-id="3d4bd-118">Valid</span></span>|<span data-ttu-id="3d4bd-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3d4bd-119">ValidationStates</span></span>|<span data-ttu-id="3d4bd-120">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="3d4bd-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3d4bd-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3d4bd-121">InvalidFocused</span></span>|<span data-ttu-id="3d4bd-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3d4bd-122">ValidationStates</span></span>|<span data-ttu-id="3d4bd-123">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d4bd-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3d4bd-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3d4bd-124">InvalidUnfocused</span></span>|<span data-ttu-id="3d4bd-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3d4bd-125">ValidationStates</span></span>|<span data-ttu-id="3d4bd-126">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d4bd-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="3d4bd-127">프레임 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="3d4bd-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="3d4bd-128">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Frame> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d4bd-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="3d4bd-129">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d4bd-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="3d4bd-130">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d4bd-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d4bd-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="3d4bd-131">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3d4bd-132">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="3d4bd-132">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="3d4bd-133">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3d4bd-133">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="3d4bd-134">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="3d4bd-134">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="3d4bd-135">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3d4bd-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
