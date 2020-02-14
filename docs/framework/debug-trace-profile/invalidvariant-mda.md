---
title: invalidVariant MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
ms.openlocfilehash: 8d686621ae4aa087e1b4f4bea9df7fc3de758d40
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216270"
---
# <a name="invalidvariant-mda"></a><span data-ttu-id="3fd30-102">invalidVariant MDA</span><span class="sxs-lookup"><span data-stu-id="3fd30-102">invalidVariant MDA</span></span>
<span data-ttu-id="3fd30-103">`invalidVariant` MDA(관리 디버깅 도우미)는 네이티브 코드나 비관리 코드에서 관리 코드로 호출하는 동안 잘못된 `VARIANT` 구조가 발생할 때 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fd30-103">The `invalidVariant` managed debugging assistant (MDA) is activated when an invalid `VARIANT` structure is encountered during a call from native or unmanaged code to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="3fd30-104">증상</span><span class="sxs-lookup"><span data-stu-id="3fd30-104">Symptoms</span></span>  
 <span data-ttu-id="3fd30-105">`VARIANT`를 개체로 마샬링하는 작업과 관련해서 네이티브 코드와 관리 코드 간에 전환하는 동안 발생하는 예기치 않은 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="3fd30-105">Unexpected behavior during a transition between native and managed code involving the marshaling of a `VARIANT` to an object.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="3fd30-106">원인</span><span class="sxs-lookup"><span data-stu-id="3fd30-106">Cause</span></span>  
 <span data-ttu-id="3fd30-107">네이티브 코드는 형식이 잘못된 `VARIANT` 구조를 관리 코드로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd30-107">Native code is passing a malformed `VARIANT` structure to managed code.</span></span>  <span data-ttu-id="3fd30-108">런타임에서는 이 `VARIANT`를 개체로 마샬링하려고 시도하고 `VARIANT`가 유효하지 않으면 MDA를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd30-108">The runtime attempts to marshal this `VARIANT` to an object and activates the MDA if the `VARIANT` is not valid.</span></span> <span data-ttu-id="3fd30-109">잘못된 `VARIANT`의 예로는 `VARIANT`와 `VARTYPE` VT_EMPTY &#124; VT_BYREF를 함께 사용하거나 `VARIANT`를 `VARTYPE` VT_VARIANT와 함께 사용하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd30-109">Examples of invalid `VARIANT`S include a `VARIANT` with `VARTYPE` VT_EMPTY &#124; VT_BYREF or a `VARIANT` with `VARTYPE` VT_VARIANT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="3fd30-110">해결 방법</span><span class="sxs-lookup"><span data-stu-id="3fd30-110">Resolution</span></span>  
 <span data-ttu-id="3fd30-111">`VARIANT`를 전달하는 네이티브 코드나 비관리 코드는 `VARIANT`가 제대로 서식 지정되고 초기화되었는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd30-111">The native or unmanaged code passing the `VARIANT` must ensure that the `VARIANT` is correctly formed and initialized.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="3fd30-112">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="3fd30-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="3fd30-113">MDA는 런타임 동작에 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd30-113">The MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="3fd30-114">출력</span><span class="sxs-lookup"><span data-stu-id="3fd30-114">Output</span></span>  
 <span data-ttu-id="3fd30-115">런타임에서 비관리 모듈을 통해 관리 코드에 전달된 잘못된 `VARIANT`를 감지했음을 나타내는 MDA 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="3fd30-115">An MDA message indicating that the runtime detected an invalid `VARIANT` passed to managed code by an unmanaged module.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="3fd30-116">구성</span><span class="sxs-lookup"><span data-stu-id="3fd30-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3fd30-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fd30-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="3fd30-118">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="3fd30-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="3fd30-119">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="3fd30-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
