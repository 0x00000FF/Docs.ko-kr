---
title: '방법: 설치 된 글꼴 열거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 0124d2bdd8b9c60dc2bf2508348044d76a2c7eb4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602236"
---
# <a name="how-to-enumerate-installed-fonts"></a>방법: 설치 된 글꼴 열거
합니다 <xref:System.Drawing.Text.InstalledFontCollection> 클래스에서 상속 된 <xref:System.Drawing.Text.FontCollection> 추상 기본 클래스입니다. 사용할 수는 <xref:System.Drawing.Text.InstalledFontCollection> 컴퓨터에 설치 된 글꼴을 열거 하는 개체입니다. 합니다 <xref:System.Drawing.Text.FontCollection.Families%2A> 의 속성을 <xref:System.Drawing.Text.InstalledFontCollection> 개체의 배열이 <xref:System.Drawing.FontFamily> 개체입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 컴퓨터에 설치 하는 모든 글꼴 패밀리 이름을 나열 합니다. 코드를 검색 합니다 <xref:System.Drawing.FontFamily.Name%2A> 의 각 속성 <xref:System.Drawing.FontFamily> 반환한 배열의 개체에에서는 <xref:System.Drawing.Text.FontCollection.Families%2A> 속성. 제품군 이름 검색은 쉼표로 구분 된 형식 목록에 연결 합니다. 그런 다음 <xref:System.Drawing.Graphics.DrawString%2A> 메서드는 <xref:System.Drawing.Graphics> 클래스 쉼표로 구분 된 목록 사각형을 그립니다.  
  
 예제 코드를 실행 하는 경우 다음 그림에 나와 있는 것과 비슷한 출력이 됩니다.  
  
 ![설치 된 글꼴](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다. 또한 가져와야는 <xref:System.Drawing.Text> 네임 스페이스입니다.  
  
## <a name="see-also"></a>참고자료
- [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
