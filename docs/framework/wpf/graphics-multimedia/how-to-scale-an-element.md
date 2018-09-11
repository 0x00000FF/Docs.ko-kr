---
title: '방법: 요소 배율 조정'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 44c638b58d828e5beb0b9de5c7bb0b67c8e82d87
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2018
ms.locfileid: "44366022"
---
# <a name="how-to-scale-an-element"></a>방법: 요소 배율 조정
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.ScaleTransform> 요소 배율을 조정 합니다.  
  
 사용 된 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 및 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 요소의 크기를 조정 하 여 지정한 배율로 속성. 예를 들어, 한 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 원래 너비의 150%로 요소를 확장 하는 값이 1.5 합니다. <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 0.5의 50%가 요소의 높이 축소 합니다.  
  
 사용 된 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 및 <xref:System.Windows.Media.ScaleTransform.CenterY%2A> 크기 조정 작업의 중심 지점을 지정 하는 속성입니다. 기본적으로 <xref:System.Windows.Media.ScaleTransform> 의 중심은 사각형의 왼쪽 위 모퉁이에 해당 하는 점 (0, 0). 이 설정은 요소를 이동 하는 고 적용 하는 경우 더 크게 표시 되 게 적용을 <xref:System.Windows.Media.Transform>는 개체가 있는 좌표 공간을 변경 합니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Media.ScaleTransform> 50-에서-50의 크기를 두 배로 <xref:System.Windows.Shapes.Rectangle>합니다. 합니다 <xref:System.Windows.Media.ScaleTransform> 값이 0 (기본값)를 둘 다에 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 고 <xref:System.Windows.Media.ScaleTransform.CenterY%2A>합니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[transformsSample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 일반적으로 설정한 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 하 고 <xref:System.Windows.Media.ScaleTransform.CenterY%2A> 크기가 조정 되는 개체의 가운데에: (<xref:System.Windows.FrameworkElement.Width%2A>/2,  <xref:System.Windows.FrameworkElement.Height%2A> /2).  
  
 다음 예제에서는 다른 <xref:System.Windows.Shapes.Rectangle> 크기의 두 배로 증가 하는 단,이 <xref:System.Windows.Media.ScaleTransform> 값이 25 둘 다에 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 및 <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, 사각형의 중심에 해당 하는 합니다.  
  
 [!code-xaml[transformsSample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 다음 그림에서는 둘 사이의 차이 보여 줍니다. <xref:System.Windows.Media.ScaleTransform> 작업 합니다. 점선은 크기 조정 전의 사각형 크기 및 위치를 나타냅니다.  
  
 ![여러 중심점을 사용한 2x 배율 조정](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")  
ScaleX 및 ScaleY 값은 같지만 중심은 다른 두 개의 ScaleTransform 작업  
  
 전체 샘플을 보려면 [2차원 변환 샘플](https://go.microsoft.com/fwlink/?LinkID=158252)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
