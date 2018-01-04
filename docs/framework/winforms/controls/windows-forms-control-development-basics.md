---
title: "Windows Forms 컨트롤 개발 기본 사항"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bcf06f4dc0d8c70ae85d5add5a2fee078238d5e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-control-development-basics"></a><span data-ttu-id="602de-102">Windows Forms 컨트롤 개발 기본 사항</span><span class="sxs-lookup"><span data-stu-id="602de-102">Windows Forms Control Development Basics</span></span>
<span data-ttu-id="602de-103">Windows Forms 컨트롤에서 직접 또는 간접적으로 파생 되는 클래스는 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="602de-103">A Windows Forms control is a class that derives directly or indirectly from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="602de-104">다음 목록에서는 Windows Forms 컨트롤 개발 하기 위한 일반적인 시나리오를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="602de-104">The following list describes common scenarios for developing Windows Forms controls:</span></span>  
  
-   <span data-ttu-id="602de-105">결합 기존 복합 컨트롤을 만드는 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="602de-105">Combining existing controls to author a composite control.</span></span>  
  
     <span data-ttu-id="602de-106">복합 컨트롤 컨트롤로 다시 사용할 수 있는 사용자 인터페이스를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="602de-106">Composite controls encapsulate a user interface that can be reused as a control.</span></span> <span data-ttu-id="602de-107">합성 컨트롤의 예로 텍스트 상자 및 다시 설정으로 구성 된 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="602de-107">An example of a composite control is a control that consists of a text box and a reset button.</span></span> <span data-ttu-id="602de-108">비주얼 디자이너에는 복합 컨트롤을 만들기 위한 풍부한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="602de-108">Visual designers offer rich support for creating composite controls.</span></span> <span data-ttu-id="602de-109">파생 되는 복합 컨트롤을 작성 하려면 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="602de-109">To author a composite control, derive from <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span> <span data-ttu-id="602de-110">기본 클래스 <xref:System.Windows.Forms.UserControl> 자식 컨트롤과 자식 컨트롤을 그룹으로 작업할 수 있도록에 대 한 키보드 라우팅을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="602de-110">The base class <xref:System.Windows.Forms.UserControl> provides keyboard routing for child controls and enables child controls to work as a group.</span></span> <span data-ttu-id="602de-111">자세한 내용은 [Windows Forms 복합 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="602de-111">For more information, see [Developing a Composite Windows Forms Control](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md).</span></span>  
  
-   <span data-ttu-id="602de-112">사용자 지정 하거나 해당 기능을 추가 하는 기존 컨트롤을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="602de-112">Extending an existing control to customize it or to add to its functionality.</span></span>  
  
     <span data-ttu-id="602de-113">색을 변경할 수 없습니다 단추 및가 클릭 횟수를 추적 하는 추가 속성이 있는 확장 된 컨트롤의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="602de-113">A button whose color cannot be changed and a button that has an additional property that tracks how many times it has been clicked are examples of extended controls.</span></span> <span data-ttu-id="602de-114">파생 하 고 재정의 하거나 속성, 메서드 및 이벤트를 추가 하 여 Windows Forms 컨트롤을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="602de-114">You can customize any Windows Forms control by deriving from it and overriding or adding properties, methods, and events.</span></span>  
  
-   <span data-ttu-id="602de-115">결합 되지 않거나 기존 컨트롤을 확장 하는 컨트롤을 제작 합니다.</span><span class="sxs-lookup"><span data-stu-id="602de-115">Authoring a control that does not combine or extend existing controls.</span></span>  
  
     <span data-ttu-id="602de-116">이 시나리오에서는 기본 클래스에서 컨트롤을 파생 <xref:System.Windows.Forms.Control>합니다.</span><span class="sxs-lookup"><span data-stu-id="602de-116">In this scenario, derive your control from the base class <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="602de-117">재정의 속성, 메서드 및 기본 클래스의 이벤트 수 있을 뿐만 아니라 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="602de-117">You can add as well as override properties, methods, and events of the base class.</span></span> <span data-ttu-id="602de-118">시작 하려면 참조 [하는 방법: 간단한 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="602de-118">To get started, see [How to: Develop a Simple Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md).</span></span>  
  
 <span data-ttu-id="602de-119">Windows Forms 컨트롤에 대 한 기본 클래스 <xref:System.Windows.Forms.Control>, 클라이언트 측 Windows 기반 응용 프로그램의 시각적 표시에 필요한 연결이 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="602de-119">The base class for Windows Forms controls, <xref:System.Windows.Forms.Control>, provides the plumbing required for visual display in client-side Windows-based applications.</span></span> <span data-ttu-id="602de-120"><xref:System.Windows.Forms.Control>창 핸들, 메시지 라우팅을 처리와 마우스 및 키보드 이벤트 뿐만 아니라 여러 가지 사용자 인터페이스 이벤트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="602de-120"><xref:System.Windows.Forms.Control> provides a window handle, handles message routing, and provides mouse and keyboard events as well as many other user interface events.</span></span> <span data-ttu-id="602de-121">고급 레이아웃을 제공 하 고 같은 시각적 표시는 관련 된 속성을 주지 <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, 및 다른 많은 요인을 합니다.</span><span class="sxs-lookup"><span data-stu-id="602de-121">It provides advanced layout and has properties specific to visual display, such as <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, and many others.</span></span> <span data-ttu-id="602de-122">또한 보안을 스레딩 지원 및 ActiveX 컨트롤의 상호 운용성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="602de-122">Additionally, it provides security, threading support, and interoperability with ActiveX controls.</span></span> <span data-ttu-id="602de-123">인프라의 상당 부분이 기본 클래스에서 제공되므로 비교적 쉽게 사용자 고유의 Windows Forms 컨트롤을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="602de-123">Because so much of the infrastructure is provided by the base class, it is relatively easy to develop your own Windows Forms controls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="602de-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="602de-124">See Also</span></span>  
 [<span data-ttu-id="602de-125">방법: 간단한 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="602de-125">How to: Develop a Simple Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)  
 [<span data-ttu-id="602de-126">합성 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="602de-126">Developing a Composite Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)  
 [<span data-ttu-id="602de-127">방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="602de-127">How to: Create a Windows Forms Control That Shows Progress</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)  
 [<span data-ttu-id="602de-128">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="602de-128">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
