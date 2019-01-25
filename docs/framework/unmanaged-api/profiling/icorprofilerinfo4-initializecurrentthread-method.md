---
title: ICorProfilerInfo4::InitializeCurrentThread 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 990ae316a780af9be96f6b91900f33cbb2db4f36
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727978"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="5baf4-102">ICorProfilerInfo4::InitializeCurrentThread 메서드</span><span class="sxs-lookup"><span data-stu-id="5baf4-102">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>
<span data-ttu-id="5baf4-103">후속 프로파일러 해당 교착 상태를 방지할 수 있도록 동일한 스레드에서 API 호출 하기 전에 현재 스레드를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="5baf4-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5baf4-104">구문</span><span class="sxs-lookup"><span data-stu-id="5baf4-104">Syntax</span></span>  
  
```  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5baf4-105">설명</span><span class="sxs-lookup"><span data-stu-id="5baf4-105">Remarks</span></span>  
 <span data-ttu-id="5baf4-106">호출 하는 것이 좋습니다 `InitializeCurrentThread` 있기는 API는 프로파일러를 호출 하는 모든 스레드에서 스레드를 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="5baf4-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="5baf4-107">이 메서드는 일반적으로 샘플링 프로파일러는 자체 스레드를 호출 하 여 사용 합니다 [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) 대상 스레드가 일시 중단 된 동안 스택 수행 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5baf4-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="5baf4-108">호출 하 여 `InitializeCurrentThread` 프로파일러 CLR 그렇지 않은 경우 첫 번째 호출 하는 동안 수행 하는 해당 스레드 단위 지연 초기화 확실히 경우 프로파일러는 샘플링 스레드를 먼저 만듭니다, 면 `DoStackSnapshot` 다른 스레드가 없을 때 안전 하 게 발생 이제 수 일시 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5baf4-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5baf4-109">`InitializeCurrentThread` 잠금을 하 고 교착 상태가 발생할 수 있는 작업을 완료 하기 전에 초기화를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5baf4-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="5baf4-110">호출 `InitializeCurrentThread` 일시 중단 된 스레드가 없는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="5baf4-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5baf4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5baf4-111">Requirements</span></span>  
 <span data-ttu-id="5baf4-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5baf4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5baf4-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5baf4-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5baf4-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5baf4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5baf4-115">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5baf4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5baf4-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="5baf4-116">See also</span></span>
- [<span data-ttu-id="5baf4-117">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5baf4-117">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="5baf4-118">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5baf4-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="5baf4-119">프로파일링</span><span class="sxs-lookup"><span data-stu-id="5baf4-119">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
