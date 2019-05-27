---
title: '방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying Web links
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], linking to Web pages
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
ms.openlocfilehash: 05d9ad4766584b59cca7c31f49b737d4696a9921
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053534"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="ab79b-102">방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시</span><span class="sxs-lookup"><span data-stu-id="ab79b-102">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="ab79b-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> 제어와 색이 지정 된 밑줄 웹 링크를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab79b-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display Web links as colored and underlined.</span></span> <span data-ttu-id="ab79b-104">브라우저 창에 링크를 클릭할 때 링크 텍스트에 지정 된 웹 사이트를 표시 하는 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab79b-104">You can write code that opens a browser window showing the Web site specified in the link text when the link is clicked.</span></span>  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a><span data-ttu-id="ab79b-105">RichTextBox 컨트롤을 사용 하 여 웹 페이지에 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="ab79b-105">To link to a Web page with the RichTextBox control</span></span>  
  
1. <span data-ttu-id="ab79b-106">설정 된 <xref:System.Windows.Forms.RichTextBox.Text%2A> 속성을 유효한 URL이 포함 된 문자열 (예를 들어, "http://www.microsoft.com/").</span><span class="sxs-lookup"><span data-stu-id="ab79b-106">Set the <xref:System.Windows.Forms.RichTextBox.Text%2A> property to a string that includes a valid URL (for example, "http://www.microsoft.com/").</span></span>  
  
2. <span data-ttu-id="ab79b-107">있는지 확인 합니다 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> 속성이 `true` (기본값).</span><span class="sxs-lookup"><span data-stu-id="ab79b-107">Make sure the <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> property is set to `true` (the default).</span></span>  
  
3. <span data-ttu-id="ab79b-108">새 전역 인스턴스를 만들고는 <xref:System.Diagnostics.Process> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ab79b-108">Create a new global instance of the <xref:System.Diagnostics.Process> object.</span></span>  
  
4. <span data-ttu-id="ab79b-109">에 대 한 이벤트 처리기를 작성 합니다 <xref:System.Windows.Forms.RichTextBox.LinkClicked> 브라우저에 원하는 텍스트를 전송 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="ab79b-109">Write an event handler for the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event that sends the browser the desired text.</span></span>  
  
     <span data-ttu-id="ab79b-110">아래 예제에서는 <xref:System.Windows.Forms.RichTextBox.LinkClicked> 이벤트에 지정 된 URL Internet Explorer의 인스턴스를 열고는 <xref:System.Windows.Forms.RichTextBox.Text%2A> 의 속성은 <xref:System.Windows.Forms.RichTextBox> 컨트롤.</span><span class="sxs-lookup"><span data-stu-id="ab79b-110">In the example below, the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event opens an instance of Internet Explorer to the URL specified in the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="ab79b-111">이 예에서는 가정 된 폼을 <xref:System.Windows.Forms.RichTextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab79b-111">This example assumes a form with a <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ab79b-112">호출에는 <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> 메서드를 접하게 되는 <xref:System.Security.SecurityException> 권한 부족으로 인해 부분 신뢰 컨텍스트에서 코드를 실행 하는 경우 예외.</span><span class="sxs-lookup"><span data-stu-id="ab79b-112">In calling the <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> method, you will encounter a <xref:System.Security.SecurityException> exception if you are running the code in a partial-trust context because of insufficient privileges.</span></span> <span data-ttu-id="ab79b-113">자세한 내용은 [코드 액세스 보안 기본 사항](../../misc/code-access-security-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab79b-113">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>  
  
    ```vb  
    Public p As New System.Diagnostics.Process  
    Private Sub RichTextBox1_LinkClicked _  
       (ByVal sender As Object, ByVal e As _  
       System.Windows.Forms.LinkClickedEventArgs) _  
       Handles RichTextBox1.LinkClicked  
          ' Call Process.Start method to open a browser  
          ' with link text as URL.  
          p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText)  
    End Sub  
    ```  
  
    ```csharp  
    public System.Diagnostics.Process p = new System.Diagnostics.Process();  
  
    private void richTextBox1_LinkClicked(object sender,   
    System.Windows.Forms.LinkClickedEventArgs e)  
    {  
       // Call Process.Start method to open a browser  
       // with link text as URL.  
       p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText);  
    }  
    ```  
  
    ```cpp  
    public:  
       System::Diagnostics::Process ^ p;  
  
    private:  
       void richTextBox1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkClickedEventArgs ^  e)  
       {  
          // Call Process.Start method to open a browser  
          // with link text as URL.  
          p = System::Diagnostics::Process::Start("IExplore.exe",  
             e->LinkText);  
       }  
    ```  
  
     <span data-ttu-id="ab79b-114">(Visual C++) 프로세스를 초기화 해야 `p`, 폼의 생성자에서 다음 문을 포함 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab79b-114">(Visual C++) You must initialize process `p`, which you can do by including the following statement in the constructor of your form:</span></span>  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     <span data-ttu-id="ab79b-115">(Visual C#, Visual C++) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab79b-115">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.LinkClicked += new   
       System.Windows.Forms.LinkClickedEventHandler  
       (this.richTextBox1_LinkClicked);  
    ```  
  
    ```cpp  
    this->richTextBox1->LinkClicked += gcnew  
       System::Windows::Forms::LinkClickedEventHandler  
       (this, &Form1::richTextBox1_LinkClicked);  
    ```  
  
     <span data-ttu-id="ab79b-116">즉시 작업을 마친 후 만든 프로세스를 중지 하는 것이 반드시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab79b-116">It is important to immediately stop the process you have created once you have finished working with it.</span></span> <span data-ttu-id="ab79b-117">위에 나오는 코드를 참조 하는 프로세스를 중지 하는 코드 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab79b-117">Referring to the code presented above, your code to stop the process might look like this:</span></span>  
  
    ```vb  
    Public Sub StopWebProcess()  
       p.Kill()  
    End Sub  
    ```  
  
    ```csharp  
    public void StopWebProcess()  
    {  
       p.Kill();  
    }  
    ```  
  
    ```cpp  
    public: void StopWebProcess()  
    {  
       p->Kill();  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ab79b-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="ab79b-118">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="ab79b-119">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ab79b-119">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="ab79b-120">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ab79b-120">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
