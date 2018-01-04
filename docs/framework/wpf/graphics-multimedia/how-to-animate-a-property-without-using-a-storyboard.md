---
title: "방법: Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- non-Storyboard animation
- local animation [WPF]
- animation [WPF], non-Storyboard (local)
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a1292dae3a6fc7e86387ecbe3bf2b1da6912cc0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a><span data-ttu-id="ae737-102">방법: Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="ae737-102">How to: Animate a Property Without Using a Storyboard</span></span>
<span data-ttu-id="ae737-103">사용 하지 않고 속성에 애니메이션을 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Storyboard>합니다.</span><span class="sxs-lookup"><span data-stu-id="ae737-103">This example shows one way to apply an animation to a property without using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae737-104">이 기능은 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae737-104">This functionality is not available in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="ae737-105">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 속성에 애니메이션 효과를 주는 방법에 대한 자세한 내용은 [Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae737-105">For information about animating a property in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="ae737-106">속성에 로컬 애니메이션을 적용 하려면 사용 된 <xref:System.Windows.UIElement.BeginAnimation%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="ae737-106">To apply a local animation to a property, use the <xref:System.Windows.UIElement.BeginAnimation%2A> method.</span></span> <span data-ttu-id="ae737-107">이 메서드는 두 개의 매개 변수:는 <xref:System.Windows.DependencyProperty> 애니메이션을 효과를 줄 속성 및 해당 속성에 적용할 애니메이션을 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae737-107">This method takes two parameters: a <xref:System.Windows.DependencyProperty> that specifies the property to animate, and the animation to apply to that property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae737-108">예</span><span class="sxs-lookup"><span data-stu-id="ae737-108">Example</span></span>  
 <span data-ttu-id="ae737-109">너비 및 배경 색 애니메이션 효과를 주는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="ae737-109">The following example shows how to animate the width and background color of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 <span data-ttu-id="ae737-110">다양 한 애니메이션 클래스에는 <xref:System.Windows.Media.Animation> 다양 한 유형의 속성에 애니메이션을 적용 하는 것에 대 한 네임 스페이스 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae737-110">A variety of animation classes in the <xref:System.Windows.Media.Animation> namespace exist for animating different types of properties.</span></span> <span data-ttu-id="ae737-111">속성 애니메이션에 대한 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ae737-111">For more information about animating properties, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="ae737-112">종속성 속성(이 예제에 표시되는 속성의 형식) 및 해당 기능에 대한 자세한 내용은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae737-112">For more information about dependency properties (the type of properties that are shown in these examples) and their features, see [Dependency Properties Overview](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
 <span data-ttu-id="ae737-113">다른 여러 가지를 사용 하지 않고 애니메이션 효과를 주는 <xref:System.Windows.Media.Animation.Storyboard> 개체, 자세한 내용은 참조 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae737-113">There are other ways to animate without using <xref:System.Windows.Media.Animation.Storyboard> objects; for more information, see [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae737-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae737-114">See Also</span></span>  
 <xref:System.Windows.Media.Animation.AnimationTimeline>  
 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>  
 <xref:System.Windows.Media.Animation>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [<span data-ttu-id="ae737-115">속성 애니메이션 기술 개요</span><span class="sxs-lookup"><span data-stu-id="ae737-115">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [<span data-ttu-id="ae737-116">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="ae737-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
