---
title: '방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 순서 변경'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: 7ada2124c0cfb1a14d757963f186da90c553470e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855507"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="0a631-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 순서 변경</span><span class="sxs-lookup"><span data-stu-id="0a631-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="0a631-103">Windows Forms 바인딩하면 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 소스를 자동으로 생성 된 열의 표시 순서는 데이터 원본에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a631-103">When you bind a Windows Forms <xref:System.Windows.Forms.DataGridView> control to a data source, the display order of the automatically generated columns is dictated by the data source.</span></span> <span data-ttu-id="0a631-104">이 순서를 원하는 경우에 디자이너를 사용 하 여 열의 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a631-104">If this order is not what you prefer, you can change the order of the columns using the designer.</span></span> <span data-ttu-id="0a631-105">컨트롤에 바인딩되지 않은 열을 추가 및 표시 순서를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a631-105">You may also want to add unbound columns to the control and change their display order.</span></span> <span data-ttu-id="0a631-106">열 순서를 프로그래밍 방식으로 변경 하는 방법에 대 한 정보를 참조 하세요 [방법: Windows Forms DataGridView 컨트롤에서 열 순서 변경](../../../../docs/framework/winforms/controls/how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a631-106">For information about how to change the column order programmatically, see [How to: Change the Order of Columns in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="0a631-107">다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a631-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0a631-108">이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows 응용 프로그램 프로젝트를 만듭니다](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a631-108">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a631-109">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a631-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0a631-110">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a631-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0a631-111">자세한 내용은 참조 하세요. [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)</span><span class="sxs-lookup"><span data-stu-id="0a631-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)</span></span>  
  
### <a name="to-change-the-column-order-using-the-designer"></a><span data-ttu-id="0a631-112">디자이너를 사용 하 여 열 순서를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="0a631-112">To change the column order using the designer</span></span>  
  
1.  <span data-ttu-id="0a631-113">스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택한 후 **열 편집**합니다.</span><span class="sxs-lookup"><span data-stu-id="0a631-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="0a631-114">열을 선택 합니다 **선택한 열** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0a631-114">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="0a631-115">위쪽 또는 아래쪽 화살표 오른쪽에는 **선택한 열** 원하는 위치에서 선택한 열을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a631-115">Click the up or down arrow to the right of the **Selected Columns** list until the selected column is in the position you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a631-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a631-116">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="0a631-117">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="0a631-117">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="0a631-118">방법: Windows 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="0a631-118">How to: Create a Windows Application Project</span></span>](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="0a631-119">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="0a631-119">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
