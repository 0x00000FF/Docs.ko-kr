---
title: "MenuStrip 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eb27503fffc798b644f95fd213f8f23bdb3e228a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="78365-102">MenuStrip 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="78365-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="78365-103">메뉴는 상황도 별로 그룹화 되어 있는 명령을 포함 하 여 사용자에 게 기능을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="78365-104"><xref:System.Windows.Forms.MenuStrip> 컨트롤이이 버전의 Visual Studio 및.NET Framework의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="78365-104">The <xref:System.Windows.Forms.MenuStrip> control is new to this version of Visual Studio and the .NET Framework.</span></span> <span data-ttu-id="78365-105">컨트롤을 예: Microsoft Office에서 메뉴를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78365-105">With the control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="78365-106"><xref:System.Windows.Forms.MenuStrip> 다중 문서 인터페이스 (MDI)와 메뉴 병합, 도구 설명 및 오버플로 컨트롤을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="78365-107">선택 키, 바로 가기 키, 확인 표시, 이미지 및 구분선을 추가 하 여 유용성 및 메뉴의 가독성을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78365-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="78365-108">그러나 <xref:System.Windows.Forms.MenuStrip> 대체 하 고 여기에 새로운 기능이 추가 된 <xref:System.Windows.Forms.MainMenu> 컨트롤는 <xref:System.Windows.Forms.MainMenu> 컨트롤을 선택 하는 경우 이전 버전과 호환성 및 이후 사용에 대 한 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="78365-109">MenuStrip 컨트롤을 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="78365-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="78365-110">사용 하 여는 <xref:System.Windows.Forms.MenuStrip> 를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
-   <span data-ttu-id="78365-111">지 원하는 일반적인된 메뉴가 등의 고급 사용자 인터페이스 및 레이아웃 기능 텍스트 및 이미지 정렬 및 정렬, 끌어서 놓기 작업, MDI, 오버플로 및 메뉴 명령에 액세스 하기 위한 대체 모드, 쉽게 사용자 지정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="78365-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
-   <span data-ttu-id="78365-112">일반적인 모양 및 동작의 운영 체제를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
-   <span data-ttu-id="78365-113">다른 컨트롤에 대 한 이벤트를 처리 하는 동일한 방식으로, 모든 컨테이너 및 포함 된 항목에는 일관성 있게 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="78365-114">다음 표에서 몇 가지 특히 중요 한 속성을 <xref:System.Windows.Forms.MenuStrip> 및 연결 된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="78365-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="78365-115">속성</span><span class="sxs-lookup"><span data-stu-id="78365-115">Property</span></span>|<span data-ttu-id="78365-116">설명</span><span class="sxs-lookup"><span data-stu-id="78365-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="78365-117">가져오거나는 <xref:System.Windows.Forms.ToolStripMenuItem> MDI 자식 폼의 목록을 표시 하는 데 사용 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="78365-118">자식 메뉴를 MDI 응용 프로그램의 부모 메뉴와 병합 하는 방법을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="78365-119">MDI 응용 프로그램에서 메뉴 내에서 병합된 된 항목의 위치를 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="78365-120">폼이 MDI 자식 폼의 컨테이너 인지를 나타내는 값을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="78365-121">에 대 한 도구 설명에 표시 되는지 여부를 나타내는 값을 가져오거나 설정 합니다.는 <xref:System.Windows.Forms.MenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="78365-122"><xref:System.Windows.Forms.MenuStrip>에서 오버플로 기능을 지원하는지를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="78365-123">와 연결 된 바로 가기 키를 가져오거나 설정 합니다.는 <xref:System.Windows.Forms.ToolStripMenuItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="78365-124">연결 된 바로 가기 키는 있는 여부를 나타내는 값을 가져오거나는 <xref:System.Windows.Forms.ToolStripMenuItem> 옆에 표시 되는 <xref:System.Windows.Forms.ToolStripMenuItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="78365-125">다음 표에서 중요 한 <xref:System.Windows.Forms.MenuStrip> 도우미 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="78365-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="78365-126">클래스</span><span class="sxs-lookup"><span data-stu-id="78365-126">Class</span></span>|<span data-ttu-id="78365-127">설명</span><span class="sxs-lookup"><span data-stu-id="78365-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="78365-128">에 표시 된 선택 가능한 옵션을 나타냅니다는 <xref:System.Windows.Forms.MenuStrip> 또는 <xref:System.Windows.Forms.ContextMenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="78365-129">바로 가기 메뉴를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="78365-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="78365-130">사용자는 사용자가 클릭할 때 표시 되는 목록에서 단일 항목을 선택할 수 있게 하는 컨트롤을 나타냅니다는 <xref:System.Windows.Forms.ToolStripDropDownButton> 또는 더 높은 수준의 메뉴 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="78365-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="78365-131">파생 된 컨트롤에 대 한 기본 기능을 제공 <xref:System.Windows.Forms.ToolStripItem> 클릭 하면 드롭다운 항목을 표시 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78365-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78365-132">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
