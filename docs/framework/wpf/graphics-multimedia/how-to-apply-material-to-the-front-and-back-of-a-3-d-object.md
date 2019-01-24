---
title: '방법: 3차원 개체의 앞과 뒤에 Material 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 16f30e3a880d7dcc943a9583ba0f04c4bd682827
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652035"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a><span data-ttu-id="da1ac-102">방법: 3차원 개체의 앞과 뒤에 Material 적용</span><span class="sxs-lookup"><span data-stu-id="da1ac-102">How to: Apply Material to the Front and Back of a 3-D Object</span></span>
<span data-ttu-id="da1ac-103">다음 예제에 적용 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Media3D.Material> 전면 및 후면 3 차원 개체 및 개체의 양쪽에 표시할 개체에 애니메이션을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="da1ac-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3-D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="da1ac-104"><xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> 의 속성을 <xref:System.Windows.Media.Media3D.GeometryModel3D> 빨간색을 적용 하는 데 사용 됩니다 <xref:System.Windows.Media.Brush> 개체의 전면에 및 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> 속성의는 <xref:System.Windows.Media.Media3D.GeometryModel3D> 파란색을 적용 하는 데 사용 됩니다 <xref:System.Windows.Media.Brush> 개체의 뒷면에.</span><span class="sxs-lookup"><span data-stu-id="da1ac-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="da1ac-105">아래 코드에서는 개체에 대 한 자료의 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da1ac-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="da1ac-106">예제</span><span class="sxs-lookup"><span data-stu-id="da1ac-106">Example</span></span>  
 <span data-ttu-id="da1ac-107">다음 코드에는 전체 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da1ac-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="da1ac-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="da1ac-108">See also</span></span>
- [<span data-ttu-id="da1ac-109">3차원 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="da1ac-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="da1ac-110">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="da1ac-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [<span data-ttu-id="da1ac-111">3차원 장면의 Material 속성에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="da1ac-111">Animate Material Properties in a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="da1ac-112">3차원 개체에 EmissiveMaterial 적용</span><span class="sxs-lookup"><span data-stu-id="da1ac-112">Apply Emissive Material to a 3-D Object</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
