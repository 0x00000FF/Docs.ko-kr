---
title: ICorProfilerInfo2::GetGenerationBounds 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetGenerationBounds
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetGenerationBounds
helpviewer_keywords:
- ICorProfilerInfo2::GetGenerationBounds method [.NET Framework profiling]
- GetGenerationBounds method [.NET Framework profiling]
ms.assetid: 9c37185f-d1e0-4a6e-8b99-707f7df61d88
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 760c2d927409ef9f0a1f7a72c33efd3a7618f771
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678627"
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a><span data-ttu-id="b7e62-102">ICorProfilerInfo2::GetGenerationBounds 메서드</span><span class="sxs-lookup"><span data-stu-id="b7e62-102">ICorProfilerInfo2::GetGenerationBounds Method</span></span>
<span data-ttu-id="b7e62-103">다양한 가비지 컬렉션 세대를 구성하는 힙 세그먼트인 메모리 영역을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b7e62-103">Gets the memory regions, which are segments of the heap, that make up the various garbage collection generations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7e62-104">구문</span><span class="sxs-lookup"><span data-stu-id="b7e62-104">Syntax</span></span>  
  
```  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7e62-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7e62-105">Parameters</span></span>  
 `cObjectRanges`  
 <span data-ttu-id="b7e62-106">[in] `ranges` 배열에 대해 호출자가 할당한 요소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7e62-106">[in] The number of elements allocated by the caller for the `ranges` array.</span></span>  
  
 `pcObjectRanges`  
 <span data-ttu-id="b7e62-107">[out] 일부 또는 전체가 `ranges` 배열로 반환되는 총 범위 수를 지정하는 정수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b7e62-107">[out] A pointer to an integer that specifies the total number of ranges, some or all of which will be returned in the `ranges` array.</span></span>  
  
 `ranges`  
 <span data-ttu-id="b7e62-108">[out] 배열을 [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) 가비지 컬렉션 중인 세대 내의 메모리 범위 (즉, 블록)를 설명 하는 각 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="b7e62-108">[out] An array of [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7e62-109">설명</span><span class="sxs-lookup"><span data-stu-id="b7e62-109">Remarks</span></span>  
 <span data-ttu-id="b7e62-110">가비지 컬렉션이 진행되고 있지 않으면 모든 프로파일러 콜백에서 `GetGenerationBounds` 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e62-110">The `GetGenerationBounds` method can be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="b7e62-111">즉, 간에 발생 하는 작업을 제외한 모든 콜백에서 호출할 수 있습니다 [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) 하 고 [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e62-111">That is, it can be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
 <span data-ttu-id="b7e62-112">대부분의 세대 이동은 가비지 컬렉션 중에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e62-112">Most shifting of generations takes place during garbage collections.</span></span> <span data-ttu-id="b7e62-113">컬렉션 간에 세대가 증가할 수 있지만 일반적으로 이동하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e62-113">Generations might grow between collections but generally do not move around.</span></span> <span data-ttu-id="b7e62-114">따라서 가장 흥미로운 `GetGenerationBounds` 호출 위치는 `ICorProfilerCallback2::GarbageCollectionStarted` 및 `ICorProfilerCallback2::GarbageCollectionFinished`입니다.</span><span class="sxs-lookup"><span data-stu-id="b7e62-114">Therefore, the most interesting places to call `GetGenerationBounds` are in `ICorProfilerCallback2::GarbageCollectionStarted` and `ICorProfilerCallback2::GarbageCollectionFinished`.</span></span>  
  
 <span data-ttu-id="b7e62-115">프로그램 시작 중에 일부 개체는 CLR(공용 언어 런타임)에 의해 일반적으로 3세대 및 0세대에서 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7e62-115">During program startup, some objects are allocated by the common language runtime (CLR) itself, generally in generations 3 and 0.</span></span> <span data-ttu-id="b7e62-116">따라서 관리 코드 실행이 시작되는 시간에는 이러한 세대에 이미 개체가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e62-116">Thus, by the time managed code starts executing, these generations will already contain objects.</span></span> <span data-ttu-id="b7e62-117">1세대와 2세대는 가비지 수집기에서 생성되는 더미 개체를 제외하고 일반적으로 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e62-117">Generations 1 and 2 will normally be empty, except for dummy objects that are generated by the garbage collector.</span></span> <span data-ttu-id="b7e62-118">더미 개체의 크기는 32비트 CLR 구현에서 12바이트이고 64비트 구현에서는 크기가 더 큽니다. 네이티브 이미지 생성기(NGen.exe)에 의해 생성된, 모듈 내에 있는 2세대 범위가 표시될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e62-118">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span></span> <span data-ttu-id="b7e62-119">이 경우에 2 세대의 개체는 *개체를 고정*, NGen.exe가 실행 하는 경우 보다는 가비지 수집기에 의해 할당 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e62-119">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span></span>  
  
 <span data-ttu-id="b7e62-120">이 함수는 호출자 할당 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e62-120">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7e62-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7e62-121">Requirements</span></span>  
 <span data-ttu-id="b7e62-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b7e62-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7e62-123">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b7e62-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b7e62-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7e62-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7e62-125">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7e62-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7e62-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="b7e62-126">See also</span></span>
- [<span data-ttu-id="b7e62-127">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7e62-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="b7e62-128">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7e62-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [<span data-ttu-id="b7e62-129">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7e62-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="b7e62-130">프로파일링</span><span class="sxs-lookup"><span data-stu-id="b7e62-130">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
