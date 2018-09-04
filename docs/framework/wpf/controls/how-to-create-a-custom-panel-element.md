---
title: '방법: 사용자 지정 패널 요소 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: bca8900ccb3c31a78066a43709a5e9334bc09eab
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43531786"
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="8054e-102">방법: 사용자 지정 패널 요소 만들기</span><span class="sxs-lookup"><span data-stu-id="8054e-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="8054e-103">예제</span><span class="sxs-lookup"><span data-stu-id="8054e-103">Example</span></span>  
 <span data-ttu-id="8054e-104">기본 레이아웃 동작을 재정의 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Panel> 요소에서 파생 되는 사용자 지정 레이아웃 요소를 만들고 <xref:System.Windows.Controls.Panel>합니다.</span><span class="sxs-lookup"><span data-stu-id="8054e-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="8054e-105">이 예제에서는 간단한 사용자 지정 정의 <xref:System.Windows.Controls.Panel> 라는 요소가 `PlotPanel`, 자식 요소에 따라 두 하드 코드 된 x 및 y 좌표를 배치 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="8054e-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="8054e-106">이 예에서 `x` 및 `y` 로 설정 됩니다 `50`하므로 x 및 y에 해당 위치에 배치 됩니다 모든 자식 요소 축.</span><span class="sxs-lookup"><span data-stu-id="8054e-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="8054e-107">사용자 지정 구현 <xref:System.Windows.Controls.Panel> 동작을 사용 하 여 합니다 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 및 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="8054e-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="8054e-108">각 메서드는 반환 된 <xref:System.Windows.Size> 배치 하 고 자식 요소를 렌더링 하는 데 필요한 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="8054e-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8054e-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8054e-109">See Also</span></span>  
 <xref:System.Windows.Controls.Panel>  
 [<span data-ttu-id="8054e-110">패널 개요</span><span class="sxs-lookup"><span data-stu-id="8054e-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="8054e-111">사용자 지정 콘텐츠 줄 바꿈 패널 샘플 만들기</span><span class="sxs-lookup"><span data-stu-id="8054e-111">Create a Custom Content-Wrapping Panel Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159979)
