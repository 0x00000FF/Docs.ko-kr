---
title: DocumentViewer 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], DocumentViewer
- DocumentViewer [WPF], styles and templates
- states [WPF], DocumentViewer
- ControlTemplate [WPF], DocumentViewer
- parts [WPF], DocumentViewer
- styles [WPF], DocumentViewer
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
ms.openlocfilehash: 217fa0ff7b8c34de817a269effbf64311bbea7f2
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457240"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="ea8c7-102">DocumentViewer 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="ea8c7-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="ea8c7-103">이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.DocumentViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8c7-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="ea8c7-104">기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea8c7-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ea8c7-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea8c7-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="ea8c7-106">DocumentViewer 부분</span><span class="sxs-lookup"><span data-stu-id="ea8c7-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="ea8c7-107">다음 표에서 명명된 된 요소를 나열는 <xref:System.Windows.Controls.DocumentViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8c7-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="ea8c7-108">파트</span><span class="sxs-lookup"><span data-stu-id="ea8c7-108">Part</span></span>|<span data-ttu-id="ea8c7-109">형식</span><span class="sxs-lookup"><span data-stu-id="ea8c7-109">Type</span></span>|<span data-ttu-id="ea8c7-110">설명</span><span class="sxs-lookup"><span data-stu-id="ea8c7-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ea8c7-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="ea8c7-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="ea8c7-112">콘텐츠 및 스크롤 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8c7-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="ea8c7-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="ea8c7-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="ea8c7-114">기본적으로 아래쪽에 있는 검색 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8c7-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="ea8c7-115">DocumentViewer 상태</span><span class="sxs-lookup"><span data-stu-id="ea8c7-115">DocumentViewer States</span></span>  
 <span data-ttu-id="ea8c7-116">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.DocumentViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8c7-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="ea8c7-117">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="ea8c7-117">VisualState Name</span></span>|<span data-ttu-id="ea8c7-118">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="ea8c7-118">VisualStateGroup Name</span></span>|<span data-ttu-id="ea8c7-119">설명</span><span class="sxs-lookup"><span data-stu-id="ea8c7-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ea8c7-120">유효</span><span class="sxs-lookup"><span data-stu-id="ea8c7-120">Valid</span></span>|<span data-ttu-id="ea8c7-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ea8c7-121">ValidationStates</span></span>|<span data-ttu-id="ea8c7-122">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8c7-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ea8c7-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ea8c7-123">InvalidFocused</span></span>|<span data-ttu-id="ea8c7-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ea8c7-124">ValidationStates</span></span>|<span data-ttu-id="ea8c7-125"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea8c7-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ea8c7-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ea8c7-126">InvalidUnfocused</span></span>|<span data-ttu-id="ea8c7-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ea8c7-127">ValidationStates</span></span>|<span data-ttu-id="ea8c7-128"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8c7-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="ea8c7-129">DocumentViewer ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="ea8c7-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="ea8c7-130">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.DocumentViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8c7-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="ea8c7-131">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8c7-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ea8c7-132">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea8c7-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8c7-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea8c7-133">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="ea8c7-134">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="ea8c7-134">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="ea8c7-135">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ea8c7-135">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="ea8c7-136">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="ea8c7-136">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="ea8c7-137">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ea8c7-137">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
