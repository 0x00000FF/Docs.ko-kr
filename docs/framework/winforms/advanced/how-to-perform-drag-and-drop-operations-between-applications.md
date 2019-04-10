---
title: '방법: 애플리케이션 간에 끌어서 놓기 작업 수행'
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms], between applications
ms.assetid: fa347436-2b12-4dd6-8507-59d7241f6a06
ms.openlocfilehash: 9aac3a0efd6359c25a6972f0e0b52dd489ec31db
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59327531"
---
# <a name="how-to-perform-drag-and-drop-operations-between-applications"></a><span data-ttu-id="7bcbe-102">방법: 애플리케이션 간에 끌어서 놓기 작업 수행</span><span class="sxs-lookup"><span data-stu-id="7bcbe-102">How to: Perform Drag-and-Drop Operations Between Applications</span></span>
<span data-ttu-id="7bcbe-103">응용 프로그램 간 끌어서 놓기 작업 수행은 두 응용 프로그램이 <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> 및 <xref:System.Windows.Forms.DragEventArgs.Effect%2A> 속성 간에 설정된 “계약"에 따른 행동을 포함하는 경우 응용 프로그램 내에서 이 작업을 사용하도록 설정하는 방법과 다르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-103">Performing drag-and-drop operations between applications is no different than enabling this action within an application, as long as both applications involved behave according to the "contract" established between the <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> and <xref:System.Windows.Forms.DragEventArgs.Effect%2A> properties.</span></span>  
  
 <span data-ttu-id="7bcbe-104">다음 절차에서는 생성한 Windows 기반 응용 프로그램 및 응용 프로그램 간 끌어서 놓기 작업을 수행하는 Windows 운영 체제에 포함된 워드 패드 워드 프로세서를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-104">In the following procedure, you will use a Windows-based application you create and the WordPad word processor that is included with the Windows operating system to perform drag-and-drop operations between applications.</span></span> <span data-ttu-id="7bcbe-105">워드 패드는 끌어서 놓기 작업을 성공적으로 완료하도록 효과를 수행하기 위한 코트를 작성하는 Windows 기반 응용 프로그램인 텍스트 끌어서 놓기 효과를 허용하는 특정 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-105">WordPad has a certain set of allowed effects for text being dragged and dropped; the Windows-based application you will write code for will work with these effects so that drag-and-drop operations may be completed successfully.</span></span>  
  
### <a name="to-perform-a-drag-and-drop-procedure-between-applications"></a><span data-ttu-id="7bcbe-106">응용 프로그램 간에 끌어서 놓기 프로시저를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="7bcbe-106">To perform a drag-and-drop procedure between applications</span></span>  
  
1. <span data-ttu-id="7bcbe-107">새 Windows Forms 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-107">Create a new Windows Forms application.</span></span>  
  
2. <span data-ttu-id="7bcbe-108">폼에 <xref:System.Windows.Forms.TextBox> 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-108">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
3. <span data-ttu-id="7bcbe-109">놓은 데이터를 받으려면 <xref:System.Windows.Forms.TextBox> 컨트롤을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-109">Configure the <xref:System.Windows.Forms.TextBox> control to receive dropped data.</span></span>  
  
     <span data-ttu-id="7bcbe-110">자세한 내용은 [연습: Windows Forms에서 끌어서 놓기 작업 수행](walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-110">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
4. <span data-ttu-id="7bcbe-111">Windows 기반 응용 프로그램을 실행하고 응용 프로그램이 실행되는 동안 워드패드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-111">Run your Windows-based application, and while the application is running, run WordPad.</span></span>  
  
     <span data-ttu-id="7bcbe-112">워드패드는 끌어서 놓기 작업을 허용하는 Windows에 설치된 텍스트 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-112">WordPad is a text editor installed by Windows that allows drag-and-drop operations.</span></span> <span data-ttu-id="7bcbe-113">키를 눌러 액세스할 수는 **시작** 단추를 선택 하 **실행**를 입력 하 고 다음 `WordPad` 의 텍스트 상자에는 **실행** 대화 상자 및 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-113">It is accessible by pressing the **Start** button, selecting **Run**, and then typing `WordPad` into the text box of the **Run** dialog box and clicking **OK**.</span></span>  
  
5. <span data-ttu-id="7bcbe-114">워드 패드를 열면 텍스트 문자열을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-114">Once WordPad is open, type a string of text into it.</span></span>  
  
6. <span data-ttu-id="7bcbe-115">마우스를 사용하여 텍스트를 선택한 다음 Windows 기반 응용 프로그램에 <xref:System.Windows.Forms.TextBox> 컨트롤 위로 선택한 텍스트를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-115">Using the mouse, select the text, and then drag the selected text over to the <xref:System.Windows.Forms.TextBox> control in your Windows-based application.</span></span>  
  
     <span data-ttu-id="7bcbe-116"><xref:System.Windows.Forms.TextBox> 컨트롤(결과적으로 <xref:System.Windows.Forms.Control.DragEnter> 이벤트 발생), 커서 변경 사항 위로 마우스를 이동한 경우 참조하여 <xref:System.Windows.Forms.TextBox> 컨트롤에서 선택한 텍스트를 놓을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-116">Observe that when you mouse over the <xref:System.Windows.Forms.TextBox> control (and, consequently, raise the <xref:System.Windows.Forms.Control.DragEnter> event), the cursor changes, and you can drop the selected text into the <xref:System.Windows.Forms.TextBox> control.</span></span>  
  
     <span data-ttu-id="7bcbe-117">또한 워드 패드에 끌어서 놓는 텍스트 스트링을 허용하기 위한 <xref:System.Windows.Forms.TextBox> 컨트롤을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-117">Additionally, you can configure your <xref:System.Windows.Forms.TextBox> control to allow text strings to be dragged and dropped into WordPad.</span></span> <span data-ttu-id="7bcbe-118">자세한 내용은 [연습: Windows Forms에서 끌어서 놓기 작업 수행](walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcbe-118">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bcbe-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="7bcbe-119">See also</span></span>

- [<span data-ttu-id="7bcbe-120">방법: 클립보드에 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="7bcbe-120">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="7bcbe-121">방법: 클립보드에서 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="7bcbe-121">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="7bcbe-122">끌어서 놓기 작업 및 클립보드 지원</span><span class="sxs-lookup"><span data-stu-id="7bcbe-122">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
