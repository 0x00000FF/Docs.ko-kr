---
title: '방법: 단일 B 그리기&#233;zier 스플라인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: 9e91b63275c37fc0cdde5721fddd114e1bf2264e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521338"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a>방법: 단일 B 그리기&#233;zier 스플라인
베 지 어 스플라인을 4 개의 점으로 정의:, 두 개의 제어점 시작점과 끝점입니다.  
  
## <a name="example"></a>예제  
 다음 예제에는 (10, 100) 시작점 및 끝점 (200, 100)으로 베 지 어 스플라인을 그립니다. 컨트롤은 (100, 10) 및 (150, 150)을 가리킵니다.  
  
 다음 그림에서는 결과 베 지 어 스플라인을 시작점, 제어점, 끝점 함께 보여 줍니다. 그림에는 직선으로 4 개의 점을 연결 하 여 다각형 스플라인의 네 점을 보여 줍니다.  
  
 ![베 지 어 스플라인을](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [GDI+의 3차원 곡선 스플라인](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [방법: 일련의 3차원 곡선 스플라인 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
