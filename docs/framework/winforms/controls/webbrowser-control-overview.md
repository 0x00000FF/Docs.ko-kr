---
title: "WebBrowser 컨트롤 개요"
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
- WebBrowser
helpviewer_keywords:
- WebBrowser control [Windows Forms], about
- Web pages [Windows Forms], displaying in applications
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2c1ed93769cc91d9622a86ea2d894cea57f5bcd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="webbrowser-control-overview"></a><span data-ttu-id="e997b-102">WebBrowser 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="e997b-102">WebBrowser Control Overview</span></span>
<span data-ttu-id="e997b-103"><xref:System.Windows.Forms.WebBrowser> 컨트롤은 WebBrowser ActiveX 컨트롤에 대 한 관리 되는 래퍼를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-103">The <xref:System.Windows.Forms.WebBrowser> control provides a managed wrapper for the WebBrowser ActiveX control.</span></span> <span data-ttu-id="e997b-104">관리 되는 래퍼를 사용 하면 Windows Forms 클라이언트 응용 프로그램에서 웹 페이지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-104">The managed wrapper lets you display Web pages in your Windows Forms client applications.</span></span> <span data-ttu-id="e997b-105">사용할 수는 <xref:System.Windows.Forms.WebBrowser> Internet Explorer 웹 응용 프로그램에 검색 기능을 복제 하는 컨트롤 기본 Internet Explorer 기능을 사용 하지 않도록 설정 하 고 간단한 HTML 문서 뷰어 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-105">You can use the <xref:System.Windows.Forms.WebBrowser> control to duplicate Internet Explorer Web browsing functionality in your application or you can disable default Internet Explorer functionality and use the control as a simple HTML document viewer.</span></span> <span data-ttu-id="e997b-106">DHTML 기반 사용자 인터페이스 요소를 폼에 추가 하 고 숨길에서 호스트 되는 팩트에 컨트롤을 사용할 수도 있습니다는 <xref:System.Windows.Forms.WebBrowser> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-106">You can also use the control to add DHTML-based user interface elements to your form and hide the fact that they are hosted in the <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="e997b-107">이 방법을 사용 하면 단일 응용 프로그램에서 Windows Forms 컨트롤을 사용 하 여 웹 컨트롤을 원활 하 게 결합 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-107">This approach lets you seamlessly combine Web controls with Windows Forms controls in a single application.</span></span>  
  
## <a name="frequently-used-properties-methods-and-events"></a><span data-ttu-id="e997b-108">자주 사용 되는 속성, 메서드 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="e997b-108">Frequently Used Properties, Methods, and Events</span></span>  
 <span data-ttu-id="e997b-109"><xref:System.Windows.Forms.WebBrowser> 컨트롤에 여러 속성, 메서드 및 Internet Explorer에 있는 컨트롤을 구현 하는 데 사용할 수 있는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-109">The <xref:System.Windows.Forms.WebBrowser> control has several properties, methods, and events that you can use to implement controls found in Internet Explorer.</span></span> <span data-ttu-id="e997b-110">예를 들어 사용할 수 있습니다는 `Navigate` 주소 표시줄을 구현 하는 메서드 및 `GoBack`, `GoForward`, `Stop`, 및 `Refresh` 도구 모음에 탐색 단추를 구현 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-110">For example, you can use the `Navigate` method to implement an address bar, and the `GoBack`, `GoForward`, `Stop`, and `Refresh` methods to implement navigation buttons on a toolbar.</span></span> <span data-ttu-id="e997b-111">처리할 수 있습니다는 `Navigated` 주소 표시줄의 값으로 업데이트 하는 이벤트는 `Url` 속성 및 값이 있는 제목 표시줄의 `DocumentTitle` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-111">You can handle the `Navigated` event to update the address bar with the value of the `Url` property and the title bar with the value of the `DocumentTitle` property.</span></span>  
  
 <span data-ttu-id="e997b-112">응용 프로그램 내에서 고유한 페이지 콘텐츠를 생성 하려는 경우 설정할 수 있습니다는 `DocumentText` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-112">If you want to generate your own page content within your application, you can set the `DocumentText` property.</span></span> <span data-ttu-id="e997b-113">HTML 문서 개체 모델 (DOM)에 잘 알고 있다면 통해 현재 웹 페이지의 내용을 조작할 수도 있습니다는 `Document` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-113">If you are familiar with the HTML document object model (DOM), you can also manipulate the contents of the current Web page through the `Document` property.</span></span> <span data-ttu-id="e997b-114">이 속성을 저장 하 고 파일을 탐색 하는 대신 메모리에 문서를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-114">With this property, you can store and modify documents in memory instead of navigating among files.</span></span>  
  
 <span data-ttu-id="e997b-115">`Document` 속성 또한 웹 페이지 스크립팅 코드에서 클라이언트 응용 프로그램 코드에서에서 구현 되는 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-115">The `Document` property also lets you call methods implemented in Web page scripting code from your client application code.</span></span> <span data-ttu-id="e997b-116">설정 스크립팅 코드에서 클라이언트 응용 프로그램 코드에 액세스 하려면는 `ObjectForScripting` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-116">To access your client application code from your scripting code, set the `ObjectForScripting` property.</span></span> <span data-ttu-id="e997b-117">스크립트 코드에서 지정 하는 개체를 액세스할 수 있습니다는 `window.external` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-117">The object that you specify can be accessed by your script code as the `window.external` object.</span></span>  
  
|<span data-ttu-id="e997b-118">name</span><span class="sxs-lookup"><span data-stu-id="e997b-118">Name</span></span>|<span data-ttu-id="e997b-119">설명</span><span class="sxs-lookup"><span data-stu-id="e997b-119">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="e997b-120"><xref:System.Windows.Forms.WebBrowser.Document%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="e997b-120"><xref:System.Windows.Forms.WebBrowser.Document%2A> property</span></span>|<span data-ttu-id="e997b-121">현재 웹 페이지의 HTML 문서 개체 모델 (DOM)에 대 한 관리 되는 액세스를 제공 하는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-121">Gets an object that provides managed access to the HTML document object model (DOM) of the current Web page.</span></span>|  
|<span data-ttu-id="e997b-122"><xref:System.Windows.Forms.WebBrowser.DocumentCompleted>이벤트</span><span class="sxs-lookup"><span data-stu-id="e997b-122"><xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event</span></span>|<span data-ttu-id="e997b-123">웹 페이지 로드가 완료 되 면 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-123">Occurs when a Web page finishes loading.</span></span>|  
|<span data-ttu-id="e997b-124"><xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="e997b-124"><xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property</span></span>|<span data-ttu-id="e997b-125">현재 웹 페이지의 콘텐츠는 HTML 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-125">Gets or sets the HTML content of the current Web page.</span></span>|  
|<span data-ttu-id="e997b-126"><xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="e997b-126"><xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A> property</span></span>|<span data-ttu-id="e997b-127">현재 웹 페이지의 제목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-127">Gets the title of the current Web page.</span></span>|  
|<span data-ttu-id="e997b-128"><xref:System.Windows.Forms.WebBrowser.GoBack%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="e997b-128"><xref:System.Windows.Forms.WebBrowser.GoBack%2A> method</span></span>|<span data-ttu-id="e997b-129">기록의 이전 페이지를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-129">Navigates to the previous page in history.</span></span>|  
|<span data-ttu-id="e997b-130"><xref:System.Windows.Forms.WebBrowser.GoForward%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="e997b-130"><xref:System.Windows.Forms.WebBrowser.GoForward%2A> method</span></span>|<span data-ttu-id="e997b-131">기록의 다음 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-131">Navigates to the next page in history.</span></span>|  
|<span data-ttu-id="e997b-132"><xref:System.Windows.Forms.WebBrowser.Navigate%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="e997b-132"><xref:System.Windows.Forms.WebBrowser.Navigate%2A> method</span></span>|<span data-ttu-id="e997b-133">지정된 된 URL로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-133">Navigates to the specified URL.</span></span>|  
|<span data-ttu-id="e997b-134"><xref:System.Windows.Forms.WebBrowser.Navigating>이벤트</span><span class="sxs-lookup"><span data-stu-id="e997b-134"><xref:System.Windows.Forms.WebBrowser.Navigating> event</span></span>|<span data-ttu-id="e997b-135">작업을 취소할 수 있도록 탐색이 시작 되기 전에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-135">Occurs before navigation begins, enabling the action to be canceled.</span></span>|  
|<span data-ttu-id="e997b-136"><xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="e997b-136"><xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> property</span></span>|<span data-ttu-id="e997b-137">웹 페이지 스크립팅 코드에서 응용 프로그램과 통신 하는 데 사용할 수 있는 개체를 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-137">Gets or sets an object that Web page scripting code can use to communicate with your application.</span></span>|  
|<span data-ttu-id="e997b-138"><xref:System.Windows.Forms.WebBrowser.Print%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="e997b-138"><xref:System.Windows.Forms.WebBrowser.Print%2A> method</span></span>|<span data-ttu-id="e997b-139">현재 웹 페이지를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-139">Prints the current Web page.</span></span>|  
|<span data-ttu-id="e997b-140"><xref:System.Windows.Forms.WebBrowser.Refresh%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="e997b-140"><xref:System.Windows.Forms.WebBrowser.Refresh%2A> method</span></span>|<span data-ttu-id="e997b-141">현재 웹 페이지를 다시 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-141">Reloads the current Web page.</span></span>|  
|<span data-ttu-id="e997b-142"><xref:System.Windows.Forms.WebBrowser.Stop%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="e997b-142"><xref:System.Windows.Forms.WebBrowser.Stop%2A> method</span></span>|<span data-ttu-id="e997b-143">현재 탐색 하 고 소리 및 애니메이션과 같은 동적 페이지 요소를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-143">Halts the current navigation and stops dynamic page elements such as sounds and animation.</span></span>|  
|<span data-ttu-id="e997b-144"><xref:System.Windows.Forms.WebBrowser.Url%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="e997b-144"><xref:System.Windows.Forms.WebBrowser.Url%2A> property</span></span>|<span data-ttu-id="e997b-145">현재 웹 페이지의 URL을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-145">Gets or sets the URL of the current Web page.</span></span> <span data-ttu-id="e997b-146">컨트롤에 새 URL 탐색이 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e997b-146">Setting this property navigates the control to the new URL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e997b-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e997b-147">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventArgs>  
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventHandler>  
 <xref:System.Windows.Forms.WebBrowserEncryptionLevel>  
 <xref:System.Windows.Forms.WebBrowserNavigatedEventArgs>  
 <xref:System.Windows.Forms.WebBrowserNavigatedEventHandler>  
 <xref:System.Windows.Forms.WebBrowserNavigatingEventArgs>  
 <xref:System.Windows.Forms.WebBrowserNavigatingEventHandler>  
 <xref:System.Windows.Forms.WebBrowserProgressChangedEventArgs>  
 <xref:System.Windows.Forms.WebBrowserReadyState>  
 <xref:System.Windows.Forms.WebBrowserRefreshOption>  
 [<span data-ttu-id="e997b-148">방법: WebBrowser 컨트롤을 사용하여 URL 탐색</span><span class="sxs-lookup"><span data-stu-id="e997b-148">How to: Navigate to a URL with the WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [<span data-ttu-id="e997b-149">방법: WebBrowser 컨트롤을 사용하여 인쇄</span><span class="sxs-lookup"><span data-stu-id="e997b-149">How to: Print with a WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)  
 [<span data-ttu-id="e997b-150">방법: Windows Forms 응용 프로그램에 웹 브라우저 기능 추가</span><span class="sxs-lookup"><span data-stu-id="e997b-150">How to: Add Web Browser Capabilities to a Windows Forms Application</span></span>](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)  
 [<span data-ttu-id="e997b-151">방법: Windows Forms 응용 프로그램에서 HTML 문서 뷰어 만들기</span><span class="sxs-lookup"><span data-stu-id="e997b-151">How to: Create an HTML Document Viewer in a Windows Forms Application</span></span>](../../../../docs/framework/winforms/controls/how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)  
 [<span data-ttu-id="e997b-152">방법: DHTML 코드와 클라이언트 응용 프로그램 코드 간의 양방향 통신 구현</span><span class="sxs-lookup"><span data-stu-id="e997b-152">How to: Implement Two-Way Communication Between DHTML Code and Client Application Code</span></span>](../../../../docs/framework/winforms/controls/implement-two-way-com-between-dhtml-and-client.md)  
 [<span data-ttu-id="e997b-153">WebBrowser 보안</span><span class="sxs-lookup"><span data-stu-id="e997b-153">WebBrowser Security</span></span>](../../../../docs/framework/winforms/controls/webbrowser-security.md)
