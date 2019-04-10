---
title: '방법: 런타임 시 Windows Forms의 이벤트 처리기 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
ms.openlocfilehash: 09f090c6267093e3ad59266d8c77ea13b13b63d3
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343269"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a><span data-ttu-id="775fb-102">방법: 런타임 시 Windows Forms의 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="775fb-102">How to: Create Event Handlers at Run Time for Windows Forms</span></span>
<span data-ttu-id="775fb-103">Windows Forms 디자이너를 사용하여 이벤트를 만들 수 있을 뿐만 아니라 런타임에 이벤트 처리기를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="775fb-103">In addition to creating events using the Windows Forms Designer, you can also create an event handler at run time.</span></span> <span data-ttu-id="775fb-104">이렇게 하면 프로그램이 처음 시작될 때 이벤트 처리기를 연결하는 대신 런타임에 코드를 사용하여 조건에 따라 이벤트 처리기를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="775fb-104">This action allows you to connect event handlers based on conditions in code at run time as opposed to having them connected when the program initially starts.</span></span>  
  
### <a name="to-create-an-event-handler-at-run-time"></a><span data-ttu-id="775fb-105">런타임에 이벤트 처리기를 만들려면</span><span class="sxs-lookup"><span data-stu-id="775fb-105">To create an event handler at run time</span></span>  
  
1. <span data-ttu-id="775fb-106">이벤트 처리기를 추가할 양식을 코드 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="775fb-106">Open the form in the Code Editor that you want to add an event handler to.</span></span>  
  
2. <span data-ttu-id="775fb-107">처리할 이벤트의 메서드 시그니처가 있는 양식에 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="775fb-107">Add a method to your form with the method signature for the event that you want to handle.</span></span>  
  
     <span data-ttu-id="775fb-108">예를 들어 처리 하는 경우는 <xref:System.Windows.Forms.Control.Click> 의 이벤트를 <xref:System.Windows.Forms.Button> 컨트롤 같은 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="775fb-108">For example, if you were handling the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control, you would create a method such as the following:</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)  
       ' Add event handler code here.  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
    // Add event handler code here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          // Add event handler code here.  
       }  
    ```  
  
3. <span data-ttu-id="775fb-109">애플리케이션에 적합한 코드를 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="775fb-109">Add code to the event handler as appropriate to your application.</span></span>  
  
4. <span data-ttu-id="775fb-110">이벤트 처리기를 만들 양식 또는 컨트롤을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="775fb-110">Determine which form or control you want to create an event handler for.</span></span>  
  
5. <span data-ttu-id="775fb-111">양식의 클래스에 있는 메서드에 이벤트를 처리할 이벤트 처리기를 지정하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="775fb-111">In a method within your form's class, add code that specifies the event handler to handle the event.</span></span> <span data-ttu-id="775fb-112">다음 코드에서는 이벤트 처리기를 지정 하는 예를 들어 `button1_Click` 핸들을 <xref:System.Windows.Forms.Control.Click> 이벤트를 <xref:System.Windows.Forms.Button> 제어:</span><span class="sxs-lookup"><span data-stu-id="775fb-112">For example, the following code specifies the event handler `button1_Click` handles the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control:</span></span>  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="775fb-113"><xref:System.ComponentModel.EventHandlerList.AddHandler%2A> 위의 Visual Basic 코드에서 설명 하는 방법에는 단추의 click 이벤트 처리기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="775fb-113">The <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> method demonstrated in the Visual Basic code above establishes a click event handler for the button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="775fb-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="775fb-114">See also</span></span>

- [<span data-ttu-id="775fb-115">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="775fb-115">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="775fb-116">이벤트 처리기 개요</span><span class="sxs-lookup"><span data-stu-id="775fb-116">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
- [<span data-ttu-id="775fb-117">Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="775fb-117">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
