---
title: '방법: Windows Forms RichTextBox 컨트롤에 대 한 글꼴 특성 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- .rtf files [Windows Forms], formatting in RichTextBox control
- fonts [Windows Forms], changing attributes in RichTextBox control
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting font attributes
- text [Windows Forms]
- text boxes [Windows Forms], formatting text
- formatting [Windows Forms]
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
ms.openlocfilehash: 3793c33d378ee242656889434c7b29c415e9ec9a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496207"
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a>방법: Windows Forms RichTextBox 컨트롤에 대 한 글꼴 특성 설정
Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤에 표시 되는 텍스트 서식 지정에 대 한 다양 한 옵션이 있습니다. 가능 선택한 문자 굵게, 밑줄, 또는 기울임꼴를 사용 하 여 <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> 속성. 또한 이 속성을 사용하여 선택한 문자의 크기와 서체를 변경할 수도 있습니다. <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> 속성을 사용 하면 선택한 문자의 색을 변경할 수 있습니다.  
  
### <a name="to-change-the-appearance-of-characters"></a>문자의 모양을 변경하려면  
  
1.  설정 된 <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> 속성을 적절 한 글꼴로 합니다.  
  
     사용자가 응용 프로그램에서 글꼴 패밀리, 크기 및 서체를 설정할 수 있도록 일반적으로 사용 된 <xref:System.Windows.Forms.FontDialog> 구성 요소입니다. 개요는 [FontDialog 구성 요소 개요](../../../../docs/framework/winforms/controls/fontdialog-component-overview-windows-forms.md)를 참조하세요.  
  
2.  설정 된 <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> 속성을 적절 한 색을 합니다.  
  
     사용자가 응용 프로그램에서 색을 설정할 수 있도록 일반적으로 사용 된 <xref:System.Windows.Forms.ColorDialog> 구성 요소입니다. 개요는 [ColorDialog 구성 요소 개요](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)를 참조하세요.  
  
    ```vb  
    RichTextBox1.SelectionFont = New Font("Tahoma", 12, FontStyle.Bold)  
    RichTextBox1.SelectionColor = System.Drawing.Color.Red  
    ```  
  
    ```csharp  
    richTextBox1.SelectionFont = new Font("Tahoma", 12, FontStyle.Bold);  
    richTextBox1.SelectionColor = System.Drawing.Color.Red;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionFont =  
       gcnew System::Drawing::Font("Tahoma", 12, FontStyle::Bold);  
    richTextBox1->SelectionColor = System::Drawing::Color::Red;  
    ```  
  
    > [!NOTE]
    >  이러한 속성은 선택한 텍스트에만 적용되며, 선택한 텍스트가 없으면 삽입 지점의 현재 위치에서 입력한 텍스트에 적용됩니다. 프로그래밍 방식으로 텍스트를 선택 하는 내용은 <xref:System.Windows.Forms.TextBoxBase.Select%2A>합니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox 컨트롤](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)
- [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
