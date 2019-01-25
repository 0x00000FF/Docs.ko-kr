---
title: '방법: Windows Forms 컨트롤에서 사용자 입력된 이벤트를 처리 합니다.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, user input
- user input [Windows Forms], Windows Forms controls
ms.assetid: 3de74dcf-fae3-42d0-92b5-bc04a61a6888
ms.openlocfilehash: ae4a6f7087c82be6531a91980e2fee0108298a46
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738711"
---
# <a name="how-to-handle-user-input-events-in-windows-forms-controls"></a><span data-ttu-id="f3642-102">방법: Windows Forms 컨트롤에서 사용자 입력된 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3642-102">How to: Handle User Input Events in Windows Forms Controls</span></span>
<span data-ttu-id="f3642-103">이 예제에서는 Windows Forms 컨트롤에서 발생할 수 있는 대부분의 키보드, 마우스, 포커스 및 유효성 검사 이벤트를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3642-103">This example demonstrates how to handle most keyboard, mouse, focus, and validation events that can occur in a Windows Forms control.</span></span> <span data-ttu-id="f3642-104">포커스가 있을 경우 `TextBoxInput`이라는 텍스트 상자가 이벤트를 수신하며, 각 이벤트에 대한 정보가 이벤트 발생 순서대로 `TextBoxOutput`이라는 텍스트 상자에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3642-104">The text box named `TextBoxInput` receives the events when it has focus, and information about each event is written in the text box named `TextBoxOutput` in the order in which the events are raised.</span></span> <span data-ttu-id="f3642-105">애플리케이션에는 보고할 이벤트를 필터링하는 데 사용할 수 있는 확인란 집합도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3642-105">The application also includes a set of check boxes that can be used to filter which events to report.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3642-106">예제</span><span class="sxs-lookup"><span data-stu-id="f3642-106">Example</span></span>  
 [!code-cpp[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f3642-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f3642-107">Compiling the Code</span></span>  
 <span data-ttu-id="f3642-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f3642-108">This example requires:</span></span>  
  
-   <span data-ttu-id="f3642-109">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="f3642-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="f3642-110">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3642-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="f3642-111">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3642-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="f3642-112">또한 참조 [방법: 컴파일 및 Visual Studio를 사용 하 여 전체 Windows Forms 코드 예제를 실행](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="f3642-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3642-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="f3642-113">See also</span></span>
- [<span data-ttu-id="f3642-114">Windows Forms에 사용자 입력</span><span class="sxs-lookup"><span data-stu-id="f3642-114">User Input in Windows Forms</span></span>](../../../docs/framework/winforms/user-input-in-windows-forms.md)
