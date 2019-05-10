---
title: Windows Forms에서 이벤트 처리기 만들기
ms.date: 03/30/2017
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
ms.openlocfilehash: 329060e0c53178a9320be9a7cdff492d69917782
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211243"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="08b47-102">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="08b47-102">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="08b47-103">이벤트 처리기는 사용자가 단추를 클릭하거나 메시지 큐에서 메시지를 수신하는 등의 이벤트 발생 시 수행되는 작업을 결정하는 코드 내의 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="08b47-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="08b47-104">이벤트가 발생하면 해당 이벤트를 수신하는 하나 이상의 이벤트 처리기가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b47-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="08b47-105">이벤트는 여러 처리기에 할당될 수 있으며 특정 이벤트를 처리하는 메서드가 동적으로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b47-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="08b47-106">이벤트 처리기를 만들려면 Visual Studio에서 Windows Forms 디자이너를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b47-106">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="08b47-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="08b47-107">In This Section</span></span>

 <span data-ttu-id="08b47-108">[이벤트 개요](events-overview-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="08b47-108">[Events Overview](events-overview-windows-forms.md)\\</span></span>
 <span data-ttu-id="08b47-109">이벤트 모델과 대리자 역할에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08b47-109">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="08b47-110">[이벤트 처리기 개요](event-handlers-overview-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="08b47-110">[Event Handlers Overview](event-handlers-overview-windows-forms.md)\\</span></span>
 <span data-ttu-id="08b47-111">이벤트를 처리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08b47-111">Describes how to handle events.</span></span>

 <span data-ttu-id="08b47-112">[방법: 런타임에 Windows Forms 이벤트 처리기 만들기](how-to-create-event-handlers-at-run-time-for-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="08b47-112">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)\\</span></span>
 <span data-ttu-id="08b47-113">시스템 또는 사용자 이벤트에 동적으로 응답하는 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="08b47-113">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="08b47-114">[방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="08b47-114">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)\\</span></span>
 <span data-ttu-id="08b47-115">이벤트를 통해 여러 컨트롤에 같은 기능을 할당하도록 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="08b47-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="08b47-116">[Windows Forms의 이벤트 순서](order-of-events-in-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="08b47-116">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)\\</span></span>
 <span data-ttu-id="08b47-117">Windows Forms 컨트롤에서 이벤트가 발생하는 순서에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08b47-117">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="08b47-118">[방법: 디자이너를 사용 하 여 이벤트 처리기 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Windows Forms 디자이너를 사용 하 여 이벤트 처리기를 만드는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b47-118">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="08b47-119">관련 단원</span><span class="sxs-lookup"><span data-stu-id="08b47-119">Related Sections</span></span>

 <span data-ttu-id="08b47-120">[이벤트](../../standard/events/index.md)\\</span><span class="sxs-lookup"><span data-stu-id="08b47-120">[Events](../../standard/events/index.md)\\</span></span>
 <span data-ttu-id="08b47-121">처리에 사용 하 여 이벤트를 발생 시키는 항목에 대 한 링크를 제공 합니다 [!INCLUDE [dnprdnshort](../../../includes/dnprdnshort-md.md)\].</span><span class="sxs-lookup"><span data-stu-id="08b47-121">Provides links to topics on handling and raising events using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)\].</span></span>

 <span data-ttu-id="08b47-122">[Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)\\</span><span class="sxs-lookup"><span data-stu-id="08b47-122">[Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)\\</span></span>
 <span data-ttu-id="08b47-123">상속된 구성 요소의 이벤트 처리기에서 발생하는 일반적인 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08b47-123">Lists common issues that occur with event handlers in inherited components.</span></span>
