---
title: '방법: 경로를 따라 개체에 애니메이션 효과 주기(매트릭스 애니메이션)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: 03e1e40f8ee6840558ad7b712d96e63d9e2bf15f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559005"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a><span data-ttu-id="2c4ca-102">방법: 경로를 따라 개체에 애니메이션 효과 주기(매트릭스 애니메이션)</span><span class="sxs-lookup"><span data-stu-id="2c4ca-102">How to: Animate an Object Along a Path (Matrix Animation)</span></span>
<span data-ttu-id="2c4ca-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 클래스에서 정의 된 경로 따라 개체를 애니메이션 효과를 주는 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4ca-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path that is defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c4ca-104">예제</span><span class="sxs-lookup"><span data-stu-id="2c4ca-104">Example</span></span>  
 <span data-ttu-id="2c4ca-105">다음 예제에서는 다음을 수행하여 경로를 따라 개체에 애니메이션 효과를 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c4ca-105">The following example animates an object along a path by doing the following:</span></span>  
  
-   <span data-ttu-id="2c4ca-106">적용 한 <xref:System.Windows.Media.MatrixTransform> 개체로 이동할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4ca-106">Applies a <xref:System.Windows.Media.MatrixTransform> to the object in order to move it.</span></span>  
  
-   <span data-ttu-id="2c4ca-107">경로 사용 하 여 정의 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4ca-107">Defines the path by using a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
-   <span data-ttu-id="2c4ca-108">만듭니다는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 애니메이션 효과를 사용 하 여는 <xref:System.Windows.Media.Matrix> 의 속성은 <xref:System.Windows.Media.MatrixTransform>합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4ca-108">Creates a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and uses it to animate the <xref:System.Windows.Media.Matrix> property of the <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="2c4ca-109"><xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 사용는 <xref:System.Windows.Media.PathGeometry> 사용 하 여 생성 하 고 <xref:System.Windows.Media.Matrix> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2c4ca-109">The <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> takes the <xref:System.Windows.Media.PathGeometry> and uses it to generate <xref:System.Windows.Media.Matrix> values.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 <span data-ttu-id="2c4ca-110">전체 샘플을 참조 하십시오. [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4ca-110">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="2c4ca-111">기하학적 경로 대 한 자세한 내용은 참조는 [기 하 도형 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4ca-111">For more information about geometric paths, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c4ca-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c4ca-112">See Also</span></span>  
 [<span data-ttu-id="2c4ca-113">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="2c4ca-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="2c4ca-114">경로 애니메이션 샘플</span><span class="sxs-lookup"><span data-stu-id="2c4ca-114">Path Animation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [<span data-ttu-id="2c4ca-115">경로 애니메이션 방법 항목</span><span class="sxs-lookup"><span data-stu-id="2c4ca-115">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
