---
title: '방법: Windows Forms RichTextBox 컨트롤을 사용 하 여 파일을 저장 합니다.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- RTF files [Windows Forms], saving in RichTextBox control
- examples [Windows Forms], text boxes
- saving files [Windows Forms], RichTextBox control
- files [Windows Forms], saving with RichTextBox control
- RichTextBox control [Windows Forms], saving files
- .rtf files [Windows Forms], saving in RichTextBox control
- text files [Windows Forms], saving from RichTextBox control
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
ms.openlocfilehash: 739cc33df873ef2c8ec7a2f5eaf867abadb8da75
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539781"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a>방법: Windows Forms RichTextBox 컨트롤을 사용 하 여 파일을 저장 합니다.
Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤 몇 가지 형식 중 하나에 표시 될 정보를 작성할 수 있습니다.  
  
-   일반 텍스트  
  
-   유니코드 일반 텍스트  
  
-   서식 있는 텍스트 (Rtf)  
  
-   OLE 개체 대신 공백 사용 하 여 RTF  
  
-   OLE 개체의 텍스트 표현 사용 하 여 일반 텍스트  
  
 파일을 저장 하려면 호출을 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 메서드. 사용할 수도 있습니다는 **SaveFile** 스트림에 데이터를 저장 하는 방법입니다. 자세한 내용은 <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>을 참조하세요.  
  
### <a name="to-save-the-contents-of-the-control-to-a-file"></a>컨트롤의 내용을 파일에 저장 하려면  
  
1.  저장할 파일의 경로 확인 합니다.  
  
     실제 응용 프로그램에서 이렇게 하려면 일반적으로 사용 된 <xref:System.Windows.Forms.SaveFileDialog> 구성 요소입니다. 개요를 보려면 [SaveFileDialog 구성 요소 개요](../../../../docs/framework/winforms/controls/savefiledialog-component-overview-windows-forms.md)합니다.  
  
2.  호출을 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 메서드의 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 저장할 파일 및 필요에 따라 파일 형식을 지정 합니다. 파일 이름 유일한 인수로 사용 하 여 메서드를 호출 하면 파일이 RTF로 저장 됩니다. 다른 파일 형식을 지정하려면 <xref:System.Windows.Forms.RichTextBoxStreamType> 열거형의 값을 두 번째 인수로 사용하여 메서드를 호출합니다.  
  
     아래 예제에서는 서식 있는 텍스트 파일의 위치 설정 된 경로 **내 문서** 폴더입니다. 이 폴더는 Windows 운영 체제를 실행 하는 대부분의 컴퓨터에 포함 되도록 알 수 없으므로이 위치가 사용 됩니다. 안전 하 게 응용 프로그램을 실행 하려면 사용자는 최소한의 시스템 액세스 수준에서는이 위치를 선택 합니다. 아래 예제에서는 가정 된 폼을 <xref:System.Windows.Forms.RichTextBox> 이미 추가 된 컨트롤입니다.  
  
    ```vb  
    Public Sub SaveFile()  
       ' You should replace the bold file name in the   
       ' sample below with a file name of your own choosing.  
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Testdoc.rtf", _  
          RichTextBoxStreamType.RichNoOleObjs)  
    End Sub  
    ```  
  
    ```csharp  
    public void SaveFile()  
    {  
       // You should replace the bold file name in the   
       // sample below with a file name of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       richTextBox1.SaveFile(System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Testdoc.rtf",  
          RichTextBoxStreamType.RichNoOleObjs);  
    }  
    ```  
  
    ```cpp  
    public:  
       void SaveFile()  
       {  
          // You should replace the bold file name in the   
          // sample below with a file name of your own choosing.  
          richTextBox1->SaveFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);  
       }  
    ```  
  
    > [!IMPORTANT]
    >  이 예제에서는 파일이 아직 없는 경우 새 파일을 만듭니다. 응용 프로그램 파일을 만드는 경우, 해당 응용 프로그램 폴더에 대 한 만들기 액세스를 해야 합니다. 권한은 액세스 제어 목록을 사용하여 설정됩니다. 파일이 이미 있는 경우 응용 프로그램 권한인 쓰기 권한만 필요 합니다. 가능한 경우에 파일을 배포 하는 동안 만듭니다 및만 단일 파일에 대 한 읽기 액세스 권한을 부여 작성 하기 보다는 폴더에 대 한 액세스 더 안전 합니다. 또한 루트 폴더나 Program Files 폴더보다 사용자 폴더에 데이터를 쓰는 것이 더 안전합니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox 컨트롤](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)
- [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
