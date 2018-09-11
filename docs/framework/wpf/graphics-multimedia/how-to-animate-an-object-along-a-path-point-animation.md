---
title: '방법: 경로를 따라 개체에 애니메이션 효과 주기(포인트 애니메이션)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: d6dc79cd7a15aef2a4168fffb293c5e1f33cde08
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259784"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a><span data-ttu-id="dcaaa-102">방법: 경로를 따라 개체에 애니메이션 효과 주기(포인트 애니메이션)</span><span class="sxs-lookup"><span data-stu-id="dcaaa-102">How to: Animate an Object Along a Path (Point Animation)</span></span>
<span data-ttu-id="dcaaa-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 애니메이션을 적용할 개체는 <xref:System.Windows.Point> 곡선된 경로 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-103">This example shows how to use a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> object to animate a <xref:System.Windows.Point> along a curved path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcaaa-104">예제</span><span class="sxs-lookup"><span data-stu-id="dcaaa-104">Example</span></span>  
 <span data-ttu-id="dcaaa-105">이동 하는 다음 예제는 <xref:System.Windows.Media.EllipseGeometry> 정의한 경로 따라는 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-105">The following example moves an <xref:System.Windows.Media.EllipseGeometry> along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="dcaaa-106">타원 기 하 도형의 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 사용 하는 속성을 <xref:System.Windows.Point> 값에 애니메이션 효과 적용 하면 타원 기 하, 이동 하려면 해당 위치를 지정 하 고, 해당 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-106">The ellipse geometry's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property, which takes a <xref:System.Windows.Point> value, specifies its position; to move the ellipse geometry, you animate its <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span> <span data-ttu-id="dcaaa-107">이 예제에서는 사용을 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 애니메이션 효과를 주는 <xref:System.Windows.Media.EllipseGeometry> 개체의 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-107">The example uses a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate the <xref:System.Windows.Media.EllipseGeometry> object's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 <span data-ttu-id="dcaaa-108">전체 샘플을 참조 하세요 [경로 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160028)합니다.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-108">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="dcaaa-109">사용 하는 이전 샘플의 코드 버전을 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션 효과를 주는 <xref:System.Windows.Media.EllipseGeometry>하나만 애니메이션이 적용 된 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="dcaaa-110">A <xref:System.Windows.Media.Animation.Storyboard> 동일한 이러한 애니메이션을 제어할 수 있으므로 여러 애니메이션을 적용 하는 가장 쉬운 방법은 경우가 <xref:System.Windows.Media.Animation.Storyboard>합니다.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-110">A <xref:System.Windows.Media.Animation.Storyboard> is often the easiest way to apply multiple animations because these animations can be controlled by the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="dcaaa-111">그러나 코드를 사용 하는 경우 속성에 단일 애니메이션을 적용 하는 간단한 방법인 사용 하는 것은 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-111">However, an easier way to apply a single animation to a property when using code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="dcaaa-112">예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-112">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcaaa-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcaaa-113">See Also</span></span>  
 [<span data-ttu-id="dcaaa-114">경로 애니메이션 샘플</span><span class="sxs-lookup"><span data-stu-id="dcaaa-114">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)  
 [<span data-ttu-id="dcaaa-115">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="dcaaa-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="dcaaa-116">경로 애니메이션 방법 항목</span><span class="sxs-lookup"><span data-stu-id="dcaaa-116">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
