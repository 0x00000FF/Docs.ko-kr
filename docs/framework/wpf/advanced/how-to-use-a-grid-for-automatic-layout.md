---
title: '방법: 자동 레이아웃에 Grid 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 6ea0b64af07924867c2de97baf5a81f8e8da6a56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544624"
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a><span data-ttu-id="65b6e-102">방법: 자동 레이아웃에 Grid 사용</span><span class="sxs-lookup"><span data-stu-id="65b6e-102">How to: Use a Grid for Automatic Layout</span></span>
<span data-ttu-id="65b6e-103">이 예제에서는 지역화할 수 있는 응용 프로그램을 만드는 자동 레이아웃 방법에서 그리드를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="65b6e-103">This example describes how to use a grid in the automatic layout approach to creating a localizable application.</span></span>  
  
 <span data-ttu-id="65b6e-104">지역화 된 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 많은 시간이 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b6e-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="65b6e-105">지역화 담당자는 텍스트를 번역하는 작업 외에도 요소의 크기를 조정하고 위치를 변경해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="65b6e-105">Often localizers need to re-size and reposition elements in addition to translating text.</span></span> <span data-ttu-id="65b6e-106">이전에는 각 언어는는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 가 조정 작업이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b6e-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="65b6e-107">기능으로 이제 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 조정 사용할 필요성이 감소 하는 요소를 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b6e-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="65b6e-108">보다 쉽게 크기가 조정 및 위치를 조정할 수 있는 응용 프로그램을 작성 하는 방법을 라고 `auto layout`합니다.</span><span class="sxs-lookup"><span data-stu-id="65b6e-108">The approach to writing applications that can be more easily re-sized and repositioned is called `auto layout`.</span></span>  
  
 <span data-ttu-id="65b6e-109">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 표를 사용 하 여 일부 단추 및 텍스트 위치에 대 한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="65b6e-109">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="65b6e-110">셀의 너비와 높이가로 설정 된 알림 `Auto`; 따라서 단추 이미지와 함께 포함 된 셀을 이미지에 맞게 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b6e-110">Notice that the height and width of the cells are set to `Auto`; therefore the cell that contains the button with an image adjusts to fit the image.</span></span> <span data-ttu-id="65b6e-111">때문에 <xref:System.Windows.Controls.Grid> 요소 내용에 맞게 지역화할 수 있는 응용 프로그램 디자인에 자동 레이아웃의 접근 하는 경우에 유용할 수 있습니다 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b6e-111">Because the <xref:System.Windows.Controls.Grid> element can adjust to its content it can be useful when taking the automatic layout approach to designing applications that can be localized.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65b6e-112">예제</span><span class="sxs-lookup"><span data-stu-id="65b6e-112">Example</span></span>  
 <span data-ttu-id="65b6e-113">다음 예제에서는 그리드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65b6e-113">The following example shows how to use a grid.</span></span>  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="65b6e-114">다음 그래픽에서는 코드 샘플의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65b6e-114">The following graphic shows the output of the code sample.</span></span>  
  
 <span data-ttu-id="65b6e-115">![표 예제](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="65b6e-115">![Grid example](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="65b6e-116">표</span><span class="sxs-lookup"><span data-stu-id="65b6e-116">Grid</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65b6e-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65b6e-117">See Also</span></span>  
 [<span data-ttu-id="65b6e-118">자동 레이아웃 사용 개요</span><span class="sxs-lookup"><span data-stu-id="65b6e-118">Use Automatic Layout Overview</span></span>](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [<span data-ttu-id="65b6e-119">자동 레이아웃을 사용하여 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="65b6e-119">Use Automatic Layout to Create a Button</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)
