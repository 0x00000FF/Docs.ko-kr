---
title: "방법: Windows Forms RichTextBox 컨트롤에서 스크롤 막대 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4645e502544072cbc6268ae07e054ea5450d9c5c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="87929-102">방법: Windows Forms RichTextBox 컨트롤에서 스크롤 막대 표시</span><span class="sxs-lookup"><span data-stu-id="87929-102">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="87929-103">기본적으로 Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤 필요에 따라 가로 및 세로 스크롤 막대를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="87929-103">By default, the Windows Forms <xref:System.Windows.Forms.RichTextBox> control displays horizontal and vertical scroll bars as necessary.</span></span> <span data-ttu-id="87929-104">7 개의 가능한 값에 대 한는 <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> 속성의는 <xref:System.Windows.Forms.RichTextBox> 아래 표에서 설명 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="87929-104">There are seven possible values for the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property of the <xref:System.Windows.Forms.RichTextBox> control, which are described in the table below.</span></span>  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a><span data-ttu-id="87929-105">RichTextBox 컨트롤에서 스크롤 막대를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="87929-105">To display scroll bars in a RichTextBox control</span></span>  
  
1.  <span data-ttu-id="87929-106"><xref:System.Windows.Forms.RichTextBox.Multiline%2A> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="87929-106">Set the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="87929-107">없음 유형의 스크롤 막대를 포함 하 여 가로 스크롤 하는 경우 표시 됩니다는 <xref:System.Windows.Forms.RichTextBox.Multiline%2A> 속성이 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="87929-107">No type of scroll bar, including horizontal, will display if the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property is set to `false`.</span></span>  
  
2.  <span data-ttu-id="87929-108">설정의 <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> 속성의 적절 한 값을는 <xref:System.Windows.Forms.RichTextBoxScrollBars> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="87929-108">Set the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property to an appropriate value of the <xref:System.Windows.Forms.RichTextBoxScrollBars> enumeration.</span></span>  
  
    |<span data-ttu-id="87929-109">값</span><span class="sxs-lookup"><span data-stu-id="87929-109">Value</span></span>|<span data-ttu-id="87929-110">설명</span><span class="sxs-lookup"><span data-stu-id="87929-110">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="87929-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both>(기본값)</span><span class="sxs-lookup"><span data-stu-id="87929-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (default)</span></span>|<span data-ttu-id="87929-112">텍스트 너비 또는 컨트롤의 길이 초과 하는 경우에 가로 또는 세로 스크롤 막대 또는 둘 다를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="87929-112">Displays horizontal or vertical scroll bars, or both, only when text exceeds the width or length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|<span data-ttu-id="87929-113">스크롤 막대의 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87929-113">Never displays any type of scroll bar.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|<span data-ttu-id="87929-114">가로 스크롤 막대는 텍스트 컨트롤의 너비를 초과 하는 경우에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87929-114">Displays a horizontal scroll bar only when the text exceeds the width of the control.</span></span> <span data-ttu-id="87929-115">(이 위해서는는 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성으로 설정 되어 있어야 `false`.)</span><span class="sxs-lookup"><span data-stu-id="87929-115">(For this to occur, the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property must be set to `false`.)</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|<span data-ttu-id="87929-116">세로 스크롤 막대는 텍스트 컨트롤의 높이 초과 하는 경우에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87929-116">Displays a vertical scroll bar only when the text exceeds the height of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|<span data-ttu-id="87929-117">가로 스크롤 막대의 경우 표시는 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성이 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="87929-117">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="87929-118">텍스트 컨트롤의 너비를 초과 하지 않는 스크롤 막대를 흐리게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87929-118">The scroll bar appears dimmed when text does not exceed the width of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|<span data-ttu-id="87929-119">항상 세로 스크롤 막대를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="87929-119">Always displays a vertical scroll bar.</span></span> <span data-ttu-id="87929-120">텍스트 컨트롤의 길이 초과 하지 않는 스크롤 막대를 흐리게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87929-120">The scroll bar appears dimmed when text does not exceed the length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|<span data-ttu-id="87929-121">항상 세로 스크롤 막대를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="87929-121">Always displays a vertical scrollbar.</span></span> <span data-ttu-id="87929-122">가로 스크롤 막대의 경우 표시는 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성이 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="87929-122">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="87929-123">스크롤 막대 컨트롤의 너비나 텍스트 크지 않으면 흐리게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87929-123">The scroll bars appear grayed when text does not exceed the width or length of the control.</span></span>|  
  
3.  <span data-ttu-id="87929-124"><xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="87929-124">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="87929-125">값</span><span class="sxs-lookup"><span data-stu-id="87929-125">Value</span></span>|<span data-ttu-id="87929-126">설명</span><span class="sxs-lookup"><span data-stu-id="87929-126">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="87929-127">컨트롤의에서 텍스트 줄 바꿈을 도달할 때까지 오른쪽으로 스크롤됩니다 컨트롤의 너비에 맞게 자동으로 조정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87929-127">Text in the control is not automatically adjusted to fit the width of the control, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="87929-128">위의 가로 스크롤 막대 또는 둘 모두를 선택 하는 경우이 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87929-128">Use this value if you chose horizontal scroll bars or both, above.</span></span>|  
    |<span data-ttu-id="87929-129">`true`(기본값)</span><span class="sxs-lookup"><span data-stu-id="87929-129">`true` (default)</span></span>|<span data-ttu-id="87929-130">컨트롤의에서 텍스트를 자동으로 컨트롤의 너비에 맞게 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87929-130">Text in the control is automatically adjusted to fit the width of the control.</span></span> <span data-ttu-id="87929-131">가로 스크롤 막대가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87929-131">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="87929-132">하나 이상의 단락 표시 위에 세로 스크롤 막대 또는 none을 선택 하는 경우이 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87929-132">Use this value if you chose vertical scroll bars or none, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87929-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87929-133">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBoxScrollBars>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="87929-134">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="87929-134">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="87929-135">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="87929-135">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
