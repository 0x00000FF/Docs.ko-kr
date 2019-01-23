---
title: ICorProfilerInfo2::GetContextStaticAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d4ebf93c103b74be458ba51577a5195795029176
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520402"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="01183-102">ICorProfilerInfo2::GetContextStaticAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="01183-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="01183-103">지정 된 컨텍스트의 범위 내에 있는 지정된 된 컨텍스트 정적 필드에 대 한 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="01183-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01183-104">구문</span><span class="sxs-lookup"><span data-stu-id="01183-104">Syntax</span></span>  
  
```  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01183-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="01183-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="01183-106">[in] 요청한 컨텍스트 정적 필드를 포함 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="01183-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="01183-107">[in] 요청한 컨텍스트 정적 필드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="01183-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="01183-108">[in] 요청한 컨텍스트 정적 필드에 대 한 범위는 컨텍스트의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="01183-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="01183-109">[out] 지정된 된 컨텍스트 내에 있는 정적 필드의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="01183-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01183-110">설명</span><span class="sxs-lookup"><span data-stu-id="01183-110">Remarks</span></span>  
 <span data-ttu-id="01183-111">`GetContextStaticAddress` 메서드 중 하나를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01183-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="01183-112">지정 된 정적 필드에 지정 된 컨텍스트에서 주소 할당 되지 않은 경우 CORPROF_E_DATAINCOMPLETE HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="01183-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="01183-113">가비지 컬렉션 힙에 있을 수 있는 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="01183-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="01183-114">이러한 주소 가비지 수집 후 프로파일러 가정 하지 않아야 유효한 지 하므로 가비지 컬렉션 후 잘못 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01183-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="01183-115">클래스의 클래스 생성자 완료 되기 전에 `GetContextStaticAddress` 정적 필드 중 일부를 초기화할 수는 이미 있지만 CORPROF_E_DATAINCOMPLETE 정적 해당 모든 필드에 대 한 반환 하 고 가비지 컬렉션 개체를 응원 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="01183-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01183-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01183-116">Requirements</span></span>  
 <span data-ttu-id="01183-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="01183-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01183-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="01183-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="01183-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01183-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01183-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01183-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01183-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="01183-121">See also</span></span>
- [<span data-ttu-id="01183-122">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01183-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="01183-123">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01183-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
