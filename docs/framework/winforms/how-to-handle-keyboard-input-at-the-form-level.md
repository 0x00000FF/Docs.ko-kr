---
title: '방법: 양식 수준에서 키보드 입력 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input [Windows Forms], at form level
- Windows Forms, handling keyboard input
- keyboards [Windows Forms], form-level input
ms.assetid: d7f8b390-dc91-42d2-ae0f-2ffa388127ad
ms.openlocfilehash: 8e346c5b69c507307d459f6246e26a6a96bb9e24
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591306"
---
# <a name="how-to-handle-keyboard-input-at-the-form-level"></a><span data-ttu-id="de800-102">방법: 양식 수준에서 키보드 입력 처리</span><span class="sxs-lookup"><span data-stu-id="de800-102">How to: Handle Keyboard Input at the Form Level</span></span>
<span data-ttu-id="de800-103">Windows Forms에서는 메시지가 컨트롤에 도달하기 전에 폼 수준에서 키보드 메시지를 처리하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="de800-103">Windows Forms provides the ability to handle keyboard messages at the form level, before the messages reach a control.</span></span> <span data-ttu-id="de800-104">이 항목에서는 다음 작업을 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de800-104">This topic shows how to accomplish this task.</span></span>  
  
### <a name="to-handle-a-keyboard-message-at-the-form-level"></a><span data-ttu-id="de800-105">폼 수준에서 키보드 메시지를 처리하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="de800-105">To handle a keyboard message at the form level</span></span>  
  
- <span data-ttu-id="de800-106">시작 폼의 <xref:System.Windows.Forms.Control.KeyPress> 또는 <xref:System.Windows.Forms.Control.KeyDown> 이벤트를 처리하고 키보드 메시지가 폼의 컨트롤에 도달하기 전에 폼이 이 메시지를 수신하도록 폼의 <xref:System.Windows.Forms.Form.KeyPreview%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="de800-106">Handle the <xref:System.Windows.Forms.Control.KeyPress> or <xref:System.Windows.Forms.Control.KeyDown> event of the startup form, and set the <xref:System.Windows.Forms.Form.KeyPreview%2A> property of the form to `true` so that keyboard messages are received by the form before they reach any controls on the form.</span></span> <span data-ttu-id="de800-107">다음 코드 예제에서는 모든 숫자 키를 감지하고 '1', '4', '7'을 사용하여 the <xref:System.Windows.Forms.Control.KeyPress> 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="de800-107">The following code example handles the <xref:System.Windows.Forms.Control.KeyPress> event by detecting all of the number keys and consuming '1', '4', and '7'.</span></span>  
  
     [!code-cpp[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="de800-108">예제</span><span class="sxs-lookup"><span data-stu-id="de800-108">Example</span></span>  
 <span data-ttu-id="de800-109">다음 코드 예제는 위 예제에 대한 전체 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="de800-109">The following code example is the entire application for the above example.</span></span> <span data-ttu-id="de800-110">응용 프로그램에는 <xref:System.Windows.Forms.TextBox>에서 포커스를 이동할 수 있도록 하는 여러 가지 다른 컨트롤과 함께 <xref:System.Windows.Forms.TextBox>가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="de800-110">The application includes a <xref:System.Windows.Forms.TextBox> along with several other controls that allow you to move focus from the <xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="de800-111">기본 <xref:System.Windows.Forms.Form>의 <xref:System.Windows.Forms.Control.KeyPress> 이벤트는 '1', '4', '7'을 사용하고 <xref:System.Windows.Forms.TextBox>의 <xref:System.Windows.Forms.Control.KeyPress> 이벤트는 '2', '5', '8'을 사용하면서 나머지 키를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="de800-111">The <xref:System.Windows.Forms.Control.KeyPress> event of the main <xref:System.Windows.Forms.Form> consumes '1', '4', and '7', and the <xref:System.Windows.Forms.Control.KeyPress> event of the <xref:System.Windows.Forms.TextBox> consumes '2', '5', and '8' while displaying the remaining keys.</span></span> <span data-ttu-id="de800-112">포커스가 <xref:System.Windows.Forms.TextBox>에 있을 때 <xref:System.Windows.Forms.MessageBox> 출력과 포커스가 다른 컨트롤의 하나에 있는 동안 숫자 키를 누를 때 <xref:System.Windows.Forms.MessageBox> 출력을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="de800-112">Compare the <xref:System.Windows.Forms.MessageBox> output when you press a number key while the <xref:System.Windows.Forms.TextBox> has focus with the <xref:System.Windows.Forms.MessageBox> output when you press a number key while focus is on one of the other controls.</span></span>  
  
 [!code-cpp[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="de800-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="de800-113">Compiling the Code</span></span>  
 <span data-ttu-id="de800-114">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="de800-114">This example requires:</span></span>  
  
- <span data-ttu-id="de800-115">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="de800-115">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="de800-116">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="de800-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="de800-117">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de800-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  

## <a name="see-also"></a><span data-ttu-id="de800-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="de800-118">See also</span></span>

- [<span data-ttu-id="de800-119">Windows Forms 응용 프로그램의 키보드 입력</span><span class="sxs-lookup"><span data-stu-id="de800-119">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
