---
title: "방법: Windows Forms에서 깜빡임을 줄이기 위한 픽셀 복사"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ed463b41d3c2a51b0f9be3d4ddabfd2d54a3c07
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>방법: Windows Forms에서 깜빡임을 줄이기 위한 픽셀 복사
간단한 그래픽, 애니메이션을 적용할 때 발생할 수 깜빡임을 또는 부적합 한 다른 시각 효과가 있습니다. 이 문제는 한 가지 방법은 그래픽에는 "bitblt" 프로세스를 사용 하는 것입니다. Bitblt는는 "비트 블록 전송을"는 색 데이터 픽셀의 원점 사각형에서 대상 사각형을 픽셀입니다.  
  
 Windows forms에서 bitblt 사용 하 여 수행 되는 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스입니다. 메서드의 매개 변수는 원본 및 대상 (점), 복사할 영역의 크기에 새 셰이프를 그리는 데 사용 되는 그래픽 개체를 지정 합니다.  
  
 아래 예제에서는 도형 폼에서 그려지는 해당 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다. 그런 다음 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 셰이프를 복제 하는 메서드를 사용 합니다.  
  
> [!NOTE]
>  폼의 설정 <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 속성을 `true` 그래픽 기반 코드의 하면는 <xref:System.Windows.Forms.Control.Paint> 이중 버퍼링 된 이벤트 수입니다. 아래 코드를 사용 하는 경우 모든 큰 성능 향상 수 있게 됩니다, 하는 동안 설정 하는 것 보다 복잡 한 그래픽 조작이 코드로 작업할 때 염두에서에 둬야 합니다.  
  
## <a name="example"></a>예제  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 위의 코드를 폼의 실행 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기는 폼을 다시 그리면 그래픽 유지 되도록 합니다. 따라서 그래픽 관련 메서드를 호출 하지 않습니다는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기 그려진된 내용은 활성 및 비활성 폼 크기를 조정 하거나 다른 형식으로 가려진 경우 때문에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.CopyPixelOperation>  
 <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
