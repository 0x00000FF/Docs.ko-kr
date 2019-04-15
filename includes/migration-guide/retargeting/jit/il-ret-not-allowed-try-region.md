---
ms.openlocfilehash: 1687b1b9a1a6861f9569a0e29426de7f32ffc32b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234457"
---
### <a name="il-ret-not-allowed-in-a-try-region"></a><span data-ttu-id="23952-101">IL ret은 try 영역에서 허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="23952-101">IL ret not allowed in a try region</span></span>

|   |   |
|---|---|
|<span data-ttu-id="23952-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="23952-102">Details</span></span>|<span data-ttu-id="23952-103">JIT64 Just-In-Time 컴파일러와 달리 RyuJIT(.NET Framework 4.6에서 사용됨)는 try 영역에서 IL ret 명령을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23952-103">Unlike the JIT64 just-in-time compiler, RyuJIT (used in .NET Framework 4.6) does not allow an IL ret instruction in a try region.</span></span> <span data-ttu-id="23952-104">try 영역에서 반환은 ECMA-335 사양에서 허용되지 않으며 이러한 IL을 생성하는 알려진 관리 컴파일러는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23952-104">Returning from a try region is disallowed by the ECMA-335 specification, and no known managed compiler generates such IL.</span></span> <span data-ttu-id="23952-105">그러나 이러한 IL이 리플렉션 내보내기를 사용하여 생성된 경우에는 JIT64 컴파일러에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="23952-105">However, the JIT64 compiler will execute such IL if it is generated using reflection emit.</span></span>|
|<span data-ttu-id="23952-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="23952-106">Suggestion</span></span>|<span data-ttu-id="23952-107">앱이 try 영역에 ret opcode가 포함된 IL을 생성하는 경우 앱은 .NET Framework 4.5를 대상으로 이전 JIT를 사용하고 이 중단을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23952-107">If an app is generating IL that includes a ret opcode in a try region, the app may target .NET Framework 4.5 to use the old JIT and avoid this break.</span></span> <span data-ttu-id="23952-108">또는 생성된 IL이 try 영역 이후로 돌아가도록 업데이트될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23952-108">Alternatively, the generated IL may be updated to return after the try region.</span></span>|
|<span data-ttu-id="23952-109">범위</span><span class="sxs-lookup"><span data-stu-id="23952-109">Scope</span></span>|<span data-ttu-id="23952-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="23952-110">Edge</span></span>|
|<span data-ttu-id="23952-111">버전</span><span class="sxs-lookup"><span data-stu-id="23952-111">Version</span></span>|<span data-ttu-id="23952-112">4.6</span><span class="sxs-lookup"><span data-stu-id="23952-112">4.6</span></span>|
|<span data-ttu-id="23952-113">형식</span><span class="sxs-lookup"><span data-stu-id="23952-113">Type</span></span>|<span data-ttu-id="23952-114">대상 변경</span><span class="sxs-lookup"><span data-stu-id="23952-114">Retargeting</span></span>|
