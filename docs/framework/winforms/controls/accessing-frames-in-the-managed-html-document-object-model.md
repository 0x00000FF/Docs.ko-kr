---
title: 관리되는 HTML 문서 개체 모델의 프레임에 액세스
ms.date: 03/30/2017
helpviewer_keywords:
- HTML [Windows Forms], dOM
- managed HTML DOM
- HTML [Windows Forms], managed
- HTML DOM [Windows Forms], managed
- frames [Windows Forms], accessing
- DOM [Windows Forms], accessing frames in managed HTML
ms.assetid: cdeeaa22-0be4-4bbf-9a75-4ddc79199f8d
ms.openlocfilehash: 5a9864184e92c3c6bbcf6a613fd1092238181a93
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487296"
---
# <a name="accessing-frames-in-the-managed-html-document-object-model"></a><span data-ttu-id="361c2-102">관리되는 HTML 문서 개체 모델의 프레임에 액세스</span><span class="sxs-lookup"><span data-stu-id="361c2-102">Accessing Frames in the Managed HTML Document Object Model</span></span>
<span data-ttu-id="361c2-103">일부 HTML 문서도 구성 됩니다 *프레임*, 또는 자신의 고유 HTML 문서를 포함할 수 있는 창입니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-103">Some HTML documents are composed out of *frames*, or windows that can hold their own distinct HTML documents.</span></span> <span data-ttu-id="361c2-104">프레임을 사용하면 탐색 모음과 같이 페이지 조각 하나 이상이 정적으로 유지되지만 다른 프레임의 콘텐츠가 지속적으로 바뀌는 HTML 페이지를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-104">Using frames makes it easy to create HTML pages in which one or more pieces of the page remain static, such as a navigation bar, while other frames constantly change their content.</span></span>  
  
 <span data-ttu-id="361c2-105">HTML 작성자는 다음 두 방법의 하나로 프레임을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-105">HTML authors can create frames in one of two ways:</span></span>  
  
- <span data-ttu-id="361c2-106">고정된 창을 만드는 `FRAMESET` 및 `FRAME` 태그 사용.</span><span class="sxs-lookup"><span data-stu-id="361c2-106">Using the `FRAMESET` and `FRAME` tags, which create fixed windows.</span></span>  
  
 <span data-ttu-id="361c2-107">또는</span><span class="sxs-lookup"><span data-stu-id="361c2-107">-or-</span></span>  
  
- <span data-ttu-id="361c2-108">런타임에 위치가 변경될 수 있는 부동 창을 만드는 `IFRAME` 태그 사용.</span><span class="sxs-lookup"><span data-stu-id="361c2-108">Using the `IFRAME` tag, which creates a floating window that can be repositioned at run time.</span></span>  
  
1. <span data-ttu-id="361c2-109">프레임은 HTML 문서를 포함하므로 DOM(문서 개체 모델)에서 창 요소 및 프레임 요소로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-109">Because frames contain HTML documents, they are represented in the Document Object Model (DOM) as both window elements and frame elements.</span></span>  
  
2. <span data-ttu-id="361c2-110"><xref:System.Windows.Forms.HtmlWindow>의 프레임 컬렉션을 사용하여 `FRAME` 또는 `IFRAME` 태그에 액세스하면 프레임에 해당하는 창 요소가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-110">When you access a `FRAME` or `IFRAME` tag by using the Frames collection of <xref:System.Windows.Forms.HtmlWindow>, you are retrieving the window element corresponding to the frame.</span></span> <span data-ttu-id="361c2-111">이는 현재 URL, 문서 및 크기와 같은 프레임의 모든 동적 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-111">This represents all of the frame's dynamic properties, such as its current URL, document, and size.</span></span>  
  
3. <span data-ttu-id="361c2-112"><xref:System.Windows.Forms.HtmlElementCollection.GetElementsByName%2A> 또는 <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A>와 같은 메서드, <xref:System.Windows.Forms.HtmlElement.Children%2A> 컬렉션 또는 <xref:System.Windows.Forms.HtmlWindow>의 <xref:System.Windows.Forms.HtmlWindow.WindowFrameElement%2A> 속성을 사용하여 `FRAME` 또는 `IFRAME` 태그에 액세스하면 프레임 요소가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-112">When you access a `FRAME` or `IFRAME` tag by using the <xref:System.Windows.Forms.HtmlWindow.WindowFrameElement%2A> property of <xref:System.Windows.Forms.HtmlWindow>, the <xref:System.Windows.Forms.HtmlElement.Children%2A> collection, or methods such as <xref:System.Windows.Forms.HtmlElementCollection.GetElementsByName%2A> or <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A>, you are retrieving the frame element.</span></span> <span data-ttu-id="361c2-113">이는 원래 HTML 파일에 지정된 URL을 포함하는 프레임의 정적 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-113">This represents the static properties of the frame, including the URL specified in the original HTML file.</span></span>  
  
## <a name="frames-and-security"></a><span data-ttu-id="361c2-114">프레임 및 보안</span><span class="sxs-lookup"><span data-stu-id="361c2-114">Frames and Security</span></span>  
 <span data-ttu-id="361c2-115">프레임에 대 한 액세스를 관리 되는 HTML DOM으로 이라는 보안 조치를 구현 한다는 사실을 복잡 *프레임 간 스크립팅 보안*합니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-115">Access to frames is complicated by the fact that the managed HTML DOM implements a security measure known as *cross-frame scripting security*.</span></span> <span data-ttu-id="361c2-116">서로 다른 도메인에 `FRAME`이 두 개 이상 있는 `FRAMESET`이 문서에 포함되면 이들 `FRAME`이 서로 상호 작용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-116">If a document contains a `FRAMESET` with two or more `FRAME`s in different domains, these `FRAME`s cannot interact with one another.</span></span> <span data-ttu-id="361c2-117">즉, 한 `FRAME` 웹 사이트의 콘텐츠를 표시 된 정보에 액세스할 수 없습니다는 `FRAME` 와 같은 타사 사이트를 호스팅하는 `http://www.adatum.com/`합니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-117">In other words, a `FRAME` that displays content from your Web site cannot access information in a `FRAME` that hosts a third-party site such as `http://www.adatum.com/`.</span></span> <span data-ttu-id="361c2-118">이 보안은 <xref:System.Windows.Forms.HtmlWindow> 클래스 수준에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-118">This security is implemented at the level of the <xref:System.Windows.Forms.HtmlWindow> class.</span></span> <span data-ttu-id="361c2-119">해당 URL과 같은 또 다른 웹 사이트를 호스트하는 `FRAME`에 대한 일반적인 정보를 가져올 수 있지만, <xref:System.Windows.Forms.HtmlWindow.Document%2A>에 액세스하거나 호스트 `FRAME` 또는 `IFRAME`의 크기나 위치를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-119">You can obtain general information about a `FRAME` hosting another Web site, such as its URL, but you will be unable to access its <xref:System.Windows.Forms.HtmlWindow.Document%2A> or change the size or location of its hosting `FRAME` or `IFRAME`.</span></span>  
  
 <span data-ttu-id="361c2-120"><xref:System.Windows.Forms.HtmlWindow.Open%2A> 및 <xref:System.Windows.Forms.HtmlWindow.OpenNew%2A> 메서드를 사용하여 연 창에도 이 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-120">This rule also applies to windows that you open using the <xref:System.Windows.Forms.HtmlWindow.Open%2A> and <xref:System.Windows.Forms.HtmlWindow.OpenNew%2A> methods.</span></span> <span data-ttu-id="361c2-121"><xref:System.Windows.Forms.WebBrowser> 컨트롤에 호스트된 페이지와 다른 도메인에 있는 창을 열면 해당 창을 이동하거나 콘텐츠를 검사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-121">If the window you open is in a different domain from the page hosted in the <xref:System.Windows.Forms.WebBrowser> control, you will not be able to move that window or examine its contents.</span></span> <span data-ttu-id="361c2-122"><xref:System.Windows.Forms.WebBrowser> 컨트롤을 통해 Windows Forms 기반 애플리케이션을 배포하는 데 사용된 웹 사이트를 표시하는 경우에도 이들 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-122">These restrictions are also enforced if you use the <xref:System.Windows.Forms.WebBrowser> control to display a Web site that is different from the Web site used to deploy your Windows Forms-based application.</span></span> <span data-ttu-id="361c2-123">ClickOnce 배포 기술을 사용 하 여 웹 사이트 A에서에서 응용 프로그램을 설치 및 사용 하는 경우는 <xref:System.Windows.Forms.WebBrowser> 웹 사이트 B에 표시할 수 없게 됩니다 액세스 웹 사이트 B의 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="361c2-123">If you use ClickOnce deployment technology to install your application from Web site A, and you use the <xref:System.Windows.Forms.WebBrowser> to display Web site B, you will not be able to access Web site B's data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="361c2-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="361c2-124">See also</span></span>

- [<span data-ttu-id="361c2-125">\<프레임 > 요소</span><span class="sxs-lookup"><span data-stu-id="361c2-125">\<frame> element</span></span>](https://developer.mozilla.org/docs/Web/HTML/Element/frame)
- [<span data-ttu-id="361c2-126">관리되는 HTML 문서 개체 모델 사용</span><span class="sxs-lookup"><span data-stu-id="361c2-126">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)
