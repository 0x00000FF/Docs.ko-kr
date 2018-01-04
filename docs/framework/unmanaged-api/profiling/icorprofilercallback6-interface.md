---
title: "ICorProfilerCallback6 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type: COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 733ca2f03e73852f2fef1e42fb9ec961ade2975d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="2850b-102">ICorProfilerCallback6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2850b-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="2850b-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="2850b-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="2850b-104">서브 클래스 [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) 공용 언어 런타임 어셈블리를 로드 하는 프로파일러에 알리기 위해 사용 하는 콜백 메서드를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2850b-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2850b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2850b-105">Methods</span></span>  
  
|<span data-ttu-id="2850b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2850b-106">Method</span></span>|<span data-ttu-id="2850b-107">설명</span><span class="sxs-lookup"><span data-stu-id="2850b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2850b-108">GetAssemblyReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="2850b-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="2850b-109">공용 언어 런타임이 어셈블리 참조 closure 워커를 수행할 때 어셈블리가 초기 로드 상태임을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2850b-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2850b-110">설명</span><span class="sxs-lookup"><span data-stu-id="2850b-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2850b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2850b-111">Requirements</span></span>  
 <span data-ttu-id="2850b-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2850b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2850b-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2850b-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2850b-114">**.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2850b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2850b-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2850b-115">See Also</span></span>  
 [<span data-ttu-id="2850b-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2850b-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
