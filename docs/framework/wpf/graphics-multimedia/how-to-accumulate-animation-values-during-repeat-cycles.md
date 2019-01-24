---
title: '방법: 주기가 반복되는 동안 애니메이션 값 누적'
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: 6e98b7eefd0c30e728b60926096c0f082bc079ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587283"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a><span data-ttu-id="dcc1f-102">방법: 주기가 반복되는 동안 애니메이션 값 누적</span><span class="sxs-lookup"><span data-stu-id="dcc1f-102">How to: Accumulate Animation Values During Repeat Cycles</span></span>
<span data-ttu-id="dcc1f-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 반복 주기에 대해 애니메이션 값 누적 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc1f-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate animation values across repeating cycles.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcc1f-104">예제</span><span class="sxs-lookup"><span data-stu-id="dcc1f-104">Example</span></span>  
 <span data-ttu-id="dcc1f-105">사용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 반복 주기에 대해 애니메이션의 기본 값을 누적 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc1f-105">Use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate base values of an animation across repeating cycles.</span></span> <span data-ttu-id="dcc1f-106">예를 들어 애니메이션 9 번 반복을 설정 하는 경우 (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9 x") 10 월 15 일 까지의 애니메이션 효과를 주는 속성을 설정 (10 = = 15), 속성에 애니메이션 효과 10에서 15 15 두 번째 주기 동안 20에서 첫 번째 주기 동안 세 번째 주기 등에 중 25 20에서입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc1f-106">For example, if you set an animation to repeat 9 times (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") and you set the property to animate between 10 and 15 (From = 10 To = 15), the property animates from 10 to 15 during the first cycle, from 15 to 20 during the second cycle, from 20 to 25 during the third cycle, and so on.</span></span> <span data-ttu-id="dcc1f-107">따라서 각 애니메이션 주기는 기준 값으로 이전 애니메이션 주기에서 끝 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc1f-107">Hence, each animation cycle uses the ending animation value from the previous animation cycle as its base value.</span></span>  
  
 <span data-ttu-id="dcc1f-108">사용할 수는 `IsCumulative` 가장 기본적인 애니메이션 및 대부분의 키 프레임 애니메이션을 사용 하 여 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc1f-108">You can use the `IsCumulative` property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="dcc1f-109">자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) 하 고 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc1f-109">For more information, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) and [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="dcc1f-110">다음 예제에서는 네 개의 사각형의 너비를 애니메이션으로이 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dcc1f-110">The following example shows this behavior by animating the width of four rectangles.</span></span> <span data-ttu-id="dcc1f-111">예제:</span><span class="sxs-lookup"><span data-stu-id="dcc1f-111">The example:</span></span>  
  
-   <span data-ttu-id="dcc1f-112">사용 하 여 첫 번째 사각형에 애니메이션을 적용 <xref:System.Windows.Media.Animation.DoubleAnimation> 가져오거나 설정 합니다 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc1f-112">Animates the first rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to `true`.</span></span>  
  
-   <span data-ttu-id="dcc1f-113">사용 하 여 두 번째 사각형에 애니메이션을 적용 <xref:System.Windows.Media.Animation.DoubleAnimation> 가져오거나 설정 합니다 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 속성의 기본값을 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc1f-113">Animates the second rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to the default value of `false`.</span></span>  
  
-   <span data-ttu-id="dcc1f-114">사용 하 여 세 번째 사각형에 애니메이션을 적용 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 가져오거나 설정 합니다 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc1f-114">Animates the third rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `true`.</span></span>  
  
-   <span data-ttu-id="dcc1f-115">사용 하 여 마지막 사각형에 애니메이션을 적용 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 가져오거나 설정 합니다 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> 속성을 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc1f-115">Animates the last rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `false`.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="dcc1f-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="dcc1f-116">See also</span></span>
- [<span data-ttu-id="dcc1f-117">애니메이션 시작 값에 애니메이션 출력 값 추가</span><span class="sxs-lookup"><span data-stu-id="dcc1f-117">Add an Animation Output Value to an Animation Starting Value</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [<span data-ttu-id="dcc1f-118">애니메이션 반복</span><span class="sxs-lookup"><span data-stu-id="dcc1f-118">Repeat an Animation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)
- [<span data-ttu-id="dcc1f-119">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="dcc1f-119">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="dcc1f-120">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="dcc1f-120">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [<span data-ttu-id="dcc1f-121">방법 항목</span><span class="sxs-lookup"><span data-stu-id="dcc1f-121">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
