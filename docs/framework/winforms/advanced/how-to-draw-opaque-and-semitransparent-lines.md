---
title: '방법: 불투명 및 반투명 선 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- transparency [Windows Forms], lines
- lines [Windows Forms], drawing alpha blended
- alpha blending [Windows Forms], drawing lines
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
ms.openlocfilehash: 44047b5a35c2ca87f3136d082331d2f31a1abbec
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721153"
---
# <a name="how-to-draw-opaque-and-semitransparent-lines"></a>방법: 불투명 및 반투명 선 그리기
선을 그리는 경우 <xref:System.Drawing.Pen> 개체를 <xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드에 전달해야 합니다. <xref:System.Drawing.Pen.%23ctor%2A> 생성자의 매개 변수 중 하나는 <xref:System.Drawing.Color> 개체입니다. 불투명 선을 그리려면 색의 알파 구성 요소를 255로 설정합니다. 반투명 선을 그리려면 알파 구성 요소를 1에서 254 사이의 임의 값으로 설정합니다.  
  
 배경 위에 반투명 선을 그리면 선 색이 배경색과 혼합됩니다. 알파 구성 요소는 선 색과 배경색을 혼합하는 방법을 지정합니다. 알파 값이 0에 가까우면 배경색에 더 많은 가중치가 적용되고 알파 값이 255에 가까우면 선 색에 더 많은 가중치가 적용됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 비트맵을 그린 다음 이 비트맵을 배경으로 사용하는 세 개의 선을 그립니다. 첫 번째 선은 알파 구성 요소 255를 사용하므로 불투명합니다. 두 번째 및 세 번째 선은 알파 구성 요소 128을 사용하므로 반투명합니다. 선을 통과하는 배경 이미지를 볼 수 있습니다. <xref:System.Drawing.Graphics.CompositingQuality%2A> 속성을 설정하는 문은 감마 보정과 함께 세 번째 선에 대한 혼합이 수행되도록 합니다.  
  
 다음 그림에서는 다음 코드의 출력을 보여 줍니다.  
  
 ![불투명 및 반투명](./media/compqualline.png "compqualline")  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.  
  
## <a name="see-also"></a>참고자료
- [선 및 채우기 알파 혼합](alpha-blending-lines-and-fills.md)
- [방법: 컨트롤에 투명 한 배경을 제공합니다](../controls/how-to-give-your-control-a-transparent-background.md)
- [방법: 불투명 및 반투명 브러시를 사용 하 여 그리기](how-to-draw-with-opaque-and-semitransparent-brushes.md)
