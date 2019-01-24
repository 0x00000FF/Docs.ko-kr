---
title: '방법: Windows Forms Label 컨트롤을 사용 하 여 액세스 키 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: a1317f34b39c5689e285f8822fff9bfcc42db1d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680324"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a><span data-ttu-id="2d55b-102">방법: Windows Forms Label 컨트롤을 사용 하 여 액세스 키 만들기</span><span class="sxs-lookup"><span data-stu-id="2d55b-102">How to: Create Access Keys with Windows Forms Label Controls</span></span>
<span data-ttu-id="2d55b-103">Windows Forms <xref:System.Windows.Forms.Label> 다른 컨트롤에 대 한 액세스 키를 정의 하려면 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d55b-103">Windows Forms <xref:System.Windows.Forms.Label> controls can be used to define access keys for other controls.</span></span> <span data-ttu-id="2d55b-104">Label 컨트롤의 액세스 키를 정의할 때 사용자 ALT 키와 탭 순서에서 오는 컨트롤에 포커스를 이동 하도록 지정 하는 문자를 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d55b-104">When you define an access key in a label control, the user can press the ALT key plus the character you designate to move the focus to the control that follows it in the tab order.</span></span> <span data-ttu-id="2d55b-105">레이블 포커스를 받을 수 없습니다 때문에 포커스가 탭 순서의 다음 컨트롤로 자동으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d55b-105">Because labels cannot receive focus, focus automatically moves to the next control in the tab order.</span></span> <span data-ttu-id="2d55b-106">이 기술을 사용 하 여 액세스 키 텍스트 상자, 콤보 상자, 목록 상자 및 데이터 표를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d55b-106">Use this technique to assign access keys to text boxes, combo boxes, list boxes, and data grids.</span></span>  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a><span data-ttu-id="2d55b-107">레이블 컨트롤에 액세스 키를 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="2d55b-107">To assign an access key to a control with a label</span></span>  
  
1.  <span data-ttu-id="2d55b-108">레이블을 먼저 그린 하 한 다음 다른 컨트롤을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="2d55b-108">Draw the label first, and then draw the other control.</span></span>  
  
     <span data-ttu-id="2d55b-109">또는</span><span class="sxs-lookup"><span data-stu-id="2d55b-109">-or-</span></span>  
  
     <span data-ttu-id="2d55b-110">순서에 관계 없이 컨트롤을 그리고 설정 된 <xref:System.Windows.Forms.Control.TabIndex%2A> 다른 컨트롤 보다 1 작은 레이블의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2d55b-110">Draw the controls in any order and set the <xref:System.Windows.Forms.Control.TabIndex%2A> property of the label to one less than the other control.</span></span>  
  
2.  <span data-ttu-id="2d55b-111">레이블 설정 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="2d55b-111">Set the label's <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="2d55b-112">앰퍼샌드 (&) 레이블의에서 <xref:System.Windows.Forms.Label.Text%2A> 레이블에 대 한 액세스 키를 할당 하는 속성.</span><span class="sxs-lookup"><span data-stu-id="2d55b-112">Use an ampersand (&) in the label's <xref:System.Windows.Forms.Label.Text%2A> property to assign the access key for the label.</span></span> <span data-ttu-id="2d55b-113">자세한 내용은 [만드는 액세스 키에 대 한 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2d55b-113">For more information, see [Creating Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2d55b-114">액세스 키를 만드는 데 사용할 하는 것이 아니라 레이블 컨트롤에서 앰퍼샌드를 표시 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d55b-114">You may want to display ampersands in a label control, rather than use them to create access keys.</span></span> <span data-ttu-id="2d55b-115">이 데이터는 앰퍼샌드를 포함 하는 위치 레코드 집합에서 필드 레이블 컨트롤을 바인딩하는 경우 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d55b-115">This may occur if you bind a label control to a field in a recordset where the data includes ampersands.</span></span> <span data-ttu-id="2d55b-116">앰퍼샌드 레이블 컨트롤에 표시할 설정 합니다 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="2d55b-116">To display ampersands in a label control, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `false`.</span></span> <span data-ttu-id="2d55b-117">앰퍼샌드를 표시 하 고 액세스 키를 갖게 하려는 경우 설정 합니다 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `true` 하나의 앰퍼샌드를 사용 하 여 액세스 키를 보여 주고 (&) 및 앰퍼샌드를 앰퍼샌드를 두 번 표시할입니다.</span><span class="sxs-lookup"><span data-stu-id="2d55b-117">If you wish to display ampersands and also have an access key, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true` and indicate the access key with one ampersand (&) and the ampersand to display with two ampersands.</span></span>  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2d55b-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="2d55b-118">See also</span></span>
- [<span data-ttu-id="2d55b-119">방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정</span><span class="sxs-lookup"><span data-stu-id="2d55b-119">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="2d55b-120">Label 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="2d55b-120">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)
- [<span data-ttu-id="2d55b-121">레이블 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2d55b-121">Label Control</span></span>](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
