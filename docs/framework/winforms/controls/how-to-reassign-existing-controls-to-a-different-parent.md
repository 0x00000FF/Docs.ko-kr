---
title: '방법: 다른 부모에 기존 컨트롤 다시 할당'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: 113afc642ca313f10062a496d2f170e3666d5043
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162246"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="67029-102">방법: 다른 부모에 기존 컨트롤 다시 할당</span><span class="sxs-lookup"><span data-stu-id="67029-102">How to: Reassign Existing Controls to a Different Parent</span></span>
<span data-ttu-id="67029-103">폼에 있는 컨트롤을 새 컨테이너 컨트롤에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67029-103">You can assign controls that exist on your form to a new container control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67029-104">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67029-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="67029-105">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67029-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="67029-106">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67029-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="67029-107">기존 컨트롤을 다른 부모에 다시 할당하려면</span><span class="sxs-lookup"><span data-stu-id="67029-107">To reassign existing controls to a different parent</span></span>  
  
1.  <span data-ttu-id="67029-108"><xref:System.Windows.Forms.Button> 도구 상자 **의 세** 컨트롤을 폼으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="67029-108">Drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span>  
  
     <span data-ttu-id="67029-109">서로 정렬되지 않은 상태로 근처에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="67029-109">Position them near to each other, but leave them unaligned.</span></span>  
  
2.  <span data-ttu-id="67029-110">**도구 상자**에서 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="67029-110">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span>  
  
     <span data-ttu-id="67029-111">아이콘을 폼으로 끌어오지 마세요.</span><span class="sxs-lookup"><span data-stu-id="67029-111">Do not drag the icon onto the form.</span></span>  
  
3.  <span data-ttu-id="67029-112">마우스 포인터를 세 <xref:System.Windows.Forms.Button> 컨트롤 쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="67029-112">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
     <span data-ttu-id="67029-113">포인터가 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤 아이콘이 연결된 십자형으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="67029-113">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>  
  
4.  <span data-ttu-id="67029-114">마우스 단추를 길게 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="67029-114">Click and hold the mouse button.</span></span>  
  
5.  <span data-ttu-id="67029-115">마우스 포인터를 끌어 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤의 윤곽선을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="67029-115">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
6.  <span data-ttu-id="67029-116">세 <xref:System.Windows.Forms.Button> 컨트롤 주위에 윤곽선을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="67029-116">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
7.  <span data-ttu-id="67029-117">마우스 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="67029-117">Release the mouse button.</span></span>  
  
     <span data-ttu-id="67029-118">이제 세 <xref:System.Windows.Forms.Button> 컨트롤이 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="67029-118">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67029-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="67029-119">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="67029-120">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="67029-120">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="67029-121">연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="67029-121">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="67029-122">연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="67029-122">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
