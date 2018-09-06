---
title: '방법: Polygon 요소를 사용하여 닫힌 도형 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 89c78877e196e803f6b4139ffcfa2b4def1a07d7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43873038"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a>방법: Polygon 요소를 사용하여 닫힌 도형 그리기
이 예제에서는 사용 하 여 닫힌된 도형 그리기를 <xref:System.Windows.Shapes.Polygon> 요소입니다. 닫힌된 도형 그리기, 만들려면를 <xref:System.Windows.Shapes.Polygon> 요소 및 사용 하 여 해당 <xref:System.Windows.Shapes.Polygon.Points%2A> 도형의 꼭지점을 지정 하는 속성입니다. 줄의 첫 번째 및 마지막 지점을 연결 하는 그려집니다 자동으로. 마지막으로, 지정 된 <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>, 또는 둘 다.  
  
## <a name="example"></a>예제  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 지점에 대 한 구문이 공백으로 구분 된 목록 쉼표로 구분 된 x 및 y 좌표 쌍입니다.  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 이 예제에서는 사용 되지만 <xref:System.Windows.Controls.Canvas> 다각형을 포함 하려면 사용할 수 있습니다 다각형 요소 (및 다른 모든 도형 요소)와 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control> 텍스트가 아닌 콘텐츠를 지 원하는 합니다.  
  
 이 예제는 더 큰 샘플;의 일부 전체 샘플을 참조 하세요 [도형 요소 샘플](https://go.microsoft.com/fwlink/?LinkID=160037)합니다.
