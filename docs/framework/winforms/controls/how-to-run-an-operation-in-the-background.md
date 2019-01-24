---
title: '방법: 백그라운드에서 작업 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
ms.openlocfilehash: 99567897c90244c2768dfbcfe36762d1ec54a070
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510639"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="dec31-102">방법: 백그라운드에서 작업 실행</span><span class="sxs-lookup"><span data-stu-id="dec31-102">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="dec31-103">완료하는 데 오랜 시간이 걸리는 작업이 있으며 사용자 인터페이스에서 지연이 발생되지 않게 하려는 경우 <xref:System.ComponentModel.BackgroundWorker> 클래스를 사용하여 다른 스레드에서 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec31-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="dec31-104">다음 코드 예제에서는 시간이 많이 걸리는 작업을 백그라운드에서 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dec31-104">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="dec31-105">양식에는 **시작** 및 **취소** 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec31-105">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="dec31-106">비동기 작업을 실행하려면 **시작** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dec31-106">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="dec31-107">비동기 작업 실행을 중지하려면 **취소** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dec31-107">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="dec31-108">각 작업의 결과가 <xref:System.Windows.Forms.MessageBox>에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dec31-108">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="dec31-109">Visual Studio에서는 이 작업이 광범위하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="dec31-109">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="dec31-110">또한 참조 [연습: 백그라운드에서 작업 실행](walkthrough-running-an-operation-in-the-background.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dec31-110">Also see [Walkthrough: Running an Operation in the Background](walkthrough-running-an-operation-in-the-background.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dec31-111">예제</span><span class="sxs-lookup"><span data-stu-id="dec31-111">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dec31-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="dec31-112">Compiling the Code</span></span>  
 <span data-ttu-id="dec31-113">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dec31-113">This example requires:</span></span>  
  
-   <span data-ttu-id="dec31-114">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="dec31-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="dec31-115">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dec31-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="dec31-116">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec31-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="dec31-117">또한 참조 [방법: 컴파일 및 Visual Studio를 사용 하 여 전체 Windows Forms 코드 예제를 실행](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="dec31-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dec31-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="dec31-118">See also</span></span>
- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="dec31-119">방법: 백그라운드 작업을 사용 하는 폼 구현</span><span class="sxs-lookup"><span data-stu-id="dec31-119">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="dec31-120">BackgroundWorker 구성 요소</span><span class="sxs-lookup"><span data-stu-id="dec31-120">BackgroundWorker Component</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
