---
title: "방법: 애니메이션이 있는 미디어 재생"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44ebb89c25fc37292f82533c929aae44854db5c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-play-media-with-animations"></a>방법: 애니메이션이 있는 미디어 재생
사용 하 여 동시에 미디어 및 애니메이션을 재생 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.MediaTimeline> 및 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 클래스를 같은 <xref:System.Windows.Media.Animation.Storyboard>합니다.  
  
## <a name="example"></a>예  
 하나 이상 사용할 수 <xref:System.Windows.Media.MediaTimeline> 개체에 <xref:System.Windows.Media.Animation.Storyboard> 다른 함께 <xref:System.Windows.Media.Animation.Timeline> 애니메이션과 같은 개체입니다.  
  
 다음 예에서는 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> 속성의는 <xref:System.Windows.Media.Animation.Storyboard> 의 값에 `Slip`, 애니메이션, (이 예의 비디오) 미디어 진행 될 때까지 진행 되지 않는 지정 합니다. 이 기능은 로드 시간 때문에 미디어 재생을 지연해야 할 경우에 필요할 수 있습니다.  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [그래픽 및 멀티미디어](../../../../docs/framework/wpf/graphics-multimedia/index.md)
