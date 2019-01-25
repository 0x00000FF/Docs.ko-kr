---
title: ICorProfilerModuleEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Next
helpviewer_keywords:
- ICorProfilerModuleEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: a3cea59d-7622-4323-897a-0a464c40f77f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fc33936735c40e2f30189066d80444b9fcb075ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671891"
---
# <a name="icorprofilermoduleenumnext-method"></a><span data-ttu-id="2a759-102">ICorProfilerModuleEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="2a759-102">ICorProfilerModuleEnum::Next Method</span></span>
<span data-ttu-id="2a759-103">시퀀스에서 열거자의 현재 위치부터 시작하여 순차적 모듈 컬렉션에서 지정된 개수의 연속 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2a759-103">Gets the specified number of contiguous modules from a sequential collection of modules, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a759-104">구문</span><span class="sxs-lookup"><span data-stu-id="2a759-104">Syntax</span></span>  
  
```  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    ModuleID ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a759-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a759-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2a759-106">[in] 검색할 모듈 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2a759-106">[in] The number of modules to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="2a759-107">[out] 각각 검색된 모듈을 나타내는 `ModuleID` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2a759-107">[out] An array of `ModuleID` values, each of which represents a retrieved module.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2a759-108">[out] `ids` 배열에 실제로 반환된 모듈 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2a759-108">[out] A pointer to the number of elements actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a759-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="2a759-109">Return Value</span></span>  
 <span data-ttu-id="2a759-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2a759-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2a759-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a759-111">HRESULT</span></span>|<span data-ttu-id="2a759-112">설명</span><span class="sxs-lookup"><span data-stu-id="2a759-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a759-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a759-113">S_OK</span></span>|<span data-ttu-id="2a759-114">`celt` 요소가 반환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2a759-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="2a759-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2a759-115">S_FALSE</span></span>|<span data-ttu-id="2a759-116">`celt`개 미만의 요소가 반환되었으며 이는 열거형이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2a759-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a759-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a759-117">Requirements</span></span>  
 <span data-ttu-id="2a759-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2a759-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a759-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2a759-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2a759-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a759-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a759-121">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a759-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a759-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="2a759-122">See also</span></span>
- [<span data-ttu-id="2a759-123">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a759-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="2a759-124">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a759-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
