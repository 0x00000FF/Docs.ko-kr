---
title: '방법: (Windows Forms) 문자열에 인용 부호 넣기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- quotation marks
- TextBox control [Windows Forms], displaying quotation marks
- quotation marks [Windows Forms], adding to strings in text boxes
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
ms.openlocfilehash: 24d7ea17384a912fda454bfb1136696ab18d9843
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651645"
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a><span data-ttu-id="77429-102">방법: (Windows Forms) 문자열에 인용 부호 넣기</span><span class="sxs-lookup"><span data-stu-id="77429-102">How to: Put Quotation Marks in a String (Windows Forms)</span></span>
<span data-ttu-id="77429-103">경우에 따라 텍스트의 문자열에 따옴표(" ")를 배치하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="77429-103">Sometimes you might want to place quotation marks (" ") in a string of text.</span></span> <span data-ttu-id="77429-104">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="77429-104">For example:</span></span>  
  
 <span data-ttu-id="77429-105">그녀는 "당신은 그럴 자격이 있어!"라고 말했습니다.</span><span class="sxs-lookup"><span data-stu-id="77429-105">She said, "You deserve a treat!"</span></span>  
  
 <span data-ttu-id="77429-106">대신 사용할 수도 있습니다는 <xref:Microsoft.VisualBasic.ControlChars.Quote> 상수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="77429-106">As an alternative, you can also use the <xref:Microsoft.VisualBasic.ControlChars.Quote> field as a constant.</span></span>  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a><span data-ttu-id="77429-107">코드의 문자열에 따옴표를 배치하려면</span><span class="sxs-lookup"><span data-stu-id="77429-107">To place quotation marks in a string in your code</span></span>  
  
1.  <span data-ttu-id="77429-108">Visual basic의 경우를 포함 하는 인용 부호로 행에 두 개의 따옴표를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="77429-108">In Visual Basic, insert two quotation marks in a row as an embedded quotation mark.</span></span> <span data-ttu-id="77429-109">시각적 개체의 C# 하 고 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], 이스케이프 시퀀스를 삽입 \\"로 포함 된 큰따옴표를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="77429-109">In Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], insert the escape sequence \\" as an embedded quotation mark.</span></span> <span data-ttu-id="77429-110">예를 들어 위의 문자열을 만들려면 다음 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="77429-110">For example, to create the preceding string, use the following code.</span></span>  
  
    ```vb  
    Private Sub InsertQuote()  
       TextBox1.Text = "She said, ""You deserve a treat!"" "  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertQuote(){  
       textBox1.Text = "She said, \"You deserve a treat!\" ";  
    }  
    ```  
  
    ```cpp  
    private:  
       void InsertQuote()  
       {  
          textBox1->Text = "She said, \"You deserve a treat!\" ";  
       }  
    ```  
  
     <span data-ttu-id="77429-111">또는</span><span class="sxs-lookup"><span data-stu-id="77429-111">-or-</span></span>  
  
2.  <span data-ttu-id="77429-112">따옴표에 대한 ASCII 또는 유니코드 문자를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="77429-112">Insert the ASCII or Unicode character for a quotation mark.</span></span> <span data-ttu-id="77429-113">Visual basic에서는 ASCII 문자 (34)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="77429-113">In Visual Basic, use the ASCII character (34).</span></span> <span data-ttu-id="77429-114">시각적 개체의 C#, 유니코드 문자 (\u0022)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="77429-114">In Visual C#, use the Unicode character (\u0022).</span></span>  
  
    ```vb  
    Private Sub InsertAscii()  
       TextBox1.Text = "She said, " & Chr(34) & "You deserve a treat!" & Chr(34)  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertAscii(){  
       textBox1.Text = "She said, " + '\u0022' + "You deserve a treat!" + '\u0022';  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="77429-115">이 예제에서는 기본 문자 집합에서 문자를 지정하는 범용 문자 이름을 사용할 수 없으므로 \u0022를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77429-115">In this example, you cannot use \u0022 because you cannot use a universal character name that designates a character in the basic character set.</span></span> <span data-ttu-id="77429-116">그렇지 않으면 C3851을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="77429-116">Otherwise, you produce C3851.</span></span> <span data-ttu-id="77429-117">자세한 내용은 [컴파일러 오류 C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77429-117">For more information, see [Compiler Error C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span></span>  
  
     <span data-ttu-id="77429-118">또는</span><span class="sxs-lookup"><span data-stu-id="77429-118">-or-</span></span>  
  
3.  <span data-ttu-id="77429-119">문자에 대한 상수를 정의하고 필요한 부분에 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77429-119">You can also define a constant for the character, and use it where needed.</span></span>  
  
    ```vb  
    Const quote As String = """"  
    TextBox1.Text = "She said, " & quote & "You deserve a treat!" & quote  
    ```  
  
    ```csharp  
    const string quote = "\"";  
    textBox1.Text = "She said, " + quote +  "You deserve a treat!"+ quote ;  
    ```  
  
    ```cpp  
    const String^ quote = "\"";  
    textBox1->Text = String::Concat("She said, ",  
       const_cast<String^>(quote), "You deserve a treat!",  
       const_cast<String^>(quote));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="77429-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="77429-120">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- <xref:Microsoft.VisualBasic.ControlChars.Quote>
- [<span data-ttu-id="77429-121">TextBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="77429-121">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="77429-122">방법: Windows Forms TextBox 컨트롤의 삽입 지점 제어</span><span class="sxs-lookup"><span data-stu-id="77429-122">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="77429-123">방법: Windows Forms TextBox 컨트롤을 사용 하 여 암호 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="77429-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="77429-124">방법: 읽기 전용 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="77429-124">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="77429-125">방법: Windows Forms TextBox 컨트롤에서 텍스트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="77429-125">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="77429-126">방법: Windows Forms TextBox 컨트롤에서 여러 줄 보기</span><span class="sxs-lookup"><span data-stu-id="77429-126">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="77429-127">TextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="77429-127">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
