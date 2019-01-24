---
title: '방법: DockPanel 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], creating
ms.assetid: 9194f663-e279-4f1a-86d7-125a57d05c6f
ms.openlocfilehash: 1686ce0d9cd6f02fc524789c1e3ad7daedcbbaf2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674351"
---
# <a name="how-to-create-a-dockpanel"></a><span data-ttu-id="5709d-102">방법: DockPanel 만들기</span><span class="sxs-lookup"><span data-stu-id="5709d-102">How to: Create a DockPanel</span></span>
## <a name="example"></a><span data-ttu-id="5709d-103">예제</span><span class="sxs-lookup"><span data-stu-id="5709d-103">Example</span></span>  
 <span data-ttu-id="5709d-104">다음 예제에서는 만들고의 인스턴스를 사용 하 여 <xref:System.Windows.Controls.DockPanel> 코드를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="5709d-104">The following example creates and uses an instance of <xref:System.Windows.Controls.DockPanel> by using code.</span></span> <span data-ttu-id="5709d-105">이 예제에서는 5 개를 만들어 공간을 분할 하는 방법을 보여 줍니다. <xref:System.Windows.Shapes.Rectangle> 요소 및 (고정) 위치를 지정 하는 부모 내에서 <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="5709d-105">The example shows you how to partition space by creating five <xref:System.Windows.Shapes.Rectangle> elements and positioning (docking) them inside a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="5709d-106">기본값을 유지 하는 경우 최종 사각형 모든 나머지 할당 되지 않은 공간을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5709d-106">If you retain the default setting, the final rectangle fills all the remaining unallocated space.</span></span>  
  
 [!code-csharp[DockPanelCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelCode/CSharp/DockPanel_Code.cs#1)]
 [!code-vb[DockPanelCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelCode/VisualBasic/dockpanel_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5709d-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="5709d-107">See also</span></span>
- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.Dock>
- [<span data-ttu-id="5709d-108">패널 개요</span><span class="sxs-lookup"><span data-stu-id="5709d-108">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
