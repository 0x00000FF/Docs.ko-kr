---
title: ICorProfilerInfo10::EnumerateObjectReferences
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: ac193b6b78434245b8f11a4f627b4e1992feb8a7
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661282"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="8f950-102">ICorProfilerInfo10:: EnumerateObjectReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="8f950-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="8f950-103">ObjectID, callback 및 clientData가 지정 된 경우 각 개체 참조를 열거 합니다 (있는 경우).</span><span class="sxs-lookup"><span data-stu-id="8f950-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="8f950-104">구문</span><span class="sxs-lookup"><span data-stu-id="8f950-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

#### <a name="parameters"></a><span data-ttu-id="8f950-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f950-105">Parameters</span></span>

`objectId` \
<span data-ttu-id="8f950-106">진행 참조를 열거할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8f950-106">[in] The object to enumerate references on.</span></span>

`callback` \
<span data-ttu-id="8f950-107">진행 개체에 대 한 참조를 사용 하 여 호출 되는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f950-107">[in] The function that will be called with the references for the object.</span></span>

`clientData` \
<span data-ttu-id="8f950-108">진행 프로파일러에서 `callback` 함수에 전달할 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f950-108">[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f950-109">설명</span><span class="sxs-lookup"><span data-stu-id="8f950-109">Remarks</span></span>

<span data-ttu-id="8f950-110">메서드 `EnumerateObjectReferences` 는 참조를 저장 하는 배열을 미리 할당 하는 대신 프로파일러의 요청 시 참조를 [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)한다는 점을 제외 하 고는와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f950-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f950-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f950-111">Requirements</span></span>

<span data-ttu-id="8f950-112">**플랫폼** [.Net Core 지원 운영 체제](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f950-112">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="8f950-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8f950-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="8f950-114">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f950-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="8f950-115">**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f950-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8f950-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="8f950-116">See also</span></span>

- [<span data-ttu-id="8f950-117">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f950-117">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
