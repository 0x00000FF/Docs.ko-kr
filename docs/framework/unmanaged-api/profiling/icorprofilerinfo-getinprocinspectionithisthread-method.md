---
title: ICorProfilerInfo::GetInprocInspectionIThisThread 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionIThisThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 019a85d6d58c99adb7c16be5cc3b31b029b0312d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513146"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="6aa2f-102">ICorProfilerInfo::GetInprocInspectionIThisThread 메서드</span><span class="sxs-lookup"><span data-stu-id="6aa2f-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="6aa2f-103">ICorDebugThread 인터페이스에 대해 쿼리할 수 있는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6aa2f-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="6aa2f-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa2f-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aa2f-105">구문</span><span class="sxs-lookup"><span data-stu-id="6aa2f-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6aa2f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6aa2f-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="6aa2f-107">[out](/cpp/atl/iunknown) 에 대해 쿼리할 수 있는 개체는 `ICorDebugThread` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa2f-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6aa2f-108">설명</span><span class="sxs-lookup"><span data-stu-id="6aa2f-108">Remarks</span></span>  
 <span data-ttu-id="6aa2f-109">공용 언어 런타임 (CLR) 디버깅 서비스는.NET Framework 버전 1.0에서에서 제한 된 in process 디버깅 지원.</span><span class="sxs-lookup"><span data-stu-id="6aa2f-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="6aa2f-110">디버깅 프로세스에 프로파일러를 사용 하 여 디버깅 API의 검사 부분을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa2f-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="6aa2f-111">고객 피드백의 결과로 in process 디버깅 버전 2.0에서에서.NET Framework에서 제거 되어 프로 파일링 API에 따라 더 기능 집합으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa2f-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aa2f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6aa2f-112">Requirements</span></span>  
 <span data-ttu-id="6aa2f-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6aa2f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aa2f-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6aa2f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6aa2f-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6aa2f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6aa2f-116">**.NET framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="6aa2f-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa2f-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="6aa2f-117">See also</span></span>
- [<span data-ttu-id="6aa2f-118">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6aa2f-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
