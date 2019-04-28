---
title: '방법: 상대 값을 사용하여 변환 원점 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
ms.openlocfilehash: 48b3b0df8dab8516873495a996074eae57ffe00f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651144"
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a><span data-ttu-id="2b387-102">방법: 상대 값을 사용하여 변환 원점 지정</span><span class="sxs-lookup"><span data-stu-id="2b387-102">How to: Specify the Origin of a Transform by Using Relative Values</span></span>
<span data-ttu-id="2b387-103">이 예제에서는 상대 값의 출처를 지정 하는 데는 <xref:System.Windows.UIElement.RenderTransform%2A> 에 적용 되는 한 <xref:System.Windows.FrameworkElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="2b387-103">This example shows how to use relative values to specify the origin of a <xref:System.Windows.UIElement.RenderTransform%2A> that is applied to a <xref:System.Windows.FrameworkElement>.</span></span>  
  
 <span data-ttu-id="2b387-104">회전, 크기 조정 또는 기울일 때를 <xref:System.Windows.FrameworkElement> 를 사용 하 여는 <xref:System.Windows.UIElement.RenderTransform%2A> 요소의 왼쪽 위 모퉁이에 변환을 적용 하는 속성을 기본 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b387-104">When you rotate, scale, or skew a <xref:System.Windows.FrameworkElement> by using the <xref:System.Windows.UIElement.RenderTransform%2A> property, the default setting applies the transform to the upper-left corner of the element.</span></span> <span data-ttu-id="2b387-105">요소 중심에서 회전, 크기 조정 또는 기울이기를 수행하려면 변환의 중심을 요소의 중심으로 설정하여 보완할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b387-105">If you want to rotate, scale, or skew from the center of the element, you can compensate by setting the center of the transform to the center of the element.</span></span> <span data-ttu-id="2b387-106">그러나 해당 솔루션에서는 요소의 크기를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b387-106">However, that solution requires that you know the size of the element.</span></span> <span data-ttu-id="2b387-107">요소 중심에 변환을 적용 하는 보다 손쉬운 방법을 설정 하는 것의 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성을 (0.5, 0.5) 변환 자체에 대해 중심 값을 설정 하는 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b387-107">An easier way of applying a transform to the center of an element is to set its <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to (0.5, 0.5), instead of setting a center value on the transform itself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b387-108">예제</span><span class="sxs-lookup"><span data-stu-id="2b387-108">Example</span></span>  
 <span data-ttu-id="2b387-109">다음 예에서는 <xref:System.Windows.Media.RotateTransform> 회전 하는 <xref:System.Windows.Controls.Button> 시계 방향으로 45도 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b387-109">The following example uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise.</span></span> <span data-ttu-id="2b387-110">이 예제에서는 중심을 지정하지 않으므로 단추는 왼쪽 위 구석에 해당하는 점 (0,0)에 대해 회전합니다.</span><span class="sxs-lookup"><span data-stu-id="2b387-110">Because the example does not specify a center, the button rotates about the point (0, 0), which is its upper-left corner.</span></span> <span data-ttu-id="2b387-111">합니다 <xref:System.Windows.Media.RotateTransform> 에 적용 되는 <xref:System.Windows.UIElement.RenderTransform%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2b387-111">The <xref:System.Windows.Media.RotateTransform> is applied to the <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="2b387-112">다음 그림에서는 이어지는 예제의 변환 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b387-112">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="2b387-113">![RenderTransform을 사용 하 여 변형 된 단추](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")</span><span class="sxs-lookup"><span data-stu-id="2b387-113">![A button transformed using RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")</span></span>  
<span data-ttu-id="2b387-114">RenderTransform 속성을 사용한 45도 시계 방향 회전</span><span class="sxs-lookup"><span data-stu-id="2b387-114">A 45 degree clockwise rotation by using the RenderTransform property</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 <span data-ttu-id="2b387-115">다음 예제에서는 또한 사용 하 여는 <xref:System.Windows.Media.RotateTransform> 회전 하는 <xref:System.Windows.Controls.Button> 45도 시계 방향으로, 단,이 예제에서는 설정는 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 단추 (0.5, 0.5).</span><span class="sxs-lookup"><span data-stu-id="2b387-115">The following example also uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise; however, this example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> of the button to (0.5, 0.5).</span></span> <span data-ttu-id="2b387-116">결과적으로, 회전은 왼쪽 위 구석 대신 단추의 중심에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b387-116">As a result, the rotation is applied to the center of the button instead of to the upper-left corner.</span></span>  
  
 <span data-ttu-id="2b387-117">다음 그림에서는 이어지는 예제의 변환 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b387-117">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="2b387-118">![가운데를 중심으로 변형 된 단추](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")</span><span class="sxs-lookup"><span data-stu-id="2b387-118">![A button transformed about its center](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")</span></span>  
<span data-ttu-id="2b387-119">RenderTransformOrigin (0.5, 0.5)의 RenderTransform 속성을 사용하여 45도 회전</span><span class="sxs-lookup"><span data-stu-id="2b387-119">A 45 degree rotation by using the RenderTransform property with a RenderTransformOrigin of (0.5, 0.5)</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 <span data-ttu-id="2b387-120">변환 하는 방법에 대 한 자세한 내용은 <xref:System.Windows.FrameworkElement> 개체를 참조 합니다 [변환 개요](transforms-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b387-120">For more information about transforming <xref:System.Windows.FrameworkElement> objects, see the [Transforms Overview](transforms-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b387-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="2b387-121">See also</span></span>

- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="2b387-122">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="2b387-122">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="2b387-123">방법 항목</span><span class="sxs-lookup"><span data-stu-id="2b387-123">How-to Topics</span></span>](transformations-how-to-topics.md)
