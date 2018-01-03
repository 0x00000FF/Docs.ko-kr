---
title: "관리되지 않는 DLL 함수 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unmanaged functions, calling
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- platform invoke, about platform invoke
- DLL functions, consuming unmanaged
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke
- DLL functions
ms.assetid: eca7606e-ebfb-4f47-b8d9-289903fdc045
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6276f2dc2bd57dc3eaf81eb2949e3c1ea3727e69
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="consuming-unmanaged-dll-functions"></a><span data-ttu-id="e572d-102">관리되지 않는 DLL 함수 사용</span><span class="sxs-lookup"><span data-stu-id="e572d-102">Consuming Unmanaged DLL Functions</span></span>
<span data-ttu-id="e572d-103">플랫폼 호출은 Win32 API의 함수와 같이 DLL(동적 연결 라이브러리)에서 구현된 관리되지 않는 함수를 관리 코드가 호출할 수 있도록 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-103">Platform invoke is a service that enables managed code to call unmanaged functions implemented in dynamic link libraries (DLLs), such as those in the Win32 API.</span></span> <span data-ttu-id="e572d-104">이 서비스는 내보낸 함수를 찾아서 호출하고 필요에 따라 상호 운용 경계를 가로질러 인수(정수, 문자열, 배열, 구조체 등)를 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-104">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span> <span data-ttu-id="e572d-105">이 서비스에 대한 자세한 내용은 [플랫폼 호출 자세히 보기](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e572d-105">For more information about this service, see [A Closer Look at Platform Invoke](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243).</span></span>  
  
 <span data-ttu-id="e572d-106">이 섹션에서는 관리되지 않는 DLL 함수 사용과 관련된 여러 가지 작업을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-106">This section introduces several tasks associated with consuming unmanaged DLL functions.</span></span> <span data-ttu-id="e572d-107">다음 작업 이외에 일반적인 고려 사항과 추가 정보 및 예제를 제공하는 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-107">In addition to the following tasks, there are general considerations and a link providing additional information and examples.</span></span>  
  
#### <a name="to-consume-exported-dll-functions"></a><span data-ttu-id="e572d-108">내보낸 DLL 함수를 사용하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-108">To consume exported DLL functions</span></span>  
  
1.  <span data-ttu-id="e572d-109">[DLL에서 함수를 식별합니다](../../../docs/framework/interop/identifying-functions-in-dlls.md).</span><span class="sxs-lookup"><span data-stu-id="e572d-109">[Identify functions in DLLs](../../../docs/framework/interop/identifying-functions-in-dlls.md).</span></span>  
  
     <span data-ttu-id="e572d-110">최소한 함수 이름 및 함수가 포함된 DLL 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-110">Minimally, you must specify the name of the function and name of the DLL that contains it.</span></span>  
  
2.  <span data-ttu-id="e572d-111">[DLL 함수가 포함된 클래스를 만듭니다](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).</span><span class="sxs-lookup"><span data-stu-id="e572d-111">[Create a class to hold DLL functions](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).</span></span>  
  
     <span data-ttu-id="e572d-112">기존 클래스를 사용하거나, 각 관리되지 않는 함수에 대한 개별 클래스를 만들거나, 관련 관리되지 않는 함수 집합을 포함하는 클래스 하나를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-112">You can use an existing class, create an individual class for each unmanaged function, or create one class that contains a set of related unmanaged functions.</span></span>  
  
3.  <span data-ttu-id="e572d-113">[관리 코드에서 프로토타입을 만듭니다](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="e572d-113">[Create prototypes in managed code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span></span>  
  
     <span data-ttu-id="e572d-114">[Visual Basic] **Declare** 문을 **Function** 및 **Lib** 키워드와 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-114">[Visual Basic] Use the **Declare** statement with the **Function** and **Lib** keywords.</span></span> <span data-ttu-id="e572d-115">드물지만 **DllImportAttribute**를 **Shared Function** 키워드와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-115">In some rare cases, you can use the **DllImportAttribute** with the **Shared Function** keywords.</span></span> <span data-ttu-id="e572d-116">이러한 경우에 대해서는 이 섹션의 뒷부분에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-116">These cases are explained later in this section.</span></span>  
  
     <span data-ttu-id="e572d-117">[C#] **DllImportAttribute**를 사용하여 DLL 및 함수를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-117">[C#] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="e572d-118">**static** 및 **extern** 한정자를 사용하여 메서드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-118">Mark the method with the **static** and **extern** modifiers.</span></span>  
  
     <span data-ttu-id="e572d-119">[C++] **DllImportAttribute**를 사용하여 DLL 및 함수를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-119">[C++] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="e572d-120">**extern “C”**를 사용하여 래퍼 메서드 또는 함수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-120">Mark the wrapper method or function with **extern "C"**.</span></span>  
  
4.  <span data-ttu-id="e572d-121">[DLL 함수를 호출합니다](../../../docs/framework/interop/calling-a-dll-function.md).</span><span class="sxs-lookup"><span data-stu-id="e572d-121">[Call a DLL function](../../../docs/framework/interop/calling-a-dll-function.md).</span></span>  
  
     <span data-ttu-id="e572d-122">다른 관리되는 메서드에서 호출하는 것처럼 관리되는 클래스에서 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-122">Call the method on your managed class as you would any other managed method.</span></span> <span data-ttu-id="e572d-123">[구조체 전달](../../../docs/framework/interop/passing-structures.md) 및 [콜백 함수 구현](../../../docs/framework/interop/callback-functions.md)은 특별한 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-123">[Passing structures](../../../docs/framework/interop/passing-structures.md) and [implementing callback functions](../../../docs/framework/interop/callback-functions.md) are special cases.</span></span>  
  
 <span data-ttu-id="e572d-124">플랫폼 호출에서 사용되는 .NET 기반 선언을 생성하는 방법을 보여 주는 예제는 [플랫폼 호출을 사용하여 데이터 마샬링](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e572d-124">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="a-closer-look-at-platform-invoke"></a><span data-ttu-id="e572d-125">플랫폼 호출 자세히 보기</span><span class="sxs-lookup"><span data-stu-id="e572d-125">A closer look at platform invoke</span></span>  
 <span data-ttu-id="e572d-126">플랫폼 호출은 메타데이터에 의존하여 내보낸 함수를 찾고 런타임에 해당 인수를 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-126">Platform invoke relies on metadata to locate exported functions and marshal their arguments at run time.</span></span> <span data-ttu-id="e572d-127">다음 그림에서 이 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-127">The following illustration shows this process.</span></span>  
  
 <span data-ttu-id="e572d-128">![플랫폼 호출](../../../docs/framework/interop/media/pinvoke.gif "pinvoke")</span><span class="sxs-lookup"><span data-stu-id="e572d-128">![Platform invoke](../../../docs/framework/interop/media/pinvoke.gif "pinvoke")</span></span>  
<span data-ttu-id="e572d-129">관리되는 DLL 함수에 대한 플랫폼 호출</span><span class="sxs-lookup"><span data-stu-id="e572d-129">A platform invoke call to an unmanaged DLL function</span></span>  
  
 <span data-ttu-id="e572d-130">플랫폼 호출이 관리되지 않는 함수를 호출할 때 다음 작업 시퀀스를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-130">When platform invoke calls an unmanaged function, it performs the following sequence of actions:</span></span>  
  
1.  <span data-ttu-id="e572d-131">함수가 포함된 DLL을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-131">Locates the DLL containing the function.</span></span>  
  
2.  <span data-ttu-id="e572d-132">DLL을 메모리로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-132">Loads the DLL into memory.</span></span>  
  
3.  <span data-ttu-id="e572d-133">메모리에서 함수를 찾고 인수를 스택에 넣어 필요에 따라 데이터를 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-133">Locates the address of the function in memory and pushes its arguments onto the stack, marshaling data as required.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e572d-134">DLL을 찾아서 로드하고 메모리에서 함수의 주소를 찾는 작업은 함수에 대한 첫 번째 호출에서만 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-134">Locating and loading the DLL, and locating the address of the function in memory occur only on the first call to the function.</span></span>  
  
4.  <span data-ttu-id="e572d-135">컨트롤을 관리되지 않는 함수에 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-135">Transfers control to the unmanaged function.</span></span>  
  
 <span data-ttu-id="e572d-136">플랫폼 호출은 관리되지 않는 함수에서 생성된 예외를 관리되는 호출자로 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="e572d-136">Platform invoke throws exceptions generated by the unmanaged function to the managed caller.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e572d-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e572d-137">See Also</span></span>  
 [<span data-ttu-id="e572d-138">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="e572d-138">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)  
 [<span data-ttu-id="e572d-139">플랫폼 호출 예제</span><span class="sxs-lookup"><span data-stu-id="e572d-139">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="e572d-140">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="e572d-140">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 [<span data-ttu-id="e572d-141">관리되지 않는 DLL 함수 사용</span><span class="sxs-lookup"><span data-stu-id="e572d-141">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
