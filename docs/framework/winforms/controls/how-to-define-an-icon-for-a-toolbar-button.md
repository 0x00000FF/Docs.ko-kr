---
title: '방법: 도구 모음 단추에 대한 아이콘 정의'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- buttons [Windows Forms], icons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: 84db98b4-8566-49ce-b2c8-1fd66a5eb3a0
ms.openlocfilehash: 2c1c3d8529662c1e1f1a3d28e3853d31f5d940ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054278"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a>방법: 도구 모음 단추에 대한 아이콘 정의
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 <xref:System.Windows.Forms.ToolBar> 단추는 사용자가 쉽게 식별할 수 있도록 내에 아이콘을 표시할 수 있습니다. 추가 이미지를 통해 얻을 수는 [ImageList 구성 요소](imagelist-component-windows-forms.md) 구성 요소와 연결 하는 방법의 <xref:System.Windows.Forms.ImageList> 구성 요소는 <xref:System.Windows.Forms.ToolBar> 컨트롤입니다.  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a>도구 모음 단추의 아이콘을 프로그래밍 방식으로 설정 하려면  
  
1. 프로시저에서 인스턴스화하는 <xref:System.Windows.Forms.ImageList> 구성 요소 및 <xref:System.Windows.Forms.ToolBar> 제어 합니다.  
  
2. 동일한 프로시저를 할당 하려면 이미지를 <xref:System.Windows.Forms.ImageList> 구성 요소입니다.  
  
3. 동일한 프로시저를 할당 합니다 <xref:System.Windows.Forms.ImageList> 컨트롤을 <xref:System.Windows.Forms.ToolBar> 제어 하 고 할당을 <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> 개별 도구 모음 단추 속성.  
  
     다음 코드 예제에서는 이미지의 위치 설정 된 경로 **내 문서** 폴더입니다. 이렇게 하면 수 없으므로 Windows 운영 체제를 실행 하는 대부분의 컴퓨터는이 디렉터리를 포함 합니다. 또한 최소한의 시스템 액세스 수준을 가진 사용자가 안전하게 애플리케이션을 실행할 수 있습니다. 아래 예제에서는 가정 된 폼을 <xref:System.Windows.Forms.PictureBox> 이미 추가 된 컨트롤입니다.  
  
     위의 단계를 다음 아래 표시 된 것과 유사한 코드가 작성 합니다.  
  
    ```vb  
    Public Sub InitializeMyToolBar()  
    ' Instantiate an ImageList component and a ToolBar control.  
       Dim ToolBar1 as New ToolBar  
       Dim ImageList1 as New ImageList  
    ' Assign an image to the ImageList component.  
    ' You should replace the bold image  
    ' in the sample below with an icon of your own choosing.  
       Dim myImage As System.Drawing.Image = _   
          Image.FromFile Image.FromFile _  
          (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.Personal) _  
          & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    ' Create a ToolBarButton.  
       Dim ToolBarButton1 As New ToolBarButton()  
    ' Add the ToolBarButton to the ToolBar.  
       ToolBar1.Buttons.Add(toolBarButton1)  
    ' Assign an ImageList to the ToolBar.  
       ToolBar1.ImageList = ImageList1  
    ' Assign the ImageIndex property of the ToolBarButton.  
       ToolBarButton1.ImageIndex = 0  
    End Sub  
    ```  
  
    ```csharp  
    public void InitializeMyToolBar()  
    {  
       // Instantiate an ImageList component and a ToolBar control.  
       ToolBar toolBar1 = new  ToolBar();   
       ImageList imageList1 = new ImageList();  
       // Assign an image to the ImageList component.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       Image myImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
       // Create a ToolBarButton.  
       ToolBarButton toolBarButton1 = new ToolBarButton();  
       // Add the ToolBarButton to the ToolBar.  
       toolBar1.Buttons.Add(toolBarButton1);  
       // Assign an ImageList to the ToolBar.  
       toolBar1.ImageList = imageList1;  
       // Assign ImageIndex property of the ToolBarButton.  
       toolBarButton1.ImageIndex = 0;  
    }  
    ```  
  
    ```cpp  
    public:  
       void InitializeMyToolBar()  
       {  
          // Instantiate an ImageList component and a ToolBar control.  
          ToolBar ^ toolBar1 = gcnew  ToolBar();   
          ImageList ^ imageList1 = gcnew ImageList();  
          // Assign an image to the ImageList component.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          Image ^ myImage = Image::FromFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
          // Create a ToolBarButton.  
          ToolBarButton ^ toolBarButton1 = gcnew ToolBarButton();  
          // Add the ToolBarButton to the ToolBar.  
          toolBar1->Buttons->Add(toolBarButton1);  
          // Assign an ImageList to the ToolBar.  
          toolBar1->ImageList = imageList1;  
          // Assign ImageIndex property of the ToolBarButton.  
          toolBarButton1->ImageIndex = 0;  
       }  
    ```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ToolBar>
- [방법: Toolbar 단추의 메뉴 이벤트 트리거](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [ToolBar 컨트롤](toolbar-control-windows-forms.md)
- [ImageList 구성 요소](imagelist-component-windows-forms.md)
