---
title: '방법: 3차원 장면의 Material 속성에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3-D scenes
- animation [WPF], Material properties in 3-D scenes
- 3-D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: ed4bbb3b22b09c24ed40b72a483db38b35038759
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559055"
---
# <a name="how-to-animate-material-properties-in-a-3-d-scene"></a><span data-ttu-id="23d26-102">방법: 3차원 장면의 Material 속성에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="23d26-102">How to: Animate Material Properties in a 3-D Scene</span></span>
<span data-ttu-id="23d26-103">애니메이션 효과 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Brush.Opacity%2A> 속성은 <xref:System.Windows.Media.Media3D.Material> 에 적용 한 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="23d26-103">This example shows how to animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Media3D.Material> applied to a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="23d26-104">다음 코드 예제에서는 정의 <xref:System.Windows.Media.LinearGradientBrush> 로 사용 되는 <xref:System.Windows.Media.Media3D.Material> 3D 개체에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d26-104">The following code example defines the <xref:System.Windows.Media.LinearGradientBrush> used as the <xref:System.Windows.Media.Media3D.Material> applied to the 3D object.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 <span data-ttu-id="23d26-105"><xref:System.Windows.Media.Brush.Opacity%2A> 속성 <xref:System.Windows.Media.LinearGradientBrush> 아래 코드 예제를 사용 하 여 애니메이션 효과가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23d26-105">The <xref:System.Windows.Media.Brush.Opacity%2A> property of this <xref:System.Windows.Media.LinearGradientBrush> is animated using the code example below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="23d26-106">예제</span><span class="sxs-lookup"><span data-stu-id="23d26-106">Example</span></span>  
 <span data-ttu-id="23d26-107">다음 코드에서는 전체 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="23d26-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="23d26-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23d26-108">See Also</span></span>  
 [<span data-ttu-id="23d26-109">3차원 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="23d26-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="23d26-110">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="23d26-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
