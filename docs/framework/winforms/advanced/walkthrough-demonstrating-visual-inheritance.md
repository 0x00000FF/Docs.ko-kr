---
title: '연습: 시각적 상속 설명'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
ms.openlocfilehash: bc91e3bde54eedb4d9dbcfcb9f7faa0ccc98e397
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505626"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a>연습: 시각적 상속 설명
시각적 상속을 통해 기본 폼의 컨트롤을 보고 새 컨트롤을 추가할 수 있습니다. 이 연습에서는 기본 폼을 만들고 클래스 라이브러리로 컴파일합니다. 이 클래스 라이브러리를 다른 프로젝트로 가져와 기본 폼에서 상속하는 새 양식을 만듭니다. 이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.  
  
-   기본 폼을 포함하는 클래스 라이브러리 프로젝트를 만듭니다.  
  
-   기본 폼의 파생 클래스가 수정할 수 있는 속성을 가진 단추를 추가합니다.  
  
-   기본 폼의 상속자가 수정할 수 없는 단추를 추가합니다.  
  
-   `BaseForm`에서 상속하는 폼을 포함하는 프로젝트를 만듭니다.  
  
 궁극적으로, 이 연습에서는 상속된 폼의 private 컨트롤과 protected 컨트롤 간의 차이점을 보여 줍니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
> [!CAUTION]
>  일부 컨트롤은 기본 폼에서의 시각적 상속을 지원하지 않습니다. 다음 컨트롤은 이 연습에 설명된 시나리오를 지원하지 않습니다.  
>   
>  <xref:System.Windows.Forms.WebBrowser>  
>   
>  <xref:System.Windows.Forms.ToolStrip>  
>   
>  <xref:System.Windows.Forms.ToolStripPanel>  
>   
>  <xref:System.Windows.Forms.TableLayoutPanel>  
>   
>  <xref:System.Windows.Forms.FlowLayoutPanel>  
>   
>  <xref:System.Windows.Forms.DataGridView>  
>   
>  상속된 폼의 이러한 컨트롤은 사용하는 한정자(`private`, `protected` 또는 `public`)에 관계없이 항상 읽기 전용입니다.  
  
## <a name="scenario-steps"></a>시나리오 단계  
 첫 번째 단계는 기본 폼을 만드는 것입니다.  
  
#### <a name="to-create-a-class-library-project-containing-a-base-form"></a>기본 폼을 포함하는 클래스 라이브러리 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 선택 **새로 만들기**를 차례로 **프로젝트** 여는 **새 프로젝트** 대화 상자.  
  
2.  라는 Windows Forms 응용 프로그램을 만드는 `BaseFormLibrary`합니다.  
  
3.  표준 Windows Forms 응용 프로그램을 대신 클래스 라이브러리를 만들려는 **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **BaseFormLibrary** 프로젝트 노드를 선택한 **속성**.  
  
4.  프로젝트에 대 한 속성을 변경 합니다 **출력 형식** 에서 **Windows 응용 프로그램** 하 **클래스 라이브러리**합니다.  
  
5.  **파일** 메뉴 선택 **모두 저장** 파일과 프로젝트 기본 위치에 저장 합니다.  
  
 다음 두 절차에서는 기본 폼에 단추를 추가합니다. 시각적 상속을 보여 주기 위해 단추의 `Modifiers` 속성을 설정하여 단추에 다양한 액세스 수준을 제공합니다.  
  
#### <a name="to-add-a-button-that-inheritors-of-the-base-form-can-modify"></a>기본 폼의 상속자가 수정할 수 있는 단추를 추가하려면  
  
1.  오픈 **Form1** 디자이너에서 합니다.  
  
2.  에 **모든 Windows Forms** 탭을 **도구 상자**를 두 번 클릭 **단추** 폼에 단추를 추가 하려면. 마우스를 사용하여 단추를 배치하고 크기를 조정합니다.  
  
3.  속성 창에서 단추의 다음 속성을 설정합니다.  
  
    -   설정 된 **텍스트** 속성을 **Say Hello**합니다.  
  
    -   설정 된 **(이름)** 속성을 **btnProtected**합니다.  
  
    -   설정 된**한정자** 속성을 **Protected**합니다. 따라서에서 상속 하는 폼 **Form1** 속성을 수정 하려면 **btnProtected**합니다.  
  
4.  두 번 클릭 합니다 **Say Hello** 에 대 한 이벤트 처리기를 추가 하려면 단추를 **클릭** 이벤트입니다.  
  
5.  다음 코드 줄을 이벤트 처리기에 추가합니다.  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### <a name="to-add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a>기본 폼의 상속자가 수정할 수 없는 단추를 추가하려면  
  
1.  클릭 하 여 디자인 뷰로 전환 합니다 **Form1.vb [디자인], Form1.cs [Design] 또는 Form1.jsl [Design]** 코드 편집기를 초과 하거나 F7 키를 눌러 탭 합니다.  
  
2.  두 번째 단추를 추가하고 해당 속성을 다음과 같이 설정합니다.  
  
    -   설정 된 **텍스트** 속성을 **Say Goodbye**합니다.  
  
    -   설정 된 **(이름)** 속성을 **btnPrivate**합니다.  
  
    -   설정 된 **한정자** 속성을 **개인**합니다. 상속 하는 폼에 대 한 없게 **Form1** 속성을 수정 하려면 **btnPrivate**합니다.  
  
3.  두 번 클릭 합니다 **Say Goodbye** 에 대 한 이벤트 처리기를 추가 하려면 단추를 **클릭** 이벤트입니다. 다음 코드 줄을 이벤트 프로시저에 배치합니다.  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4.  **빌드** 메뉴 선택 **BaseForm 라이브러리 빌드** 클래스 라이브러리를 빌드합니다.  
  
     라이브러리가 빌드되고 나면 방금 만든 폼에서 상속하는 새 프로젝트를 만들 수 있습니다.  
  
#### <a name="to-create-a-project-containing-a-form-that-inherits-from-the-base-form"></a>기본 폼에서 상속하는 폼을 포함하는 프로젝트를 만들려면  
  
1.  합니다 **파일** 메뉴에서 선택 **추가** 차례로 **새 프로젝트** 여는 **새 프로젝트 추가** 대화 상자.  
  
2.  라는 Windows Forms 응용 프로그램을 만드는 `InheritanceTest`합니다.  
  
#### <a name="to-add-an-inherited-form"></a>상속된 폼을 추가하려면  
  
1.  **솔루션 탐색기**, 마우스 오른쪽 단추로 클릭 합니다 **InheritanceTest** 프로젝트를 **추가**를 선택한 후**새 항목**합니다.  
  
2.  **새 항목 추가** 대화 상자를 선택 합니다 **Windows Forms** 범주 (범주 목록이 표시) 하는 경우 선택한 후는 **상속 된 폼** 템플릿.  
  
3.  기본 이름을 그대로 `Form2` 을 클릭 한 다음 **추가**합니다.  
  
4.  에 **상속 선택** 대화 상자에서 **Form1** 에서 합니다 **BaseFormLibrary** 프로젝트의 양식에서 상속 하 고 클릭 **확인** .  
  
     양식을 만듭니다.이 **InheritanceTest** 프로젝트에서 양식에서 파생 되는 **BaseFormLibrary**합니다.  
  
5.  상속 된 폼을 엽니다 (**Form2**)을 두 번 클릭 열려 있지 않으면 디자이너에서.  
  
     디자이너에서 상속 된 단추의 있는 기호 (![VisualBasicInheritanceSymbol screenshot](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.gif "vbInheritanceGlyph"))의 위쪽 모퉁이 표시 됩니다.  
  
6.  선택 된 **Say Hello** 단추 및 크기 조정 핸들을 관찰 합니다. 이 단추는 protected이므로 상속자가 이동하고, 크기를 조정하고, 캡션을 변경하고, 기타 수정 작업을 할 수 있습니다.  
  
7.  개인 선택 **Say Goodbye** 단추 및 크기 조정 핸들 없기는 알림입니다. 또한 합니다 **속성** 창에서이 단추의 속성은 수정할 수 없음을 나타내기 위해 회색으로 표시 합니다.  
  
8.  Visual C# 사용 중인 경우:  
  
    1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **Form1** 에 **InheritanceTest** 프로젝트를 선택한 다음 **삭제**합니다. 표시 되는 메시지 상자에서 클릭 **확인** 삭제를 확인 합니다.  
  
    2.  Program.cs 파일을 열고 `Application.Run(new Form1());` 줄을 `Application.Run(new Form2());`으로 변경합니다.  
  
9. **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **InheritanceTest** 프로젝트를 마우스 **시작 프로젝트로 설정**합니다.  
  
10. **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **InheritanceTest** 프로젝트를 마우스 **속성**합니다.  
  
11. 에 **InheritanceTest** 속성 페이지 설정 합니다 **시작 개체** 상속된 된 폼 되도록 (**Form2**).  
  
12. F5 키를 눌러 응용 프로그램을 실행하고 상속된 폼의 동작을 관찰합니다.  
  
## <a name="next-steps"></a>다음 단계  
 사용자 정의 컨트롤의 상속도 거의 동일한 방식으로 작동합니다. 새 클래스 라이브러리 프로젝트를 열고 사용자 정의 컨트롤을 추가합니다. 구성 요소 컨트롤을 배치하고 프로젝트를 컴파일합니다. 다른 새 클래스 라이브러리 프로젝트를 열고 컴파일된 클래스 라이브러리에 대한 참조를 추가합니다. 또한 상속된 된 컨트롤을 추가 해 보세요 (통해는 **새 항목 추가** 대화 상자) 프로젝트에 사용 하는 **상속 선택**합니다. 사용자 정의 컨트롤을 추가 하 고 변경 합니다 `Inherits` (`:` Visual C#) 문입니다. 자세한 내용은 [방법: Windows Forms 상속](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Windows Forms 상속](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [Windows Forms 시각적 개체 상속](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [Windows Forms](../../../../docs/framework/winforms/index.md)
