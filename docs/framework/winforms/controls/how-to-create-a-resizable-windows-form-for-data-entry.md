---
title: '방법: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms], resizing
- forms [Windows Forms], creating resizable
- Windows Forms, resizable
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
ms.openlocfilehash: a319fba43c6735cd5552dd71d1fb614a6192da97
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43563199"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a><span data-ttu-id="afc89-102">방법: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기</span><span class="sxs-lookup"><span data-stu-id="afc89-102">How to: Create a Resizable Windows Form for Data Entry</span></span>
<span data-ttu-id="afc89-103">좋은 레이아웃은 부모 폼의 크기 변경에 제대로 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="afc89-103">A good layout responds well to changes in the dimensions of its parent form.</span></span> <span data-ttu-id="afc89-104"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 통해 폼의 레이아웃을 정렬하면 폼 크기가 변경될 때 일관된 방식으로 컨트롤의 크기를 조정하고 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc89-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to arrange the layout of your form to resize and position your controls in a consistent way as the form's dimensions change.</span></span> <span data-ttu-id="afc89-105"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 컨트롤의 콘텐츠 변경으로 인해 레이아웃이 변경되는 경우에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="afc89-105">The <xref:System.Windows.Forms.TableLayoutPanel> control is also useful when changes in the contents of your controls cause changes in the layout.</span></span> <span data-ttu-id="afc89-106">이 절차에서 설명하는 프로세스는 Visual Studio 환경 내에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc89-106">The process covered in this procedure can be done within the Visual Studio environment.</span></span>  <span data-ttu-id="afc89-107">또한 [연습: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기](https://msdn.microsoft.com/library/991eahec\(v=vs.110\))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="afc89-107">Also see [Walkthrough: Creating a Resizable Windows Form for Data Entry](https://msdn.microsoft.com/library/991eahec\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="afc89-108">예제</span><span class="sxs-lookup"><span data-stu-id="afc89-108">Example</span></span>  
 <span data-ttu-id="afc89-109">다음 예제에서는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 통해 사용자가 폼 크기를 조정할 때 제대로 대응하는 레이아웃을 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="afc89-109">The following example demonstrates how to use a <xref:System.Windows.Forms.TableLayoutPanel> control to build a layout that responds well when the user resizes the form.</span></span> <span data-ttu-id="afc89-110">또한 지역화에 제대로 대응하는 레이아웃을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="afc89-110">It also demonstrates a layout that responds well to localization.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="afc89-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="afc89-111">Compiling the Code</span></span>  
 <span data-ttu-id="afc89-112">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="afc89-112">This example requires:</span></span>  
  
-   <span data-ttu-id="afc89-113">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="afc89-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="afc89-114">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="afc89-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="afc89-115">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc89-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="afc89-116">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="afc89-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afc89-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="afc89-117">See Also</span></span>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="afc89-118">방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="afc89-118">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="afc89-119">방법: 지역화에 적합한 Windows Forms 레이아웃 디자인</span><span class="sxs-lookup"><span data-stu-id="afc89-119">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [<span data-ttu-id="afc89-120">Microsoft Windows 사용자 환경, 사용자 인터페이스 개발자 및 디자이너를 위한 공식 지침. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)</span><span class="sxs-lookup"><span data-stu-id="afc89-120">Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)</span></span>](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)
