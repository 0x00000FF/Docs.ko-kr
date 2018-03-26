---
title: ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
api_name:
- ICorProfiler7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
caps.latest.revision: ''
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 898adf043e425c00d6e311e2f67c53ed65cacb33
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2018
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="571f3-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span><span class="sxs-lookup"><span data-stu-id="571f3-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="571f3-103">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="571f3-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="571f3-104">메모리 내 모듈과 연관 된 기호 스트림이 업데이트 될 때마다 프로파일러를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="571f3-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="571f3-105">구문</span><span class="sxs-lookup"><span data-stu-id="571f3-105">Syntax</span></span>  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="571f3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="571f3-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="571f3-107">메모리 내 모듈과 된 기호 스트림이 업데이트의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="571f3-107">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="571f3-108">설명</span><span class="sxs-lookup"><span data-stu-id="571f3-108">Remarks</span></span>  
 <span data-ttu-id="571f3-109">이 콜백을 설정 하 여 제어는 [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) 이벤트 마스크 플래그를 호출할 때는 [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="571f3-109">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="571f3-110">이 이벤트는 암시적으로 만들거나 수정한 통해 기호에 대 한 현재 발생 되지 <xref:System.Reflection.Emit> Api입니다.</span><span class="sxs-lookup"><span data-stu-id="571f3-110">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="571f3-111">도 경우 기호에에서 제공 된 들겠지만 관리 되는 오버 로드 중 하나에 대 한 호출 <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> 메서드를 포함 하는 `rawSymbolStore` 런타임 어셈블리에 대 한 기호를 지정 하려면 인수 기호 데이터 모듈과 함께 실제로 연결 하지 않을 수 있습니다 될 때까지 후의 [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백이 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="571f3-111">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="571f3-112">이 이벤트는 이러한 모듈에 대 한 기호를 수집 하는 이후 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="571f3-112">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="571f3-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="571f3-113">Requirements</span></span>  
 <span data-ttu-id="571f3-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="571f3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="571f3-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="571f3-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="571f3-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="571f3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="571f3-117">**.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="571f3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="571f3-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="571f3-118">See Also</span></span>  
 [<span data-ttu-id="571f3-119">ModuleLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="571f3-119">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [<span data-ttu-id="571f3-120">SetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="571f3-120">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)  
 [<span data-ttu-id="571f3-121">ICorProfilerCallback7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="571f3-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
