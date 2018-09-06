---
title: StatusStrip 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- StatusStrip
helpviewer_keywords:
- StatusStrip control [Windows Forms], about StatusStrip control
- status bars [Windows Forms], about status bars
ms.assetid: c0d9bcbb-f8b8-46ef-bae2-4146b8c8ce99
ms.openlocfilehash: e40373dd05e59325cdb6c2272d5749f3828b0755
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864565"
---
# <a name="statusstrip-control-overview"></a><span data-ttu-id="6a932-102">StatusStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="6a932-102">StatusStrip Control Overview</span></span>
<span data-ttu-id="6a932-103"><xref:System.Windows.Forms.StatusStrip> 컨트롤은 <xref:System.Windows.Forms.Form>에 표시되는 개체, 개체의 구성 요소 또는 응용 프로그램 내에서 해당 개체의 작업과 관련된 컨텍스트 정보에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6a932-103">A <xref:System.Windows.Forms.StatusStrip> control displays information about an object being viewed on a <xref:System.Windows.Forms.Form>, the object's components, or contextual information that relates to that object's operation within your application.</span></span> <span data-ttu-id="6a932-104">일반적으로 <xref:System.Windows.Forms.StatusStrip> 컨트롤은 각각 텍스트, 아이콘 또는 둘 다를 표시하는 <xref:System.Windows.Forms.ToolStripStatusLabel> 개체로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a932-104">Typically, a <xref:System.Windows.Forms.StatusStrip> control consists of <xref:System.Windows.Forms.ToolStripStatusLabel> objects, each of which displays text, an icon, or both.</span></span> <span data-ttu-id="6a932-105"><xref:System.Windows.Forms.StatusStrip>에 <xref:System.Windows.Forms.ToolStripDropDownButton>, <xref:System.Windows.Forms.ToolStripSplitButton> 및 <xref:System.Windows.Forms.ToolStripProgressBar> 컨트롤이 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a932-105">The <xref:System.Windows.Forms.StatusStrip> can also contain <xref:System.Windows.Forms.ToolStripDropDownButton>, <xref:System.Windows.Forms.ToolStripSplitButton>, and <xref:System.Windows.Forms.ToolStripProgressBar> controls.</span></span>  
  
 <span data-ttu-id="6a932-106">기본 <xref:System.Windows.Forms.StatusStrip>에는 패널이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a932-106">The default <xref:System.Windows.Forms.StatusStrip> has no panels.</span></span> <span data-ttu-id="6a932-107"><xref:System.Windows.Forms.StatusStrip>에 패널을 추가하려면 <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6a932-107">To add panels to a <xref:System.Windows.Forms.StatusStrip>, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="6a932-108">Visual Studio에서는 <xref:System.Windows.Forms.StatusStrip> 항목 및 일반적인 명령 처리가 광범위하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a932-108">There is extensive support for handling <xref:System.Windows.Forms.StatusStrip> items and common commands in Visual Studio.</span></span>  
  
 <span data-ttu-id="6a932-109">도 참조 하세요 [StatusStrip 항목 컬렉션 편집기](https://msdn.microsoft.com/library/ms233631\(v=vs.110\))하십시오 [StatusStrip 작업 대화 상자](https://msdn.microsoft.com/library/ms233642\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="6a932-109">Also see [StatusStrip Items Collection Editor](https://msdn.microsoft.com/library/ms233631\(v=vs.110\)), [StatusStrip Tasks Dialog Box](https://msdn.microsoft.com/library/ms233642\(v=vs.110\)).</span></span>  
  
 <span data-ttu-id="6a932-110"><xref:System.Windows.Forms.StatusStrip>은 이전 버전의 <xref:System.Windows.Forms.StatusBar> 컨트롤을 대체하고 확장하지만 이전 버전과의 호환성 및 앞으로의 사용 가능성을 고려하여 <xref:System.Windows.Forms.StatusBar>를 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a932-110">Although <xref:System.Windows.Forms.StatusStrip> replaces and extends the <xref:System.Windows.Forms.StatusBar> control of previous versions, <xref:System.Windows.Forms.StatusBar> is retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="important-statusstrip-members"></a><span data-ttu-id="6a932-111">중요한 StatusStrip 멤버</span><span class="sxs-lookup"><span data-stu-id="6a932-111">Important StatusStrip Members</span></span>  
  
|<span data-ttu-id="6a932-112">이름</span><span class="sxs-lookup"><span data-stu-id="6a932-112">Name</span></span>|<span data-ttu-id="6a932-113">설명</span><span class="sxs-lookup"><span data-stu-id="6a932-113">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.StatusStrip.CanOverflow%2A>|<span data-ttu-id="6a932-114"><xref:System.Windows.Forms.StatusStrip>에서 오버플로 기능을 지원하는지를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a932-114">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.StatusStrip.Stretch%2A>|<span data-ttu-id="6a932-115"><xref:System.Windows.Forms.StatusStrip>이 <xref:System.Windows.Forms.ToolStripContainer>의 끝에서 끝까지 확장되는지를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a932-115">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> stretches from end to end in its <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
  
### <a name="important-statusstrip-companion-classes"></a><span data-ttu-id="6a932-116">중요한 StatusStrip 도우미 클래스</span><span class="sxs-lookup"><span data-stu-id="6a932-116">Important StatusStrip Companion Classes</span></span>  
  
|<span data-ttu-id="6a932-117">이름</span><span class="sxs-lookup"><span data-stu-id="6a932-117">Name</span></span>|<span data-ttu-id="6a932-118">설명</span><span class="sxs-lookup"><span data-stu-id="6a932-118">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|<span data-ttu-id="6a932-119"><xref:System.Windows.Forms.StatusStrip> 컨트롤의 패널을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6a932-119">Represents a panel in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|<span data-ttu-id="6a932-120">사용자가 단일 항목을 선택할 수 있는 연결된 <xref:System.Windows.Forms.ToolStripDropDown>을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6a932-120">Displays an associated <xref:System.Windows.Forms.ToolStripDropDown> from which the user can select a single item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|<span data-ttu-id="6a932-121">표준 단추와 드롭다운 메뉴인 두 부분으로 구성된 컨트롤을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6a932-121">Represents a two-part control that is a standard button and a drop-down menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|<span data-ttu-id="6a932-122">프로세스의 완료 상태를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6a932-122">Displays the completion state of a process.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a932-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a932-123">See Also</span></span>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>
