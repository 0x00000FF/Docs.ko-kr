---
title: "방법: 애니메이션 가속 또는 감속"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c06518e3eada30bd4e22549a9ee3c8f16070f5ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="10c1d-102">방법: 애니메이션 가속 또는 감속</span><span class="sxs-lookup"><span data-stu-id="10c1d-102">How to: Accelerate or Decelerate an Animation</span></span>
<span data-ttu-id="10c1d-103">이 예제에는 애니메이션을 가속화 하 고 시간이 지남에 따라 감속 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="10c1d-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="10c1d-104">다음 예제에서는 여러 사각형은 애니메이션 효과 적용 하 여 서로 다른 사용 하 여 애니메이션 <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> 및 <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="10c1d-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10c1d-105">예</span><span class="sxs-lookup"><span data-stu-id="10c1d-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="10c1d-106">이 예제에서 코드는 생략 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="10c1d-106">Code has been omitted from this example.</span></span> <span data-ttu-id="10c1d-107">전체 코드에 대 한 참조는 [애니메이션 타이밍 동작 샘플](http://go.microsoft.com/fwlink/?LinkID=159970)합니다.</span><span class="sxs-lookup"><span data-stu-id="10c1d-107">For the complete code, see the [Animation Timing Behavior Sample](http://go.microsoft.com/fwlink/?LinkID=159970).</span></span>
