---
title: ICorProfilerInfo5::SetEventMask2 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IcorProfilerInfo5.SetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22a783b7564c3545edea93bf4faca1fc40b54cec
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499799"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="084b6-102">ICorProfilerInfo5::SetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="084b6-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="084b6-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="084b6-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="084b6-104">프로파일러가 CLR(공용 언어 런타임)에서 이벤트 알림을 받을 이벤트 형식을 지정하는 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="084b6-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="084b6-105">보다 많은 기능을 제공 합니다 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="084b6-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="084b6-106">구문</span><span class="sxs-lookup"><span data-stu-id="084b6-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="084b6-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="084b6-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="084b6-108">[in] 이벤트 범주를 지정하는 4바이트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="084b6-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="084b6-109">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="084b6-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="084b6-110">설명 하는 비트를 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="084b6-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="084b6-111">[in] 이벤트 범주를 지정하는 4바이트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="084b6-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="084b6-112">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="084b6-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="084b6-113">설명 하는 비트를 [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="084b6-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="084b6-114">설명</span><span class="sxs-lookup"><span data-stu-id="084b6-114">Remarks</span></span>  
 <span data-ttu-id="084b6-115">
  `SetEventMask2\` 메서드를 사용하여 프로파일러가 구독하는 콜백을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="084b6-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="084b6-116">호출 하는 일반적으로 [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) 설정 되는 비트를 확인 하는 방법의 논리 OR를 수행 해당 `pdwEventsLow` 및 `pdwEventsHigh` 값을 설정 하 고 호출 하려는 새 비트를 `SetEventMask2` 메서드.</span><span class="sxs-lookup"><span data-stu-id="084b6-116">Typically, you call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="084b6-117">이 메서드는 권장 되는 대신 합니다 [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="084b6-117">This method is the recommended alternative to the [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="084b6-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="084b6-118">Requirements</span></span>  
 <span data-ttu-id="084b6-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="084b6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="084b6-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="084b6-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="084b6-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="084b6-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="084b6-122">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="084b6-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="084b6-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="084b6-123">See also</span></span>
- [<span data-ttu-id="084b6-124">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="084b6-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="084b6-125">GetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="084b6-125">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
