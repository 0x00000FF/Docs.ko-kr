---
title: '방법: ToolStripContainer의 ToolStrip을 폼으로 이동'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: 6cc54264033eca541ce845b75d608087fee8a542
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532333"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="fe570-102">방법: ToolStripContainer의 ToolStrip을 폼으로 이동</span><span class="sxs-lookup"><span data-stu-id="fe570-102">How to: Move a ToolStrip Out of a ToolStripContainer onto a Form</span></span>
<span data-ttu-id="fe570-103">이동 하려면 다음 절차를 사용 하 여 한 <xref:System.Windows.Forms.ToolStrip> 부재 중는 <xref:System.Windows.Forms.ToolStripContainer> 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe570-103">Use the following procedure to move a <xref:System.Windows.Forms.ToolStrip> out of a <xref:System.Windows.Forms.ToolStripContainer> onto a form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe570-104">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe570-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fe570-105">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe570-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fe570-106">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe570-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="fe570-107">ToolStrip을 폼으로 ToolStripContainer 외부로 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="fe570-107">To move a ToolStrip out of a ToolStripContainer onto a form</span></span>  
  
1.  <span data-ttu-id="fe570-108"><xref:System.Windows.Forms.ToolStrip>를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe570-108">Select the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
2.  <span data-ttu-id="fe570-109">잘라내기는 <xref:System.Windows.Forms.ToolStrip> 에서 CTRL + X 키를 누르거나 마우스 오른쪽 단추로 클릭는 <xref:System.Windows.Forms.ToolStrip> 선택 **잘라내기** 상황에 맞는 메뉴입니다.</span><span class="sxs-lookup"><span data-stu-id="fe570-109">Cut the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+X, or right-click the <xref:System.Windows.Forms.ToolStrip> and choose **Cut** from the context menu.</span></span>  
  
3.  <span data-ttu-id="fe570-110">폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe570-110">Select the form.</span></span>  
  
4.  <span data-ttu-id="fe570-111">붙여넣기는 <xref:System.Windows.Forms.ToolStrip> 에서 CTRL + V를 누르거나 선택 **붙여넣기** 에서 **편집** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="fe570-111">Paste the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+V, or choose **Paste** from the **Edit** menu.</span></span>  
  
5.  <span data-ttu-id="fe570-112">설정의 <xref:System.Windows.Forms.ToolStrip.Dock%2A> 속성은 <xref:System.Windows.Forms.ToolStrip> 를 **Top**합니다.</span><span class="sxs-lookup"><span data-stu-id="fe570-112">Set the <xref:System.Windows.Forms.ToolStrip.Dock%2A> property of the <xref:System.Windows.Forms.ToolStrip> to **Top**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe570-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe570-113">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [<span data-ttu-id="fe570-114">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="fe570-114">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
