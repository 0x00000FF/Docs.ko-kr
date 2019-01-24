---
title: '방법: 정방형 3차원 곡선 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: a5d424f3fda3957bf54d7073d41d9fe2dabb1736
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650095"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a><span data-ttu-id="c4869-102">방법: 정방형 3차원 곡선 만들기</span><span class="sxs-lookup"><span data-stu-id="c4869-102">How to: Create a Quadratic Bezier Curve</span></span>
<span data-ttu-id="c4869-103">이 예제에서는 정방형 베 지 어 곡선을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4869-103">This example shows how to create a quadratic Bezier curve.</span></span>  <span data-ttu-id="c4869-104">정방형 베 지 어 곡선을 만들려면 사용 합니다 <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, 및 <xref:System.Windows.Media.QuadraticBezierSegment> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c4869-104">To create a quadratic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.QuadraticBezierSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4869-105">예제</span><span class="sxs-lookup"><span data-stu-id="c4869-105">Example</span></span>  
 <span data-ttu-id="c4869-106">다음 예제에서는 정방형 베 지 어 곡선을 그려집니다 (10100)에서 (300100).</span><span class="sxs-lookup"><span data-stu-id="c4869-106">In the following examples, a quadratic Bezier curve is drawn from (10,100) to (300,100).</span></span> <span data-ttu-id="c4869-107">곡선에 있는 (200200)의 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="c4869-107">The curve has a control point of (200,200).</span></span>  
  
 <span data-ttu-id="c4869-108">[xaml]</span><span class="sxs-lookup"><span data-stu-id="c4869-108">[xaml]</span></span>  
  
 <span data-ttu-id="c4869-109">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 경로를 설명할 특성 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4869-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#54](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 <span data-ttu-id="c4869-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="c4869-110">[xaml]</span></span>  
  
 <span data-ttu-id="c4869-111">(이 특성 구문은 실제로 만들어지는 참고를 <xref:System.Windows.Media.StreamGeometry>, 가벼운 버전의는 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="c4869-111">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="c4869-112">자세한 내용은 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) 페이지를 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="c4869-112">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="c4869-113">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 개체 요소 구문을 사용 하 여 정방형 베 지 어 곡선을 그릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4869-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a quadratic Bezier curve using object element syntax.</span></span> <span data-ttu-id="c4869-114">다음 예제는 이전 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="c4869-114">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="c4869-115">이 예제는 더 큰 샘플에 속합니다. 전체 샘플을 보려면 [기하 도형 샘플](https://go.microsoft.com/fwlink/?LinkID=159989)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4869-115">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4869-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="c4869-116">See also</span></span>
- [<span data-ttu-id="c4869-117">타원형 원호 만들기</span><span class="sxs-lookup"><span data-stu-id="c4869-117">Create an Elliptical Arc</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="c4869-118">입방형 3차원 곡선 만들기</span><span class="sxs-lookup"><span data-stu-id="c4869-118">Create a Cubic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
