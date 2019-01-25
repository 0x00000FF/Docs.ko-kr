---
title: '방법: MatrixTransform을 사용하여 사용자 지정 변환 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 3b5a6fbedd30c859dffadad00c8faab74fc0773b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628801"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a>방법: MatrixTransform을 사용하여 사용자 지정 변환 만들기
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.MatrixTransform> 변환 (이동) 하는 위치 늘이기, 및의 기울이기는 <xref:System.Windows.Controls.Button>합니다.  
  
> [!NOTE]
>  사용 합니다 <xref:System.Windows.Media.MatrixTransform> 클래스에서 제공 하지 않는 사용자 지정 변환을 만들 수는 <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, 또는 <xref:System.Windows.Media.TranslateTransform> 클래스입니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[Transforms_snip#MatrixTransform](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
- [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
- [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
