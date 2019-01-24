---
title: '방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: eb9de4098c5fb9bde74fa93dda6dd5a878ed0339
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54697532"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기
이 예제에서는입니다 개체에 애니메이션을 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Page.Background%2A> 의 속성을 <xref:System.Windows.Controls.Page> 키 프레임을 사용 하 여 컨트롤을 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 색에 애니메이션 효과를 클래스에 대 한 변경 합니다 <xref:System.Windows.Controls.Page.Background%2A> 의 속성을 <xref:System.Windows.Controls.Page> 컨트롤. 예제에서는 애니메이션 배경 브러시를 정기적으로 변경합니다. 이 애니메이션 사용을 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 세 가지 다른 키 프레임을 만들 클래스입니다. 애니메이션 키 프레임을 사용 하 여 다음과 같은 방법으로:  
  
1.  첫 번째 두 번째 끝의 인스턴스를 애니메이션 합니다 <xref:System.Windows.Media.LinearGradientBrush> 클래스입니다. 예제의이 섹션에서는 색 노랑에서 빨강 주황색 전환 되도록 배경색으로 선형 그라데이션을 적용 됩니다.  
  
2.  끝에 다음 두 번째 애니메이션의 인스턴스는 <xref:System.Windows.Media.RadialGradientBrush> 클래스입니다. 예제의이 섹션에서는 색을 검정으로 파란색 흰색에서 전환 되도록 배경색에 방사형 그라데이션을 적용 됩니다.  
  
3.  세 번째 두 번째 끝의 인스턴스를 애니메이션 합니다 <xref:System.Windows.Media.DrawingBrush> 클래스입니다. 예제의이 섹션에는 백그라운드에 체크 무늬 패턴을 적용 됩니다.  
  
4.  애니메이션이 다시 시작 되 고 무기한 반복 됩니다.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 사용 하 여 사용할 수 있는 키 프레임의 유일한 형식인는 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 클래스입니다. 같은 키 프레임 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 즉 값에서 급격 한 변화를 만들고,이 예제에서 색 변경 갑자기 합니다.  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [키 프레임 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
