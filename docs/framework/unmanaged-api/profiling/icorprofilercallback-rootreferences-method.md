---
title: ICorProfilerCallback::RootReferences 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94b736a8e3250f4d208d4a9a46a022140b676318
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631355"
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="99334-102">ICorProfilerCallback::RootReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="99334-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="99334-103">가비지 컬렉션 후 루트 참조에 대 한 정보를 사용 하 여 프로파일러를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="99334-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99334-104">구문</span><span class="sxs-lookup"><span data-stu-id="99334-104">Syntax</span></span>  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99334-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99334-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="99334-106">[in] 에 대 한 참조 횟수를 `rootRefIds` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="99334-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="99334-107">[in] 스택에 있는 개체 또는 정적 개체를 참조 하는 개체 Id의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="99334-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99334-108">설명</span><span class="sxs-lookup"><span data-stu-id="99334-108">Remarks</span></span>  
 <span data-ttu-id="99334-109">둘 다 `RootReferences` 하 고 [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) 프로파일러에 알리기 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99334-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="99334-110">하나 또는 다른 프로파일러는 일반적으로 구현 됩니다 둘 모두가 아닌 정보를 전달 되므로 `RootReferences2` 전달의 상위 집합이 `RootReferences`합니다.</span><span class="sxs-lookup"><span data-stu-id="99334-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="99334-111">이기는 `rootRefIds` null 개체가 포함 될 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="99334-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="99334-112">예를 들어 스택에 선언 된 모든 개체 참조는 가비지 수집기에서 루트로 처리 되 고 항상 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99334-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="99334-113">개체 Id가 반환한 `RootReferences` 가비지 컬렉션 이전 주소에서 개체를 새 주소로 이동 하는 중일 수 있으므로 자체를 콜백 하는 동안 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99334-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="99334-114">따라서 프로파일러 시도 하지 않아야 하는 동안 개체를 검사 한 `RootReferences` 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="99334-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="99334-115">때 [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) 는 호출 개체를 모두 새 위치로 이동 되었습니다 및 안전 하 게 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99334-115">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99334-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99334-116">Requirements</span></span>  
 <span data-ttu-id="99334-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="99334-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99334-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="99334-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="99334-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99334-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99334-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99334-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99334-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="99334-121">See also</span></span>
- [<span data-ttu-id="99334-122">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99334-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
