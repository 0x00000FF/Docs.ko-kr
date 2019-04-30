---
title: ICorProfilerCallback5::ConditionalWeakTableElementReferences 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5.ConditionalWeakTableReferences
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ConditionalWeakTableElementReferences
helpviewer_keywords:
- ConditionalWeakTableElementReferences method, ICorProfilerCallback5 interface [.NET Framework profiling]
- ICorProfilerCallback5::ConditionalWeakTableElementReferences method [.NET Framework profiling]
ms.assetid: 532c7a02-a9de-4cea-bb2b-7f470da594de
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 39ce72451f3a375f0cd3adb67a431162fc421a93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041604"
---
# <a name="icorprofilercallback5conditionalweaktableelementreferences-method"></a><span data-ttu-id="f7935-102">ICorProfilerCallback5::ConditionalWeakTableElementReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="f7935-102">ICorProfilerCallback5::ConditionalWeakTableElementReferences Method</span></span>

<span data-ttu-id="f7935-103">직접 멤버 필드 참조와 `ConditionalWeakTable` 종속성을 모두 사용하여 루트를 통해 참조되는 개체의 전이적 Closure를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f7935-103">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>

## <a name="syntax"></a><span data-ttu-id="f7935-104">구문</span><span class="sxs-lookup"><span data-stu-id="f7935-104">Syntax</span></span>

```cpp
HRESULT ConditionalWeakTableElementReferences(
     [in]                     ULONG    cRootRefs,
     [in, size_is(cRootRefs)] ObjectID keyRefIds[],
     [in, size_is(cRootRefs)] ObjectID valueRefIds[],
     [in, size_is(cRootRefs)] GCHandleID rootIds[]
);
```

## <a name="parameters"></a><span data-ttu-id="f7935-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f7935-105">Parameters</span></span>

`cRootRefs`\
<span data-ttu-id="f7935-106">[in] `keyRefIds`, `valueRefIds` 및 `rootIds` 배열의 요소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f7935-106">[in] The number of elements in the `keyRefIds`, `valueRefIds`, and `rootIds` arrays.</span></span>

`keyRefIds`\
<span data-ttu-id="f7935-107">[in] 각각 종속 핸들 쌍의 주 요소에 대한 `ObjectID`를 포함하는 개체 ID의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f7935-107">[in] An array of object IDs, each of which contains the `ObjectID` for the primary element in the dependent handle pair.</span></span>

`valueRefIds`\
<span data-ttu-id="f7935-108">[in] 각각 종속 핸들 쌍의 보조 요소에 대한 `ObjectID`를 포함하는 개체 ID의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f7935-108">[in] An array of object IDs, each of which contains the `ObjectID` for the secondary element in the dependent handle pair.</span></span> <span data-ttu-id="f7935-109">(`keyRefIds[i]` 유지 `valueRefIds[i]` 유지 합니다.)</span><span class="sxs-lookup"><span data-stu-id="f7935-109">(`keyRefIds[i]` keeps `valueRefIds[i]` alive.)</span></span>

`rootIds`\
<span data-ttu-id="f7935-110">[in] 가비지 컬렉션 루트에 대한 추가 정보를 포함하는 정수를 가리키는 `GCHandleID` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f7935-110">[in] An array of `GCHandleID` values that point to an integer that contains additional information about the garbage collection root.</span></span>

<span data-ttu-id="f7935-111">콜백 자체가 진행되는 동안 `ObjectID` 메서드에서 반환되는 `ConditionalWeakTableElementReferences` 값은 유효하지 않습니다. 가비지 수집기가 이전 위치에서 새 위치로 개체를 이동하는 중일 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f7935-111">None of the `ObjectID` values returned by the `ConditionalWeakTableElementReferences` method are valid during the callback itself, because the garbage collector may be in the process of moving objects from old to new locations.</span></span> <span data-ttu-id="f7935-112">그러므로 프로파일러는 `ConditionalWeakTableElementReferences` 호출 중에 개체 검사를 시도하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7935-112">Therefore, profilers should not attempt to inspect objects during a `ConditionalWeakTableElementReferences` call.</span></span> <span data-ttu-id="f7935-113">`GarbageCollectionFinished` 시에는 모든 개체가 새 위치로 이동했으므로 검사를 수행해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7935-113">At `GarbageCollectionFinished`, all objects have been moved to their new locations, and inspection may be done.</span></span>

## <a name="example"></a><span data-ttu-id="f7935-114">예제</span><span class="sxs-lookup"><span data-stu-id="f7935-114">Example</span></span>

<span data-ttu-id="f7935-115">다음 코드 예제에서는 구현 방법을 보여 줍니다 [ICorProfilerCallback5](icorprofilercallback5-interface.md) 이 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7935-115">The following code example demonstrates how to implement [ICorProfilerCallback5](icorprofilercallback5-interface.md) and use this method.</span></span>

```cpp
HRESULT Callback5Impl::ConditionalWeakTableElementReferences(
    ULONG      cRootRefs,
    ObjectID   keyRefIds[],
    ObjectID   valueRefIds[],
    GCHandleID rootIds[])
{
    printf("Callback5Impl::ConditionalWeakTableElementReferences called\n");
    for (unsigned int i = 0; i < cRootRefs; ++i)
    {
        // Save dependency to XML for later retrieval
        PersistDependencyToXml(rootIds[i], keyRefIds[i], valueRefIds[i]);
        // or store dependency to an internal map
        m_cwt_deps->add_dep(rootIds[i], keyRefIds[i], valueRefIds[i]);
        // or add arc to object graph
        m_obj_graph->add_arc(keyRefIds[i], valueRefIds[i], rootIds[i]);
    }
    return S_OK;
}
```

## <a name="remarks"></a><span data-ttu-id="f7935-116">설명</span><span class="sxs-lookup"><span data-stu-id="f7935-116">Remarks</span></span>

<span data-ttu-id="f7935-117">에 대 한 프로파일러를 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] 또는 이후 버전 구현을 [ICorProfilerCallback5](icorprofilercallback5-interface.md) 인터페이스와 지정 된 종속성을 기록 합니다 `ConditionalWeakTableElementReferences` 메서드.</span><span class="sxs-lookup"><span data-stu-id="f7935-117">A profiler for the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] or later versions implements the [ICorProfilerCallback5](icorprofilercallback5-interface.md) interface and records the dependencies specified by the `ConditionalWeakTableElementReferences` method.</span></span> <span data-ttu-id="f7935-118">`ICorProfilerCallback5` 표시 되는 라이브 개체 간의 종속성의 전체 집합을 제공 `ConditionalWeakTable` 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="f7935-118">`ICorProfilerCallback5` provides the complete set of dependencies among live objects represented by `ConditionalWeakTable` entries.</span></span> <span data-ttu-id="f7935-119">이러한 종속성과 멤버 필드 참조 하 여 지정 된 [icorprofilercallback:: Objectreferences](icorprofilercallback-objectreferences-method.md) 메서드 사용을 관리 되는 프로파일러가 라이브 개체의 전체 개체 그래프를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7935-119">These dependencies and the member field references specified by the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) method enable a managed profiler to generate the full object graph of live objects.</span></span>

## <a name="requirements"></a><span data-ttu-id="f7935-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7935-120">Requirements</span></span>

<span data-ttu-id="f7935-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f7935-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="f7935-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f7935-122">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="f7935-123">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7935-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f7935-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="f7935-124">See also</span></span>

- [<span data-ttu-id="f7935-125">ICorProfilerCallback5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7935-125">ICorProfilerCallback5 Interface</span></span>](icorprofilercallback5-interface.md)