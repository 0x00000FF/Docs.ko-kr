---
title: "방법: Windows Forms RichTextBox 컨트롤을 사용하여 파일 저장"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d28aeaefca6f8aa13607f1c1e6f72557ef536754
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="67208-102">방법: Windows Forms RichTextBox 컨트롤을 사용하여 파일 저장</span><span class="sxs-lookup"><span data-stu-id="67208-102">How to: Save Files with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="67208-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤 여러 형식 중 하나에 표시 하는 정보를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67208-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can write the information it displays in one of several formats:</span></span>  
  
-   <span data-ttu-id="67208-104">일반 텍스트</span><span class="sxs-lookup"><span data-stu-id="67208-104">Plain text</span></span>  
  
-   <span data-ttu-id="67208-105">유니코드 일반 텍스트</span><span class="sxs-lookup"><span data-stu-id="67208-105">Unicode plain text</span></span>  
  
-   <span data-ttu-id="67208-106">서식 있는 텍스트 형식 RTF)</span><span class="sxs-lookup"><span data-stu-id="67208-106">Rich-Text Format (RTF)</span></span>  
  
-   <span data-ttu-id="67208-107">OLE 개체 대신 공백으로 RTF</span><span class="sxs-lookup"><span data-stu-id="67208-107">RTF with spaces in place of OLE objects</span></span>  
  
-   <span data-ttu-id="67208-108">OLE 개체의 텍스트 표현으로 일반 텍스트</span><span class="sxs-lookup"><span data-stu-id="67208-108">Plain text with a textual representation of OLE objects</span></span>  
  
 <span data-ttu-id="67208-109">파일을 저장 하려면 호출 된 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="67208-109">To save a file, call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method.</span></span> <span data-ttu-id="67208-110">사용할 수도 있습니다는 **SaveFile** 메서드를 데이터 스트림으로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="67208-110">You can also use the **SaveFile** method to save data to a stream.</span></span> <span data-ttu-id="67208-111">자세한 내용은 <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="67208-111">For more information, see <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>  
  
### <a name="to-save-the-contents-of-the-control-to-a-file"></a><span data-ttu-id="67208-112">컨트롤의 내용을 파일에 저장 하려면</span><span class="sxs-lookup"><span data-stu-id="67208-112">To save the contents of the control to a file</span></span>  
  
1.  <span data-ttu-id="67208-113">저장할 파일의 경로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="67208-113">Determine the path of the file to be saved.</span></span>  
  
     <span data-ttu-id="67208-114">실제 응용 프로그램에서이 작업을 수행 하려면 일반적으로 사용 된 <xref:System.Windows.Forms.SaveFileDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="67208-114">To do this in a real-world application, you would typically use the <xref:System.Windows.Forms.SaveFileDialog> component.</span></span> <span data-ttu-id="67208-115">에 대 한 개요 [SaveFileDialog 구성 요소 개요](../../../../docs/framework/winforms/controls/savefiledialog-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="67208-115">For an overview, see [SaveFileDialog Component Overview](../../../../docs/framework/winforms/controls/savefiledialog-component-overview-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="67208-116">호출의 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 의 메서드는 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 저장할 파일 및 필요에 따라 파일 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67208-116">Call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to save and optionally a file type.</span></span> <span data-ttu-id="67208-117">파일 이름 인수로 사용 하 여 메서드를 호출 하는 경우 파일은 RTF로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67208-117">If you call the method with a file name as its only argument, the file will be saved as RTF.</span></span> <span data-ttu-id="67208-118">다른 파일 형식을 지정하려면 <xref:System.Windows.Forms.RichTextBoxStreamType> 열거형의 값을 두 번째 인수로 사용하여 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="67208-118">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>  
  
     <span data-ttu-id="67208-119">아래 예제에서는 서식 있는 텍스트 파일의 위치 설정 된 경로 **내 문서** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="67208-119">In the example below, the path set for the location of the rich-text file is the **My Documents** folder.</span></span> <span data-ttu-id="67208-120">대부분의 Windows 운영 체제를 실행 중인 컴퓨터에이 폴더 포함 됩니다는 알 수 없으므로이 위치가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67208-120">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="67208-121">안전 하 게 응용 프로그램을 실행 하려면 사용자는 최소한의 시스템 액세스 수준에서는이 폴더를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67208-121">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="67208-122">다음 예제에서는 가정 된 폼을 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 이미 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="67208-122">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control already added.</span></span>  
  
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
    >  <span data-ttu-id="67208-123">이 예제에서는 파일이 아직 없는 경우 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67208-123">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="67208-124">응용 프로그램 파일을 만드는 경우, 해당 응용 프로그램 폴더에 대 한 Create 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="67208-124">If an application needs to create a file, that application needs Create access for the folder.</span></span> <span data-ttu-id="67208-125">권한은 액세스 제어 목록을 사용하여 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="67208-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="67208-126">파일이 이미 있는 경우 응용 프로그램에는 권한인 쓰기 액세스만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="67208-126">If the file already exists, the application needs only Write access, a lesser privilege.</span></span> <span data-ttu-id="67208-127">가능한 경우에 더 안전 배포 하는 동안 파일을 만들 및만 단일 파일에 대 한 읽기 권한을 부여 작성 하기 보다는 폴더에 대 한 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="67208-127">Where possible, it is more secure to create the file during deployment, and only grant Read access to a single file, rather than Create access for a folder.</span></span> <span data-ttu-id="67208-128">또한 루트 폴더나 Program Files 폴더보다 사용자 폴더에 데이터를 쓰는 것이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="67208-128">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67208-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67208-129">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="67208-130">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="67208-130">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="67208-131">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="67208-131">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
