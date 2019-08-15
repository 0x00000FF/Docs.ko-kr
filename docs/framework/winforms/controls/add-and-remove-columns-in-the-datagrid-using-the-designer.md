---
title: '방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거'
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: d88d658b31c87e7ae89bfb4a11fe794bfbb0e848
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040103"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="ce842-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="ce842-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="ce842-103">Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤은 데이터를 표시 하기 위해 열을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce842-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="ce842-104">컨트롤을 수동으로 채울 계획인 경우 열을 직접 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce842-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="ce842-105">또는 데이터 소스에 컨트롤을 바인딩할 수 있습니다. 그러면 열이 자동으로 생성 되 고 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="ce842-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="ce842-106">데이터 원본에 표시 하려는 열 보다 많은 열이 포함 된 경우 원하지 않는 열을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce842-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>

 <span data-ttu-id="ce842-107">다음 절차에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce842-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="ce842-108">이러한 프로젝트 [를 설정 하는 방법에 대 한 자세한 내용은 방법: Windows Forms 응용 프로그램 프로젝트](/visualstudio/ide/step-1-create-a-windows-forms-application-project) [를 만들고 방법: Windows Forms](how-to-add-controls-to-windows-forms.md)에 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce842-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="ce842-109">디자이너를 사용 하 여 열을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="ce842-109">To add a column using the designer</span></span>

1. <span data-ttu-id="ce842-110"><xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 스마트 태그 문자 모양 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))을 클릭 한 다음 **열 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce842-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>

2. <span data-ttu-id="ce842-111">**열 추가** 대화 상자에서 데이터 **바인딩 열** 옵션을 선택 하 고 데이터 원본에서 열을 선택 하거나 **바인딩되지 않은 열** 옵션을 선택 하 고 제공 된 필드를 사용 하 여 열을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce842-111">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>

3. <span data-ttu-id="ce842-112">**추가** 단추를 클릭 하 여 열을 추가 하면 기존 열이 컨트롤 표시 영역을 아직 채우지 않은 경우 디자이너에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce842-112">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="ce842-113">컨트롤의 스마트 태그를 사용 하 여 액세스할 수 있는 **열 편집** 대화 상자에서 열 속성을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce842-113">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>

## <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="ce842-114">디자이너를 사용 하 여 열을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="ce842-114">To remove a column using the designer</span></span>

1. <span data-ttu-id="ce842-115">컨트롤의 스마트 태그에서 **열 편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce842-115">Choose **Edit Columns** from the control's smart tag.</span></span>

2. <span data-ttu-id="ce842-116">**선택한 열** 목록에서 열을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce842-116">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="ce842-117">**제거** 단추를 클릭 하 여 열을 삭제 하면 디자이너에서 해당 열이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="ce842-117">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce842-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="ce842-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="ce842-119">방법: Windows Forms 애플리케이션 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="ce842-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="ce842-120">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="ce842-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
