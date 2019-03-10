---
title: '방법: 관리 되는 HTML 문서 개체 모델에 액세스'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- HTML DOM [Windows Forms], accessing
- managed HTML DOM [Windows Forms], accessing
ms.assetid: 40fa5cd5-1ed8-42f6-a93f-9ac01608bbeb
ms.openlocfilehash: f2e2593b161a0dc072f0ecaa872bfa9ab83ac24c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715947"
---
# <a name="how-to-access-the-managed-html-document-object-model"></a><span data-ttu-id="737f6-102">방법: 관리 되는 HTML 문서 개체 모델에 액세스</span><span class="sxs-lookup"><span data-stu-id="737f6-102">How to: Access the Managed HTML Document Object Model</span></span>
<span data-ttu-id="737f6-103">다음과 같은 두 가지 유형의 애플리케이션에서 관리되는 HTML DOM(문서 개체 모델)에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="737f6-103">You can access the managed HTML Document Object Model (DOM) from two types of applications:</span></span>  
  
-   <span data-ttu-id="737f6-104">관리되는 <xref:System.Windows.Forms.WebBrowser> 컨트롤을 호스팅하는 Windows Forms 응용 프로그램(.exe).</span><span class="sxs-lookup"><span data-stu-id="737f6-104">A Windows Forms application (.exe) that hosted the managed <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="737f6-105">이러한 두 가지 기술은 서로를 보완하며 <xref:System.Windows.Forms.WebBrowser> 컨트롤을 통해 사용자에게 페이지를 표시하고 HTML DOM을 통해 문서의 논리 구조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="737f6-105">These two technologies complement one another, with the <xref:System.Windows.Forms.WebBrowser> control displaying the page to the user and the HTML DOM representing the document's logical structure.</span></span>  
  
-   <span data-ttu-id="737f6-106">Internet Explorer 내에서 호스팅되는 <xref:System.Windows.Forms.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="737f6-106">A Windows Forms <xref:System.Windows.Forms.UserControl> hosted within Internet Explorer.</span></span> <span data-ttu-id="737f6-107"><xref:System.Windows.Forms.UserControl>이 호스팅되는 페이지를 나타내는 HTML DOM에 액세스하여 문서 구조를 변경하거나 모달 대화 상자를 여는 등 여러 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="737f6-107">You can access the HTML DOM representing the page on which your <xref:System.Windows.Forms.UserControl> is hosted in order to change the document's structure or open modal dialog boxes, among many other possibilities.</span></span>  
  
### <a name="to-access-dom-from-a-windows-forms-application"></a><span data-ttu-id="737f6-108">Windows Forms 애플리케이션에서 DOM에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="737f6-108">To access DOM from a Windows Forms application</span></span>  
  
1.  <span data-ttu-id="737f6-109">Windows Forms 응용 프로그램 내에서 <xref:System.Windows.Forms.WebBrowser> 컨트롤을 호스팅하고 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 이벤트를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="737f6-109">Host a <xref:System.Windows.Forms.WebBrowser> control within your Windows Forms application and monitor for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="737f6-110">컨트롤 호스팅 및 이벤트 모니터링에 대한 자세한 내용은 [이벤트](../../../standard/events/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="737f6-110">For details on hosting controls and monitoring for events, see [Events](../../../standard/events/index.md).</span></span>  
  
2.  <span data-ttu-id="737f6-111"><xref:System.Windows.Forms.HtmlDocument> 컨트롤의 <xref:System.Windows.Forms.WebBrowser.Document%2A> 속성에 액세스하여 현재 페이지에 대해 <xref:System.Windows.Forms.WebBrowser>를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="737f6-111">Retrieve the <xref:System.Windows.Forms.HtmlDocument> for the current page by accessing the <xref:System.Windows.Forms.WebBrowser.Document%2A> property of the <xref:System.Windows.Forms.WebBrowser> control.</span></span>  

### <a name="to-access-dom-from-a-usercontrol-hosted-in-internet-explorer"></a><span data-ttu-id="737f6-112">Internet Explorer에서 호스팅되는 UserControl에서 DOM에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="737f6-112">To access DOM from a UserControl hosted in Internet Explorer</span></span>  
  
1.  <span data-ttu-id="737f6-113"><xref:System.Windows.Forms.UserControl> 클래스의 고유한 사용자 지정 파생 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="737f6-113">Create your own custom derived class of the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="737f6-114">자세한 내용은 [방법: 합성 컨트롤 제작](how-to-author-composite-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="737f6-114">For more information, see [How to: Author Composite Controls](how-to-author-composite-controls.md).</span></span>  
  
2.  <span data-ttu-id="737f6-115"><xref:System.Windows.Forms.UserControl>의 로드 이벤트 처리기 내에 다음 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="737f6-115">Place the following code inside of your Load event handler for your <xref:System.Windows.Forms.UserControl>:</span></span>  
  
 [!code-csharp[AccessHTMLDOMControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/AccessHTMLDOMControl/cs/UserControl1.cs#1)]
 [!code-vb[AccessHTMLDOMControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/AccessHTMLDOMControl/vb/UserControl1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="737f6-116">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="737f6-116">Robust Programming</span></span>  
  
1.  <span data-ttu-id="737f6-117"><xref:System.Windows.Forms.WebBrowser> 컨트롤을 통해 DOM을 사용할 때는 항상 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 이벤트가 발생할 때까지 기다린 후에 <xref:System.Windows.Forms.WebBrowser.Document%2A> 컨트롤의 <xref:System.Windows.Forms.WebBrowser> 속성 액세스를 시도해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="737f6-117">When using the DOM through the <xref:System.Windows.Forms.WebBrowser> control, you should always wait until the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event occurs before attempting to access the <xref:System.Windows.Forms.WebBrowser.Document%2A> property of the <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="737f6-118">전체 문서가 로드되고 나면 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 이벤트가 발생합니다. 그 전에 DOM을 사용하면 응용 프로그램에서 런타임 예외가 발생할 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="737f6-118">The <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event is raised after the entire document has loaded; if you use the DOM before then, you risk causing a run-time exception in your application.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="737f6-119">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="737f6-119">.NET Framework Security</span></span>  
  
1.  <span data-ttu-id="737f6-120">관리되는 HTML DOM에 액세스하려면 응용 프로그램 또는 <xref:System.Windows.Forms.UserControl>을 완전히 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="737f6-120">Your application or <xref:System.Windows.Forms.UserControl> will require full trust in order to access the managed HTML DOM.</span></span> <span data-ttu-id="737f6-121">[!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]를 사용하여 Windows Forms 응용 프로그램을 배포하는 경우 권한 상승 또는 신뢰할 수 있는 응용 프로그램 배포를 통해 완전 신뢰를 요청할 수 있습니다. 자세한 내용은 [ClickOnce 응용 프로그램 보안](/visualstudio/deployment/securing-clickonce-applications)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="737f6-121">If you are deploying a Windows Forms application using [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], you can request full trust using either Permission Elevation or Trusted Application Deployment; see [Securing ClickOnce Applications](/visualstudio/deployment/securing-clickonce-applications) for details.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="737f6-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="737f6-122">See also</span></span>
- [<span data-ttu-id="737f6-123">관리되는 HTML 문서 개체 모델 사용</span><span class="sxs-lookup"><span data-stu-id="737f6-123">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)
