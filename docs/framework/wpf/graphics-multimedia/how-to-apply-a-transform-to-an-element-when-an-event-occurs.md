---
title: '방법: 이벤트가 발생할 때 요소에 변환 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
ms.openlocfilehash: 3862ffcb8e0dcabd2de67c495204470ac9fa6c14
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726392"
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a><span data-ttu-id="ab378-102">방법: 이벤트가 발생할 때 요소에 변환 적용</span><span class="sxs-lookup"><span data-stu-id="ab378-102">How to: Apply a Transform to an Element When an Event Occurs</span></span>
<span data-ttu-id="ab378-103">적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.ScaleTransform> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab378-103">This example shows how to apply a <xref:System.Windows.Media.ScaleTransform> when an event occurs.</span></span> <span data-ttu-id="ab378-104">여기에 표시된 개념은 다른 유형의 변환을 적용할 때 사용하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab378-104">The concept that is shown here is the same that you use for applying other types of transformations.</span></span> <span data-ttu-id="ab378-105">변환의 사용 가능한 형식에 대 한 자세한 내용은 참조는 <xref:System.Windows.Media.Transform> 클래스 또는 [변환 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab378-105">For more information about the available types of transformations, see the <xref:System.Windows.Media.Transform> class or [Transforms Overview](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).</span></span>  
  
 <span data-ttu-id="ab378-106">다음 두 가지 방법으로 요소에 변환을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab378-106">You can apply a transform to an element in either of these two ways:</span></span>  
  
-   <span data-ttu-id="ab378-107">않으려면 *하지* 레이아웃에 영향을 사용 하 여 변환이 <xref:System.Windows.UIElement.RenderTransform%2A> 요소의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ab378-107">If you do *not* want the transform to affect layout, use the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
-   <span data-ttu-id="ab378-108">변환이 레이아웃에 영향을 줄에 사용 하지 않으려면 사용 된 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 요소의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ab378-108">If you do want the transform to affect layout, use the <xref:System.Windows.FrameworkElement.LayoutTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="ab378-109">다음 예제에서는 적용을 <xref:System.Windows.Media.ScaleTransform> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 단추의 속성.</span><span class="sxs-lookup"><span data-stu-id="ab378-109">The following example applies a <xref:System.Windows.Media.ScaleTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a button.</span></span> <span data-ttu-id="ab378-110">마우스를 단추 위로 이동할 때를 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 및 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 의 속성을 <xref:System.Windows.Media.ScaleTransform> 로 설정 됩니다 `2`, 단추가 더 커집니다.</span><span class="sxs-lookup"><span data-stu-id="ab378-110">When the mouse moves over the button, the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties of the <xref:System.Windows.Media.ScaleTransform> are set to `2`, which causes the button to become larger.</span></span> <span data-ttu-id="ab378-111">마우스 포인터를 단추 밖 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 하 고 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 로 설정 됩니다 `1`, 단추가 원래 크기로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="ab378-111">When the mouse moves off the button, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> are set to `1`, which causes the button to return to its original size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab378-112">예제</span><span class="sxs-lookup"><span data-stu-id="ab378-112">Example</span></span>  
 [!code-xaml[ButtonTransform#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a><span data-ttu-id="ab378-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="ab378-113">See also</span></span>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="ab378-114">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="ab378-114">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
- [<span data-ttu-id="ab378-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="ab378-115">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
- [<span data-ttu-id="ab378-116">라우트된 이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="ab378-116">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
