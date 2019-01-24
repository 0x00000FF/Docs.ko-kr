---
title: 자동 레이아웃 사용 개요
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: 4cb351b0db83bd83c17aa4aca004b310dc957437
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609605"
---
# <a name="use-automatic-layout-overview"></a><span data-ttu-id="92fde-102">자동 레이아웃 사용 개요</span><span class="sxs-lookup"><span data-stu-id="92fde-102">Use Automatic Layout Overview</span></span>
<span data-ttu-id="92fde-103">이 항목에서는 개발자가 작성 하는 방법에 대 한 지침을 소개 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램을 지역화할 수 있는 [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-103">This topic introduces guidelines for developers on how to write [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications with localizable [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)].</span></span> <span data-ttu-id="92fde-104">과거에는 UI의 지역화는 시간이 오래 걸리는 프로세스 였습니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-104">In the past, localization of a UI was a time consuming process.</span></span> <span data-ttu-id="92fde-105">에 대 한 UI를 조정 하는 각 언어는 픽셀 단위 조정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-105">Each language that the UI was adapted for required a pixel by pixel adjustment.</span></span> <span data-ttu-id="92fde-106">적합 한 설계 및 코딩 표준을 사용 하 여 오늘 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 는 작은 크기 조정 및 위치 조정 작업을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-106">Today with the right design and right coding standards, [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] can be constructed so that localizers have less resizing and repositioning to do.</span></span> <span data-ttu-id="92fde-107">보다 쉽게 크기 및 위치가 변경 될 수 있는 응용 프로그램을 작성 하는 방법을 자동 레이아웃 이라고 하며 사용 하 여 구현할 수 있습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 디자인.</span><span class="sxs-lookup"><span data-stu-id="92fde-107">The approach to writing applications that can be more easily resized and repositioned is called automatic layout, and can be achieved by using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application design.</span></span>  

<a name="advantages_of_autolayout"></a>   
## <a name="advantages-of-using-automatic-layout"></a><span data-ttu-id="92fde-108">자동 레이아웃 사용의 이점</span><span class="sxs-lookup"><span data-stu-id="92fde-108">Advantages of Using Automatic Layout</span></span>  
 <span data-ttu-id="92fde-109">때문에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프레젠테이션 시스템은 강력 하 고 유연한, 다른 언어의 요구 사항에 맞게 조정할 수 있는 응용 프로그램에서 레이아웃 요소 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-109">Because the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presentation system is powerful and flexible, it provides the ability to layout elements in an application that can be adjusted to fit the requirements of different languages.</span></span> <span data-ttu-id="92fde-110">다음 목록에서는 자동 레이아웃의 몇 가지 이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-110">The following list points out some of the advantages of automatic layout.</span></span>  

-   <span data-ttu-id="92fde-111">UI는 모든 언어에서 잘 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-111">UI displays well  in any language.</span></span>  

-   <span data-ttu-id="92fde-112">텍스트가 변환된 후 컨트롤의 위치 및 크기를 다시 조정할 필요가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-112">Reduces the need to readjust position and size of controls after text is translated.</span></span>  
  
-   <span data-ttu-id="92fde-113">창 크기를 다시 조정할 필요가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-113">Reduces the need to readjust window size.</span></span>  

-   <span data-ttu-id="92fde-114">UI 레이아웃이 모든 언어에서 제대로 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-114">UI layout renders properly in any language.</span></span>  

-   <span data-ttu-id="92fde-115">지역화를 문자열 변환 정도의 수준으로 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-115">Localization can be reduced to the point that it is little more than string translation.</span></span>  
  
<a name="autolayout_controls"></a>   
## <a name="automatic-layout-and-controls"></a><span data-ttu-id="92fde-116">자동 레이아웃 및 컨트롤</span><span class="sxs-lookup"><span data-stu-id="92fde-116">Automatic Layout and Controls</span></span>  
 <span data-ttu-id="92fde-117">자동 레이아웃을 사용하면 애플리케이션에서 컨트롤의 크기를 자동으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-117">Automatic layout enables an application to adjust the size of a control automatically.</span></span> <span data-ttu-id="92fde-118">예를 들어 컨트롤이 문자열의 길이 맞게 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-118">For example, a control can change to accommodate the length of a string.</span></span> <span data-ttu-id="92fde-119">이 기능을 통해 로컬라이저는 문자열을 변환할 수 있으며, 더 이상 변환된 텍스트에 맞게 컨트롤의 크기를 조정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-119">This capability enables  localizers to translate the string; they no longer need to resize the control to fit the translated text.</span></span> <span data-ttu-id="92fde-120">다음 예제에서는 영어 콘텐츠가 있는 단추를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-120">The following example creates a button with English content.</span></span>  
  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="92fde-121">이 예제에서 스페인어 단추를 만들려면 텍스트만 변경하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-121">In the example, all you have to do to make a Spanish button is change the text.</span></span> <span data-ttu-id="92fde-122">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-122">For example,</span></span>  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="92fde-123">다음 그림에서는 코드 샘플의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-123">The following graphic shows the output of the code samples.</span></span>  
  
 <span data-ttu-id="92fde-124">![서로 다른 언어로 텍스트는 동일한 단추](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span><span class="sxs-lookup"><span data-stu-id="92fde-124">![The same button with text in different languages](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span></span>  
<span data-ttu-id="92fde-125">자동 크기 조정 단추</span><span class="sxs-lookup"><span data-stu-id="92fde-125">Auto Resizable Button</span></span>  
  
<a name="autolayout_coding"></a>   
## <a name="automatic-layout-and-coding-standards"></a><span data-ttu-id="92fde-126">자동 레이아웃 및 코딩 표준</span><span class="sxs-lookup"><span data-stu-id="92fde-126">Automatic Layout and Coding Standards</span></span>  
 <span data-ttu-id="92fde-127">자동 레이아웃 방식을 사용 하 여 코딩 및 디자인 표준 및 완전히 지역화할 수 있는 UI를 생성 하는 규칙 집합이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-127">Using the automatic layout approach requires a set of coding and design standards and rules to produce a fully localizable UI.</span></span> <span data-ttu-id="92fde-128">다음은 자동 레이아웃 코딩에 도움이 되는 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-128">The following guidelines will aid your automatic layout coding.</span></span>  

<span data-ttu-id="92fde-129">**절대 위치를 사용 하지 마세요**</span><span class="sxs-lookup"><span data-stu-id="92fde-129">**Do not use absolute positions**</span></span>

- <span data-ttu-id="92fde-130">사용 하지 않는 <xref:System.Windows.Controls.Canvas> 요소를 절대 위치에 배치 하기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-130">Do not use <xref:System.Windows.Controls.Canvas> because it positions elements absolutely.</span></span>

- <span data-ttu-id="92fde-131">사용 하 여 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, 및 <xref:System.Windows.Controls.Grid> 컨트롤의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-131">Use <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, and <xref:System.Windows.Controls.Grid> to position controls.</span></span>

<span data-ttu-id="92fde-132">다양 한 패널 유형에 대 한 자세한 내용은 참조 하세요. [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-132">For a discussion about various types of panels, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span>

<span data-ttu-id="92fde-133">**창에 대 한 고정된 크기를 설정 하지**</span><span class="sxs-lookup"><span data-stu-id="92fde-133">**Do not set a fixed size for a window**</span></span>

- <span data-ttu-id="92fde-134"><xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="92fde-134">Use <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="92fde-135">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="92fde-135">For example:</span></span>

   [!code-xaml[LocalizationGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

<span data-ttu-id="92fde-136">**추가 <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span><span class="sxs-lookup"><span data-stu-id="92fde-136">**Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span></span>

- <span data-ttu-id="92fde-137">추가 된 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 응용 프로그램의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-137">Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A> to the root element of your application.</span></span>

   <span data-ttu-id="92fde-138">WPF는 편리 하 게 지원 가로, 양방향 및 세로 레이아웃을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-138">WPF provides a convenient way to support horizontal, bidirectional, and vertical layouts.</span></span> <span data-ttu-id="92fde-139">프레젠테이션 프레임 워크에서는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 레이아웃을 정의 하려면 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-139">In presentation framework, the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property can be used to define layout.</span></span> <span data-ttu-id="92fde-140">흐름 방향 패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-140">The flow-direction patterns are:</span></span>
   
     - <span data-ttu-id="92fde-141"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) — 라틴어, 동아시아, 등을 위한 가로 레이아웃.</span><span class="sxs-lookup"><span data-stu-id="92fde-141"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) — horizontal layout for Latin, East Asian, and so forth.</span></span>
     
     - <span data-ttu-id="92fde-142"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb) — 아랍어, 히브리어 등을 위한 양방향.</span><span class="sxs-lookup"><span data-stu-id="92fde-142"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb) — bidirectional for Arabic, Hebrew, and so forth.</span></span>

<span data-ttu-id="92fde-143">**실제 글꼴 대신 합성 글꼴을 사용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="92fde-143">**Use composite fonts instead of physical fonts**</span></span>

- <span data-ttu-id="92fde-144">합성 글꼴을 사용 합니다 <xref:System.Windows.Controls.Control.FontFamily%2A> 속성 지역화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-144">With composite fonts, the <xref:System.Windows.Controls.Control.FontFamily%2A> property does not need to be localized.</span></span>

- <span data-ttu-id="92fde-145">개발자는 다음 글꼴 중 하나를 사용하거나 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-145">Developers can use one of the following fonts or create their own.</span></span>

   - <span data-ttu-id="92fde-146">전역 사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92fde-146">Global User Interface</span></span>
   - <span data-ttu-id="92fde-147">전역 San Serif</span><span class="sxs-lookup"><span data-stu-id="92fde-147">Global San Serif</span></span>
   - <span data-ttu-id="92fde-148">전역 Serif</span><span class="sxs-lookup"><span data-stu-id="92fde-148">Global Serif</span></span>

<span data-ttu-id="92fde-149">**Xml: lang를 추가 합니다.**</span><span class="sxs-lookup"><span data-stu-id="92fde-149">**Add xml:lang**</span></span>

- <span data-ttu-id="92fde-150">추가 된 `xml:lang` 하면 UI의 루트 요소와 같은 특성 `xml:lang="en-US"` 영어 응용 프로그램에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-150">Add the `xml:lang` attribute in the root element of your UI, such as `xml:lang="en-US"` for an English application.</span></span>

- <span data-ttu-id="92fde-151">합성 글꼴을 사용 하므로 `xml:lang` 글꼴을 사용 하 여 결정할 다국어 시나리오를 지원 하도록이 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-151">Because composite fonts use `xml:lang` to determine what font to use, set this property to support multilingual scenarios.</span></span>

<a name="autolay_grids"></a>   
## <a name="automatic-layout-and-grids"></a><span data-ttu-id="92fde-152">자동 레이아웃 및 그리드</span><span class="sxs-lookup"><span data-stu-id="92fde-152">Automatic Layout and Grids</span></span>  
 <span data-ttu-id="92fde-153"><xref:System.Windows.Controls.Grid> 요소는 요소의 위치를 개발자 수 있기 때문에 자동 레이아웃에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-153">The <xref:System.Windows.Controls.Grid> element, is useful for automatic layout because it enables a developer to position elements.</span></span> <span data-ttu-id="92fde-154"><xref:System.Windows.Controls.Grid> 컨트롤은 열 및 행 정렬을 사용 하 여 해당 자식 요소 간에 사용 가능한 공간을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-154">A <xref:System.Windows.Controls.Grid> control is capable of distributing the available space among its child elements, using a column and row arrangement.</span></span> <span data-ttu-id="92fde-155">UI 요소에는 여러 셀에 걸쳐 있을 수 있으며 그리드 내에 그리드를 가질 수 것.</span><span class="sxs-lookup"><span data-stu-id="92fde-155">The UI elements can span multiple cells, and it is possible to have grids within grids.</span></span> <span data-ttu-id="92fde-156">표를 만들고 복잡 한 UI를 배치할 수 있도록 하므로 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-156">Grids are useful because they enable you to create and position complex UI.</span></span> <span data-ttu-id="92fde-157">다음 예제에서는 그리드를 사용하여 몇 가지 단추 및 텍스트 위치를 지정하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-157">The following example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="92fde-158">셀의 너비와 높이가 설정 된 알림 <xref:System.Windows.GridUnitType.Auto>따라서 이미지가 있는 단추가 포함 된 셀이 이미지에 맞게 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-158">Notice that the height and width of the cells are set to <xref:System.Windows.GridUnitType.Auto>; therefore, the cell that contains the button with an image adjusts to fit the image.</span></span>  

 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="92fde-159">다음 그래픽에서는 이전 코드로 생성된 그리드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-159">The following graphic shows the grid produced by the previous code.</span></span>  
  
 <span data-ttu-id="92fde-160">![그리드 예제](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="92fde-160">![Grid example](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="92fde-161">표</span><span class="sxs-lookup"><span data-stu-id="92fde-161">Grid</span></span>  
  
<a name="autolay_grids_issharedsizescope"></a>   
## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a><span data-ttu-id="92fde-162">IsSharedSizeScope 속성을 사용하는 자동 레이아웃 및 그리드</span><span class="sxs-lookup"><span data-stu-id="92fde-162">Automatic Layout and Grids Using the IsSharedSizeScope Property</span></span>  
 <span data-ttu-id="92fde-163"><xref:System.Windows.Controls.Grid> 요소 내용에 맞게 조정 되는 컨트롤을 만들려면 지역화 가능 응용 프로그램에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-163">A <xref:System.Windows.Controls.Grid> element is useful in localizable applications to create controls that adjust to fit content.</span></span> <span data-ttu-id="92fde-164">그러나 경우에 따라 콘텐츠에 관계없이 컨트롤을 특정 크기로 유지하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-164">However, at times you want controls to maintain a particular size regardless of content.</span></span> <span data-ttu-id="92fde-165">예를 들어 "확인", "취소" 및 "찾아보기" 단추가 있는 경우 콘텐츠에 맞게 단추 크기를 조정하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-165">For example, if you have "OK", "Cancel" and "Browse" buttons you probably do not want the buttons sized to fit the content.</span></span> <span data-ttu-id="92fde-166">이 경우에 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> 연결 된 속성은 여러 그리드 요소 간에 동일한 크기 조정을 공유 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-166">In this case the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> attached property is useful for sharing the same sizing among multiple grid elements.</span></span> <span data-ttu-id="92fde-167">다음 예제에서는 열 및 행 크기 조정 여러 간에 데이터를 공유 하는 방법에 설명 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="92fde-167">The following example demonstrates how to share column and row sizing data between multiple <xref:System.Windows.Controls.Grid> elements.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="92fde-168">**참고** 전체 코드 샘플을 보려면 [그리드 간 공유 크기 조정 속성](../../../../docs/framework/wpf/controls/how-to-share-sizing-properties-between-grids.md)</span><span class="sxs-lookup"><span data-stu-id="92fde-168">**Note** For the complete code sample, see [Share Sizing Properties Between Grids](../../../../docs/framework/wpf/controls/how-to-share-sizing-properties-between-grids.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92fde-169">참고자료</span><span class="sxs-lookup"><span data-stu-id="92fde-169">See also</span></span>
- [<span data-ttu-id="92fde-170">WPF의 전역화</span><span class="sxs-lookup"><span data-stu-id="92fde-170">Globalization for WPF</span></span>](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)
- [<span data-ttu-id="92fde-171">자동 레이아웃을 사용하여 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="92fde-171">Use Automatic Layout to Create a Button</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)
- [<span data-ttu-id="92fde-172">자동 레이아웃에 그리드 사용</span><span class="sxs-lookup"><span data-stu-id="92fde-172">Use a Grid for Automatic Layout</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
