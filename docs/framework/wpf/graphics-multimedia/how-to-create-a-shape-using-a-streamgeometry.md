---
title: '방법: StreamGeometry를 사용하여 도형 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
ms.openlocfilehash: 94e7683d22b685c95f9f70612bc0aacef06e23bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554207"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a><span data-ttu-id="f650f-102">방법: StreamGeometry를 사용하여 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="f650f-102">How to: Create a Shape Using a StreamGeometry</span></span>
<span data-ttu-id="f650f-103"><xref:System.Windows.Media.StreamGeometry> 간단한 대신 <xref:System.Windows.Media.PathGeometry> 기 하 도형 만들기에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f650f-103"><xref:System.Windows.Media.StreamGeometry> is light-weight alternative to <xref:System.Windows.Media.PathGeometry> for creating geometric shapes.</span></span> <span data-ttu-id="f650f-104">사용 하 여는 <xref:System.Windows.Media.StreamGeometry> 복잡 한 기 하 도형을 설명 해야 하지만 데이터 바인딩, 애니메이션 또는 수정을 지원 오버 헤드를 원하지 않는 합니다.</span><span class="sxs-lookup"><span data-stu-id="f650f-104">Use a <xref:System.Windows.Media.StreamGeometry> when you need to describe a complex geometry but do not want the overhead of supporting data binding, animation, or modification.</span></span> <span data-ttu-id="f650f-105">예를 들어는 효율성으로 인해는 <xref:System.Windows.Media.StreamGeometry> 클래스는 표시기 (adorner)를 설명 하는 데 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="f650f-105">For example, because of its efficiency, the <xref:System.Windows.Media.StreamGeometry> class is a good choice for describing adorners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f650f-106">예제</span><span class="sxs-lookup"><span data-stu-id="f650f-106">Example</span></span>  
 <span data-ttu-id="f650f-107">다음 예제에서는 특성 구문을 사용 하 여 삼각형을 만드는 <xref:System.Windows.Media.StreamGeometry> 에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="f650f-107">The following example uses attribute syntax to create a triangular <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 <span data-ttu-id="f650f-108">에 대 한 자세한 내용은 <xref:System.Windows.Media.StreamGeometry> 특성 구문, 참조는 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="f650f-108">For more information about <xref:System.Windows.Media.StreamGeometry> attribute syntax, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f650f-109">예제</span><span class="sxs-lookup"><span data-stu-id="f650f-109">Example</span></span>  
 <span data-ttu-id="f650f-110">다음 예제에서는 <xref:System.Windows.Media.StreamGeometry> 코드에서 삼각형을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f650f-110">The next example uses a <xref:System.Windows.Media.StreamGeometry> to define a triangle in code.</span></span> <span data-ttu-id="f650f-111">첫째,이 예에서는 만듭니다는 <xref:System.Windows.Media.StreamGeometry>을 구합니다를 <xref:System.Windows.Media.StreamGeometryContext> 삼각형을 설명 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f650f-111">First, the example creates a <xref:System.Windows.Media.StreamGeometry>, then obtains a <xref:System.Windows.Media.StreamGeometryContext> and uses it to describe the triangle.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="f650f-112">예제</span><span class="sxs-lookup"><span data-stu-id="f650f-112">Example</span></span>  
 <span data-ttu-id="f650f-113">다음 예제를 사용 하는 메서드를 만듭니다는 <xref:System.Windows.Media.StreamGeometry> 및 <xref:System.Windows.Media.StreamGeometryContext> 에 지정 된 매개 변수를 기반으로 도형을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f650f-113">The next example creates a method that uses a <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.StreamGeometryContext> to define a geometric shape based on specified parameters.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="f650f-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="f650f-114">See also</span></span>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.StreamGeometryContext>
- [<span data-ttu-id="f650f-115">PathGeometry를 사용하여 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="f650f-115">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
- [<span data-ttu-id="f650f-116">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="f650f-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
