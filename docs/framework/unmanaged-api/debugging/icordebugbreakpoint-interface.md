---
title: ICorDebugBreakpoint 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7e454c15ddfa977a6d06921a5d80a6c05dca92f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973576"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="ff206-102">ICorDebugBreakpoint 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff206-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="ff206-103">함수 또는 값에 대 한 조사식 위치에서 중단점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ff206-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff206-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ff206-104">Methods</span></span>  
  
|<span data-ttu-id="ff206-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ff206-105">Method</span></span>|<span data-ttu-id="ff206-106">설명</span><span class="sxs-lookup"><span data-stu-id="ff206-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff206-107">Activate 메서드</span><span class="sxs-lookup"><span data-stu-id="ff206-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="ff206-108">이 활성 상태를 설정 `ICorDebugBreakpoint`합니다.</span><span class="sxs-lookup"><span data-stu-id="ff206-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="ff206-109">IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="ff206-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="ff206-110">나타내는 값을 가져옵니다 여부를이 `ICorDebugBreakpoint` 활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff206-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff206-111">설명</span><span class="sxs-lookup"><span data-stu-id="ff206-111">Remarks</span></span>  
 <span data-ttu-id="ff206-112">중단점 조건 식을 직접 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff206-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="ff206-113">이러한 기능을 원하는 경우 디버거를 구현 해야 위에 `ICorDebugBreakpoint`합니다.</span><span class="sxs-lookup"><span data-stu-id="ff206-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="ff206-114">ICorDebugFunctionBreakpoint 인터페이스 확장 `ICorDebugBreakpoint` 함수 내에서 중단점을 지원 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff206-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff206-115">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff206-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff206-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff206-116">Requirements</span></span>  
 <span data-ttu-id="ff206-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ff206-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff206-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff206-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff206-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff206-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff206-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff206-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff206-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="ff206-121">See also</span></span>
- [<span data-ttu-id="ff206-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff206-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
