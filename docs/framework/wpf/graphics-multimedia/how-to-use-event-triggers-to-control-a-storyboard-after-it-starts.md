---
title: '방법: Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: f31b1233f00147fdccde5e0816fa4839ae33d549
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "44036394"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="4eb21-102">방법: Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어</span><span class="sxs-lookup"><span data-stu-id="4eb21-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>
<span data-ttu-id="4eb21-103">제어 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Storyboard> 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb21-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="4eb21-104">시작 하는 <xref:System.Windows.Media.Animation.Storyboard> 를 사용 하 여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용 하 여 <xref:System.Windows.Media.Animation.BeginStoryboard>, 개체 및 속성에 애니메이션을 적용 하 고 시작한 다음 스토리 보드에 애니메이션을 배포 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb21-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="4eb21-105">제공 하는 경우 <xref:System.Windows.Media.Animation.BeginStoryboard> 이름을 지정 하 여 해당 <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> 속성을 만들면 제어 가능한 storyboard입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb21-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="4eb21-106">제어할 수 있습니다 다음 대화형으로 스토리 보드 시작 된 후.</span><span class="sxs-lookup"><span data-stu-id="4eb21-106">You can then interactively control the storyboard after it starts.</span></span>  
  
 <span data-ttu-id="4eb21-107">와 함께 다음 스토리 보드 작업을 사용 하 여 <xref:System.Windows.EventTrigger> storyboard를 제어 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb21-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>  
  
-   <span data-ttu-id="4eb21-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Storyboard를 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb21-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="4eb21-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: 일시 중지 된 storyboard를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb21-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="4eb21-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Storyboard 속도 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb21-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>  
  
-   <span data-ttu-id="4eb21-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: 있는 경우 채우기 기간이의 끝에 스토리 보드를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb21-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="4eb21-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Storyboard를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb21-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>  
  
-   <span data-ttu-id="4eb21-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: 리소스를 확보 하 여 storyboard를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb21-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4eb21-114">예제</span><span class="sxs-lookup"><span data-stu-id="4eb21-114">Example</span></span>  
 <span data-ttu-id="4eb21-115">다음 예제에서는 제어 가능한 storyboard 작업이 storyboard를 대화형으로 제어 하려면</span><span class="sxs-lookup"><span data-stu-id="4eb21-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="4eb21-116">**참고:** 코드를 사용 하 여 스토리 보드 제어의 예제를 보려면 [컨트롤을 스토리 보드 후 해당 시작를 사용 하 여 해당 대화형 메서드](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb21-116">**Note:** To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 <span data-ttu-id="4eb21-117">추가 예제를 보려면 합니다 [애니메이션 예제 갤러리](https://go.microsoft.com/fwlink/?LinkID=159969)합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb21-117">For additional examples, see the [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eb21-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4eb21-118">See Also</span></span>  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>  
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>  
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>  
 <xref:System.Windows.Media.Animation.PauseStoryboard>  
 <xref:System.Windows.Media.Animation.StopStoryboard>  
 <xref:System.Windows.Media.Animation.SeekStoryboard>  
 [<span data-ttu-id="4eb21-119">대화형 메서드를 사용하여 이미 시작된 Storyboard 제어</span><span class="sxs-lookup"><span data-stu-id="4eb21-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)  
 [<span data-ttu-id="4eb21-120">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="4eb21-120">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="4eb21-121">Storyboard 개요</span><span class="sxs-lookup"><span data-stu-id="4eb21-121">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
