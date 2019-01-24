---
title: '방법: 키 프레임 애니메이션 타이밍 제어'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-fram animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 3a8e11ee8bfbbe87ca5a1c51b815dd21c124a951
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712027"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="f5c49-102">방법: 키 프레임 애니메이션 타이밍 제어</span><span class="sxs-lookup"><span data-stu-id="f5c49-102">How to: Control Key-Frame Animation Timing</span></span>
<span data-ttu-id="f5c49-103">이 예제에서는 키 프레임 애니메이션 내의 키 프레임의 타이밍을 제어 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="f5c49-104">다른 애니메이션과 마찬가지로 키 프레임 애니메이션에는 한 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="f5c49-105">애니메이션의 지속 시간을 지정 하는 것 외에도 각 키 프레임에 할당 된 해당 기간의 부분을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="f5c49-106">지정 시간을 할당 하는 <xref:System.Windows.Media.Animation.KeyTime> 각 키 프레임 애니메이션에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>  
  
 <span data-ttu-id="f5c49-107"><xref:System.Windows.Media.Animation.KeyTime> 때 (키 프레임이 재생 되는 시간의 길이 지정 하지 않습니다)는 키 프레임이 끝나는 시간을 지정 하는 각 키 프레임에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="f5c49-108">지정할 수 있습니다는 <xref:System.Windows.Media.Animation.KeyTime> 으로 <xref:System.TimeSpan> 값 또는 백분율로 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> 또는 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 특수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5c49-109">예제</span><span class="sxs-lookup"><span data-stu-id="f5c49-109">Example</span></span>  
 <span data-ttu-id="f5c49-110">다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 화면에서 사각형에 애니메이션 효과를 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="f5c49-111">키 프레임의 키 시간으로 설정 되어 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
 [!code-vb[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
 [!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]  
  
 <span data-ttu-id="f5c49-112">다음 그림에서는 각 키 프레임의 값에 도달할 때를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-112">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="f5c49-113">![3, 4, 10 초에 키 값에 도달](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="f5c49-113">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>  
  
 <span data-ttu-id="f5c49-114">다음 예제에서는 키 프레임의 키 시간이 백분율 값으로 설정 되는 점을 제외 하면 동일는 애니메이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
 [!code-vb[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
 [!code-xaml[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]  
  
 <span data-ttu-id="f5c49-115">다음 그림에서는 각 키 프레임의 값에 도달할 때를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-115">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="f5c49-116">![3, 4, 10 초에 키 값에 도달](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="f5c49-116">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>  
  
 <span data-ttu-id="f5c49-117">다음 예제에서는 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> 키 시간 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
 [!code-vb[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
 [!code-xaml[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]  
  
 <span data-ttu-id="f5c49-118">다음 그림에서는 각 키 프레임의 값에 도달할 때를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-118">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="f5c49-119">![키 값은 3.3, 6.6 및 9.9 초에 도달](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="f5c49-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>  
  
 <span data-ttu-id="f5c49-120">마지막 예제에서는 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 키 시간 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
 [!code-vb[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
 [!code-xaml[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]  
  
 <span data-ttu-id="f5c49-121">다음 그림에서는 각 키 프레임의 값에 도달할 때를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-121">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="f5c49-122">![키 값은 0, 5, 10 초에 도달](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="f5c49-122">![Key values are reached at 0, 5, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>  
  
 <span data-ttu-id="f5c49-123">편의상이 예제에서는 사용 하 여 로컬 애니메이션 코드 버전 하지 storyboard를 단일 속성에 단일 애니메이션을 적용 되 고 있지만 스토리 보드를 대신 사용 하도록 예제를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="f5c49-124">코드에서 스토리 보드를 선언 하는 방법을 보여 주는 예제를 참조 하세요 [Storyboard를 사용 하 여 속성에 애니메이션 효과](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="f5c49-125">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5c49-125">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span> <span data-ttu-id="f5c49-126">키 프레임 애니메이션에 대 한 자세한 내용은 참조는 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c49-126">For more information about key frame animations, see the [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c49-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="f5c49-127">See also</span></span>
- [<span data-ttu-id="f5c49-128">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="f5c49-128">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [<span data-ttu-id="f5c49-129">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="f5c49-129">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="f5c49-130">방법 항목</span><span class="sxs-lookup"><span data-stu-id="f5c49-130">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
