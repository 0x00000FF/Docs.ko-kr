---
title: "방법: 선 조인"
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
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d12cc7b4b4c878ec812190fd56a1face64118ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-join-lines"></a>방법: 선 조인
선 조인은 두 줄 끝 부분이 만나거나 겹칠으로 구성 되는 일반 영역입니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]세 개의 선 조인 스타일 제공: 마이터, 빗면 및 반올림 합니다. 선 조인 스타일의 속성은는 <xref:System.Drawing.Pen> 클래스입니다. 선 조인 스타일을 지정 하는 경우는 <xref:System.Drawing.Pen> 개체에 연결 된 모든 행에는 음 스타일 적용 됨 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체 펜을 사용 하 여 그려집니다.  
  
 다음 그림에서는 빗면된 선 조인 예제 결과 보여 줍니다.  
  
 ![펜](../../../../docs/framework/winforms/advanced/media/pens5.gif "pens5")  
  
## <a name="example"></a>예  
 사용 하 여 선 조인 스타일을 지정할 수 있습니다는 <xref:System.Drawing.Pen.LineJoin%2A> 의 속성은 <xref:System.Drawing.Pen> 클래스입니다. 가로 줄 사이의 세로 선이 빗면된 선 조인을 보여 줍니다. 다음 코드에서는 값 <xref:System.Drawing.Drawing2D.LineJoin.Bevel> 에 할당 된 <xref:System.Drawing.Pen.LineJoin%2A> 속성의 구성원은는 <xref:System.Drawing.Drawing2D.LineJoin> 열거형입니다. 다른 멤버는 <xref:System.Drawing.Drawing2D.LineJoin> 열거 <xref:System.Drawing.Drawing2D.LineJoin.Miter> 및 <xref:System.Drawing.Drawing2D.LineJoin.Round>합니다.  
  
 [!code-csharp[System.Drawing.UsingAPen#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
