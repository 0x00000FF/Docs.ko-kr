---
title: '방법: 그라데이션 중지점의 위치 또는 색에 애니메이션 효과 적용'
ms.date: 03/30/2017
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
ms.openlocfilehash: fcbb546b64810416d3f7dbe052da77b7bc941e7a
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083987"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="a8d7b-102">방법: 그라데이션 중지점의 위치 또는 색에 애니메이션 효과 적용</span><span class="sxs-lookup"><span data-stu-id="a8d7b-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="a8d7b-103">애니메이션을 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.GradientStop.Color%2A> 하 고 <xref:System.Windows.Media.GradientStop.Offset%2A> 의 <xref:System.Windows.Media.GradientStop> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7b-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8d7b-104">예제</span><span class="sxs-lookup"><span data-stu-id="a8d7b-104">Example</span></span>  
 <span data-ttu-id="a8d7b-105">다음 예제에서는 세 그라데이션 내에서 애니메이션을 <xref:System.Windows.Media.LinearGradientBrush>입니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7b-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="a8d7b-106">이 예제에서는 다양 한 그라데이션 중지점에 애니메이션을 적용 하는 각 세 가지 애니메이션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7b-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
-   <span data-ttu-id="a8d7b-107">첫 번째 애니메이션을 <xref:System.Windows.Media.Animation.DoubleAnimation>, 첫 번째 그라데이션 중지점의 애니메이션 <xref:System.Windows.Media.GradientStop.Offset%2A> 0.0에서 1.0의 0.0으로 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7b-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="a8d7b-108">결과적으로, 첫 번째 사각형의 왼쪽에서 오른쪽으로 왼쪽에서 그라데이션 만큼의 색을 왼쪽으로 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7b-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
-   <span data-ttu-id="a8d7b-109">두 번째 애니메이션을 <xref:System.Windows.Media.Animation.ColorAnimation>, 두 번째 그라데이션 중지점의 애니메이션 효과 줍니다 <xref:System.Windows.Media.GradientStop.Color%2A> 에서 <xref:System.Windows.Media.Colors.Purple%2A> 에 <xref:System.Windows.Media.Colors.Yellow%2A> 다시 <xref:System.Windows.Media.Colors.Purple%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7b-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="a8d7b-110">결과적으로, 노란색, 보라색으로 다시로 자주색에서 그라데이션의 중간 색을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7b-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
-   <span data-ttu-id="a8d7b-111">세 번째 애니메이션 다른 <xref:System.Windows.Media.Animation.ColorAnimation>, 세 번째 그라데이션 중지점의 불투명도 애니메이션을 적용 <xref:System.Windows.Media.GradientStop.Color%2A> -1로 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7b-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="a8d7b-112">결과적으로, 세 번째 그라데이션 색 희미해 및 다시 불투명해 집니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7b-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="a8d7b-113">이 예제에서는 <xref:System.Windows.Media.LinearGradientBrush>, 프로세스에 애니메이션 효과를 동일 <xref:System.Windows.Media.GradientStop> 내에서 개체를 <xref:System.Windows.Media.RadialGradientBrush>입니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7b-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="a8d7b-114">추가 예제를 보려면 합니다 [브러시 샘플](https://go.microsoft.com/fwlink/?LinkID=159973)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7b-114">For additional examples, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8d7b-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8d7b-115">See Also</span></span>  
 <xref:System.Windows.Media.GradientStop>  
 [<span data-ttu-id="a8d7b-116">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="a8d7b-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="a8d7b-117">Storyboard 개요</span><span class="sxs-lookup"><span data-stu-id="a8d7b-117">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
