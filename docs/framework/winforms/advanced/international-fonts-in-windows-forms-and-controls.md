---
title: Windows Forms 및 컨트롤에서 국가별 글꼴
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: b2738f174c9837a2ba83c1306f4617f39ce17de1
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208602"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="babf5-102">Windows Forms 및 컨트롤에서 국가별 글꼴</span><span class="sxs-lookup"><span data-stu-id="babf5-102">International fonts in Windows Forms and controls</span></span>

<span data-ttu-id="babf5-103">국가별 응용 프로그램에서 글꼴을 선택 하는 권장된 방법은 가능 글꼴 대체 (fallback)를 사용 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-103">In International applications, the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="babf5-104">글꼴 대체 방법 결정 된다는 문자 스크립트에 속해 있습니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-104">Font fallback means that the system determines what script the character belongs to.</span></span>

## <a name="using-font-fallback"></a><span data-ttu-id="babf5-105">글꼴 대체 (fallback)를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="babf5-105">Using font fallback</span></span>

<span data-ttu-id="babf5-106">이 기능을 이용 하려면 설정 하지 않습니다는 <xref:System.Drawing.Font> 속성 폼 이나 다른 요소에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-106">To take advantage of this feature, don't set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="babf5-107">응용 프로그램에는 다른 운영 체제의 한 지역화 된 언어에서 다른 기본 시스템 글꼴을 자동으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="babf5-108">응용 프로그램이 실행 되 면 시스템 운영 체제에서 선택 된 문화권에 대 한 올바른 글꼴을 자동으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>

<span data-ttu-id="babf5-109">글꼴, 글꼴 스타일을 변경 하기 위한 경우를 설정 하지 않는 규칙에 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-109">There's an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="babf5-110">이는 사용자는 굵은 글꼴 텍스트 상자에 텍스트를 표시 하려면 단추를 클릭 하는 응용 프로그램에 대 한 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="babf5-111">이렇게 하려면 폼의 글꼴을 굵게, 입력란의 글꼴 스타일을 변경 하는 함수를 작성할 것 있습니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="babf5-112">두 위치에서이 함수를 호출 해야: 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 및는 <xref:System.Windows.Forms.Control.FontChanged> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-112">It's important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="babf5-113">경우에 함수가 호출 되는 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 및 코드의 다른 부분에는 전체 폼의 글꼴 패밀리 변경 내용, 텍스트 상자 폼의 나머지 부분과 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box doesn't change with the rest of the form.</span></span>

```vb
Private Sub MakeBold()
   ' Change the TextBox to a bold version of the form font
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)
End Sub

Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
   ' Clicking this button makes the TextBox bold
   MakeBold()
End Sub

Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged
   ' If the TextBox is already bold and the form's font changes,
   ' change the TextBox to a bold version of the new form font
   If (TextBox1.Font.Style = FontStyle.Bold) Then
      MakeBold()
   End If
End Sub
```

```csharp
private void button1_Click(object sender, System.EventArgs e)
{
   // Clicking this button makes the TextBox bold
   MakeBold();
}

private void MakeBold()
{
   // Change the TextBox to a bold version of the form's font
   textBox1.Font = new Font(this.Font, FontStyle.Bold);
}

private void Form1_FontChanged(object sender, System.EventArgs e)
{
   // If the TextBox is already bold and the form's font changes,
   // change the TextBox to a bold version of the new form font
   if (textBox1.Font.Style == FontStyle.Bold)
   {
      MakeBold();
   }
}
```

<span data-ttu-id="babf5-114">그러나 응용 프로그램을 지역화할 굵은 글꼴 표시 될 수 있다는 불완전 하 게 특정 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="babf5-115">중요 하지 않은 경우 원하는 굵은 글꼴을 일반 텍스트로 전환의 수를 지역화 합니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="babf5-116">지역화 되지 개발자는 일반적으로 소스 코드에 액세스할 수 없는 이므로 리소스 파일에만이 옵션 설정 해야 리소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-116">Since localizers are typically not developers and don't have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="babf5-117">이 위해 설정한는 <xref:System.Drawing.Font.Bold%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="babf5-118">따라서 지역화 담당자 편집할 수 있는 리소스 파일에 작성 되 고 글꼴 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="babf5-119">다음 뒤에 코드를 작성은 `InitializeComponent` 글꼴 다시 설정 하는 메서드를 폼의 글꼴을 기반으로 하지만 리소스 파일에 지정 된 글꼴 스타일을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="babf5-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a><span data-ttu-id="babf5-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="babf5-120">See also</span></span>

[<span data-ttu-id="babf5-121">Windows Forms 응용 프로그램 전역화</span><span class="sxs-lookup"><span data-stu-id="babf5-121">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)  
[<span data-ttu-id="babf5-122">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="babf5-122">Using Fonts and Text</span></span>](using-fonts-and-text.md)