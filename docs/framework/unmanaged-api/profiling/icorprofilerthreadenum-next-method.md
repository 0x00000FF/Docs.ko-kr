---
title: ICorProfilerThreadEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Next
helpviewer_keywords:
- ICorProfilerThreadEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: f3535279-3c63-41a2-ab0e-a129dc5a01e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44595229eaefa0d8fc8ca7bf15a88d0fbf1ee0d7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104314"
---
# <a name="icorprofilerthreadenumnext-method"></a><span data-ttu-id="6fed8-102">ICorProfilerThreadEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="6fed8-102">ICorProfilerThreadEnum::Next Method</span></span>
<span data-ttu-id="6fed8-103">시퀀스에서 열거자의 현재 위치부터 시작하여 순차적 스레드 컬렉션에서 지정된 개수의 연속 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6fed8-103">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fed8-104">구문</span><span class="sxs-lookup"><span data-stu-id="6fed8-104">Syntax</span></span>  
  
```  
HRESULT Next (    [in]  ULONG      celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                    ThreadID ids[],  
    [out] ULONG *   pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fed8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6fed8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6fed8-106">[in] 검색할 스레드 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="6fed8-106">[in] The number of threads to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="6fed8-107">[out] 각각 검색된 스레드를 나타내는 `ThreadID` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6fed8-107">[out] An array of `ThreadID` values, each of which represents a retrieved thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6fed8-108">[out] `ids` 배열에 실제로 반환된 스레드 개수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6fed8-108">[out] A pointer to the number of threads actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6fed8-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="6fed8-109">Return Value</span></span>  
 <span data-ttu-id="6fed8-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fed8-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6fed8-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6fed8-111">HRESULT</span></span>|<span data-ttu-id="6fed8-112">설명</span><span class="sxs-lookup"><span data-stu-id="6fed8-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6fed8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="6fed8-113">S_OK</span></span>|<span data-ttu-id="6fed8-114">`celt` 요소가 반환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fed8-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="6fed8-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6fed8-115">S_FALSE</span></span>|<span data-ttu-id="6fed8-116">`celt`개 미만의 요소가 반환되었으며 이는 열거형이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6fed8-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6fed8-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6fed8-117">Requirements</span></span>  
 <span data-ttu-id="6fed8-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fed8-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fed8-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6fed8-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6fed8-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fed8-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fed8-121">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fed8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fed8-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="6fed8-122">See also</span></span>

- [<span data-ttu-id="6fed8-123">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fed8-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="6fed8-124">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fed8-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
