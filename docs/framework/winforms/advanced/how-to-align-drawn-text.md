---
title: "방법: 그린 텍스트 맞추기"
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
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6be28641073bf430b1dc51c428228d0fb114d4cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-align-drawn-text"></a>방법: 그린 텍스트 맞추기
사용자 지정 그리기를 수행 하는 경우 폼 이나 컨트롤에 그려지는 텍스트를 가운데에 하려는 경우가 많습니다. 으로 그린 텍스트를 쉽게 맞출 수 있습니다는 <xref:System.Drawing.Graphics.DrawString%2A> 또는 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 올바른 형식 지정 개체를 만들고 적절 한 형식 플래그를 설정 하 여 메서드.  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a>그릴 텍스트 GDI + (DrawString)를 가운데 맞춤  
  
1.  사용 하 여 한 <xref:System.Drawing.StringFormat> 는 적절 한 <xref:System.Drawing.Graphics.DrawString%2A> 가운데 맞춤 된 텍스트를 지정 하는 메서드.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a>그릴 GDI (DrawText)와 텍스트를 가운데 맞춤  
  
1.  사용 하 여는 <xref:System.Windows.Forms.TextFormatFlags> 래핑으로는 적절 한 텍스트를 가로 및 세로로 가운데 맞춤에 대 한 열거형 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 메서드.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 코드 예제에서는 Windows Forms에서 사용 하도록 설계 되었으며 필요한 <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: GDI를 사용하여 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [방법: 글꼴 패밀리 및 글꼴 만들기](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
