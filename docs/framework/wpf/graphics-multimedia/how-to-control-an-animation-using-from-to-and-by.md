---
title: '방법: From, To 및 By를 사용하여 애니메이션 제어'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
ms.openlocfilehash: e422c008ae3051ecd69b3278eb05fc0e2d1b1a0b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2018
ms.locfileid: "43480798"
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>방법: From, To 및 By를 사용하여 애니메이션 제어
"From/To/By" 또는 "기본 애니메이션"은 두 대상 값 사이 전환을 만듭니다 (참조 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) 다양 한 유형의 애니메이션 소개). 기본 애니메이션의 대상 값을 설정 하려면 해당 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>하십시오 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성입니다.  다음 표에서 요약 하는 방법을 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 함께 사용할 수 있습니다. 또는 개별적으로 애니메이션의 대상 값을 확인 하 합니다.  
  
|지정된 속성|결과 동작|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|지정 된 값은 애니메이션이 적용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 애니메이션 효과 줄 속성의 기준 값 또는 이전 애니메이션 속성의 이전 애니메이션이 구성 된 방식에 따라 값을 출력 합니다.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|지정 된 값은 애니메이션이 적용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 지정 된 값을는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|지정 된 값은 애니메이션이 적용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성의 합으로 지정 된 값을는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|속성의 기준 값에서 진행 되는 애니메이션 또는 이전 애니메이션의 값에 지정 된 값을 출력 합니다 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성입니다.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|애니메이션이 적용 되는 속성의 기준 값 이나 이전 애니메이션의 출력 값을 해당 값 및 지정 된 값의 합계는 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성입니다.|  
  
> [!NOTE]
>  둘 다 설정 하지 않으면 합니다 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 같은 애니메이션에서 속성입니다.  
  
 다른 보간 방법을 사용하거나 둘 이상의 대상 값 사이에 애니메이션 효과를 주려면 키 프레임 애니메이션을 사용합니다. 참조 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) 자세한 내용은 합니다.  
  
 단일 속성에 여러 애니메이션을 적용 하는 방법에 대 한 내용은 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)합니다.  
  
 아래 예제에서는 설정의 다른 결과 보여 줍니다 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, 및 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 애니메이션의 속성입니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [From, To 및 By 애니메이션 대상 값 샘플](https://go.microsoft.com/fwlink/?LinkID=159988)
