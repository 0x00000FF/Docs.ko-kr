---
title: "콜백 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 84c3f13317f771ba81af0fc7368124c59f8a1a37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="callback-functions"></a><span data-ttu-id="bcf22-102">콜백 함수</span><span class="sxs-lookup"><span data-stu-id="bcf22-102">Callback Functions</span></span>
<span data-ttu-id="bcf22-103">콜백 함수는 관리되지 않는 DLL 함수가 작업을 완료하는 데 도움이 되는, 관리되는 응용 프로그램 내의 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="bcf22-103">A callback function is code within a managed application that helps an unmanaged DLL function complete a task.</span></span> <span data-ttu-id="bcf22-104">콜백 함수 호출은 관리되는 응용 프로그램에서 간접적으로, DLL 함수를 통해, 그리고 다시 관리되는 구현으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcf22-104">Calls to a callback function pass indirectly from a managed application, through a DLL function, and back to the managed implementation.</span></span> <span data-ttu-id="bcf22-105">플랫폼 호출을 사용하여 호출되는 많은 DLL 함수 중 일부는 제대로 실행되기 위해 관리 코드에 콜백 함수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf22-105">Some of the many DLL functions called with platform invoke require a callback function in managed code to run properly.</span></span>  
  
 <span data-ttu-id="bcf22-106">관리 코드에서 대부분의 DLL 함수를 호출하려면 관리되는 함수 정의를 만든 후 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf22-106">To call most DLL functions from managed code, you create a managed definition of the function and then call it.</span></span> <span data-ttu-id="bcf22-107">프로세스는 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf22-107">The process is straightforward.</span></span>  
  
 <span data-ttu-id="bcf22-108">콜백 함수가 필요한 DLL 함수를 사용하는 경우 몇 가지 추가 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcf22-108">Using a DLL function that requires a callback function has some additional steps.</span></span> <span data-ttu-id="bcf22-109">먼저, 함수에 대한 설명서를 확인하여 함수에 콜백이 필요한지 여부를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf22-109">First, you must determine whether the function requires a callback by looking at the documentation for the function.</span></span> <span data-ttu-id="bcf22-110">다음으로, 관리되는 응용 프로그램에서 콜백 함수를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf22-110">Next, you have to create the callback function in your managed application.</span></span> <span data-ttu-id="bcf22-111">마지막으로, 콜백 함수에 대한 포인터를 인수로 전달하여 DLL 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf22-111">Finally, you call the DLL function, passing a pointer to the callback function as an argument.</span></span> <span data-ttu-id="bcf22-112">다음 그림에서는 이 단계를 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf22-112">The following illustration summarizes these steps.</span></span>  
  
 <span data-ttu-id="bcf22-113">![플랫폼 호출 콜백](../../../docs/framework/interop/media/pinvokecallback.gif "pinvokecallback")</span><span class="sxs-lookup"><span data-stu-id="bcf22-113">![Platform invoke callback](../../../docs/framework/interop/media/pinvokecallback.gif "pinvokecallback")</span></span>  
<span data-ttu-id="bcf22-114">콜백 함수 및 구현</span><span class="sxs-lookup"><span data-stu-id="bcf22-114">Callback function and implementation</span></span>  
  
 <span data-ttu-id="bcf22-115">콜백 함수는 작업이 반복적으로 수행되는 경우 사용하기에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf22-115">Callback functions are ideal for use in situations in which a task is performed repeatedly.</span></span> <span data-ttu-id="bcf22-116">또한 일반적으로 Win32 API에서 **EnumFontFamilies**, **EnumPrinters**, **EnumWindows** 등의 열거형 함수에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcf22-116">Another common usage is with enumeration functions, such as **EnumFontFamilies**, **EnumPrinters**, and **EnumWindows** in the Win32 API.</span></span> <span data-ttu-id="bcf22-117">**EnumWindows** 함수는 컴퓨터의 모든 기존 창을 열거하고 콜백 함수를 호출하여 각 창에서 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf22-117">The **EnumWindows** function enumerates through all existing windows on your computer, calling the callback function to perform a task on each window.</span></span> <span data-ttu-id="bcf22-118">자세한 내용과 예제는 [방법: 콜백 함수 구현](../../../docs/framework/interop/how-to-implement-callback-functions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bcf22-118">For instructions and an example, see [How to: Implement Callback Functions](../../../docs/framework/interop/how-to-implement-callback-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcf22-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcf22-119">See Also</span></span>  
 [<span data-ttu-id="bcf22-120">방법: 콜백 함수 구현</span><span class="sxs-lookup"><span data-stu-id="bcf22-120">How to: Implement Callback Functions</span></span>](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 [<span data-ttu-id="bcf22-121">DLL 함수 호출</span><span class="sxs-lookup"><span data-stu-id="bcf22-121">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)
