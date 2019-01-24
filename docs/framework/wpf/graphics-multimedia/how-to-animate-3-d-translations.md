---
title: '방법: 3차원 변환에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: e73035a48e32e3eec20b44c82b5b9ec6763c1e7c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653036"
---
# <a name="how-to-animate-3-d-translations"></a><span data-ttu-id="0c1ad-102">방법: 3차원 변환에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="0c1ad-102">How to: Animate 3-D Translations</span></span>
<span data-ttu-id="0c1ad-103">이 항목에 설정 된 번역 변형 애니메이션 효과를 주는 방법을 보여 줍니다는 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ad-103">This topic demonstrates how to animate a translation transformation set on a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="0c1ad-104">아래 코드의 응용 프로그램을 보여 줍니다를 <xref:System.Windows.Media.Media3D.TranslateTransform3D> 개체를 <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> 의 속성을 <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="0c1ad-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="0c1ad-105">합니다 <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> 이 <xref:System.Windows.Media.Media3D.TranslateTransform3D> 개체 아래 코드를 사용 하 여 애니메이션 효과가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ad-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="0c1ad-106">예제</span><span class="sxs-lookup"><span data-stu-id="0c1ad-106">Example</span></span>  
 <span data-ttu-id="0c1ad-107">다음 코드에는 전체 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ad-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0c1ad-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="0c1ad-108">See also</span></span>
- [<span data-ttu-id="0c1ad-109">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="0c1ad-109">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="0c1ad-110">3차원 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="0c1ad-110">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="0c1ad-111">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="0c1ad-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [<span data-ttu-id="0c1ad-112">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="0c1ad-112">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
