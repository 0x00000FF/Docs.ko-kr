---
title: '방법: 사용자 지정 팝업 위치 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: 8714cfa4f7e5bb0ca157ee9d551392571303f60e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551741"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="87b07-102">방법: 사용자 지정 팝업 위치 지정</span><span class="sxs-lookup"><span data-stu-id="87b07-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="87b07-103">에 대 한 사용자 지정 위치를 지정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Primitives.Popup> 제어는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성이로 설정 된 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>합니다.</span><span class="sxs-lookup"><span data-stu-id="87b07-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87b07-104">예제</span><span class="sxs-lookup"><span data-stu-id="87b07-104">Example</span></span>  
 <span data-ttu-id="87b07-105">때는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성이 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, <xref:System.Windows.Controls.Primitives.Popup> 호출의 정의 된 인스턴스는 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 위임 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b07-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="87b07-106">대상 영역의 왼쪽된 위 모퉁이의 왼쪽된 위 모퉁이 기준으로 가능한 지점 집합을 반환 하는이 대리자는 <xref:System.Windows.Controls.Primitives.Popup>합니다.</span><span class="sxs-lookup"><span data-stu-id="87b07-106">This delegate returns a set of possible points that are relative to the top left corner of the target area and the top left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="87b07-107"><xref:System.Windows.Controls.Primitives.Popup> 최상의 가시성을 제공 하는 지점에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b07-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="87b07-108">위치를 정의 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.Primitives.Popup> 설정 하 여는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>합니다.</span><span class="sxs-lookup"><span data-stu-id="87b07-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="87b07-109">만들고 할당 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 배치 하기 위해 대리자는 <xref:System.Windows.Controls.Primitives.Popup>합니다.</span><span class="sxs-lookup"><span data-stu-id="87b07-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="87b07-110">두 콜백 대리자 반환 <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="87b07-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="87b07-111">경우는 <xref:System.Windows.Controls.Primitives.Popup> 화면 가장자리에 첫 번째 위치에 의해 숨겨져는 <xref:System.Windows.Controls.Primitives.Popup> 두 번째 위치에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b07-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="87b07-112">전체 샘플을 참조 하십시오. [팝업 배치 샘플](http://go.microsoft.com/fwlink/?LinkID=160032)합니다.</span><span class="sxs-lookup"><span data-stu-id="87b07-112">For the complete sample, see [Popup Placement Sample](http://go.microsoft.com/fwlink/?LinkID=160032).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b07-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87b07-113">See Also</span></span>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [<span data-ttu-id="87b07-114">팝업 개요</span><span class="sxs-lookup"><span data-stu-id="87b07-114">Popup Overview</span></span>](../../../../docs/framework/wpf/controls/popup-overview.md)  
 [<span data-ttu-id="87b07-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="87b07-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)
