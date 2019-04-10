---
title: '방법: 텍스트에 변환 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: 46a57364e0c18cc4c9fe7884642cd0b718c20f31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208672"
---
# <a name="how-to-apply-transforms-to-text"></a>방법: 텍스트에 변환 적용
변환을 통해 애플리케이션에서 텍스트 표시를 변경할 수 있습니다. 다음 예제에서 텍스트 표시에 영향을 줄 다른 형식의 렌더링 변환 사용을 <xref:System.Windows.Controls.TextBlock> 제어 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 2차원 x-y 평면에서 지정된 점을 기준으로 회전하는 텍스트를 보여줍니다.  
  
 ![RotateTransform을 사용하여 회전된 텍스트](./media/how-to-apply-transforms-to-text/text-rotated-ninety-degrees.jpg)  
  
 다음 코드 예제에서는 한 <xref:System.Windows.Media.RotateTransform> 텍스트를 회전 합니다. <xref:System.Windows.Media.RotateTransform.Angle%2A> 값이 90 요소를 시계 방향으로 90도 회전 합니다.  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 다음 예에서는 텍스트의 두 번째 라인은 x축을 따라 배율을 150% 조정하여 보여주고, 텍스트의 세 번째 라인은 y축을 따라 배율을 150% 조정하여 보여줍니다.  
  
 ![ScaleTransform을 사용하여 배율 조정된 텍스트](./media/how-to-apply-transforms-to-text/scaled-text-scaletransform.jpg) 
  
 다음 코드 예제에서는 <xref:System.Windows.Media.ScaleTransform> 를 원래 크기의 텍스트를 확장 합니다.  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  텍스트의 배율 조정은 텍스트의 글꼴 크기를 늘리는 것과는 다릅니다. 여러 다른 크기에서 최상의 해상도를 제공하기 위해 글꼴 크기는 서로 독립적으로 계산됩니다. 한편 배율 조정된 크기는 원래 크기의 텍스트에 계속 비례합니다.  
  
 다음 예에서는 x축을 따라 기울어진 텍스트를 보여줍니다.  
  
 ![SkewTransform을 사용하여 기울인 텍스트](./media/how-to-apply-transforms-to-text/skewed-transformed-text.jpg)
   
 다음 코드 예제에서는 한 <xref:System.Windows.Media.SkewTransform> 텍스트입니다. 전단이라고도 하는 기울이기는 일관되지 않은 방식으로 좌표 공간을 늘리는 변환입니다. 이 예에서 두 텍스트 문자열은 x축을 따라 -30°와 30°를 기울입니다.  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 다음 예에서는 x축과 y축을 따라 변환 또는 이동되는 텍스트를 보여줍니다.  
  
 ![TranslateTransform을 사용한 텍스트 오프셋](./media/how-to-apply-transforms-to-text/transformed-text-x-y-axis.jpg)
  
 다음 코드 예제에서는 한 <xref:System.Windows.Media.TranslateTransform> 텍스트를 오프셋 합니다. 이 예제에서 기본 텍스트 아래에 있는 약간 오프셋된 텍스트 복사본이 그림자 효과를 만듭니다.  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> 그림자 효과 제공 하기 위한 다양 한 기능을 제공 합니다. 자세한 내용은 [그림자가 적용 된 텍스트 만들기](how-to-create-text-with-a-shadow.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [텍스트에 애니메이션 적용](how-to-apply-animations-to-text.md)
