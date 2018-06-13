---
title: ICorProfilerCallback5 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 338bc10e02ceba5fb38c70088c4151271fca9b2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454415"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="ec97c-102">ICorProfilerCallback5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec97c-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="ec97c-103">와 함께 사용 하는 경우 라이브 개체의 전체 closure를 식별 합니다. 프로파일러가 수 있는 정보는 [icorprofilercallback:: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) 또는 [icorprofilercallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)와 함께 메서드는 [icorprofilercallback:: Objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) 및 [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="ec97c-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="ec97c-104">관리되는 메모리 프로파일러가 `ICorProfilerCallback5`를 구현하여 종속 핸들과 관련된 알림을 구독해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec97c-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec97c-105">설명</span><span class="sxs-lookup"><span data-stu-id="ec97c-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ec97c-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ec97c-106">Methods</span></span>  
  
|<span data-ttu-id="ec97c-107">메서드</span><span class="sxs-lookup"><span data-stu-id="ec97c-107">Method</span></span>|<span data-ttu-id="ec97c-108">설명</span><span class="sxs-lookup"><span data-stu-id="ec97c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ec97c-109">ConditionalWeakTableElementReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="ec97c-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="ec97c-110">직접 멤버 필드 참조와 `ConditionalWeakTable` 종속성을 모두 사용하여 루트를 통해 참조되는 개체의 전이적 Closure를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ec97c-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec97c-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ec97c-111">Requirements</span></span>  
 <span data-ttu-id="ec97c-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec97c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec97c-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ec97c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ec97c-114">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec97c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec97c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec97c-115">See Also</span></span>  
 [<span data-ttu-id="ec97c-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec97c-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="ec97c-117">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec97c-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
