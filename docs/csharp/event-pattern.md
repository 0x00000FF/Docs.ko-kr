---
title: 표준 .NET 이벤트 패턴
description: 표준 이벤트 소스를 만들고 코드에서 표준 이벤트를 구독 및 처리하는 방법과 .NET 이벤트 패턴에 대해 알아봅니다.
ms.date: 06/20/2016
ms.assetid: 8a3133d6-4ef2-46f9-9c8d-a8ea8898e4c9
ms.openlocfilehash: 16a091dabe34a064ab3ee65a6d9f3e0ab36f1db4
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129404"
---
# <a name="standard-net-event-patterns"></a><span data-ttu-id="0dc76-103">표준 .NET 이벤트 패턴</span><span class="sxs-lookup"><span data-stu-id="0dc76-103">Standard .NET event patterns</span></span>

[<span data-ttu-id="0dc76-104">이전</span><span class="sxs-lookup"><span data-stu-id="0dc76-104">Previous</span></span>](events-overview.md)

<span data-ttu-id="0dc76-105">.NET 이벤트는 일반적으로 몇 가지 알려진 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-105">.NET events generally follow a few known patterns.</span></span> <span data-ttu-id="0dc76-106">이러한 패턴의 표준화는 개발자가 해당 표준 패턴에 대한 지식을 활용하여 모든 .NET 이벤트 프로그램에 적용할 수 있다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-106">Standardizing on these patterns means that developers can leverage knowledge of those standard patterns, which can be applied to any .NET event program.</span></span>

<span data-ttu-id="0dc76-107">표준 이벤트 소스를 만들고 코드에서 표준 이벤트를 구독 및 처리하는 데 필요한 모든 정보를 얻을 수 있도록 이러한 표준 패턴을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-107">Let's go through these standard patterns so you will have all the knowledge you need to create standard event sources, and subscribe and process standard events in your code.</span></span>

## <a name="event-delegate-signatures"></a><span data-ttu-id="0dc76-108">이벤트 대리자 시그니처</span><span class="sxs-lookup"><span data-stu-id="0dc76-108">Event Delegate Signatures</span></span>

<span data-ttu-id="0dc76-109">.NET 이벤트 대리자에 대한 표준 시그니처는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-109">The standard signature for a .NET event delegate is:</span></span>

```csharp
void OnEventRaised(object sender, EventArgs args);
```

<span data-ttu-id="0dc76-110">반환 형식은 void입니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-110">The return type is void.</span></span> <span data-ttu-id="0dc76-111">이벤트는 대리자를 기반으로 하며 멀티캐스트 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-111">Events are based on delegates and are multicast delegates.</span></span> <span data-ttu-id="0dc76-112">또한 모든 이벤트 소스에 대해 여러 구독자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-112">That supports multiple subscribers for any event source.</span></span> <span data-ttu-id="0dc76-113">메서드의 단일 반환 값은 여러 이벤트 구독자로 확장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-113">The single return value from a method doesn't scale to multiple event subscribers.</span></span> <span data-ttu-id="0dc76-114">이벤트 발생 후 이벤트 소스에 표시되는 반환 값은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="0dc76-114">Which return value does the event source see after raising an event?</span></span> <span data-ttu-id="0dc76-115">이 문서의 뒷부분에서 이벤트 소스에 정보를 보고하는 이벤트 구독자를 지원하는 이벤트 프로토콜을 만드는 방법에 대해 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-115">Later in this article you'll see how to create event protocols that support event subscribers that report information to the event source.</span></span>

<span data-ttu-id="0dc76-116">인수 목록에는 보낸 사람과 이벤트 인수의 두 인수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-116">The argument list contains two arguments: the sender, and the event arguments.</span></span> <span data-ttu-id="0dc76-117">`sender`의 컴파일 시간 형식은 `System.Object`이지만 항상 올바른 더 많이 파생된 형식을 알고 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-117">The compile time type of `sender` is `System.Object`, even though you likely know a more derived type that would always be correct.</span></span> <span data-ttu-id="0dc76-118">규칙에 따라 `object`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-118">By convention, use `object`.</span></span>

<span data-ttu-id="0dc76-119">두 번째 인수는 일반적으로 `System.EventArgs`에서 파생된 형식이었습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-119">The second argument has typically been a type that is derived from `System.EventArgs`.</span></span> <span data-ttu-id="0dc76-120">[다음 섹션](modern-events.md)에서 이 규칙이 더 이상 적용되지 않음을 확인할 수 있습니다. 이벤트 형식에 추가 인수가 필요하지 않은 경우 두 인수를 계속 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-120">(You'll see in the [next section](modern-events.md) that this convention is no longer enforced.) If your event type does not need any additional arguments, you will still provide both arguments.</span></span>
<span data-ttu-id="0dc76-121">이벤트에 추가 정보가 포함되어 있지 않음을 나타낼 때 사용해야 하는 특수 값 `EventArgs.Empty`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-121">There is a special value, `EventArgs.Empty` that you should use to denote that your event does not contain any additional information.</span></span>

<span data-ttu-id="0dc76-122">디렉터리 또는 패턴을 따르는 모든 하위 디렉터리의 파일을 나열하는 클래스를 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-122">Let's build a class that lists files in a directory, or any of its subdirectories that follow a pattern.</span></span> <span data-ttu-id="0dc76-123">이 구성 요소는 검색된 각 파일에 대해 패턴과 일치하는 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-123">This component raises an event for each file found that matches the pattern.</span></span>

<span data-ttu-id="0dc76-124">이벤트 모델을 사용하면 몇 가지 디자인 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-124">Using an event model provides some design advantages.</span></span> <span data-ttu-id="0dc76-125">검색된 파일을 찾으면 다른 작업을 수행하는 여러 이벤트 수신기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-125">You can create multiple event listeners that perform different actions when a sought file is found.</span></span> <span data-ttu-id="0dc76-126">서로 다른 수신기를 결합하면 더 강력한 알고리즘을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-126">Combining the different listeners can create more robust algorithms.</span></span>

<span data-ttu-id="0dc76-127">검색된 파일을 찾기 위한 초기 이벤트 인수 선언은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-127">Here is the initial event argument declaration for finding a sought file:</span></span> 

[!code-csharp[EventArgs](../../samples/csharp/events/Program.cs#EventArgsV1 "Define event arguments")]

<span data-ttu-id="0dc76-128">이 형식은 작은 데이터 전용 형식처럼 보이지만 규칙을 따르고 참조(`class`) 형식으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-128">Even though this type looks like a small, data-only type, you should follow the convention and make it a reference (`class`) type.</span></span> <span data-ttu-id="0dc76-129">즉, 인수 개체가 참조로 전달되며 모든 구독자가 데이터에 대한 모든 업데이트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-129">That means the argument object will be passed by reference, and any updates to the data will be viewed by all subscribers.</span></span> <span data-ttu-id="0dc76-130">첫 번째 버전은 변경할 수 없는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-130">The first version is an immutable object.</span></span> <span data-ttu-id="0dc76-131">이벤트 인수 형식에서 속성을 변경할 수 없도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-131">You should prefer to make the properties in your event argument type immutable.</span></span> <span data-ttu-id="0dc76-132">이런 방식으로 다른 구독자에게 값이 표시되기 전에는 한 구독자가 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-132">That way, one subscriber cannot change the values before another subscriber sees them.</span></span> <span data-ttu-id="0dc76-133">여기에는 아래와 가은 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-133">(There are exceptions to this, as you'll see below.)</span></span>  

<span data-ttu-id="0dc76-134">다음으로 FileSearcher 클래스에서 이벤트 선언을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-134">Next, we need to create the event declaration in the FileSearcher class.</span></span> <span data-ttu-id="0dc76-135">`EventHandler<T>` 형식을 활용하면 또 다른 형식 정의를 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-135">Leveraging the `EventHandler<T>` type means that you don't need to create yet another type definition.</span></span> <span data-ttu-id="0dc76-136">제네릭 특수화를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-136">You simply use a generic specialization.</span></span>

<span data-ttu-id="0dc76-137">FileSearcher 클래스를 입력하여 패턴과 일치하는 파일을 검색하고 일치하는 항목이 검색되면 올바른 이벤트를 발생시켜 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-137">Let's fill out the FileSearcher class to search for files that match a pattern, and raise the correct event when a match is discovered.</span></span>

[!code-csharp[FileSearxcher](../../samples/csharp/events/Program.cs#FileSearcherV1 "Create the initial file searcher")]

## <a name="defining-and-raising-field-like-events"></a><span data-ttu-id="0dc76-138">필드와 유사한 이벤트 정의 및 발생</span><span class="sxs-lookup"><span data-stu-id="0dc76-138">Defining and Raising Field-Like Events</span></span>

<span data-ttu-id="0dc76-139">이벤트를 클래스에 추가하는 가장 간단한 방법은 이전 예제와 같이 해당 이벤트를 public 필드로 선언하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-139">The simplest way to add an event to your class is to declare that event as a public field, as in the preceding example:</span></span>

[!code-csharp[DeclareEvent](../../samples/csharp/events/Program.cs#DeclareEvent "Declare the file found event")]

<span data-ttu-id="0dc76-140">이 예제는 public 필드를 선언하는 것처럼 보이며, 잘못된 개체 지향 사례인 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-140">This looks like it's declaring a public field, which would appear to be bad object-oriented practice.</span></span> <span data-ttu-id="0dc76-141">속성 또는 메서드를 통해 데이터 액세스를 보호하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-141">You want to protect data access through properties, or methods.</span></span> <span data-ttu-id="0dc76-142">이렇게 하면 잘못된 사례처럼 보이지만 안전한 방식으로 이벤트 개체에만 액세스할 수 있도록 컴파일러에 의해 생성된 코드에서 래퍼를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-142">While this make look like a bad practice, the code generated by the compiler does create wrappers so that the event objects can only be accessed in safe ways.</span></span> <span data-ttu-id="0dc76-143">필드와 유사한 이벤트에서 사용 가능한 유일한 작업은 처리기 추가입니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-143">The only operations available on a field-like event are add handler:</span></span>

[!code-csharp[DeclareEventHandler](../../samples/csharp/events/Program.cs#DeclareEventHandler "Declare the file found event handler")]

<span data-ttu-id="0dc76-144">또한 처리기 제거도 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-144">and remove handler:</span></span>

[!code-csharp[RemoveEventHandler](../../samples/csharp/events/Program.cs#RemoveHandler "Remove the event handler")]

<span data-ttu-id="0dc76-145">처리기에 대한 지역 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-145">Note that there's a local variable for the handler.</span></span> <span data-ttu-id="0dc76-146">람다 식의 본문을 사용한 경우 제거가 올바르게 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-146">If you used the body of the lambda, the remove would not work correctly.</span></span> <span data-ttu-id="0dc76-147">대리자의 다른 인스턴스가 되고 자동으로 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-147">It would be a different instance of the delegate, and silently do nothing.</span></span>

<span data-ttu-id="0dc76-148">클래스 외부의 코드는 이벤트를 발생시킬 수 없으며 다른 작업도 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-148">Code outside the class cannot raise the event, nor can it perform any other operations.</span></span>

## <a name="returning-values-from-event-subscribers"></a><span data-ttu-id="0dc76-149">이벤트 구독자에서 값 반환</span><span class="sxs-lookup"><span data-stu-id="0dc76-149">Returning Values from Event Subscribers</span></span>

<span data-ttu-id="0dc76-150">간단한 버전은 제대로 작동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-150">Your simple version is working fine.</span></span> <span data-ttu-id="0dc76-151">이제 또 다른 기능인 취소를 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-151">Let's add another feature: Cancellation.</span></span>

<span data-ttu-id="0dc76-152">찾은 이벤트를 발생시킬 때 이 파일이 마지막으로 검색된 파일인 경우 수신기에서 추가 처리를 중지할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-152">When you raise the found event, listeners should be able to stop further processing, if this file is that last one sought.</span></span>

<span data-ttu-id="0dc76-153">이벤트 처리기는 값을 반환하지 않으므로 다른 방식으로 값을 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-153">The event handlers do not return a value, so you need to communicate that in another way.</span></span> <span data-ttu-id="0dc76-154">표준 이벤트 패턴은 EventArgs 개체를 사용하 여 이벤트 구독자가 취소를 전달하는 데 사용할 수 있는 필드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-154">The standard event pattern uses the EventArgs object to include fields that event subscribers can use to communicate cancel.</span></span>

<span data-ttu-id="0dc76-155">취소 계약의 의미 체계에 따라 두 가지 다른 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-155">There are two different patterns that could be used, based on the semantics of the Cancel contract.</span></span> <span data-ttu-id="0dc76-156">두 경우 모두 찾은 파일 이벤트에 대한 EventArguments에 부울 필드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-156">In both cases, you'll add a boolean field to the EventArguments for the found file event.</span></span> 

<span data-ttu-id="0dc76-157">한 가지 패턴에서는 임의의 구독자 한 명이 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-157">One pattern would allow any one subscriber to cancel the operation.</span></span>
<span data-ttu-id="0dc76-158">이 패턴에서는 새 필드가 `false`로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-158">For this pattern, the new field is initialized to `false`.</span></span> <span data-ttu-id="0dc76-159">임의의 구독자가 이 값을 `true`로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-159">Any subscriber can change it to `true`.</span></span> <span data-ttu-id="0dc76-160">모든 구독자가 발생된 이벤트를 확인하면 FileSearcher 구성 요소에서 부울 값을 검사하고 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-160">After all subscribers have seen the event raised, the FileSearcher component examines the boolean value and takes action.</span></span>

<span data-ttu-id="0dc76-161">두 번째 패턴에서는 모든 구독자가 작업 취소를 원하는 경우에만 작업을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-161">The second pattern would only cancel the operation if all subscribers wanted the operation cancelled.</span></span> <span data-ttu-id="0dc76-162">이 패턴에서는 작업이 취소되어야 함을 나타내도록 새 필드가 초기화되고 임의의 구독자는 작업이 계속되어야 함을 나타내도록 이 필드를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-162">In this pattern, the new field is initialized to indicate the operation should cancel, and any subscriber could change it to indicate the operation should continue.</span></span>
<span data-ttu-id="0dc76-163">모든 구독자가 발생된 이벤트를 확인하면 FileSearcher 구성 요소에서 부울 값을 검사하고 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-163">After all subscribers have seen the event raised, the FileSearcher component examines the boolean and takes action.</span></span> <span data-ttu-id="0dc76-164">이 패턴에는 하나의 추가 단계가 있습니다. 구독자가 이벤트를 확인했는지 여부를 구성 요소에서 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-164">There is one extra step in this pattern: the component needs to know if any subscribers have seen the event.</span></span> <span data-ttu-id="0dc76-165">구독자가 없으면 필드는 취소를 잘못 나타내게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-165">If there are no subscribers, the field would indicate a cancel incorrectly.</span></span>

<span data-ttu-id="0dc76-166">이 샘플에 대한 첫 번째 버전을 구현해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-166">Let's implement the first version for this sample.</span></span> <span data-ttu-id="0dc76-167">`CancelRequested`라는 부울 필드를 `FileFoundArgs` 형식에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-167">You need to add a boolean field named `CancelRequested` to the `FileFoundArgs` type:</span></span>

[!code-csharp[EventArgs](../../samples/csharp/events/Program.cs#EventArgs "Update event arguments")]

<span data-ttu-id="0dc76-168">이 새 필드는 자동으로 부울 필드의 기본값인 `false`로 초기화되므로 실수로 취소될 가능성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-168">This new Field is automatically initialized to `false`, the default value for a Boolean field, so you don't cancel accidentally.</span></span> <span data-ttu-id="0dc76-169">구성 요소에서 유일한 다른 변경 사항은 이벤트를 발생시킨 후 플래그를 확인하여 구독자가 취소를 요청했는지를 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-169">The only other change to the component is to check the flag after raising the event to see if any of the subscribers have requested a cancellation:</span></span>

```csharp
public void List(string directory, string searchPattern)
{
    foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
    {
        var args = new FileFoundArgs(file);
        FileFound?.Invoke(this, args);
        if (args.CancelRequested)
            break;
    }
}
```

<span data-ttu-id="0dc76-170">이 패턴의 한 가지 장점은 새로운 변경 사항이 아니라는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-170">One advantage of this pattern is that it isn't a breaking change.</span></span>
<span data-ttu-id="0dc76-171">이전에 취소를 요청한 구독자가 없으며 여전히 요청하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-171">None of the subscribers requested a cancellation before, and they still are not.</span></span> <span data-ttu-id="0dc76-172">새로운 취소 프로토콜을 지원하려는 경우가 아니라면 구독자 코드를 업데이트할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-172">None of the subscriber code needs updating unless they want to support the new cancel protocol.</span></span> <span data-ttu-id="0dc76-173">이 경우 매우 느슨하게 결합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-173">It's very loosely coupled.</span></span>

<span data-ttu-id="0dc76-174">첫 번째 실행 파일을 찾으면 취소를 요청하도록 구독자를 업데이트해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-174">Let's update the subscriber so that it requests a cancellation once it finds the first executable:</span></span>

```csharp
EventHandler<FileFoundArgs> onFileFound = (sender, eventArgs) =>
{
    Console.WriteLine(eventArgs.FoundFile);
    eventArgs.CancelRequested = true;
};
```

## <a name="adding-another-event-declaration"></a><span data-ttu-id="0dc76-175">다른 이벤트 선언 추가</span><span class="sxs-lookup"><span data-stu-id="0dc76-175">Adding Another Event Declaration</span></span>

<span data-ttu-id="0dc76-176">기능을 하나 더 추가하고 이벤트에 대한 다른 언어 관용구를 보여 드리겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-176">Let's add one more feature, and demonstrate other language idioms for events.</span></span> <span data-ttu-id="0dc76-177">파일 검색에서 모든 하위 디렉터리를 트래버스하는 `Search` 메서드의 오버로드를 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-177">Let's add an overload of the `Search` method that traverses all subdirectories in search of files.</span></span>

<span data-ttu-id="0dc76-178">하위 디렉터리가 많은 디렉터리에서 이 작업은 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-178">This could get to be a lengthy operation in a directory with many sub-directories.</span></span> <span data-ttu-id="0dc76-179">각각의 새 디렉터리 검색이 시작될 때 발생되는 이벤트를 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-179">Let's add an event that gets raised when each new directory search begins.</span></span> <span data-ttu-id="0dc76-180">이렇게 하면 구독자가 진행률을 추적하고 진행률에 대해 사용자에게 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-180">This enables subscribers to track progress, and update the user as to progress.</span></span> <span data-ttu-id="0dc76-181">지금까지 만든 모든 샘플은 public입니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-181">All the samples you've created so far are public.</span></span> <span data-ttu-id="0dc76-182">이제 내부 이벤트로 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-182">Let's make this one an internal event.</span></span> <span data-ttu-id="0dc76-183">즉, 인수에 사용된 형식을 내부 형식으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-183">That means you can also make the types used for the arguments internal as well.</span></span>

<span data-ttu-id="0dc76-184">먼저 새 디렉터리 및 진행률을 보고하는 새 EventArgs 파생 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-184">You'll start by creating the new EventArgs derived class for reporting the new directory and progress.</span></span> 

[!code-csharp[DirEventArgs](../../samples/csharp/events/Program.cs#SearchDirEventArgs "Define search directory event arguments")]

<span data-ttu-id="0dc76-185">다시 권장 사항에 따라 이벤트 인수에 대해 변경할 수 없는 참조 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-185">Again, you can follow the recommendations to make an immutable reference type for the event arguments.</span></span>

<span data-ttu-id="0dc76-186">다음으로 이벤트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-186">Next, define the event.</span></span> <span data-ttu-id="0dc76-187">이번에는 다른 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-187">This time, you'll use a different syntax.</span></span> <span data-ttu-id="0dc76-188">필드 구문을 사용할 뿐만 아니라 추가 및 제거 처리기와 함께 속성을 명시적으로 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-188">In addition to using the field syntax, you can explicitly create the property, with add and remove handlers.</span></span> <span data-ttu-id="0dc76-189">이 샘플에서 해당 처리기에는 추가 코드가 필요하지 않지만 여기서는 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-189">In this sample, you won't need extra code in those handlers, but this shows how you would create them.</span></span>

[!code-csharp[Declare event with add and remove handlers](../../samples/csharp/events/Program.cs#DeclareSearchEvent "Declare the event with add and remove handlers")]

<span data-ttu-id="0dc76-190">여러 측면에서, 여기에서 작성하는 코드는 앞에서 살펴본 필드 이벤트 정의에 대해 컴파일러에서 생성하는 코드를 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-190">In many ways, the code you write here mirrors the code the compiler generates for the field event definitions you've seen earlier.</span></span> <span data-ttu-id="0dc76-191">[속성](properties.md)에 사용된 것과 매우 유사한 구문을 사용하여 이벤트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-191">You create the event using syntax very similar to that used for [properties](properties.md).</span></span> <span data-ttu-id="0dc76-192">처리기의 이름은 `add`와 `remove`로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-192">Notice that the handlers have different names: `add` and `remove`.</span></span> <span data-ttu-id="0dc76-193">이러한 처리기를 호출하여 이벤트를 구독하거나 이벤트에서 구독을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-193">These are called to subscribe to the event, or unsubscribe from the event.</span></span> <span data-ttu-id="0dc76-194">또한 이벤트 변수를 저장하려면 private 지원 필드를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-194">Notice that you also must declare a private backing field to store the event variable.</span></span> <span data-ttu-id="0dc76-195">이 필드는 null로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-195">It is initialized to null.</span></span>

<span data-ttu-id="0dc76-196">다음으로 하위 디렉터리를 트래버스하고 두 이벤트를 발생시키는 `Search` 메서드의 오버로드를 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-196">Next, let's add the overload of the `Search` method that traverses subdirectories and raises both events.</span></span> <span data-ttu-id="0dc76-197">이 작업을 수행하는 가장 쉬운 방법은 기본 인수를 사용하여 모든 디렉터리를 검색하도록 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-197">The easiest way to accomplish this is to use a default argument to specify that you want to search all directories:</span></span>

[!code-csharp[SearchImplementation](../../samples/csharp/events/Program.cs#FinalImplementation "Implementation to search directories")]

<span data-ttu-id="0dc76-198">이제 모든 하위 디렉터리를 검색하기 위해 오버로드를 호출하는 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-198">At this point, you can run the application calling the overload for searching all sub-directories.</span></span> <span data-ttu-id="0dc76-199">새 `ChangeDirectory` 이벤트에는 구독자가 없지만 `?.Invoke()` 관용구를 사용하여 이 작업이 제대로 작동하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-199">There are no subscribers on the new `ChangeDirectory` event, but using the `?.Invoke()` idiom ensures that this works correctly.</span></span>

 <span data-ttu-id="0dc76-200">콘솔 창에 진행률을 표시하는 줄을 작성하는 처리기를 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-200">Let's add a handler to write a line that shows the progress in the console window.</span></span> 

[!code-csharp[Search](../../samples/csharp/events/Program.cs#Search "Declare event handler")]

<span data-ttu-id="0dc76-201">.NET 에코시스템 전체에 적용되는 패턴을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-201">You've seen patterns that are followed throughout the .NET ecosystem.</span></span>
<span data-ttu-id="0dc76-202">이러한 패턴 및 규칙을 학습하면 자연스러운 C# 및 .NET을 신속하게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-202">By learning these patterns and conventions, you'll be writing idiomatic C# and .NET quickly.</span></span>

<span data-ttu-id="0dc76-203">다음으로 .NET의 최신 릴리스에서 이러한 패턴의 일부 변경 내용을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc76-203">Next, you'll see some changes in these patterns in the most recent release of .NET.</span></span>

[<span data-ttu-id="0dc76-204">다음</span><span class="sxs-lookup"><span data-stu-id="0dc76-204">Next</span></span>](modern-events.md)
