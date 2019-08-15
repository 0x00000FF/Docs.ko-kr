---
title: '방법: 디자이너를 사용하여 Windows Forms 패널 컨트롤에서 컨트롤 그룹화'
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: cadfa715b140c63b216ec0ca2e6d6a6589ae3458
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040383"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="4a95d-102">방법: 디자이너를 사용하여 Windows Forms 패널 컨트롤에서 컨트롤 그룹화</span><span class="sxs-lookup"><span data-stu-id="4a95d-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="4a95d-103">Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 다른 컨트롤을 그룹화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a95d-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="4a95d-104">컨트롤을 그룹화 하는 이유는 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a95d-104">There are three reasons to group controls.</span></span> <span data-ttu-id="4a95d-105">하나는 일반 사용자 인터페이스에 대 한 관련 폼 요소의 시각적 그룹화입니다. 또 다른 예로는 라디오 단추와 같은 프로그래밍 방식 그룹화가 있습니다. 마지막은 디자인 타임에 컨트롤을 하나의 단위로 이동 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4a95d-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>

## <a name="to-create-a-group-of-controls"></a><span data-ttu-id="4a95d-106">컨트롤 그룹을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4a95d-106">To create a group of controls</span></span>

1. <span data-ttu-id="4a95d-107">도구 상자 <xref:System.Windows.Forms.Panel> 의 **Windows Forms** 탭에서 컨트롤을 폼으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="4a95d-107">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>

2. <span data-ttu-id="4a95d-108">패널에 다른 컨트롤을 추가 하 고 패널 내부에 그립니다.</span><span class="sxs-lookup"><span data-stu-id="4a95d-108">Add other controls to the panel, drawing each inside the panel.</span></span>

     <span data-ttu-id="4a95d-109">패널에 포함 하려는 기존 컨트롤이 있는 경우 모든 컨트롤을 선택 하 고 클립보드로 잘라내고 <xref:System.Windows.Forms.Panel> 컨트롤을 선택한 다음 패널에 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a95d-109">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="4a95d-110">이러한 항목을 패널로 끌어올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a95d-110">You can also drag them into the panel.</span></span>

3. <span data-ttu-id="4a95d-111">필드 패널에 테두리를 추가 하려면 해당 <xref:System.Windows.Forms.BorderStyle> 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a95d-111">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="4a95d-112"><xref:System.Windows.Forms.BorderStyle.Fixed3D> ,<xref:System.Windows.Forms.BorderStyle.FixedSingle>및 의<xref:System.Windows.Forms.BorderStyle.None>세 가지 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a95d-112">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a95d-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="4a95d-113">See also</span></span>

- [<span data-ttu-id="4a95d-114">Panel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="4a95d-114">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="4a95d-115">Panel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="4a95d-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="4a95d-116">방법: 패널의 배경 설정</span><span class="sxs-lookup"><span data-stu-id="4a95d-116">How to: Set the Background of a Panel</span></span>](how-to-set-the-background-of-a-windows-forms-panel.md)
