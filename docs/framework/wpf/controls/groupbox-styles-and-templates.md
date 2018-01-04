---
title: "GroupBox 스타일 및 템플릿"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 99150de10fcbd45d3617621a916793ad5cfe72db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="abd51-102">GroupBox 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="abd51-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="abd51-103">이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="abd51-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="abd51-104">기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abd51-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="abd51-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="abd51-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="abd51-106">그룹 상자 부분</span><span class="sxs-lookup"><span data-stu-id="abd51-106">GroupBox Parts</span></span>  
 <span data-ttu-id="abd51-107"><xref:System.Windows.Controls.GroupBox> 컨트롤에는 명명된 된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abd51-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="abd51-108">GroupBox 상태</span><span class="sxs-lookup"><span data-stu-id="abd51-108">GroupBox States</span></span>  
 <span data-ttu-id="abd51-109">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="abd51-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="abd51-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="abd51-110">VisualState Name</span></span>|<span data-ttu-id="abd51-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="abd51-111">VisualStateGroup Name</span></span>|<span data-ttu-id="abd51-112">설명</span><span class="sxs-lookup"><span data-stu-id="abd51-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="abd51-113">유효</span><span class="sxs-lookup"><span data-stu-id="abd51-113">Valid</span></span>|<span data-ttu-id="abd51-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="abd51-114">ValidationStates</span></span>|<span data-ttu-id="abd51-115">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="abd51-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="abd51-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="abd51-116">InvalidFocused</span></span>|<span data-ttu-id="abd51-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="abd51-117">ValidationStates</span></span>|<span data-ttu-id="abd51-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abd51-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="abd51-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="abd51-119">InvalidUnfocused</span></span>|<span data-ttu-id="abd51-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="abd51-120">ValidationStates</span></span>|<span data-ttu-id="abd51-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="abd51-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="abd51-122">GroupBox ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="abd51-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="abd51-123">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="abd51-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="abd51-124"><xref:System.Windows.Controls.ControlTemplate> 다음 리소스 중 하나 이상 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="abd51-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="abd51-125">전체 샘플을 보려면 [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="abd51-125">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abd51-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abd51-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="abd51-127">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="abd51-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="abd51-128">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="abd51-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="abd51-129">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="abd51-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="abd51-130">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="abd51-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
