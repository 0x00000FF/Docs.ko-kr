---
title: '방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에 열 추가'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: e82fbcf63047873ebc6e5c40b8b9fbeb14a672e5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038178"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="79c53-102">방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="79c53-102">How to: Add Columns to the Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="79c53-103">Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤은 **자세히** 보기에서 각 목록 항목에 대해 여러 열을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79c53-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item when in the **Details** view.</span></span> <span data-ttu-id="79c53-104">열을 사용 하 여 각 목록 항목에 대 한 여러 유형의 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79c53-104">You can use the columns to display several types of information about each list item.</span></span> <span data-ttu-id="79c53-105">예를 들어 파일 목록에 파일 이름, 파일 형식, 크기 및 파일을 마지막으로 수정한 날짜를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79c53-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="79c53-106">열을 만든 [후 해당 열을 채우는 방법에 대 한 자세한 내용은 방법: Windows Forms ListView 컨트롤](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)을 사용 하 여 열에 하위 항목을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c53-106">For information on populating the columns once they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>

<span data-ttu-id="79c53-107">다음 절차에는 <xref:System.Windows.Forms.ListView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c53-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="79c53-108">이러한 프로젝트 [를 설정 하는 방법에 대 한 자세한 내용은 방법: Windows Forms 응용 프로그램 프로젝트](/visualstudio/ide/step-1-create-a-windows-forms-application-project) [를 만들고 방법: Windows Forms](how-to-add-controls-to-windows-forms.md)에 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c53-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>


### <a name="to-add-columns-in-the-designer"></a><span data-ttu-id="79c53-109">디자이너에서 열을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="79c53-109">To add columns in the designer</span></span>

1. <span data-ttu-id="79c53-110">**속성** 창에서 컨트롤의 <xref:System.Windows.Forms.ListView.View%2A> 속성을로 <xref:System.Windows.Forms.View.Details>설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c53-110">In the **Properties** window, set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

2. <span data-ttu-id="79c53-111">속성 창 에서 ![ <xref:System.Windows.Forms.ListView.Columns%2A> 속성 옆에 있는 줄임표 단추 (Visual Studio](./media/visual-studio-ellipsis-button.png)속성 창의 줄임표 단추 (...)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c53-111">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>

     <span data-ttu-id="79c53-112">**ColumnHeader 컬렉션 편집기** 가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="79c53-112">The **ColumnHeader Collection Editor** appears.</span></span>

3. <span data-ttu-id="79c53-113">**추가** 단추를 사용 하 여 새 열을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c53-113">Use the **Add** button to add new columns.</span></span> <span data-ttu-id="79c53-114">그런 다음 열 머리글을 선택 하 고 해당 텍스트 (열의 캡션), 텍스트 맞춤 및 너비를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79c53-114">You can then select the column header and set its text (the caption of the column), text alignment, and width.</span></span>

## <a name="see-also"></a><span data-ttu-id="79c53-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="79c53-115">See also</span></span>

- [<span data-ttu-id="79c53-116">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="79c53-116">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="79c53-117">방법: Windows Forms ListView 컨트롤을 사용 하 여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="79c53-117">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="79c53-118">방법: Windows Forms ListView 컨트롤을 사용 하 여 열에 하위 항목 표시</span><span class="sxs-lookup"><span data-stu-id="79c53-118">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="79c53-119">방법: Windows Forms ListView 컨트롤의 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="79c53-119">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="79c53-120">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가 (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="79c53-120">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
