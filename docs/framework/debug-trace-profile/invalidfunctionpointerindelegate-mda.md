---
title: invalidFunctionPointerInDelegate MDA
ms.date: 03/30/2017
helpviewer_keywords:
- invalidFunctionPointerInDelegate MDA
- managed debugging assistants (MDAs), invalid function pointer to delegates
- MDAs (managed debugging assistants), invalid function pointer to delegates
- function pointers, invalid
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- invalid function pointers
ms.assetid: 99ae44f1-783e-49a9-9009-24f54bbd0f09
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 847ec4d861136b46383ce7d3801764f3d962049e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33390876"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="ad7d6-102">invalidFunctionPointerInDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="ad7d6-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="ad7d6-103">`invalidFunctionPointerInDelegate` MDA(관리 디버깅 도우미)는 잘못된 함수 포인터가 네이티브 함수 포인터를 통해 대리자를 생성하도록 전달되면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad7d6-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ad7d6-104">증상</span><span class="sxs-lookup"><span data-stu-id="ad7d6-104">Symptoms</span></span>  
 <span data-ttu-id="ad7d6-105">함수 포인터를 통해 대리자를 사용할 때 액세스 위반 또는 예기치 않은 메모리 손상이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ad7d6-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ad7d6-106">원인</span><span class="sxs-lookup"><span data-stu-id="ad7d6-106">Cause</span></span>  
 <span data-ttu-id="ad7d6-107">잘못된 함수 포인터가 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ad7d6-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ad7d6-108">해결 방법</span><span class="sxs-lookup"><span data-stu-id="ad7d6-108">Resolution</span></span>  
 <span data-ttu-id="ad7d6-109">유효한 함수 포인터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad7d6-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ad7d6-110">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="ad7d6-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="ad7d6-111">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad7d6-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ad7d6-112">출력</span><span class="sxs-lookup"><span data-stu-id="ad7d6-112">Output</span></span>  
 <span data-ttu-id="ad7d6-113">잘못된 함수 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ad7d6-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ad7d6-114">구성</span><span class="sxs-lookup"><span data-stu-id="ad7d6-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad7d6-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad7d6-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="ad7d6-116">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="ad7d6-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="ad7d6-117">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="ad7d6-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
