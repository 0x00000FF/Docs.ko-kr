---
title: "RadioButton 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 67befd973dec38628f97a0d3153c399d48c18305
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="radiobutton-control-overview-windows-forms"></a><span data-ttu-id="23f24-102">RadioButton 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="23f24-102">RadioButton Control Overview (Windows Forms)</span></span>
<span data-ttu-id="23f24-103">Windows Forms <xref:System.Windows.Forms.RadioButton> 컨트롤 사용자에 게 한 상호 배타적인 두 개 이상의 옵션 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="23f24-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controls present a set of two or more mutually exclusive choices to the user.</span></span> <span data-ttu-id="23f24-104">라디오 단추 및 확인란 유사한 기능 나타날 수 있습니다는 중요 한 차이점이: 동일한 그룹에 다른 라디오 단추도 선택할 수 없는 사용자가 라디오 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="23f24-104">While radio buttons and check boxes may appear to function similarly, there is an important difference: when a user selects a radio button, the other radio buttons in the same group cannot be selected as well.</span></span> <span data-ttu-id="23f24-105">반면에 임의 개수의 확인란을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23f24-105">In contrast, any number of check boxes can be selected.</span></span> <span data-ttu-id="23f24-106">라디오 단추 그룹 사용자 지정, "여기 하나만 선택할 수 있는 선택 항목 집합이".</span><span class="sxs-lookup"><span data-stu-id="23f24-106">Defining a radio button group tells the user, "Here is a set of choices from which you can choose one and only one."</span></span>  
  
## <a name="using-the-control"></a><span data-ttu-id="23f24-107">컨트롤을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="23f24-107">Using the Control</span></span>  
 <span data-ttu-id="23f24-108">때는 <xref:System.Windows.Forms.RadioButton> 컨트롤을 클릭 하 고, 해당 <xref:System.Windows.Forms.RadioButton.Checked%2A> 속성이로 설정 되어 `true` 및 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23f24-108">When a <xref:System.Windows.Forms.RadioButton> control is clicked, its <xref:System.Windows.Forms.RadioButton.Checked%2A> property is set to `true` and the <xref:System.Windows.Forms.Control.Click> event handler is called.</span></span> <span data-ttu-id="23f24-109"><xref:System.Windows.Forms.RadioButton.CheckedChanged> 이벤트가 발생할 때의 값은 <xref:System.Windows.Forms.RadioButton.Checked%2A> 속성 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="23f24-109">The <xref:System.Windows.Forms.RadioButton.CheckedChanged> event is raised when the value of the <xref:System.Windows.Forms.RadioButton.Checked%2A> property changes.</span></span> <span data-ttu-id="23f24-110">경우는 <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> 속성이 `true` (기본값) 라디오 단추를 선택 하면 그룹의 다른 모든 자동으로 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="23f24-110">If the <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> property is set to `true` (the default), when the radio button is selected all others in the group are automatically cleared.</span></span> <span data-ttu-id="23f24-111">이 속성은 대개로 설정 `false` 선택한 라디오 단추가 있는지 유효성 검사 코드를 사용 하는 경우 허용 되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="23f24-111">This property is usually only set to `false` when validation code is used to make sure the radio button selected is an allowable option.</span></span> <span data-ttu-id="23f24-112">으로 설정 된 컨트롤에 표시 되는 텍스트는 <xref:System.Windows.Forms.Control.Text%2A> 속성 선택 키를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23f24-112">The text displayed within the control is set with the <xref:System.Windows.Forms.Control.Text%2A> property, which can contain access key shortcuts.</span></span> <span data-ttu-id="23f24-113">선택 키를 선택 하면 컨트롤을 함께 ALT 키를 눌러 "클릭" 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23f24-113">An access key enables a user to "click" the control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="23f24-114">자세한 내용은 참조 [하는 방법: 만들 액세스 키에 대 한 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) 및 [하는 방법: Windows Forms 컨트롤에서 텍스트 표시 설정](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23f24-114">For more information, see [How to: Create Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) and [How to: Set the Text Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span>  
  
 <span data-ttu-id="23f24-115"><xref:System.Windows.Forms.RadioButton> 제어 하는 경우 눌러진을 선택 된 것으로 표시 되는 명령 단추 처럼 표시는 <xref:System.Windows.Forms.RadioButton.Appearance%2A> 속성이 <xref:System.Windows.Forms.Appearance.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="23f24-115">The <xref:System.Windows.Forms.RadioButton> control can appear like a command button, which appears to have been depressed if selected, if the <xref:System.Windows.Forms.RadioButton.Appearance%2A> property is set to <xref:System.Windows.Forms.Appearance.Button>.</span></span> <span data-ttu-id="23f24-116">라디오 단추를 사용 하 여 이미지를 표시할 수도 있습니다는 <xref:System.Windows.Forms.ButtonBase.Image%2A> 및 <xref:System.Windows.Forms.ButtonBase.ImageList%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="23f24-116">Radio buttons can also display images using the <xref:System.Windows.Forms.ButtonBase.Image%2A> and <xref:System.Windows.Forms.ButtonBase.ImageList%2A> properties.</span></span> <span data-ttu-id="23f24-117">자세한 내용은 참조 [하는 방법: Windows Forms 컨트롤에서 이미지 표시 설정](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23f24-117">For more information, see [How to: Set the Image Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f24-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23f24-118">See Also</span></span>  
 <xref:System.Windows.Forms.RadioButton>  
 [<span data-ttu-id="23f24-119">Panel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="23f24-119">Panel Control Overview</span></span>](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [<span data-ttu-id="23f24-120">GroupBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="23f24-120">GroupBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="23f24-121">CheckBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="23f24-121">CheckBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="23f24-122">방법: Windows Forms 컨트롤에 대한 선택키 만들기</span><span class="sxs-lookup"><span data-stu-id="23f24-122">How to: Create Access Keys for Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [<span data-ttu-id="23f24-123">방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정</span><span class="sxs-lookup"><span data-stu-id="23f24-123">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="23f24-124">방법: 기능별로 Windows Forms RadioButton 컨트롤 그룹화</span><span class="sxs-lookup"><span data-stu-id="23f24-124">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)  
 [<span data-ttu-id="23f24-125">RadioButton 컨트롤</span><span class="sxs-lookup"><span data-stu-id="23f24-125">RadioButton Control</span></span>](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
