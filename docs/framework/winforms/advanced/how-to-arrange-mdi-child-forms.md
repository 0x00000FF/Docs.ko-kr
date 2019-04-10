---
title: '방법: MDI 자식 양식 정렬'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms [Windows Forms], arranging
- MDI [Windows Forms], arranging child forms
ms.assetid: a0786378-3206-4ccc-898e-7d3b38cc5089
ms.openlocfilehash: c7a9d03ef60586e1162f088d662dfe44bbdcb591
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317235"
---
# <a name="how-to-arrange-mdi-child-forms"></a>방법: MDI 자식 양식 정렬
응용 프로그램에는 바둑판식 배열, 계단식 배열, 정렬 등 열려 있는 MDI 자식 폼의 레이아웃을 제어하는 작업을 위한 메뉴 명령이 있는 경우가 많습니다. <xref:System.Windows.Forms.Form.LayoutMdi%2A> 메서드를 <xref:System.Windows.Forms.MdiLayout> 열거형 값 중 하나와 함께 사용하여 MDI 부모 폼에서 자식 폼을 다시 정렬할 수 있습니다.  
  
 <xref:System.Windows.Forms.MdiLayout> 열거형 값은 자식 폼을 계단식으로, 가로/세로 바둑판식으로 또는 MDI 폼 아래쪽에 정렬된 자식 폼 아이콘으로 표시합니다. 이러한 값과 같은 효과가 Windows 명령과 **계단식 창 배열**, **windows 나란히 표시**를 **창 가로 정렬 보기**, 및 **바탕 화면을 표시** , 각각.  
  
 이러한 메서드는 메뉴 항목의 <xref:System.Windows.Forms.Control.Click> 이벤트에 의해 호출되는 이벤트 처리기로 사용되는 경우가 많습니다. 이러한 방식을 통해 "계단식 창 배열" 텍스트가 포함된 메뉴 항목이 MDI 자식 창에서 적절하게 표시될 수 있습니다.  
  
### <a name="to-arrange-child-forms"></a>자식 폼을 정렬하려면  
  
1. 메서드에서 <xref:System.Windows.Forms.Form.LayoutMdi%2A> 메서드를 사용하여 MDI 부모 폼의 <xref:System.Windows.Forms.MdiLayout> 열거형을 설정합니다. 다음 예제에서는 MDI 부모 폼(<xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType>)의 자식 창에 대해 `Form1` 열거형 값을 사용합니다. 열거형에 대 한 이벤트 처리기에서 코드에 사용 되는 <xref:System.Windows.Forms.Control.Click> 의 이벤트를 **Cascade Windows** 메뉴 항목입니다.  
  
    ```vb  
    Protected Sub CascadeWindows_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)  
       Me.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade)  
    End Sub  
    ```  
  
    ```csharp  
    protected void CascadeWindows_Click(object sender, System.EventArgs e){  
       this.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade);  
    }  
    ```  
  
    > [!NOTE]
    >  사용되는 <xref:System.Windows.Forms.MdiLayout> 열거형 값을 변경하여 창을 바둑판식으로 배열하고 아이콘으로 정렬할 수도 있습니다.  
  
2. Visual C#을 사용하는 경우 폼 생성자에 다음 코드를 추가하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
## <a name="see-also"></a>참고자료

- [MDI 애플리케이션](multiple-document-interface-mdi-applications.md)
- [방법: MDI 부모 양식 만들기](how-to-create-mdi-parent-forms.md)
- [방법: MDI 자식 양식 만들기](how-to-create-mdi-child-forms.md)
- [방법: 활성 MDI 자식 확인](how-to-determine-the-active-mdi-child.md)
- [방법: 활성 MDI 자식으로 데이터 보내기](how-to-send-data-to-the-active-mdi-child.md)
