---
title: '방법: 경로를 따라 개체에 애니메이션 효과 주기(오프셋이 누적된 매트릭스 애니메이션)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: e5e619de8b90737136559db134a131fdc1833fb9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640097"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a><span data-ttu-id="b2a9c-102">방법: 경로를 따라 개체에 애니메이션 효과 주기(오프셋이 누적된 매트릭스 애니메이션)</span><span class="sxs-lookup"><span data-stu-id="b2a9c-102">How to: Animate an Object Along a Path (Matrix Animation with Offset Accumulation)</span></span>
<span data-ttu-id="b2a9c-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 클래스 경로 따라 개체에 애니메이션 효과 주고의 오프셋이 누적 애니메이션이 반복 됨에 따라 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path and have that animation accumulate its offset values as it repeats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2a9c-104">예제</span><span class="sxs-lookup"><span data-stu-id="b2a9c-104">Example</span></span>  
 <span data-ttu-id="b2a9c-105">다음 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 애니메이션을 적용할 개체를 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 의 속성을 <xref:System.Windows.Media.MatrixTransform> 단추에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> applied to a button.</span></span> <span data-ttu-id="b2a9c-106">그 결과 단추가 곡선 경로를 따라 움직입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-106">As a result, a button moves along a curved path.</span></span>  
  
 <span data-ttu-id="b2a9c-107">또한이 예제에서는 설정 합니다 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> 속성을 `true`, 누적 애니메이션이 반복 됨에 따라 애니메이션된 매트릭스의 오프셋이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-107">In addition, the example sets the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property to `true`, which causes the offset of the animated matrix to accumulate as the animation repeats.</span></span> <span data-ttu-id="b2a9c-108">오프셋이 누적되므로 애니메이션이 반복되면 단추는 시작 위치로 재설정되는 것이 아니라 화면을 가로질러 더 크게 움직입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-108">Because the offset accumulates, the button moves farther across the screen when the animation repeats, rather than resetting to the starting position.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <span data-ttu-id="b2a9c-109">없지만 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> 속성 반복 해 서 축적 오프셋된 값으로 인해, 회전 값은 누적을 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-109">Note that, although the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property causes offset values to accumulate over repetitions, it doesn't cause rotation values to accumulate.</span></span> <span data-ttu-id="b2a9c-110">회전 값을 누적 하려면 애니메이션의 설정 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 하 고 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-110">To make rotation values accumulate, set the animation's <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> and <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> properties to `true`.</span></span>  
  
 <span data-ttu-id="b2a9c-111">전체 샘플을 참조 하세요 [경로 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160028)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-111">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="b2a9c-112">애니메이션을 적용 하는 방법을 보여 주는 예제는 <xref:System.Windows.Media.Matrix> 오프셋된 누적 없이 경로 따라 값을 참조 하십시오 [는 경로 따라 개체 (매트릭스 애니메이션)에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-112">For an example showing how to animate a <xref:System.Windows.Media.Matrix> value along a path without offset accumulation, see [Animate an Object Along a Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a9c-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="b2a9c-113">See also</span></span>
- [<span data-ttu-id="b2a9c-114">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="b2a9c-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="b2a9c-115">경로 애니메이션 방법 항목</span><span class="sxs-lookup"><span data-stu-id="b2a9c-115">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
