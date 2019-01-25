---
title: '방법: 텍스트에 애니메이션 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: 56336c45639168c6432b92fe555c6d37448cb7cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720511"
---
# <a name="how-to-apply-animations-to-text"></a>방법: 텍스트에 애니메이션 적용
애니메이션은 애플리케이션의 텍스트 모양과 표시를 변경할 수 있습니다. 다음 예제에서는 다양 한 유형의 애니메이션을 사용 하 여 텍스트의 표시에 영향을 줄을 <xref:System.Windows.Controls.TextBlock> 제어 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 <xref:System.Windows.Media.Animation.DoubleAnimation> 텍스트 블록의 너비를 애니메이션 효과를 합니다. 10초 동안 너비 값을 텍스트 블록의 너비에서 0으로 변경한 후 다시 너비 값을 반대로 변경하여 계속합니다. 이러한 형식의 애니메이션은 지우기 효과를 생성합니다.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 다음 예제에서는 한 <xref:System.Windows.Media.Animation.DoubleAnimation> 텍스트 블록의 불투명도 애니메이션 효과를 합니다. 5초 동안 불투명도 값을 1.0에서 0으로 변경한 다음 불투명 값을 반대로 변경하고 계속합니다.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 다음 다이어그램은 결과 보여 줍니다.는 <xref:System.Windows.Controls.TextBlock> 불투명도를 변경 하는 컨트롤 `1.00` 하 `0.00` 정의한 5 초 간격 동안는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>합니다.  
  
 ![1.00에서 0.00으로 불투명도 변경 하는 텍스트](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")  
1.00에서 0.00으로 변경하는 텍스트 불투명도  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.ColorAnimation> 에 텍스트 블록의 전경색을 애니메이션 합니다. 전경색 값을 5초 동안 한 색상에서 두 번째 색상으로 변경한 다음 색상 값을 반대로 변경하고 계속합니다.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 다음 예제에서는 한 <xref:System.Windows.Media.Animation.DoubleAnimation> 텍스트 블록을 회전 합니다. 텍스트 블록은 20초 동안 전체 회전을 수행한 다음 회전을 계속 반복합니다.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a>참고자료
- [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
