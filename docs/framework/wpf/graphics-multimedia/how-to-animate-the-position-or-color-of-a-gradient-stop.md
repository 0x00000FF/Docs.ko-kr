---
title: "방법: 그라데이션 중지점의 위치 또는 색에 애니메이션 효과 적용"
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
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 968d285d8a3345da9810f0ba4797bf8b2e33d36e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="683dc-102">방법: 그라데이션 중지점의 위치 또는 색에 애니메이션 효과 적용</span><span class="sxs-lookup"><span data-stu-id="683dc-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="683dc-103">애니메이션 효과 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.GradientStop.Color%2A> 및 <xref:System.Windows.Media.GradientStop.Offset%2A> 의 <xref:System.Windows.Media.GradientStop> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="683dc-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="683dc-104">예제</span><span class="sxs-lookup"><span data-stu-id="683dc-104">Example</span></span>  
 <span data-ttu-id="683dc-105">다음 예제에서는 세 개의 그라데이션 중지점 내 애니메이션 효과 적용 한 <xref:System.Windows.Media.LinearGradientBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="683dc-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="683dc-106">이 예제에서는 서로 다른 그라데이션 중지점 애니메이션 효과 적용 하며 각 세 애니메이션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="683dc-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
-   <span data-ttu-id="683dc-107">첫 번째 애니메이션은 <xref:System.Windows.Media.Animation.DoubleAnimation>, 첫 번째 그라데이션 중지점의 애니메이션 효과 적용 <xref:System.Windows.Media.GradientStop.Offset%2A> 0.0에서 1.0 변환한 다음 다시 0.0으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="683dc-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="683dc-108">결과적으로, 첫 번째 사각형의 왼쪽에서 오른쪽으로 왼쪽에서 그라데이션 shifts에서 색을 왼쪽으로 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="683dc-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
-   <span data-ttu-id="683dc-109">두 번째 애니메이션은 <xref:System.Windows.Media.Animation.ColorAnimation>, 두 번째 그라데이션 중지점의 애니메이션 효과 적용 <xref:System.Windows.Media.GradientStop.Color%2A> 에서 <xref:System.Windows.Media.Colors.Purple%2A> 를 <xref:System.Windows.Media.Colors.Yellow%2A> 다시 <xref:System.Windows.Media.Colors.Purple%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="683dc-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="683dc-110">결과적으로, 노란색, 보라색 다시로 자주색에서 그라데이션의 중간 색을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="683dc-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
-   <span data-ttu-id="683dc-111">세 번째 애니메이션 다른 <xref:System.Windows.Media.Animation.ColorAnimation>, 세 번째 그라데이션 중지점의 불투명도 애니메이션 효과 적용 <xref:System.Windows.Media.GradientStop.Color%2A> -1로 변환한 다음 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="683dc-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="683dc-112">결과적으로, 세 번째 그라데이션 색 희미해 고 나면 불투명 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="683dc-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="683dc-113">이 예제에서는 한 <xref:System.Windows.Media.LinearGradientBrush>는 과정은 동일 하에 애니메이션 효과를 <xref:System.Windows.Media.GradientStop> 개체는 <xref:System.Windows.Media.RadialGradientBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="683dc-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="683dc-114">추가 예제에 대 한 참조는 [브러시 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)합니다.</span><span class="sxs-lookup"><span data-stu-id="683dc-114">For additional examples, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="683dc-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="683dc-115">See Also</span></span>  
 <xref:System.Windows.Media.GradientStop>  
 [<span data-ttu-id="683dc-116">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="683dc-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="683dc-117">Storyboard 개요</span><span class="sxs-lookup"><span data-stu-id="683dc-117">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
