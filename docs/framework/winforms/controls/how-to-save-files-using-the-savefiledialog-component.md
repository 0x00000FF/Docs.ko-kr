---
title: '방법: SaveFileDialog 구성 요소를 사용하여 파일 저장'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- SaveFileDialog component [Windows Forms], saving files
- files [Windows Forms], saving
- OpenFile method [Windows Forms], saving files with SaveFileDialog component
ms.assetid: 02e8f409-b83f-4707-babb-e71f6b223d90
ms.openlocfilehash: 32de7f7e38195271e179d4fae3884b7a39f37c45
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868085"
---
# <a name="how-to-save-files-using-the-savefiledialog-component"></a>방법: SaveFileDialog 구성 요소를 사용하여 파일 저장

사용자는 <xref:System.Windows.Forms.SaveFileDialog> 구성 요소를 사용 하 여 파일 시스템을 찾아보고 저장할 파일을 선택할 수 있습니다. 대화 상자에서 사용자가 선택한 파일의 경로와 이름을 반환합니다. 그러나 실제로 디스크에 파일을 쓰는 코드를 작성해야 합니다.

### <a name="to-save-a-file-using-the-savefiledialog-component"></a>SaveFileDialog 구성 요소를 사용하여 파일을 저장하려면

- **파일 저장** 대화 상자를 표시하고 사용자가 선택한 파일을 저장하는 메서드를 호출합니다.

  <xref:System.Windows.Forms.SaveFileDialog> 구성 요소의 <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> 메서드를 사용 하 여 파일을 저장 합니다. 이 메서드는 작성할 수 있는 <xref:System.IO.Stream> 개체를 제공 합니다.

  아래 예제에서는 <xref:System.Windows.Forms.DialogResult> 속성을 사용 하 여 파일의 이름을 가져오고 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 메서드를 사용 하 여 파일을 저장 합니다. <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> 메서드는 파일을 쓸 스트림을 제공 합니다.

  아래 예제에서는 이미지가 할당 된 <xref:System.Windows.Forms.Button> 컨트롤이 있습니다. 단추를 클릭 하면 .gif, .jpeg 및 .bmp 형식의 파일을 허용 하는 필터를 사용 하 여 <xref:System.Windows.Forms.SaveFileDialog> 구성 요소가 인스턴스화됩니다. [파일 저장] 대화 상자에서 이 형식의 파일을 선택하면 단추의 이미지가 저장됩니다.

  > [!IMPORTANT]
  > <xref:System.Windows.Forms.FileDialog.FileName%2A> 속성을 가져오거나 설정 하려면 어셈블리에 <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> 클래스에서 부여한 권한 수준이 필요 합니다. 부분 신뢰 컨텍스트에서 실행하는 경우 프로세스가 권한 부족으로 인해 예외를 throw할 수 있습니다. 자세한 내용은 [코드 액세스 보안 기본 사항](../../misc/code-access-security-basics.md)을 참조하세요.

  이 예제에서는 폼에 <xref:System.Windows.Forms.ButtonBase.Image%2A> 속성이 .gif, .jpeg 또는 .bmp 형식의 파일로 설정 된 <xref:System.Windows.Forms.Button> 컨트롤이 있다고 가정 합니다.

  > [!NOTE]
  > 상속으로 인해 <xref:System.Windows.Forms.SaveFileDialog> 클래스의 일부인 <xref:System.Windows.Forms.FileDialog> 클래스의 <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> 속성은 1부터 기반으로 하는 인덱스를 사용 합니다. 데이터를 특정 형식으로 저장하는 코드를 작성하는 경우(예: 파일을 일반 텍스트와 이진 형식으로 저장하는 경우) 이러한 인덱스가 중요합니다. 아래 예제에서 이 속성에 대해 살펴볼 수 있습니다.

  ```vb
  Private Sub Button2_Click(ByVal sender As System.Object, _
  ByVal e As System.EventArgs) Handles Button2.Click
      ' Displays a SaveFileDialog so the user can save the Image
      ' assigned to Button2.
      Dim saveFileDialog1 As New SaveFileDialog()
      saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif"
      saveFileDialog1.Title = "Save an Image File"
      saveFileDialog1.ShowDialog()

      ' If the file name is not an empty string open it for saving.
      If saveFileDialog1.FileName <> "" Then
        ' Saves the Image via a FileStream created by the OpenFile method.
        Dim fs As System.IO.FileStream = Ctype _
            (saveFileDialog1.OpenFile(), System.IO.FileStream)
        ' Saves the Image in the appropriate ImageFormat based upon the
        ' file type selected in the dialog box.
        ' NOTE that the FilterIndex property is one-based.
        Select Case saveFileDialog1.FilterIndex
            Case 1
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Jpeg)

            Case 2
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Bmp)

            Case 3
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Gif)
          End Select

          fs.Close()
      End If
  End Sub
  ```

  ```csharp
  private void button2_Click(object sender, System.EventArgs e)
  {
      // Displays a SaveFileDialog so the user can save the Image
      // assigned to Button2.
      SaveFileDialog saveFileDialog1 = new SaveFileDialog();
      saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";
      saveFileDialog1.Title = "Save an Image File";
      saveFileDialog1.ShowDialog();

      // If the file name is not an empty string open it for saving.
      if(saveFileDialog1.FileName != "")
      {
        // Saves the Image via a FileStream created by the OpenFile method.
        System.IO.FileStream fs =
            (System.IO.FileStream)saveFileDialog1.OpenFile();
        // Saves the Image in the appropriate ImageFormat based upon the
        // File type selected in the dialog box.
        // NOTE that the FilterIndex property is one-based.
        switch(saveFileDialog1.FilterIndex)
        {
            case 1 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Jpeg);
            break;

            case 2 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Bmp);
            break;

            case 3 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Gif);
            break;
        }

      fs.Close();
      }
  }
  ```

  ```cpp
  private:
      System::Void button2_Click(System::Object ^ sender,
        System::EventArgs ^ e)
      {
        // Displays a SaveFileDialog so the user can save the Image
        // assigned to Button2.
        SaveFileDialog ^ saveFileDialog1 = new SaveFileDialog();
        saveFileDialog1->Filter =
            "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";
        saveFileDialog1->Title = "Save an Image File";
        saveFileDialog1->ShowDialog();
        // If the file name is not an empty string, open it for saving.
        if(saveFileDialog1->FileName != "")
        {
            // Saves the Image through a FileStream created by
            // the OpenFile method.
            System::IO::FileStream ^ fs =
              safe_cast\<System::IO::FileStream*>(
              saveFileDialog1->OpenFile());
            // Saves the Image in the appropriate ImageFormat based on
            // the file type selected in the dialog box.
            // Note that the FilterIndex property is one based.
            switch(saveFileDialog1->FilterIndex)
            {
              case 1 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Jpeg);
                  break;
              case 2 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Bmp);
                  break;
              case 3 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Gif);
                  break;
            }
        fs->Close();
        }
      }
  ```

  (시각적 C# 개체 및 C++시각적 개체) 폼의 생성자에 다음 코드를 추가 하 여 이벤트 처리기를 등록 합니다.

  ```csharp
  this.button2.Click += new System.EventHandler(this.button2_Click);
  ```

  ```cpp
  this->button2->Click += gcnew
      System::EventHandler(this, &Form1::button2_Click);
  ```

  파일 스트림을 작성 하는 방법에 대 한 자세한 내용은 <xref:System.IO.FileStream.BeginWrite%2A> 및 <xref:System.IO.FileStream.Write%2A>를 참조 하세요.

  > [!NOTE]
  > <xref:System.Windows.Forms.RichTextBox> 컨트롤과 같은 특정 컨트롤은 파일을 저장할 수 있습니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.SaveFileDialog>
- [SaveFileDialog 구성 요소](savefiledialog-component-windows-forms.md)
