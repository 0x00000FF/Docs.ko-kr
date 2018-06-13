---
title: '방법: 해당 Timeline의 속도를 변경하지 않고 시계의 속도 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
ms.openlocfilehash: 126d260fbd59c1c35d8f56be6aa7dabe7688fa32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556616"
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a><span data-ttu-id="dd2a3-102">방법: 해당 Timeline의 속도를 변경하지 않고 시계의 속도 변경</span><span class="sxs-lookup"><span data-stu-id="dd2a3-102">How to: Change the Speed of a Clock Without Changing the Speed of Its Timeline</span></span>
<span data-ttu-id="dd2a3-103">A <xref:System.Windows.Media.Animation.ClockController> 개체의 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 속성의 속도 변경 하면는 <xref:System.Windows.Media.Animation.Clock> 변경 하지 않고는 <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> 클록의의 <xref:System.Windows.Media.Animation.Timeline>합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2a3-103">A <xref:System.Windows.Media.Animation.ClockController> object's <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> property enables you to change the speed of a <xref:System.Windows.Media.Animation.Clock> without altering the <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> of the clock's <xref:System.Windows.Media.Animation.Timeline>.</span></span> <span data-ttu-id="dd2a3-104">다음 예제에서는 <xref:System.Windows.Media.Animation.ClockController> 대화형으로 수정 하는 데 사용 되는 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 클록의 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2a3-104">In the following example, a <xref:System.Windows.Media.Animation.ClockController> is used to interactively modify the <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> of a clock.</span></span> <span data-ttu-id="dd2a3-105"><xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> 이벤트와 클록의 <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> 속성은 클록의 현재 글로벌 속도 표시 하는 데 사용 됩니다 대화형 때마다 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd2a3-105">The <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> event and the clock's <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> property are used to display the clock's current global speed each time its interactive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> is changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd2a3-106">예제</span><span class="sxs-lookup"><span data-stu-id="dd2a3-106">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
