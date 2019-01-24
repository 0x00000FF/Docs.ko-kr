---
title: '방법: Popup에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: 47555e5468c731d274707f0367122beb26e80c30
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590037"
---
# <a name="how-to-animate-a-popup"></a><span data-ttu-id="fa14c-102">방법: Popup에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="fa14c-102">How to: Animate a Popup</span></span>
<span data-ttu-id="fa14c-103">두 가지 방법으로 애니메이션 효과를 보여 주는이 예제는 <xref:System.Windows.Controls.Primitives.Popup> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa14c-103">This example shows two ways to animate a <xref:System.Windows.Controls.Primitives.Popup> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa14c-104">예제</span><span class="sxs-lookup"><span data-stu-id="fa14c-104">Example</span></span>  
 <span data-ttu-id="fa14c-105">다음 예제에서는 합니다 <xref:System.Windows.Controls.Primitives.PopupAnimation> 속성의 값을 <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, 있어는 <xref:System.Windows.Controls.Primitives.Popup> "슬라이드-in"으로 표시 되는 경우.</span><span class="sxs-lookup"><span data-stu-id="fa14c-105">The following example sets the <xref:System.Windows.Controls.Primitives.PopupAnimation> property to a value of <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, which causes the <xref:System.Windows.Controls.Primitives.Popup> to "slide-in" when it appears.</span></span>  
  
 <span data-ttu-id="fa14c-106">순환 하려면를 <xref:System.Windows.Controls.Primitives.Popup>, 지정 하는이 예제는 <xref:System.Windows.Media.RotateTransform> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 속성을는 <xref:System.Windows.Controls.Canvas>의 자식 요소는는 <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="fa14c-106">In order to rotate the <xref:System.Windows.Controls.Primitives.Popup>, this example assigns a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property on the <xref:System.Windows.Controls.Canvas>, which is the child element of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  
  
 <span data-ttu-id="fa14c-107">제대로 작동 하려면 변환에 대 한 예제 설정 해야 합니다 <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="fa14c-107">For the transform to work correctly, the example must set the <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> property to `true`.</span></span> <span data-ttu-id="fa14c-108">또한를 <xref:System.Windows.FrameworkElement.Margin%2A> 에 <xref:System.Windows.Controls.Canvas> 내용에 대 한 충분 한 공간을 지정 해야 합니다는 <xref:System.Windows.Controls.Primitives.Popup> 회전 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa14c-108">In addition, the <xref:System.Windows.FrameworkElement.Margin%2A> on the <xref:System.Windows.Controls.Canvas> content must specify enough space for the <xref:System.Windows.Controls.Primitives.Popup> to rotate.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 <span data-ttu-id="fa14c-109">다음 예제에서는 어떻게를 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 발생 하는 이벤트 때를 <xref:System.Windows.Controls.Button> 를 클릭 하면 트리거는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션을 시작 하는.</span><span class="sxs-lookup"><span data-stu-id="fa14c-109">The following example shows how a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which occurs when a <xref:System.Windows.Controls.Button> is clicked, triggers the <xref:System.Windows.Media.Animation.Storyboard> that starts the animation.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a><span data-ttu-id="fa14c-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="fa14c-110">See also</span></span>
- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Controls.Primitives.BulletDecorator>
- <xref:System.Windows.Media.RotateTransform>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="fa14c-111">방법 항목</span><span class="sxs-lookup"><span data-stu-id="fa14c-111">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)
- [<span data-ttu-id="fa14c-112">팝업 개요</span><span class="sxs-lookup"><span data-stu-id="fa14c-112">Popup Overview</span></span>](../../../../docs/framework/wpf/controls/popup-overview.md)
