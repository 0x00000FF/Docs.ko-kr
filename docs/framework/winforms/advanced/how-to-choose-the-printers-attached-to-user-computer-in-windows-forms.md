---
title: '방법: 사용자 컴퓨터에 연결 된 프린터 선택'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms], choosing printers
- printers [Windows Forms], choosing
ms.assetid: 63c1172b-2931-4ac0-953f-37f629494bbf
ms.openlocfilehash: 7fc2427468540ac0a1480f6140cbb34c3a0f1ab3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746502"
---
# <a name="how-to-choose-the-printers-attached-to-a-users-computer-in-windows-forms"></a><span data-ttu-id="b37e3-102">방법: Windows Forms에서 사용자의 컴퓨터에 연결된 프린터 선택</span><span class="sxs-lookup"><span data-stu-id="b37e3-102">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>
<span data-ttu-id="b37e3-103">사용자는 기본 프린터 이외의 프린터를 선택하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="b37e3-103">Often, users want to choose a printer other than the default printer to print to.</span></span> <span data-ttu-id="b37e3-104"><xref:System.Windows.Forms.PrintDialog> 구성 요소를 사용하면 현재 설치된 프린터 중에서 사용자가 원하는 프린터를 선택하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b37e3-104">You can enable users to choose a printer from among those currently installed by using the <xref:System.Windows.Forms.PrintDialog> component.</span></span> <span data-ttu-id="b37e3-105"><xref:System.Windows.Forms.PrintDialog> 구성 요소를 통해 <xref:System.Windows.Forms.DialogResult> 구성 요소의 <xref:System.Windows.Forms.PrintDialog> 가 캡처되고 프린터 선택에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b37e3-105">Through the <xref:System.Windows.Forms.PrintDialog> component, the <xref:System.Windows.Forms.DialogResult> of the <xref:System.Windows.Forms.PrintDialog> component is captured and used to select the printer.</span></span>  
  
 <span data-ttu-id="b37e3-106">다음 절차에서는 텍스트 파일이 기본 프린터로 인쇄되도록 선택되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b37e3-106">In the following procedure, a text file is selected to be printed to the default printer.</span></span> <span data-ttu-id="b37e3-107">그런 다음 <xref:System.Windows.Forms.PrintDialog> 클래스가 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b37e3-107">The <xref:System.Windows.Forms.PrintDialog> class is then instantiated.</span></span>  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a><span data-ttu-id="b37e3-108">프린터를 선택한 다음 파일을 인쇄하려면</span><span class="sxs-lookup"><span data-stu-id="b37e3-108">To choose a printer and then print a file</span></span>  
  
1. <span data-ttu-id="b37e3-109"><xref:System.Windows.Forms.PrintDialog> 구성 요소를 사용 하 여 사용할 프린터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b37e3-109">Select the printer to be used using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
     <span data-ttu-id="b37e3-110">다음 코드 예제에서는 두 이벤트가 처리되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b37e3-110">In the following code example, there are two events being handled.</span></span> <span data-ttu-id="b37e3-111">첫 번째, <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트에서 <xref:System.Windows.Forms.PrintDialog> 클래스가 인스턴스화되고 사용자가 선택한 프린터가 <xref:System.Windows.Forms.DialogResult> 속성에서 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="b37e3-111">In the first, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event, the <xref:System.Windows.Forms.PrintDialog> class is instantiated and the printer selected by the user is captured in the <xref:System.Windows.Forms.DialogResult> property.</span></span>  
  
     <span data-ttu-id="b37e3-112"><xref:System.Drawing.Printing.PrintDocument> 구성 요소의 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트에 대 한 두 번째 이벤트에서 샘플 문서는 지정 된 프린터로 인쇄 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b37e3-112">In the second event, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event of the <xref:System.Drawing.Printing.PrintDocument> component, a sample document is printed to the printer specified.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim PrintDialog1 As New PrintDialog()  
       PrintDialog1.Document = PrintDocument1  
       Dim result As DialogResult = PrintDialog1.ShowDialog()  
  
       If (result = DialogResult.OK) Then  
         PrintDocument1.Print()  
       End If   
  
    End Sub  
  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))          
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       PrintDialog printDialog1 = new PrintDialog();  
       printDialog1.Document = printDocument1;  
       DialogResult result = printDialog1.ShowDialog();  
       if (result == DialogResult.OK)  
       {  
          printDocument1.Print();  
       }  
    }  
  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          PrintDialog ^ printDialog1 = gcnew PrintDialog();  
          printDialog1->Document = printDocument1;  
          System::Windows::Forms::DialogResult result =   
             printDialog1->ShowDialog();  
          if (result == DialogResult::OK)  
          {  
             printDocument1->Print();  
          }  
       }  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     <span data-ttu-id="b37e3-113">(시각적 C# 개체 및 C++시각적 개체) 폼의 생성자에 다음 코드를 추가 하 여 이벤트 처리기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b37e3-113">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b37e3-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b37e3-114">See also</span></span>

- [<span data-ttu-id="b37e3-115">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="b37e3-115">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
