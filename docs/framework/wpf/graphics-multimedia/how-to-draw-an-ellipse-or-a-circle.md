---
title: '방법: 타원 또는 원 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: ddeada8619d1b6c8970f1efb7cca1bc98773d0c5
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2018
ms.locfileid: "45641432"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>방법: 타원 또는 원 그리기
사용 하 여 타원과 원을 그리는 방법을 보여 주는이 예제는 <xref:System.Windows.Shapes.Ellipse> 요소입니다. 타원을 그릴 만들기는 <xref:System.Windows.Shapes.Ellipse> 요소를 지정 하 고 해당 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A>합니다. 사용 하 여 해당 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성을 지정 합니다 <xref:System.Windows.Media.Brush> 타원의 내부를 그리는 데 사용 되는 합니다. 사용 하 여 해당 <xref:System.Windows.Shapes.Shape.Stroke%2A> 속성을 지정 합니다 <xref:System.Windows.Media.Brush> 타원 윤곽선을 그리는 데 사용 되는 합니다. <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성 타원 윤곽선의 두께 지정 합니다.  
  
 원을 그리려면 합니다 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 의 <xref:System.Windows.Shapes.Ellipse> 서로 다른 요소입니다.  
  
 다음 예제에서는 네 개의 <xref:System.Windows.Shapes.Ellipse> 내에서 요소를 <xref:System.Windows.Controls.Canvas>입니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 이 예제에서는 한 <xref:System.Windows.Controls.Canvas> 줄임표 들어 사용할 수 있습니다 ellipse 요소 (및 다른 모든 도형 요소)와 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control> 텍스트가 아닌 콘텐츠를 지 원하는 합니다.  
  
 이 예제는 더 큰 샘플;의 일부 전체 샘플을 참조 하세요 [도형 요소 샘플](https://go.microsoft.com/fwlink/?LinkID=160037)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Shapes.Ellipse>  
 <xref:System.Windows.Shapes.Shape>  
 [도형 요소 샘플](https://go.microsoft.com/fwlink/?LinkID=160037)
