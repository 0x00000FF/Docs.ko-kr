---
title: "방법: 사용자 지정 이벤트 접근자 구현(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
caps.latest.revision: 7
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 71e1c16c9c6426ffb95020e4d7211dc1000f6796
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a><span data-ttu-id="92fc3-102">방법: 사용자 지정 이벤트 접근자 구현(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="92fc3-102">How to: Implement Custom Event Accessors (C# Programming Guide)</span></span>
<span data-ttu-id="92fc3-103">이벤트는 선언된 클래스 내에서만 호출할 수 있는 특수한 종류의 멀티캐스트 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="92fc3-103">An event is a special kind of multicast delegate that can only be invoked from within the class that  it is declared in.</span></span> <span data-ttu-id="92fc3-104">클라이언트 코드는 이벤트가 발생할 때 호출되어야 하는 메서드에 대한 참조를 제공하여 이벤트를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="92fc3-104">Client code subscribes to the event by providing a reference to a method that should be invoked when the event is fired.</span></span> <span data-ttu-id="92fc3-105">이러한 메서드는 이벤트 접근자의 이름이 `add` 및 `remove`로 지정된다는 점을 제외하고 속성 접근자와 유사한 이벤트 접근자를 통해 대리자의 호출 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="92fc3-105">These methods are added to the delegate's invocation list through event accessors, which resemble property accessors, except that event accessors are named `add` and `remove`.</span></span> <span data-ttu-id="92fc3-106">대부분의 경우 사용자 지정 이벤트 접근자를 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92fc3-106">In most cases, you do not have to supply custom event accessors.</span></span> <span data-ttu-id="92fc3-107">코드에서 사용자 지정 이벤트 접근자를 제공하지 않으면 컴파일러가 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="92fc3-107">When no custom event accessors are supplied in your code, the compiler will add them automatically.</span></span> <span data-ttu-id="92fc3-108">그러나 경우에 따라 사용자 지정 동작을 제공해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92fc3-108">However, in some cases you may have to provide custom behavior.</span></span> <span data-ttu-id="92fc3-109">[방법: 인터페이스 이벤트 구현](../../../csharp/programming-guide/events/how-to-implement-interface-events.md) 항목에는 이러한 사례 중 하나가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92fc3-109">One such case is shown in the topic [How to:  Implement Interface Events](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="92fc3-110">예제</span><span class="sxs-lookup"><span data-stu-id="92fc3-110">Example</span></span>  
 <span data-ttu-id="92fc3-111">다음 예제에서는 사용자 지정 add 및 remove 이벤트 접근자를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92fc3-111">The following example shows how to implement custom add and remove event accessors.</span></span> <span data-ttu-id="92fc3-112">접근자 내의 모든 코드를 대체할 수 있지만 새 이벤트 처리기 메서드를 추가하거나 제거하기 전에 이벤트를 잠그는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="92fc3-112">Although you can substitute any code inside the accessors, we recommend that you lock the event before you add or remove a new event handler method.</span></span>  
  
```  
event EventHandler IDrawingObject.OnDraw  
        {  
            add  
            {  
                lock (PreDrawEvent)  
                {  
                    PreDrawEvent += value;  
                }  
            }  
            remove  
            {  
                lock (PreDrawEvent)  
                {  
                    PreDrawEvent -= value;  
                }  
            }  
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="92fc3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92fc3-113">See Also</span></span>  
 <span data-ttu-id="92fc3-114">[이벤트](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="92fc3-114">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 [<span data-ttu-id="92fc3-115">event</span><span class="sxs-lookup"><span data-stu-id="92fc3-115">event</span></span>](../../../csharp/language-reference/keywords/event.md)

