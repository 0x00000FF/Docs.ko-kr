---
title: 이벤트 디자인
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b257da73d33fae54ef464e9dd69906316b87fd88
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2018
ms.locfileid: "44353856"
---
# <a name="event-design"></a><span data-ttu-id="4123f-102">이벤트 디자인</span><span class="sxs-lookup"><span data-stu-id="4123f-102">Event Design</span></span>
<span data-ttu-id="4123f-103">이벤트는 자주 사용 하는 형식의 콜백 (사용자 코드를 호출 하기 위해 프레임 워크를 사용할 수 있는 구문)입니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="4123f-104">대리자, 가상 멤버 및 인터페이스 기반 플러그 인을 수행 하는 멤버를 포함 하는 다른 콜백 메커니즘입니다. 유용성 연구에서 데이터는 대부분의 개발자는 더 편리한 다른 콜백 메커니즘을 사용 하는 것 보다 이벤트를 사용 하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="4123f-105">이벤트는 Visual Studio 및 다양 한 언어와 원활 하 게 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-105">Events are nicely integrated with Visual Studio and many languages.</span></span>  
  
 <span data-ttu-id="4123f-106">두 개의 그룹 이벤트에는 반드시:의 상태가 사전 이벤트 및 상태 변경 후에 발생 하는 이벤트를 호출 하는 시스템 변경 하기 전에 발생 하는 이벤트 후 이벤트를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="4123f-107">사전 이벤트의 예로 `Form.Closing`, 폼이 닫히기 전에 발생 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="4123f-108">이후 이벤트의 예로 `Form.Closed`, 폼을 닫은 후 발생 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>  
  
 <span data-ttu-id="4123f-109">**✓ DO** "발생" 이라는 용어를 사용 하 여 이벤트 보다는 "발생" 시키는"또는"트리거"입니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-109">**✓ DO** use the term "raise" for events rather than "fire" or "trigger."</span></span>  
  
 <span data-ttu-id="4123f-110">**✓ DO** 사용 <xref:System.EventHandler%601?displayProperty=nameWithType> 수동으로 이벤트 처리기로 사용할 새 대리자를 만드는 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-110">**✓ DO** use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>  
  
 <span data-ttu-id="4123f-111">**✓ CONSIDER** 의 서브 클래스를 사용 하 여 <xref:System.EventArgs> 이벤트 인수로 제외 이벤트 데이터를 이벤트 처리 메서드를 필요가 없습니다 확실히 경우에서 사용할 수 있습니다는 `EventArgs` 직접 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-111">**✓ CONSIDER** using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>  
  
 <span data-ttu-id="4123f-112">사용 하 여 API를 제공 하는 경우 `EventArgs` 직접 있습니다 됩니다 수 호환성을 중단 하지 않고 이벤트를 사용 하 여 수행 하도록 데이터를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="4123f-113">서브 클래스를 사용 하는 경우에 하는 경우 처음에 완전히 빈 됩니다 필요할 때 하위 클래스에 속성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>  
  
 <span data-ttu-id="4123f-114">**✓ DO** 보호 된 가상 메서드를 사용 하 여 각 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-114">**✓ DO** use a protected virtual method to raise each event.</span></span> <span data-ttu-id="4123f-115">만 비정적 이벤트 봉인 되지 않은 클래스, 구조체, 봉인 된 클래스 또는 정적 이벤트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>  
  
 <span data-ttu-id="4123f-116">메서드의 용도 파생된 클래스 재정의 사용 하 여 이벤트를 처리 하는 방법을 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="4123f-117">파생된 클래스에서 기본 클래스 이벤트를 처리 하는 방법을 더 유연 하 고 더 빠르고, 더 자연 스러운 경우 재정의</span><span class="sxs-lookup"><span data-stu-id="4123f-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="4123f-118">규칙에 따라 메서드의 이름을 "On"로 시작 해야 하 고 이벤트의 이름으로와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>  
  
 <span data-ttu-id="4123f-119">파생된 클래스는 재정의에서 메서드의 기본 구현을 호출 하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="4123f-120">제대로 작동 하려면 기본 클래스에 필요한 메서드의 처리를 포함 하 여이 준비 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>  
  
 <span data-ttu-id="4123f-121">**✓ DO** 하나의 매개 변수는 이벤트를 발생 시키는 보호 된 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-121">**✓ DO** take one parameter to the protected method that raises an event.</span></span>  
  
 <span data-ttu-id="4123f-122">매개 변수 이름은 `e` 및 이벤트 인수 클래스로 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>  
  
 <span data-ttu-id="4123f-123">**X DO NOT** 비정적 이벤트를 발생 시킬 때 보낸 사람으로 null을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-123">**X DO NOT** pass null as the sender when raising a nonstatic event.</span></span>  
  
 <span data-ttu-id="4123f-124">**✓ DO** 정적 이벤트를 발생 시킬 때 보낸 사람으로 null을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-124">**✓ DO** pass null as the sender when raising a static event.</span></span>  
  
 <span data-ttu-id="4123f-125">**X DO NOT** 이벤트를 발생 시키는 경우 이벤트 데이터 매개 변수와 null을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-125">**X DO NOT** pass null as the event data parameter when raising an event.</span></span>  
  
 <span data-ttu-id="4123f-126">전달 해야 `EventArgs.Empty` 모든 데이터 이벤트 처리 메서드를 전달 하지 않을 경우.</span><span class="sxs-lookup"><span data-stu-id="4123f-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="4123f-127">개발자는이 매개 변수가 null 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-127">Developers expect this parameter not to be null.</span></span>  
  
 <span data-ttu-id="4123f-128">**✓ CONSIDER** 최종 사용자가 취소할 수 있는 이벤트를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-128">**✓ CONSIDER** raising events that the end user can cancel.</span></span> <span data-ttu-id="4123f-129">이 사전 이벤트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-129">This only applies to pre-events.</span></span>  
  
 <span data-ttu-id="4123f-130">사용 하 여 <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> 또는 최종 사용자가 이벤트를 취소할 수 있도록 이벤트 인수로 해당 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>  
  
### <a name="custom-event-handler-design"></a><span data-ttu-id="4123f-131">사용자 지정 이벤트 처리기 디자인</span><span class="sxs-lookup"><span data-stu-id="4123f-131">Custom Event Handler Design</span></span>  
 <span data-ttu-id="4123f-132">경우에는 `EventHandler<T>` 같은 프레임 워크를 제네릭을 지원 하지 않는 clr 버전을 사용 해야 하는 경우 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="4123f-133">이러한 경우를 디자인 하는 사용자 지정 이벤트 처리기 대리자를 개발 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>  
  
 <span data-ttu-id="4123f-134">**✓ DO** 이벤트 처리기에 대 한 void의 반환 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-134">**✓ DO** use a return type of void for event handlers.</span></span>  
  
 <span data-ttu-id="4123f-135">이벤트 처리기에 여러 이벤트 처리 가능한 여러 개체에서 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="4123f-136">이벤트 처리 메서드가 값을 반환할 수, 각 이벤트 호출에 대 한 여러 개의 반환 값은입니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>  
  
 <span data-ttu-id="4123f-137">**✓ DO** 사용 `object` 이벤트 처리기의 첫 번째 매개 변수 형식으로 버전을 호출 `sender`합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-137">**✓ DO** use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>  
  
 <span data-ttu-id="4123f-138">**✓ DO** 사용 <xref:System.EventArgs?displayProperty=nameWithType> 또는 해당 하위 클래스의 이벤트 처리기의 두 번째 매개 변수 형식으로 버전을 호출 `e`합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-138">**✓ DO** use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>  
  
 <span data-ttu-id="4123f-139">**X DO NOT** 이벤트 처리기에 두 개 이상의 매개 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4123f-139">**X DO NOT** have more than two parameters on event handlers.</span></span>  
  
 <span data-ttu-id="4123f-140">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="4123f-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="4123f-141">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="4123f-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4123f-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="4123f-142">See also</span></span>

- [<span data-ttu-id="4123f-143">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="4123f-143">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="4123f-144">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="4123f-144">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
