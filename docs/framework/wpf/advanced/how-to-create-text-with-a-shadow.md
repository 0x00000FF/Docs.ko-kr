---
title: '방법: 그림자가 적용된 텍스트 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: a2225e297dbc0b5f9d49799cb34eb5539746e62e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776850"
---
# <a name="how-to-create-text-with-a-shadow"></a>방법: 그림자가 적용된 텍스트 만들기
이 단원의 예제에서는 표시된 텍스트에 대해 그림자 효과를 만드는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 합니다 <xref:System.Windows.Media.Effects.DropShadowEffect> 개체를 사용 하면 다양 한 그림자 효과 만들 수 있습니다 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 개체입니다. 다음 예제에서는 그림자 효과가 적용된 텍스트를 보여 줍니다. 이 경우 그림자는 그림자 색깔이 흐린, 부드러운 그림자입니다.  
  
 ![Softness 인 텍스트 그림자 &#61; 0.25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg) 
  
 설정 하 여 그림자의 너비를 제어할 수 있습니다는 <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> 속성입니다. 값 `4.0` 은 그림자 너비가 4 픽셀임을 나타냅니다. 정도 제어할 수 있습니다. 수정 하 여 그림자의 부드러움 이나 흐림은 <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> 속성입니다. 값 `0.0` 흐리지 않음을 나타냅니다. 다음 코드 예제에서는 부드러운 그림자를 만드는 방법을 보여 줍니다.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  이러한 그림자 효과 통해 이동 하지 마십시오는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 텍스트 렌더링 파이프라인. 따라서 이러한 효과를 사용할 때 ClearType이 사용하지 않도록 설정됩니다.  
  
 다음 예제에서는 진한 그림자 효과가 적용된 텍스트를 보여 줍니다. 이 경우 그림자가 흐려지지 않습니다.  
  
 ![Softness 인 텍스트 그림자 &#61; 0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg) 
  
 설정 하 여 진한 그림자를 만들 수 있습니다는 <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> 속성을 `0.0`에 없는 흐리게 사용 됨을 나타냅니다. 수정 하 여 그림자의 방향을 제어할 수 있습니다는 <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> 속성입니다. 이 속성의 방향 값도 값으로 설정 간의 `0` 고 `360`입니다. 다음 그림의 방향 값을 보여 줍니다.는 <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> 속성을 설정 합니다.  
  
 ![그림자의 DropShadow 정도 설정](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 다음 코드 예제에서는 진한 그림자를 만드는 방법을 보여 줍니다.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>흐림 효과 사용  
 <xref:System.Windows.Media.Effects.BlurBitmapEffect> 텍스트 개체 뒤에 배치할 수 있는 그림자 같은 효과 만드는 데 사용할 수 있습니다. 텍스트에 적용된 흐림 비트맵 효과는 모든 방향에서 균등하게 텍스트를 흐리게 만듭니다.  
  
 다음 예제에서는 흐림 효과가 적용된 텍스트를 보여 줍니다.  
  
 ![BlurBitmapEffect를 사용한 텍스트 그림자](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 다음 코드 예제에는 흐린 효과를 만드는 방법을 보여 줍니다.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>좌표 이동 변환 사용  
 <xref:System.Windows.Media.TranslateTransform> 텍스트 개체 뒤에 배치할 수 있는 그림자 같은 효과 만드는 데 사용할 수 있습니다.  
  
 다음 코드 예제에서는 한 <xref:System.Windows.Media.TranslateTransform> 텍스트를 오프셋 합니다. 이 예제에서 기본 텍스트 아래에 있는 약간 오프셋된 텍스트 복사본이 그림자 효과를 만듭니다.  
  
 ![TranslateTransform을 사용한 텍스트 그림자](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)    
  
 다음 코드 예제에서는 그림자 효과에 변환을 만드는 방법을 보여 줍니다.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
