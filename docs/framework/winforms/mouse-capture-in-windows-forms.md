---
title: Windows Forms의 마우스 캡처
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: ca16d2fa2339f8d9110bb748a687f90e093598fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690330"
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="8acb1-102">Windows Forms의 마우스 캡처</span><span class="sxs-lookup"><span data-stu-id="8acb1-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="8acb1-103">*마우스 캡처* 컨트롤 명령의 모든 마우스 입력을 받는 시점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8acb1-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="8acb1-104">컨트롤이 마우스를 캡처, 포인터의 테두리 내 있는지 여부에 관계 없이 마우스 입력을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8acb1-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="8acb1-105">마우스 캡처를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8acb1-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="8acb1-106">Windows Forms 컨트롤에 마우스 단추를 누르면 마우스 단추를 놓을 때 컨트롤에서 마우스를 놓을 때 컨트롤에서 마우스가 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="8acb1-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="8acb1-107"><xref:System.Windows.Forms.Control.Capture%2A> 의 속성을 <xref:System.Windows.Forms.Control> 클래스 컨트롤이 마우스를 캡처 했는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8acb1-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="8acb1-108">컨트롤이 마우스 캡처를 손실 하는 경우를 확인 하려면 처리는 <xref:System.Windows.Forms.Control.MouseCaptureChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="8acb1-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="8acb1-109">전경 창이 마우스를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8acb1-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="8acb1-110">배경 창이 마우스를 캡처할 때 창 창의 표시 영역 내에서 마우스 포인터가 있을 때 발생 하는 마우스 이벤트의 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8acb1-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="8acb1-111">또한 전경 창이 마우스를 캡처한 경우에 여전히 클릭할 수 다른 창 전경으로 상태로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8acb1-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="8acb1-112">마우스를 캡처한 바로 가기 키 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8acb1-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8acb1-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="8acb1-113">See also</span></span>
- [<span data-ttu-id="8acb1-114">Windows Forms 애플리케이션의 마우스 입력</span><span class="sxs-lookup"><span data-stu-id="8acb1-114">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
