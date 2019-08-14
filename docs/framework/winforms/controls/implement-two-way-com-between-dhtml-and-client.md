---
title: '방법: DHTML 코드와 클라이언트 애플리케이션 코드 간의 양방향 통신 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.ObjectForScripting
- WebBrowser.Document
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- communications [Windows Forms], DHTML and client applications
- examples [Windows Forms], WebBrowser control
- WebBrowser control [Windows Forms], communication between DHTML and client application
- DHTML [Windows Forms], embedding in Windows Forms
ms.assetid: 55353a32-b09e-4479-a521-ff3a5ff9a708
ms.openlocfilehash: 45df54b3a590078eff6ddc1197db5b0124663cf5
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971915"
---
# <a name="how-to-implement-two-way-communication-between-dhtml-code-and-client-application-code"></a><span data-ttu-id="91507-102">방법: DHTML 코드와 클라이언트 애플리케이션 코드 간의 양방향 통신 구현</span><span class="sxs-lookup"><span data-stu-id="91507-102">How to: Implement Two-Way Communication Between DHTML Code and Client Application Code</span></span>

<span data-ttu-id="91507-103"><xref:System.Windows.Forms.WebBrowser> 컨트롤을 사용하여 Windows Forms 클라이언트 응용 프로그램에 기존 DHTML(동적 HTML) 웹 응용 프로그램 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91507-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to add existing dynamic HTML (DHTML) Web application code to your Windows Forms client applications.</span></span> <span data-ttu-id="91507-104">DHTML 기반 컨트롤을 만드는 데 상당한 개발 시간을 투자했으며 기존 코드를 다시 작성할 필요 없이 Windows Forms의 풍부한 사용자 인터페이스 기능을 활용하려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-104">This is useful when you have invested significant development time in creating DHTML-based controls and you want to take advantage of the rich user interface capabilities of Windows Forms without having to rewrite existing code.</span></span>

<span data-ttu-id="91507-105"><xref:System.Windows.Forms.WebBrowser> 컨트롤을 사용하면 <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> 및 <xref:System.Windows.Forms.WebBrowser.Document%2A> 속성을 통해 클라이언트 응용 프로그램 코드와 웹 페이지 스크립팅 코드 간의 양방향 통신을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91507-105">The <xref:System.Windows.Forms.WebBrowser> control lets you implement two-way communication between your client application code and your Web page scripting code through the <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> and <xref:System.Windows.Forms.WebBrowser.Document%2A> properties.</span></span> <span data-ttu-id="91507-106">또한 웹 컨트롤이 응용 프로그램 폼의 다른 컨트롤과 매끄럽게 혼합되어 해당 DHTML 구현을 숨기도록 <xref:System.Windows.Forms.WebBrowser> 컨트롤을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91507-106">Additionally, you can configure the <xref:System.Windows.Forms.WebBrowser> control so that your Web controls blend seamlessly with other controls on your application form, hiding their DHTML implementation.</span></span> <span data-ttu-id="91507-107">컨트롤을 매끄럽게 혼합하려면 배경색 및 시각적 스타일이 폼의 나머지 부분과 일치하도록 표시되는 페이지 형식을 지정하고 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>, <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> 및 <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> 속성을 통해 표준 브라우저 기능을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-107">To seamlessly blend the controls, format the page displayed so that its background color and visual style match the rest of the form, and use the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>, <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A>, and <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> properties to disable standard browser features.</span></span>

## <a name="to-embed-dhtml-in-your-windows-forms-application"></a><span data-ttu-id="91507-108">Windows Forms 응용 프로그램에 DHTML을 포함하려면</span><span class="sxs-lookup"><span data-stu-id="91507-108">To embed DHTML in your Windows Forms application</span></span>

1. <span data-ttu-id="91507-109"><xref:System.Windows.Forms.WebBrowser> 컨트롤의 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> 속성을 `false`로 설정하여 <xref:System.Windows.Forms.WebBrowser> 컨트롤이 놓여진 파일을 열지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-109">Set the <xref:System.Windows.Forms.WebBrowser> control's <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#1)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#1)]

2. <span data-ttu-id="91507-110">컨트롤의 <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> 속성을 `false`로 설정하여 사용자가 마우스 오른쪽 단추로 클릭할 때 <xref:System.Windows.Forms.WebBrowser> 컨트롤이 바로 가기 메뉴를 표시하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-110">Set the control's <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from displaying its shortcut menu when the user right-clicks it.</span></span>

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#2)]

3. <span data-ttu-id="91507-111">컨트롤의 <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> 속성을 `false`로 설정하여 <xref:System.Windows.Forms.WebBrowser> 컨트롤이 바로 가기 키에 응답하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-111">Set the control's <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from responding to shortcut keys.</span></span>

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#3)]

4. <span data-ttu-id="91507-112">폼의 생성자나 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-112">Set the <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> property in the form's constructor or a <xref:System.Windows.Forms.Form.Load> event handler.</span></span>

     <span data-ttu-id="91507-113">다음 코드에서는 스크립팅 개체에 대한 폼 클래스 자체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-113">The following code uses the form class itself for the scripting object.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="91507-114">COM(구성 요소 개체 모델)에서 스크립팅 개체에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-114">Component Object Model (COM) must be able to access the scripting object.</span></span> <span data-ttu-id="91507-115">COM에서 폼을 볼 수 있게 하려면 폼 클래스에 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-115">To make your form visible to COM, add the <xref:System.Runtime.InteropServices.ComVisibleAttribute> attribute to your form class.</span></span>

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#4)]

5. <span data-ttu-id="91507-116">스크립트 코드에서 사용할 공용 속성 또는 메서드를 응용 프로그램 코드에서 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-116">Implement public properties or methods in your application code that your script code will use.</span></span>

     <span data-ttu-id="91507-117">예를 들어 스크립팅 개체에 폼 클래스를 사용하는 경우 다음 코드를 폼 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-117">For example, if you use the form class for the scripting object, add the following code to your form class.</span></span>

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#5)]

6. <span data-ttu-id="91507-118">스크립팅 코드에서 `window.external` 개체를 사용하여 지정된 개체의 공용 속성 및 메서드에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-118">Use the `window.external` object in your scripting code to access public properties and methods of the specified object.</span></span>

     <span data-ttu-id="91507-119">다음 HTML 코드는 단추 클릭에서 스크립팅 개체에 대한 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="91507-119">The following HTML code demonstrates how to call a method on the scripting object from a button click.</span></span> <span data-ttu-id="91507-120">컨트롤의 <xref:System.Windows.Forms.WebBrowser.Navigate%2A> 메서드를 사용하여 로드하거나 컨트롤의 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 속성에 할당하는 HTML 문서의 BODY 요소에 이 코드를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-120">Copy this code into the BODY element of an HTML document that you load using the control's <xref:System.Windows.Forms.WebBrowser.Navigate%2A> method or that you assign to the control's <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property.</span></span>

    ```html
    <button onclick="window.external.Test('called from script code')">
        call client code from script code
    </button>
    ```

7. <span data-ttu-id="91507-121">응용 프로그램 코드에서 사용할 함수를 스크립트 코드에서 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-121">Implement functions in your script code that your application code will use.</span></span>

     <span data-ttu-id="91507-122">다음 HTML SCRIPT 요소는 예제 함수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-122">The following HTML SCRIPT element provides an example function.</span></span> <span data-ttu-id="91507-123">컨트롤의 <xref:System.Windows.Forms.WebBrowser.Navigate%2A> 메서드를 사용하여 로드하거나 컨트롤의 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 속성에 할당하는 HTML 문서의 HEAD 요소에 이 코드를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-123">Copy this code into the HEAD element of an HTML document that you load using the control's <xref:System.Windows.Forms.WebBrowser.Navigate%2A> method or that you assign to the control's <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property.</span></span>

    ```html
    <script>
    function test(message) {
        alert(message);
    }
    </script>
    ```

8. <span data-ttu-id="91507-124"><xref:System.Windows.Forms.WebBrowser.Document%2A> 속성을 사용하여 클라이언트 응용 프로그램 코드에서 스크립트 코드에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-124">Use the <xref:System.Windows.Forms.WebBrowser.Document%2A> property to access the script code from your client application code.</span></span>

     <span data-ttu-id="91507-125">예를 들어 단추 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-125">For example, add the following code to a button <xref:System.Windows.Forms.Control.Click> event handler.</span></span>

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#8)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#8)]

9. <span data-ttu-id="91507-126">DHTML 디버그가 완료되면 컨트롤의 <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A> 속성을 `true`로 설정하여 <xref:System.Windows.Forms.WebBrowser> 컨트롤이 스크립트 코드 문제에 대한 오류 메시지를 표시하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-126">When you are finished debugging your DHTML, set the control's <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A> property to `true` to prevent the <xref:System.Windows.Forms.WebBrowser> control from displaying error messages for script code problems.</span></span>

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#9)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#9)]

## <a name="example"></a><span data-ttu-id="91507-127">예제</span><span class="sxs-lookup"><span data-stu-id="91507-127">Example</span></span>

<span data-ttu-id="91507-128">다음 전체 코드 예제에서는 이 기능을 이해하는 데 사용할 수 있는 데모 응용 프로그램을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-128">The following complete code example provides a demonstration application that you can use to understand this feature.</span></span> <span data-ttu-id="91507-129">HTML 코드는 별도 HTML 파일에서 로드되지 않고 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 속성을 통해 <xref:System.Windows.Forms.WebBrowser> 컨트롤에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="91507-129">The HTML code is loaded into the <xref:System.Windows.Forms.WebBrowser> control through the <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property instead of being loaded from a separate HTML file.</span></span>

[!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="91507-130">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="91507-130">Compiling the Code</span></span>

<span data-ttu-id="91507-131">이 코드에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="91507-131">This code requires:</span></span>

- <span data-ttu-id="91507-132">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="91507-132">References to the System and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="91507-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="91507-133">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.Document%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A?displayProperty=nameWithType>
- [<span data-ttu-id="91507-134">WebBrowser 컨트롤</span><span class="sxs-lookup"><span data-stu-id="91507-134">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
