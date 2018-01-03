---
title: "DLL 함수가 포함된 클래스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke, creating class for functions
- DLL functions
ms.assetid: e08e4c34-0223-45f7-aa55-a3d8dd979b0f
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6d64034f8059dc094b3fc8a71c6a2b7e96fe8d89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-class-to-hold-dll-functions"></a><span data-ttu-id="82956-102">DLL 함수가 포함된 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="82956-102">Creating a Class to Hold DLL Functions</span></span>
<span data-ttu-id="82956-103">자주 사용되는 DLL 함수를 관리되는 클래스로 래핑하는 것은 플랫폼 기능을 캡슐화하는 효과적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="82956-103">Wrapping a frequently used DLL function in a managed class is an effective approach to encapsulate platform functionality.</span></span> <span data-ttu-id="82956-104">매번 래핑할 필요는 없지만 DLL 함수 정의는 번거롭고 오류가 발생할 수 있으므로 클래스 래퍼를 제공하는 것이 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="82956-104">Although it is not mandatory to do so in every case, providing a class wrapper is convenient because defining DLL functions can be cumbersome and error-prone.</span></span> <span data-ttu-id="82956-105">Visual Basic 또는 C#으로 프로그래밍할 경우 클래스 또는 Visual Basic 모듈 내에서 DLL 함수를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82956-105">If you are programming in Visual Basic or C#, you must declare DLL functions within a class or Visual Basic module.</span></span>  
  
 <span data-ttu-id="82956-106">클래스 내에서 호출할 각 DLL 함수에 대한 정적 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="82956-106">Within a class, you define a static method for each DLL function you want to call.</span></span> <span data-ttu-id="82956-107">정의에는 메서드 인수를 전달하는 데 사용되는 문자 집합 또는 호출 규칙 같은 추가 정보가 포함될 수 있습니다. 이 정보를 생략하면 기본 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="82956-107">The definition can include additional information, such as the character set or the calling convention used in passing method arguments; by omitting this information, you select the default settings.</span></span> <span data-ttu-id="82956-108">선언 옵션 및 기본 설정의 전체 목록을 보려면 [관리 코드에서 프로토타입 만들기](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82956-108">For a complete list of declaration options and their default settings, see [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span></span>  
  
 <span data-ttu-id="82956-109">래핑된 후 다른 정적 함수에서 메서드를 호출할 때 이 함수에서 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82956-109">Once wrapped, you can call methods on the function as you call methods on any other static function.</span></span> <span data-ttu-id="82956-110">플랫폼 호출은 기본 내보낸 함수를 자동으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="82956-110">Platform invoke handles the underlying exported function automatically.</span></span>  
  
 <span data-ttu-id="82956-111">플랫폼 호출에 대한 관리되는 클래스를 디자인할 때 클래스와 DLL 함수 간 관계를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="82956-111">When designing a managed class for platform invoke, consider the relationships between classes and DLL functions.</span></span> <span data-ttu-id="82956-112">예를 들어 다음 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82956-112">For example, you can:</span></span>  
  
-   <span data-ttu-id="82956-113">기존 클래스 내에서 DLL 함수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="82956-113">Declare DLL functions within an existing class.</span></span>  
  
-   <span data-ttu-id="82956-114">각 DLL 함수에 대한 개별 클래스를 만들어 함수를 격리하고 찾기 쉽게 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="82956-114">Create an individual class for each DLL function, keeping functions isolated and easy to find.</span></span>  
  
-   <span data-ttu-id="82956-115">관련 DLL 함수 집합에 대한 클래스 하나를 만들어 논리적 그룹화를 구성하고 오버헤드를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="82956-115">Create one class for a set of related DLL functions to form logical groupings and reduce overhead.</span></span>  
  
 <span data-ttu-id="82956-116">원하는 대로 클래스 및 해당 메서드의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82956-116">You can name the class and its methods as you please.</span></span> <span data-ttu-id="82956-117">플랫폼 호출에서 사용되는 .NET 기반 선언을 생성하는 방법을 보여 주는 예제는 [플랫폼 호출을 사용하여 데이터 마샬링](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82956-117">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82956-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82956-118">See Also</span></span>  
 [<span data-ttu-id="82956-119">관리되지 않는 DLL 함수 사용</span><span class="sxs-lookup"><span data-stu-id="82956-119">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 [<span data-ttu-id="82956-120">DLL 함수 식별</span><span class="sxs-lookup"><span data-stu-id="82956-120">Identifying Functions in DLLs</span></span>](../../../docs/framework/interop/identifying-functions-in-dlls.md)  
 [<span data-ttu-id="82956-121">관리 코드에서 프로토타입 만들기</span><span class="sxs-lookup"><span data-stu-id="82956-121">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="82956-122">DLL 함수 호출</span><span class="sxs-lookup"><span data-stu-id="82956-122">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)
