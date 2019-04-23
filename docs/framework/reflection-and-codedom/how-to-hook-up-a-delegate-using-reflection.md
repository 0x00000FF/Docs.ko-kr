---
title: '방법: 리플렉션을 사용하여 대리자 후크'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET Framework], adding event handlers with reflection
- reflection, adding event-handler delegates
- delegates [.NET Framework], adding event handlers with reflection
ms.assetid: 076ee62d-a964-449e-a447-c31b33518b81
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7c2956a222a47cea36abbc2f21da2d7e2061e09
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314531"
---
# <a name="how-to-hook-up-a-delegate-using-reflection"></a><span data-ttu-id="f3237-102">방법: 리플렉션을 사용하여 대리자 후크</span><span class="sxs-lookup"><span data-stu-id="f3237-102">How to: Hook Up a Delegate Using Reflection</span></span>
<span data-ttu-id="f3237-103">리플렉션을 사용하여 어셈블리를 로드하고 실행하는 경우 C# `+=` 연산자 또는 Visual Basic [AddHandler 문](~/docs/visual-basic/language-reference/statements/addhandler-statement.md)과 같은 언어 기능을 사용하여 이벤트를 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-103">When you use reflection to load and run assemblies, you cannot use language features like the C# `+=` operator or the Visual Basic [AddHandler statement](~/docs/visual-basic/language-reference/statements/addhandler-statement.md) to hook up events.</span></span> <span data-ttu-id="f3237-104">다음 절차에서는 리플렉션을 통해 필요한 모든 형식을 가져와 기존 메서드를 이벤트에 연결하는 방법 및 리플렉션 내보내기를 사용하여 동적 메서드를 만들고 이벤트에 연결하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-104">The following procedures show how to hook up an existing method to an event by getting all the necessary types through reflection, and how to create a dynamic method using reflection emit and hook it up to an event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3237-105">이벤트 처리 대리자를 연결하는 다른 방법은 <xref:System.Reflection.EventInfo> 클래스의 <xref:System.Reflection.EventInfo.AddEventHandler%2A> 메서드에 대한 코드 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3237-105">For another way to hook up an event-handling delegate, see the code example for the <xref:System.Reflection.EventInfo.AddEventHandler%2A> method of the <xref:System.Reflection.EventInfo> class.</span></span>  
  
### <a name="to-hook-up-a-delegate-using-reflection"></a><span data-ttu-id="f3237-106">리플렉션을 사용하여 대리자를 연결하려면</span><span class="sxs-lookup"><span data-stu-id="f3237-106">To hook up a delegate using reflection</span></span>  
  
1. <span data-ttu-id="f3237-107">이벤트를 발생시키는 형식을 포함하는 어셈블리를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-107">Load an assembly that contains a type that raises events.</span></span> <span data-ttu-id="f3237-108">어셈블리는 일반적으로 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 메서드를 사용하여 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-108">Assemblies are usually loaded with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f3237-109">이 예제를 단순하게 유지하기 위해 현재 어셈블리의 파생 양식이 사용되므로 <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> 메서드가 현재 어셈블리를 로드하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-109">To keep this example simple, a derived form in the current assembly is used, so the <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method is used to load the current assembly.</span></span>  
  
     [!code-cpp[HookUpDelegate#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#3)]
     [!code-csharp[HookUpDelegate#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#3)]
     [!code-vb[HookUpDelegate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#3)]  
  
2. <span data-ttu-id="f3237-110">형식을 나타내는 <xref:System.Type> 개체를 가져오고 형식 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-110">Get a <xref:System.Type> object representing the type, and create an instance of the type.</span></span> <span data-ttu-id="f3237-111">양식에 기본 생성자가 있기 때문에 다음 코드에서는 <xref:System.Activator.CreateInstance%28System.Type%29> 메서드가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-111">The <xref:System.Activator.CreateInstance%28System.Type%29> method is used in the following code because the form has a default constructor.</span></span> <span data-ttu-id="f3237-112">만들려는 형식에 기본 생성자가 없는 경우 사용할 수 있는 <xref:System.Activator.CreateInstance%2A> 메서드의 여러 다른 오버로드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-112">There are several other overloads of the <xref:System.Activator.CreateInstance%2A> method that you can use if the type you are creating does not have a default constructor.</span></span> <span data-ttu-id="f3237-113">새 인스턴스는 어셈블리에 대해 알려진 것이 없다는 가정을 유지하기 위해 <xref:System.Object> 형식으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-113">The new instance is stored as type <xref:System.Object> to maintain the fiction that nothing is known about the assembly.</span></span> <span data-ttu-id="f3237-114">이름을 미리 알지 못해도 리플렉션을 통해 어셈블리의 형식을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-114">(Reflection allows you to get the types in an assembly without knowing their names in advance.)</span></span>  
  
     [!code-cpp[HookUpDelegate#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#4)]
     [!code-csharp[HookUpDelegate#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#4)]
     [!code-vb[HookUpDelegate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#4)]  
  
3. <span data-ttu-id="f3237-115">이벤트를 나타내는 <xref:System.Reflection.EventInfo> 개체를 가져오고, <xref:System.Reflection.EventInfo.EventHandlerType%2A> 속성을 사용하여 이벤트를 처리하는 데 사용되는 대리자 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-115">Get an <xref:System.Reflection.EventInfo> object representing the event, and use the <xref:System.Reflection.EventInfo.EventHandlerType%2A> property to get the type of delegate used to handle the event.</span></span> <span data-ttu-id="f3237-116">다음 코드에서는 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 <xref:System.Reflection.EventInfo>를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-116">In the following code, an <xref:System.Reflection.EventInfo> for the <xref:System.Windows.Forms.Control.Click> event is obtained.</span></span>  
  
     [!code-cpp[HookUpDelegate#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#5)]
     [!code-csharp[HookUpDelegate#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#5)]
     [!code-vb[HookUpDelegate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#5)]  
  
4. <span data-ttu-id="f3237-117">이벤트를 처리하는 메서드를 나타내는 <xref:System.Reflection.MethodInfo> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-117">Get a <xref:System.Reflection.MethodInfo> object representing the method that handles the event.</span></span> <span data-ttu-id="f3237-118">이 항목의 뒷부분에 나오는 예제 섹션의 완성된 프로그램 코드에 <xref:System.EventHandler> 이벤트를 처리하는 <xref:System.Windows.Forms.Control.Click> 대리자의 시그니처와 일치하는 메서드가 포함되어 있지만, 런타임에 동적 메서드를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-118">The complete program code in the Example section later in this topic contains a method that matches the signature of the <xref:System.EventHandler> delegate, which handles the <xref:System.Windows.Forms.Control.Click> event, but you can also generate dynamic methods at run time.</span></span> <span data-ttu-id="f3237-119">동적 메서드를 사용하여 런타임에 이벤트 처리기를 생성하는 것에 대한 자세한 내용은 다음에 나오는 절차를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f3237-119">For details, see the accompanying procedure, for generating an event handler at run time by using a dynamic method.</span></span>  
  
     [!code-cpp[HookUpDelegate#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#6)]
     [!code-csharp[HookUpDelegate#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#6)]
     [!code-vb[HookUpDelegate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#6)]  
  
5. <span data-ttu-id="f3237-120"><xref:System.Delegate.CreateDelegate%2A> 메서드를 사용하여 대리자 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-120">Create an instance of the delegate, using the <xref:System.Delegate.CreateDelegate%2A> method.</span></span> <span data-ttu-id="f3237-121">이 메서드는 static(Visual Basic에서는 `Shared`)이므로 대리자 형식을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-121">This method is static (`Shared` in Visual Basic), so the delegate type must be supplied.</span></span> <span data-ttu-id="f3237-122"><xref:System.Reflection.MethodInfo>를 사용하는 <xref:System.Delegate.CreateDelegate%2A>의 오버로드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-122">Using the overloads of <xref:System.Delegate.CreateDelegate%2A> that take a <xref:System.Reflection.MethodInfo> is recommended.</span></span>  
  
     [!code-cpp[HookUpDelegate#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#7)]
     [!code-csharp[HookUpDelegate#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#7)]
     [!code-vb[HookUpDelegate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#7)]  
  
6. <span data-ttu-id="f3237-123">`add` 접근자 메서드를 가져온 다음 호출하여 이벤트를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-123">Get the `add` accessor method and invoke it to hook up the event.</span></span> <span data-ttu-id="f3237-124">모든 이벤트에는 상위 수준 언어 구문에서 숨겨지는 `add` 접근자 및 `remove` 접근자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-124">All events have an `add` accessor and a `remove` accessor, which are hidden by the syntax of high-level languages.</span></span> <span data-ttu-id="f3237-125">예를 들어 C#에서는 `+=` 연산자를 사용하여 이벤트를 연결하고, Visual Basic에서는 [AddHandler 문](~/docs/visual-basic/language-reference/statements/addhandler-statement.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-125">For example, C# uses the `+=` operator to hook up events, and Visual Basic uses the [AddHandler statement](~/docs/visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="f3237-126">다음 코드는 <xref:System.Windows.Forms.Control.Click> 이벤트의 `add` 접근자를 가져온 다음 대리자 인스턴스를 전달하여 런타임에 바인딩해서 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-126">The following code gets the `add` accessor of the <xref:System.Windows.Forms.Control.Click> event and invokes it late-bound, passing in the delegate instance.</span></span> <span data-ttu-id="f3237-127">인수를 배열로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-127">The arguments must be passed as an array.</span></span>  
  
     [!code-cpp[HookUpDelegate#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#8)]
     [!code-csharp[HookUpDelegate#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#8)]
     [!code-vb[HookUpDelegate#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#8)]  
  
7. <span data-ttu-id="f3237-128">이벤트를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-128">Test the event.</span></span> <span data-ttu-id="f3237-129">다음 코드는 코드 예제에서 정의된 양식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-129">The following code shows the form defined in the code example.</span></span> <span data-ttu-id="f3237-130">양식을 클릭하면 이벤트 처리기가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-130">Clicking the form invokes the event handler.</span></span>  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
<a name="procedureSection1"></a>   
### <a name="to-generate-an-event-handler-at-run-time-by-using-a-dynamic-method"></a><span data-ttu-id="f3237-131">동적 메서드를 사용하여 런타임에 이벤트 처리기를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="f3237-131">To generate an event handler at run time by using a dynamic method</span></span>  
  
1. <span data-ttu-id="f3237-132">경량 동적 메서드 및 리플렉션 내보내기를 사용하여 런타임에 이벤트 처리기 메서드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-132">Event-handler methods can be generated at run time, using lightweight dynamic methods and reflection emit.</span></span> <span data-ttu-id="f3237-133">이벤트 처리기를 생성하려면 대리자의 매개 변수 형식과 반환 형식이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-133">To construct an event handler, you need the return type and parameter types of the delegate.</span></span> <span data-ttu-id="f3237-134">대리자의 `Invoke` 메서드를 검사하여 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-134">These can be obtained by examining the delegate's `Invoke` method.</span></span> <span data-ttu-id="f3237-135">다음 코드는 `GetDelegateReturnType` 및 `GetDelegateParameterTypes` 메서드를 사용하여 이 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-135">The following code uses the `GetDelegateReturnType` and `GetDelegateParameterTypes` methods to obtain this information.</span></span> <span data-ttu-id="f3237-136">이러한 메서드에 대한 코드는 이 항목의 뒷부분에 나오는 예제 섹션에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-136">The code for these methods can be found in the Example section later in this topic.</span></span>  
  
     <span data-ttu-id="f3237-137"><xref:System.Reflection.Emit.DynamicMethod>에 이름을 지정할 필요는 없으므로 빈 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-137">It is not necessary to name a <xref:System.Reflection.Emit.DynamicMethod>, so the empty string can be used.</span></span> <span data-ttu-id="f3237-138">다음 코드에서 마지막 인수는 동적 메서드를 현재 형식과 연결하여 대리자가 `Example` 클래스의 모든 public 및 private 멤버에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-138">In the following code, the last argument associates the dynamic method with the current type, giving the delegate access to all the public and private members of the `Example` class.</span></span>  
  
     [!code-cpp[HookUpDelegate#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#9)]
     [!code-csharp[HookUpDelegate#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#9)]
     [!code-vb[HookUpDelegate#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#9)]  
  
2. <span data-ttu-id="f3237-139">메서드 본문을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-139">Generate a method body.</span></span> <span data-ttu-id="f3237-140">이 메서드는 문자열을 로드하고, 문자열을 사용하는 <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> 메서드의 오버로드를 호출한 다음 스택에서 반환 값을 팝하고(처리기에 반환 형식이 없으므로) 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-140">This method loads a string, calls the overload of the <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> method that takes a string, pops the return value off the stack (because the handler has no return type), and returns.</span></span> <span data-ttu-id="f3237-141">동적 메서드를 내보내는 방법에 대한 자세한 내용은 [방법: 동적 메서드 정의 및 실행](../../../docs/framework/reflection-and-codedom/how-to-define-and-execute-dynamic-methods.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3237-141">To learn more about emitting dynamic methods, see [How to: Define and Execute Dynamic Methods](../../../docs/framework/reflection-and-codedom/how-to-define-and-execute-dynamic-methods.md).</span></span>  
  
     [!code-cpp[HookUpDelegate#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#10)]
     [!code-csharp[HookUpDelegate#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#10)]
     [!code-vb[HookUpDelegate#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#10)]  
  
3. <span data-ttu-id="f3237-142">해당 <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> 메서드를 호출하여 동적 메서드를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-142">Complete the dynamic method by calling its <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> method.</span></span> <span data-ttu-id="f3237-143">`add` 접근자를 사용하여 이벤트에 대한 호출 목록에 대리자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-143">Use the `add` accessor to add the delegate to the invocation list for the event.</span></span>  
  
     [!code-cpp[HookUpDelegate#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#11)]
     [!code-csharp[HookUpDelegate#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#11)]
     [!code-vb[HookUpDelegate#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#11)]  
  
4. <span data-ttu-id="f3237-144">이벤트를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-144">Test the event.</span></span> <span data-ttu-id="f3237-145">다음 코드는 코드 예제에서 정의된 양식을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-145">The following code loads the form defined in the code example.</span></span> <span data-ttu-id="f3237-146">양식을 클릭하면 미리 정의된 이벤트 처리기와 내보낸 이벤트 처리기가 둘 다 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-146">Clicking the form invokes both the predefined event handler and the emitted event handler.</span></span>  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="f3237-147">예제</span><span class="sxs-lookup"><span data-stu-id="f3237-147">Example</span></span>  
 <span data-ttu-id="f3237-148">다음 코드 예제에서는 리플렉션을 사용하여 기존 메서드를 이벤트에 연결하는 방법 및 <xref:System.Reflection.Emit.DynamicMethod> 클래스를 사용하여 런타임에 메서드를 내보내고 이벤트에 연결하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-148">The following code example shows how to hook up an existing method to an event using reflection, and also how to use the <xref:System.Reflection.Emit.DynamicMethod> class to emit a method at run time and hook it up to an event.</span></span>  
  
 [!code-cpp[HookUpDelegate#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#1)]
 [!code-csharp[HookUpDelegate#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#1)]
 [!code-vb[HookUpDelegate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f3237-149">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f3237-149">Compiling the Code</span></span>  
  
-   <span data-ttu-id="f3237-150">코드에는 컴파일하는 데 필요한 C# `using` 문(Visual Basic에서는 `Imports`)이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-150">The code contains the C# `using` statements (`Imports` in Visual Basic) necessary for compilation.</span></span>  
  
-   <span data-ttu-id="f3237-151">명령줄에서 컴파일하는 데 필요한 추가 어셈블리 참조는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-151">No additional assembly references are required for compiling from the command line.</span></span> <span data-ttu-id="f3237-152">이 예제는 콘솔 애플리케이션이므로 Visual Studio에서는 System.Windows.Forms.dll에 대한 참조를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-152">In Visual Studio you must add a reference to System.Windows.Forms.dll because this example is a console application.</span></span>  
  
-   <span data-ttu-id="f3237-153">csc.exe, vbc.exe 또는 cl.exe를 사용하여 명령줄에서 코드를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-153">Compile the code at the command line using csc.exe, vbc.exe, or cl.exe.</span></span> <span data-ttu-id="f3237-154">Visual Studio에서 코드를 컴파일하려면 콘솔 애플리케이션 프로젝트 템플릿에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="f3237-154">To compile the code in Visual Studio, place it in a console application project template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3237-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3237-155">See also</span></span>

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Emit.DynamicMethod>
- <xref:System.Activator.CreateInstance%2A>
- <xref:System.Delegate.CreateDelegate%2A>
- [<span data-ttu-id="f3237-156">방법: 동적 메서드 정의 및 실행</span><span class="sxs-lookup"><span data-stu-id="f3237-156">How to: Define and Execute Dynamic Methods</span></span>](../../../docs/framework/reflection-and-codedom/how-to-define-and-execute-dynamic-methods.md)
- [<span data-ttu-id="f3237-157">리플렉션</span><span class="sxs-lookup"><span data-stu-id="f3237-157">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)
