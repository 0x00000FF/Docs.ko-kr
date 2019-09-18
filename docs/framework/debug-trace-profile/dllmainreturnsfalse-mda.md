---
title: dllMainReturnsFalse MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
author: mairaw
ms.author: mairaw
ms.openlocfilehash: adc05ae9bd357c142ff09de069aff446b5ea60e8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052852"
---
# <a name="dllmainreturnsfalse-mda"></a><span data-ttu-id="ca3b5-102">dllMainReturnsFalse MDA</span><span class="sxs-lookup"><span data-stu-id="ca3b5-102">dllMainReturnsFalse MDA</span></span>
<span data-ttu-id="ca3b5-103">DLL_PROCESS_ATTACH로 인해 호출된 사용자 어셈블리의 관리되는 `DllMain` 함수가 FALSE를 반환하면 `dllMainReturnsFalse` MDA(관리 디버깅 도우미)가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca3b5-103">The `dllMainReturnsFalse` managed debugging assistant (MDA) is activated if the managed `DllMain` function of a user assembly, called with reason DLL_PROCESS_ATTACH, returns FALSE.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ca3b5-104">증상</span><span class="sxs-lookup"><span data-stu-id="ca3b5-104">Symptoms</span></span>  
 <span data-ttu-id="ca3b5-105">`DllMain` 함수가 FALSE를 반환했고 이는 함수가 제대로 실행되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ca3b5-105">The `DllMain` function returned FALSE, indicating that it did not execute properly.</span></span> <span data-ttu-id="ca3b5-106">`DllMain` 함수에는 일반적으로 중요한 초기화 코드가 포함되므로 이로 인해 결정되지 않은 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3b5-106">This can cause undetermined issues because `DllMain` functions typically contain important initialization code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ca3b5-107">원인</span><span class="sxs-lookup"><span data-stu-id="ca3b5-107">Cause</span></span>  
 <span data-ttu-id="ca3b5-108">로드 시 DLL 초기화에 대한 DLL_PROCESS_ATTACH로 인해 `DllMain` 함수가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca3b5-108">The `DllMain` function is called with reason DLL_PROCESS_ATTACH for DLL initialization upon load.</span></span> <span data-ttu-id="ca3b5-109">함수가 FALSE를 반환하면 DLL 초기화가 실패했음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3b5-109">If it returns FALSE, it means that DLL initialization failed.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ca3b5-110">해결 방법</span><span class="sxs-lookup"><span data-stu-id="ca3b5-110">Resolution</span></span>  
 <span data-ttu-id="ca3b5-111">실패한 DLL의 `DllMain` 함수 코드를 분석하고 초기화 실패의 원인을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3b5-111">Analyze the code of the `DllMain` function of the failed DLL and identify the cause of the initialization failure.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ca3b5-112">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="ca3b5-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="ca3b5-113">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3b5-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="ca3b5-114">`DllMain`의 반환 값에 대한 데이터만 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3b5-114">It only reports data about the return value for `DllMain`.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ca3b5-115">출력</span><span class="sxs-lookup"><span data-stu-id="ca3b5-115">Output</span></span>  
 <span data-ttu-id="ca3b5-116">DLL_PROCESS_ATTACH로 인해 호출되는 `DllMain` 함수가 FALSE를 반환했음을 나타내는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="ca3b5-116">A message indicating that a `DllMain` function, called for reason DLL_PROCESS_ATTACH, returned FALSE.</span></span> <span data-ttu-id="ca3b5-117">이 MDA는 `DllMain`이 관리 코드에서 구현된 경우에만 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca3b5-117">Note that this MDA is activated only if `DllMain` is implemented in managed code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ca3b5-118">Configuration</span><span class="sxs-lookup"><span data-stu-id="ca3b5-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca3b5-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="ca3b5-119">See also</span></span>

- [<span data-ttu-id="ca3b5-120">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="ca3b5-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
