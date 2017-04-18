---
title: "연습: .NET Framework 메서드를 사용하여 파일 조작(Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- I/O [Visual Basic], walkthroughs
- text files, writing to
- reading text files
- text, writing to files
- files, searching
- StreamReader class, walkthroughs
- files, accessing
- I/O [Visual Basic], writing text to files
- writing to files, walkthroughs
- StreamWriter class, walkthroughs
- text files, reading
- I/O [Visual Basic], reading text from files
ms.assetid: 7d2109eb-f98a-4389-b43d-30f384aaa7d5
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e8bf73f32dba51455542778ed91ef3bfd2898754
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-manipulating-files-by-using-net-framework-methods-visual-basic"></a>연습: .NET Framework 메서드를 사용하여 파일 조작(Visual Basic)
이 연습에서는 <xref:System.IO.StreamReader> 클래스를 사용하여 파일을 열고 읽는 방법, 파일이 액세스되고 있는지 확인하는 방법, <xref:System.IO.StreamReader> 클래스의 인스턴스로 파일 읽기 내에서 문자열을 검색하는 방법, <xref:System.IO.StreamWriter> 클래스를 사용하여 파일에 쓰는 방법을 보여 줍니다.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-the-application"></a>응용 프로그램 작성  
 [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)]를 시작하고 사용자가 지정된 파일에 기록하기 위해 사용할 수 있는 양식을 만들어 프로젝트를 시작합니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 **새 프로젝트**를 선택합니다.  
  
2.  **새 프로젝트** 창에서 **Windows 응용 프로그램**을 클릭합니다.  
  
3.  **이름** 상자에 `MyDiary`를 입력한 다음 **확인**을 클릭합니다.  
  
     [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)]에서 **솔루션 탐색기**에 프로젝트를 추가하면 **Windows Forms 디자이너**가 열립니다.  
  
4.  다음 표의 컨트롤을 양식에 추가하고 속성의 해당 값을 설정합니다.  
  
|**개체**|**속성**|**Value**|  
|---|---|---|   
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Submit`<br /><br /> **항목 제출**|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Clear`<br /><br /> **항목 지우기**|  
|<xref:System.Windows.Forms.TextBox>|**Name**<br /><br /> **Text**<br /><br /> **Multiline**|`Entry`<br /><br /> **내용을 입력하세요.**<br /><br /> `False`|  
  
## <a name="writing-to-the-file"></a>파일에 쓰기  
 응용 프로그램을 통해 파일에 쓰는 기능을 추가하려면 <xref:System.IO.StreamWriter> 클래스를 사용합니다. <xref:System.IO.StreamWriter>는 특정 인코딩에서 문자 출력용으로 설계된 반면, <xref:System.IO.Stream> 클래스는 바이트 입력 및 출력용으로 설계되었습니다. 표준 텍스트 파일에 정보의 줄을 쓰려면 <xref:System.IO.StreamWriter>를 사용합니다. <xref:System.IO.StreamWriter> 클래스에 대한 자세한 내용은 <xref:System.IO.StreamWriter>를 참조하세요.  
  
#### <a name="to-add-writing-functionality"></a>쓰기 기능을 추가하려면  
  
1.  **보기** 메뉴에서 **코드**를 선택하여 코드 편집기를 엽니다.  
  
2.  응용 프로그램은 <xref:System.IO> 네임스페이스를 참조하므로 다음 문을 코드의 시작 부분(`Public Class Form1`을 시작하는 양식에 대한 클래스 선언 전)에 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#35](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_1.vb)]  
  
     파일에 기록하기 전에 <xref:System.IO.StreamWriter> 클래스의 인스턴스를 만들어야 합니다.  
  
3.  **보기** 메뉴에서 **디자이너**를 선택하여 **Windows Forms 디자이너**로 돌아갑니다. `Submit` 단추를 두 번 클릭하여 단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들고 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_2.vb)]  
  
> [!NOTE]
>  Visual Studio IDE(통합 개발 환경)는 코드 편집기로 돌아가서, 코드를 추가해야 하는 이벤트 처리기 내부에 삽입점을 둡니다.  
  
1.  파일에 쓰려면 <xref:System.IO.StreamWriter> 클래스의 <xref:System.IO.StreamWriter.Write%2A> 메서드를 사용합니다. `Dim fw As StreamWriter` 직후에 다음 코드를 추가합니다. 파일이 없으면 만들어지기 때문에 파일이 없을 경우 예외가 throw될 것을 우려하지 않아도 됩니다.  
  
     [!code-vb[VbVbcnMyFileSystem#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_3.vb)]  
  
2.  `Dim ReadString As String` 직후에 다음 코드를 추가하여 사용자가 빈 항목을 제출할 수 없도록 해야 합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#38](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_4.vb)]  
  
3.  이것은 일기이므로 사용자는 각 항목에 날짜를 할당하고자 할 것입니다. `fw = New StreamWriter("C:\MyDiary.txt", True)` 뒤에 다음 코드를 삽입하여 `Today` 변수를 현재 날짜로 설정합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#39](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_5.vb)]  
  
4.  마지막으로 코드를 추가하여 <xref:System.Windows.Forms.TextBox>를 지웁니다. `Clear` 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#40](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_6.vb)]  
  
## <a name="adding-display-features-to-the-diary"></a>일기에 표시 기능 추가  
 이 섹션에서는 `DisplayEntry`<xref:System.Windows.Forms.TextBox>의 최신 항목을 표시하는 기능을 추가합니다. 또한 다양한 항목을 표시할 수 있고 `DisplayEntry`<xref:System.Windows.Forms.TextBox>에 표시할 항목을 사용자가 선택할 수 있는 <xref:System.Windows.Forms.ComboBox>를 추가할 수 있습니다. <xref:System.IO.StreamReader> 클래스의 인스턴스는 `MyDiary.txt`에서 읽습니다. <xref:System.IO.StreamWriter> 클래스처럼 <xref:System.IO.StreamReader>도 텍스트 파일과 사용하도록 설계되었습니다.  
  
 이 연습의 이 섹션에서는 다음 표의 컨트롤을 양식에 추가하고 각 속성의 해당 값을 설정합니다.  
  
|컨트롤|속성|값|  
|-------------|----------------|------------|  
|<xref:System.Windows.Forms.TextBox>|**Name**<br /><br /> **Visible**<br /><br /> **Size**<br /><br /> **Multiline**|`DisplayEntry`<br /><br /> `False`<br /><br /> `120,60`<br /><br /> `True`|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Display`<br /><br /> **표시**|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`GetEntries`<br /><br /> **항목 가져오기**|  
|<xref:System.Windows.Forms.ComboBox>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`PickEntries`<br /><br /> **항목 선택**<br /><br /> `False`|  
  
#### <a name="to-populate-the-combo-box"></a>콤보 상자를 채우려면  
  
1.  `PickEntries`<xref:System.Windows.Forms.ComboBox>는 사용자가 특정 날짜의 항목을 선택할 수 있도록, 사용자가 각 항목을 제출하는 날짜를 표시하는 데 사용됩니다. `GetEntries` 단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들고 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#41](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_7.vb)]  
  
2.  코드를 테스트하려면 F5를 눌러 응용 프로그램을 컴파일한 다음 **항목 가져오기**를 클릭합니다. <xref:System.Windows.Forms.ComboBox>에서 드롭다운 화살표를 클릭하여 항목 날짜를 표시합니다.  
  
#### <a name="to-choose-and-display-individual-entries"></a>개별 항목을 선택하고 표시하려면  
  
1.  `Display` 단추에 대해 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들고 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#42](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_8.vb)]  
  
2.  코드를 테스트하려면 F5를 눌러 응용 프로그램을 컴파일한 다음 항목을 제출합니다. **항목 가져오기**를 클릭하고 <xref:System.Windows.Forms.ComboBox>에서 항목을 선택한 다음 **표시**를 클릭합니다. 선택한 항목의 내용이 `DisplayEntry`<xref:System.Windows.Forms.TextBox>에 표시됩니다.  
  
## <a name="enabling-users-to-delete-or-modify-entries"></a>사용자가 항목을 삭제 또는 수정하도록 설정  
 마지막으로 `DeleteEntry` 및 `EditEntry` 단추를 사용하여, 사용자가 항목을 삭제 또는 수정하도록 설정하는 추가 기능을 포함할 수 있습니다. 항목이 표시되지 않으면 두 단추 모두 비활성화됩니다.  
  
 다음 표의 컨트롤을 양식에 추가하고 속성의 해당 값을 설정합니다.  
  
|컨트롤|속성|값|  
|-------------|----------------|------------|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`DeleteEntry`<br /><br /> **항목 삭제**<br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`EditEntry`<br /><br /> **항목 편집**<br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`SubmitEdit`<br /><br /> **편집 제출**<br /><br /> `False`|  
  
#### <a name="to-enable-deletion-and-modification-of-entries"></a>항목을 삭제 및 수정하도록 설정하려면  
  
1.  `DisplayEntry.Text = ReadString` 뒤, `Display` 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#43](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_9.vb)]  
  
2.  `DeleteEntry` 단추에 대해 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들고 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#44](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_10.vb)]  
  
3.  사용자가 항목을 표시하면 `EditEntry` 단추가 활성화됩니다. `DisplayEntry.Text = ReadString` 뒤, `Display` 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#45](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_11.vb)]  
  
4.  `EditEntry` 단추에 대해 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들고 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#46](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_12.vb)]  
  
5.  `SubmitEdit` 단추에 대해 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들고 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#47](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_13.vb)]  
  
 코드를 테스트하려면 F5를 눌러 응용 프로그램을 컴파일합니다. **항목 가져오기**를 클릭하고 항목을 선택한 다음 **표시**를 클릭합니다. 항목이 `DisplayEntry`<xref:System.Windows.Forms.TextBox>에 나타납니다. **항목 편집**을 클릭합니다. 항목이 `Entry`<xref:System.Windows.Forms.TextBox>에 나타납니다. `Entry`<xref:System.Windows.Forms.TextBox>에서 항목을 편집하고 **편집 제출**을 클릭합니다. `MyDiary.txt` 파일을 열어 수정한 내용을 확인합니다. 이제 항목을 선택하고 **항목 삭제**를 클릭합니다. <xref:System.Windows.Forms.MessageBox>에서 확인을 요청하면 **확인**을 클릭합니다. 응용 프로그램을 닫고 `MyDiary.txt`를 열어 삭제를 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO.StreamReader>   
 <xref:System.IO.StreamWriter>   
 [연습](../../../../visual-basic/walkthroughs.md)

