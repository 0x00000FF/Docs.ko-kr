---
title: '방법: 요소 또는 브러시의 불투명도에 애니메이션 효과 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
ms.openlocfilehash: 659b051fe63c113bf1a4488b1fab12bbee75b1e3
ms.sourcegitcommit: 882a2f56bf6afdcb40d468e4ae9371296822b68c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2018
ms.locfileid: "53451250"
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>방법: 요소 또는 브러시의 불투명도에 애니메이션 효과 적용
보기 내부 및 외부 페이드 프레임 워크 요소가 하도록 애니메이션을 적용할 수 해당 <xref:System.Windows.UIElement.Opacity%2A> 하거나 속성에 애니메이션 효과 주기 수를 <xref:System.Windows.Media.Brush.Opacity%2A> 의 속성을 <xref:System.Windows.Media.Brush> (또는 브러시) 칠할 하는 데 사용 합니다. 요소의 불투명도 애니메이션 적용를 사용 하면 및 자식 뷰 내부 및 외부로 페이드 있지만 더 선별적으로 시도해볼 요소의 부분 페이드 되도록 하면 요소를 그리는 데 사용 되는 브러시에 애니메이션을 적용 합니다. 예를 들어 단추의 배경을 그리는 데 사용 되는 브러시의 불투명도 애니메이션 수 있습니다. 이렇게 하면 해당 텍스트를 완전히 불투명 하 게 두고 뷰의 페이드 인 / 아웃 단추의 배경.  
  
> [!NOTE]
>  애니메이션 효과 적용 합니다 <xref:System.Windows.Media.Brush.Opacity%2A> 의 <xref:System.Windows.Media.Brush> 애니메이션 보다 성능상 이점이 <xref:System.Windows.UIElement.Opacity%2A> 요소의 속성입니다.  
  
 다음 예제에서는 두 개의 단추는 보기에서 페이드 있도록 애니메이션이 적용 됩니다. 첫 번째의 불투명도 <xref:System.Windows.Controls.Button> 에서 애니메이션 효과가 적용 됩니다 `1.0` 에 `0.0` 위에 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 5 초입니다. 두 번째 단추에도 애니메이션이 적용 되어 있지만 SolidColorBrush의 불투명도 그리는 데 해당 <xref:System.Windows.Controls.Control.Background%2A> 전체 단추의 투명도 대신 애니메이션 효과가 적용 됩니다. 예제를 실행 하는 경우 첫 번째 단추를 두 번째 단추의 배경에 보기 내부 및 외부 페이드 보기 내부 및 외부로 완전히 사라집니다. 해당 텍스트와 테두리 완전히 불투명 하 게 유지 됩니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 이 예제의 코드는 생략 되었습니다. 전체 샘플에는 또한의 불투명도 애니메이션을 적용 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Color> 내는 <xref:System.Windows.Media.LinearGradientBrush>합니다.  전체 샘플을 참조 하세요. 합니다 [설명 하는 요소 샘플의 불투명도 애니메이션 적용](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/OpacityAnimation)합니다.
