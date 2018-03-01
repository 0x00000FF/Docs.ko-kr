---
title: "LinkLabel 컨트롤 개요(Windows Forms)"
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
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 73bbd04b9ef5d2d0c5457dafb794435b3a4db380
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="linklabel-control-overview-windows-forms"></a><span data-ttu-id="11dc5-102">LinkLabel 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="11dc5-102">LinkLabel Control Overview (Windows Forms)</span></span>
<span data-ttu-id="11dc5-103">Windows Forms <xref:System.Windows.Forms.LinkLabel> 컨트롤 Windows Forms 응용 프로그램에 웹 스타일 링크를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11dc5-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to add Web-style links to Windows Forms applications.</span></span> <span data-ttu-id="11dc5-104">사용할 수는 <xref:System.Windows.Forms.LinkLabel> 사용할 수 있는 모든 항목에 대 한 제어는 <xref:System.Windows.Forms.Label> 제어 하는 데 있습니다; 또한 파일, 폴더 또는 웹 페이지에 대 한 링크로 텍스트의 일부를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11dc5-104">You can use the <xref:System.Windows.Forms.LinkLabel> control for everything that you can use the <xref:System.Windows.Forms.Label> control for; you also can set part of the text as a link to a file, folder, or Web page.</span></span>  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a><span data-ttu-id="11dc5-105">LinkLabel 컨트롤으로 수행할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="11dc5-105">What You Can Do with the LinkLabel Control</span></span>  
 <span data-ttu-id="11dc5-106">모든 속성, 메서드 및 이벤트를 실행 하는 것 외에도 <xref:System.Windows.Forms.Label> 컨트롤의 <xref:System.Windows.Forms.LinkLabel> 컨트롤에 대 한 하이퍼링크와 링크 색에 대 한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="11dc5-106">In addition to all the properties, methods, and events of the <xref:System.Windows.Forms.Label> control, the <xref:System.Windows.Forms.LinkLabel> control has properties for hyperlinks and link colors.</span></span> <span data-ttu-id="11dc5-107"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성은 활성화 된 링크 텍스트의 영역을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11dc5-107">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property sets the area of the text that activates the link.</span></span> <span data-ttu-id="11dc5-108"><xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, 및 <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> 속성 링크의 색을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11dc5-108">The <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> properties set the colors of the link.</span></span> <span data-ttu-id="11dc5-109"><xref:System.Windows.Forms.LinkLabel.LinkClicked> 이벤트 링크 텍스트를 선택 하는 경우를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11dc5-109">The <xref:System.Windows.Forms.LinkLabel.LinkClicked> event determines what happens when the link text is selected.</span></span>  
  
 <span data-ttu-id="11dc5-110">가장 간단한 사용 시나리오는 <xref:System.Windows.Forms.LinkLabel> 제어를 사용 하 여 단일 링크를 표시 하는 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 있지만 속성을 사용 하 여 여러 개의 하이퍼링크를 표시할 수도 있습니다는 <xref:System.Windows.Forms.LinkLabel.Links%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="11dc5-110">The simplest use of the <xref:System.Windows.Forms.LinkLabel> control is to display a single link using the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property, but you can also display multiple hyperlinks using the <xref:System.Windows.Forms.LinkLabel.Links%2A> property.</span></span> <span data-ttu-id="11dc5-111"><xref:System.Windows.Forms.LinkLabel.Links%2A> 속성을 사용 하면 링크의 컬렉션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11dc5-111">The <xref:System.Windows.Forms.LinkLabel.Links%2A> property enables you to access a collection of links.</span></span> <span data-ttu-id="11dc5-112">데이터를 지정할 수도 있습니다는 <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> 속성의 각 개별 <xref:System.Windows.Forms.LinkLabel.Link> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="11dc5-112">You can also specify data in the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property of each individual <xref:System.Windows.Forms.LinkLabel.Link> object.</span></span> <span data-ttu-id="11dc5-113">값은 <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> 속성을 표시 하는 파일의 위치 또는 웹 사이트의 주소를 저장 하려면 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11dc5-113">The value of the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property can be used to store the location of a file to display or the address of a Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11dc5-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11dc5-114">See Also</span></span>  
 <xref:System.Windows.Forms.LinkLabel>  
 [<span data-ttu-id="11dc5-115">Label 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="11dc5-115">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [<span data-ttu-id="11dc5-116">방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결</span><span class="sxs-lookup"><span data-stu-id="11dc5-116">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)  
 [<span data-ttu-id="11dc5-117">방법: Windows Forms LinkLabel 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="11dc5-117">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
