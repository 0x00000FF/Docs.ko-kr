---
title: '방법: 키 프레임을 사용하여 사각형에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: 9b4a620ea58026c3be1b09d01a595e965e4c2b45
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46002946"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="221ff-102">방법: 키 프레임을 사용하여 사각형에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="221ff-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="221ff-103">애니메이션을 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 의 속성을 <xref:System.Windows.Media.RectangleGeometry> 키 프레임을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="221ff-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="221ff-104">예제</span><span class="sxs-lookup"><span data-stu-id="221ff-104">Example</span></span>  
 <span data-ttu-id="221ff-105">다음 예제에서는 합니다 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> 클래스에 애니메이션 효과를 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 의 속성을 <xref:System.Windows.Media.RectangleGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="221ff-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="221ff-106">이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="221ff-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="221ff-107">처음 2 초 동안의 인스턴스를 사용 하 여는 <xref:System.Windows.Media.Animation.LinearRectKeyFrame> 위치, 너비 및 사각형의 높이의 점진적 변화에 애니메이션 효과를 주는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="221ff-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="221ff-108">과 같은 선형 키 프레임 <xref:System.Windows.Media.Animation.LinearRectKeyFrame> 값 사이 매끄러운 선형 전환을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="221ff-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="221ff-109">0.5 초가 고 다음의 끝 중의 인스턴스를 사용 하 여 <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> 클래스를 사각형의 높이 갑자기 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="221ff-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="221ff-110">과 같은 불연속 키 프레임 <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> 값 간에 급격 한 변화를 만듭니다, 높이 감소 신속 하 게 발생 하 고는 미묘 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="221ff-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3.  <span data-ttu-id="221ff-111">마지막 2 초 동안의 인스턴스를 사용 하 여는 <xref:System.Windows.Media.Animation.SplineRectKeyFrame> 사각형을 다시 원래 크기와 위치를 변경 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="221ff-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="221ff-112">과 같은 스플라인 키 프레임 <xref:System.Windows.Media.Animation.SplineRectKeyFrame> 의 값에 따라 값 사이 가변 전환을 만듭니다는 <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="221ff-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="221ff-113">이 예제에서 변화는 느리게 시작하다가 시간 세그먼트의 끝에 다가가면 기하급수적으로 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="221ff-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="221ff-114">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="221ff-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="221ff-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="221ff-115">See Also</span></span>  
 <xref:System.Windows.Media.RectangleGeometry>  
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>  
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>  
 [<span data-ttu-id="221ff-116">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="221ff-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="221ff-117">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="221ff-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
