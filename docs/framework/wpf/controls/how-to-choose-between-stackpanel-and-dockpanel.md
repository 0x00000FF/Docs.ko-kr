---
title: '방법: StackPanel과 DockPanel 중 선택'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], StackPanel control compared to
- StackPanel control [WPF], DockPanel control compared to
- controls [WPF], StackPanel
ms.assetid: f9239086-451f-42e6-81f7-ef89ef349742
ms.openlocfilehash: c9bfb8d29051a9cfa61d3fcb93b8bb9a68d14e00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551936"
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a><span data-ttu-id="0bd8e-102">방법: StackPanel과 DockPanel 중 선택</span><span class="sxs-lookup"><span data-stu-id="0bd8e-102">How to: Choose Between StackPanel and DockPanel</span></span>
<span data-ttu-id="0bd8e-103">사용 하 여 중에서 선택 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.StackPanel> 또는 <xref:System.Windows.Controls.DockPanel> 의 콘텐츠를 스택 하는 <xref:System.Windows.Controls.Panel>합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd8e-103">This example shows how to choose between using a <xref:System.Windows.Controls.StackPanel> or a <xref:System.Windows.Controls.DockPanel> when you stack content in a <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bd8e-104">예제</span><span class="sxs-lookup"><span data-stu-id="0bd8e-104">Example</span></span>  
 <span data-ttu-id="0bd8e-105">하나를 사용할 수 있지만 <xref:System.Windows.Controls.DockPanel> 또는 <xref:System.Windows.Controls.StackPanel> 자식 요소를 스택 하는 두 컨트롤을 생성 하지 않을 동일한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd8e-105">Although you can use either <xref:System.Windows.Controls.DockPanel> or <xref:System.Windows.Controls.StackPanel> to stack child elements, the two controls do not always produce the same results.</span></span> <span data-ttu-id="0bd8e-106">자식 요소를 배치 하는 순서에 있는 자식 요소의 크기 영향을 줄 수는 예를 들어 한 <xref:System.Windows.Controls.DockPanel> 아니라는 <xref:System.Windows.Controls.StackPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd8e-106">For example, the order that you place child elements can affect the size of child elements in a <xref:System.Windows.Controls.DockPanel> but not in a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="0bd8e-107">이 다른 동작이 발생 하기 때문에 <xref:System.Windows.Controls.StackPanel> 에서 쌓는 방향으로 측정 <xref:System.Double>.<xref:System.Double.PositiveInfinity>소비량이 적어지지만 <xref:System.Windows.Controls.DockPanel> 만 사용할 수 있는 크기를 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd8e-107">This different behavior occurs because <xref:System.Windows.Controls.StackPanel> measures in the direction of stacking at <xref:System.Double>.<xref:System.Double.PositiveInfinity>; however, <xref:System.Windows.Controls.DockPanel> measures only the available size.</span></span>  
  
 <span data-ttu-id="0bd8e-108">다음 예제에서는 이러한 주요 차이 <xref:System.Windows.Controls.DockPanel> 및 <xref:System.Windows.Controls.StackPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd8e-108">The following example demonstrates this key difference between <xref:System.Windows.Controls.DockPanel> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0bd8e-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bd8e-109">See Also</span></span>  
 <xref:System.Windows.Controls.StackPanel>  
 <xref:System.Windows.Controls.DockPanel>  
 [<span data-ttu-id="0bd8e-110">패널 개요</span><span class="sxs-lookup"><span data-stu-id="0bd8e-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
