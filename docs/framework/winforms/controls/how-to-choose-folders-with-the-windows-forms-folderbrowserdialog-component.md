---
title: '방법: Windows Forms FolderBrowserDialog 구성 요소를 사용 하 여 폴더를 선택 합니다.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- directories [Windows Forms], choosing
- FolderBrowserDialog component [Windows Forms], choosing directories
- folders [Windows Forms], selecting
- folders [Windows Forms], choosing
- directories [Windows Forms], selecting
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
ms.openlocfilehash: 7055875f25aa0f39feb2d944f4b6684c6ae5d9a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614695"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a><span data-ttu-id="012d8-102">방법: Windows Forms FolderBrowserDialog 구성 요소를 사용 하 여 폴더를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="012d8-102">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>
<span data-ttu-id="012d8-103">종종 Windows 애플리케이션을 만드는 경우 파일 집합을 저장하기 위해 사용자에게 폴더를 선택하도록 요구하는 메시지를 매우 빈번하게 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="012d8-103">Often, within Windows applications you create, you will have to prompt users to select a folder, most frequently to save a set of files.</span></span> <span data-ttu-id="012d8-104">Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소를 사용 하면 쉽게이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="012d8-104">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component allows you to easily accomplish this task.</span></span>  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a><span data-ttu-id="012d8-105">Windows Forms FolderBrowserDialog 구성 요소를 사용하여 폴더를 선택하려면</span><span class="sxs-lookup"><span data-stu-id="012d8-105">To choose folders with the FolderBrowserDialog component</span></span>  
  
1.  <span data-ttu-id="012d8-106">프로시저에서 확인 합니다 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소의 <xref:System.Windows.Forms.Form.DialogResult%2A> 속성을 대화 상자를 닫은 방법을 참조 하 고 값을 가져옵니다 합니다 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소의 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="012d8-106">In a procedure, check the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.Form.DialogResult%2A> property to see how the dialog box was closed and get the value of the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property.</span></span>  
  
2.  <span data-ttu-id="012d8-107">대화 상자의 트리 보기에서 표시 되는 집합 최상위 폴더를 해야 하는 경우 설정 합니다 <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> 의 멤버를 사용 하는 속성을 <xref:System.Environment.SpecialFolder> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="012d8-107">If you need to set the top-most folder that will appear within the tree view of the dialog box, set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property, which takes a member of the <xref:System.Environment.SpecialFolder> enumeration.</span></span>  
  
3.  <span data-ttu-id="012d8-108">또한 설정할 수는 <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> 폴더 브라우저 트리 보기의 맨 위에 표시 되는 텍스트 문자열을 지정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="012d8-108">Additionally, you can set the <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> property, which specifies the text string that appears at the top of the folder-browser tree view.</span></span>  
  
     <span data-ttu-id="012d8-109">아래 예제에서는 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소를 사용 하 때 Visual Studio에서 프로젝트를 만들에 저장할 폴더를 선택 하 라는 메시지가 표시 되는 폴더를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="012d8-109">In the example below, the <xref:System.Windows.Forms.FolderBrowserDialog> component is used to select a folder, similar to when you create a project in Visual Studio and are prompted to select a folder to save it in.</span></span> <span data-ttu-id="012d8-110">이 예제에서는 폴더 이름을 그러면에 표시 됩니다는 <xref:System.Windows.Forms.TextBox> 폼에서 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="012d8-110">In this example, the folder name is then displayed in a <xref:System.Windows.Forms.TextBox> control on the form.</span></span> <span data-ttu-id="012d8-111">편집 가능한 영역을 같은 위치를 배치 하는 것이 좋습니다는 <xref:System.Windows.Forms.TextBox> 컨트롤을 사용자 오류 또는 다른 문제가 발생할 경우 해당 선택을 편집할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="012d8-111">It is a good idea to place the location in an editable area, such as a <xref:System.Windows.Forms.TextBox> control, so that users may edit their selection in case of error or other issues.</span></span> <span data-ttu-id="012d8-112">이 예에서는 가정 된 폼을 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소 및 <xref:System.Windows.Forms.TextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="012d8-112">This example assumes a form with a <xref:System.Windows.Forms.FolderBrowserDialog> component and a <xref:System.Windows.Forms.TextBox> control.</span></span>  
  
    ```vb  
    Public Sub ChooseFolder()  
        If FolderBrowserDialog1.ShowDialog() = DialogResult.OK Then  
            TextBox1.Text = FolderBrowserDialog1.SelectedPath  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    public void ChooseFolder()  
    {  
        if (folderBrowserDialog1.ShowDialog() == DialogResult.OK)   
        {  
            textBox1.Text = folderBrowserDialog1.SelectedPath;  
        }  
    }  
    ```  
  
    ```cpp  
    public:  
       void ChooseFolder()  
       {  
          if (folderBrowserDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Text = folderBrowserDialog1->SelectedPath;  
          }  
       }  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="012d8-113">이 클래스를 사용 하려면 어셈블리 권한 수준에서 부여한 필요 합니다 <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> 일부인 속성의는 <xref:System.Security.Permissions.FileIOPermissionAccess> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="012d8-113">To use this class, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> property, which is part of the <xref:System.Security.Permissions.FileIOPermissionAccess> enumeration.</span></span> <span data-ttu-id="012d8-114">부분 신뢰 컨텍스트에서 실행하는 경우 프로세스가 권한 부족으로 인해 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="012d8-114">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="012d8-115">자세한 내용은 [코드 액세스 보안 기본 사항](../../../../docs/framework/misc/code-access-security-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="012d8-115">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
 <span data-ttu-id="012d8-116">파일을 저장 하는 방법에 대 한 자세한 내용은 [방법: SaveFileDialog 구성 요소를 사용 하 여 파일 저장](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="012d8-116">For information on how to save files, see [How to: Save Files Using the SaveFileDialog Component](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="012d8-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="012d8-117">See also</span></span>
- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="012d8-118">FolderBrowserDialog 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="012d8-118">FolderBrowserDialog Component Overview (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-overview-windows-forms.md)
- [<span data-ttu-id="012d8-119">FolderBrowserDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="012d8-119">FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
