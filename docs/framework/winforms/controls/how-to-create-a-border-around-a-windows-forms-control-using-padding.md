---
title: 안쪽 여백을 사용 하 여 컨트롤 주위에 테두리 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
ms.openlocfilehash: 114186ab5784cf892cb01e9fe2648ce22cecc4b7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742191"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>방법: 안쪽 여백을 사용하여 Windows Forms 컨트롤 주위에 테두리 만들기
다음 코드 예제에서는 <xref:System.Windows.Forms.RichTextBox> 컨트롤 주위에 테두리 또는 윤곽선을 만드는 방법을 보여 줍니다. 이 예제에서는 <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Padding> 속성 값을 5로 설정 하 고 자식 <xref:System.Windows.Forms.RichTextBox> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정 합니다. <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.RichTextBox> 컨트롤 주위에 파란색 테두리를 만드는 <xref:System.Drawing.Color.Blue%2A>로 설정 됩니다.  
  
## <a name="example"></a>예  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Padding>
- [Windows Forms 컨트롤의 여백 및 안쪽 여백](margin-and-padding-in-windows-forms-controls.md)
