---
title: "방법: 단색으로 도형 채우기"
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
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f016404feeac47c5f77527b8baa68d70742d4763
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a>방법: 단색으로 도형 채우기
만들기를 단색으로 도형 채우기는 <xref:System.Drawing.SolidBrush> 개체를 다음 전달할 <xref:System.Drawing.SolidBrush> 개체의 채우기 메서드 중 하나에 대 한 인수로 <xref:System.Drawing.Graphics> 클래스입니다. 다음 예제에서는 빨간색으로 타원을 채우는 방법을 보여 줍니다.  
  
## <a name="example"></a>예  
 다음 코드에서는 <xref:System.Drawing.SolidBrush.%23ctor%2A> 생성자는 <xref:System.Drawing.Color> 인수로 개체입니다. 사용 되는 값은 <xref:System.Drawing.Color.FromArgb%2A> 메서드 색의 알파, 빨간색, 녹색 및 파랑 구성 요소를 나타냅니다. 이러한 값을 각각 0-255 사이에 있어야 합니다. 첫 번째 255 나타내며 색은 완전히 불투명 한 두 번째 255 빨강 구성 요소의 농도가 임을 나타냅니다. 두 개의 0 있는지 녹색 및 파랑 구성 요소 둘 다가 0의 강도 나타냅니다.  
  
 4 개의 숫자 (0, 0, 100, 60)에 전달 되는 <xref:System.Drawing.Graphics.FillEllipse%2A> 메서드는 타원에 대 한 경계 사각형의 크기와 위치를 지정 합니다. 사각형의 왼쪽 위 모퉁이 (0, 0), 100, 너비 및 높이 60입니다.  
  
 [!code-csharp[System.Drawing.UsingABrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [브러시를 사용하여 도형 채우기](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
