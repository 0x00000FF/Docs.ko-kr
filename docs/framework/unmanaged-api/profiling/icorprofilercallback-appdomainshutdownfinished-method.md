---
title: ICorProfilerCallback::AppDomainShutdownFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f9f8925630933e2247726f92a93cac67bdc55ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450491"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="84a1f-102">ICorProfilerCallback::AppDomainShutdownFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="84a1f-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="84a1f-103">응용 프로그램 도메인 프로세스에서 로드 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="84a1f-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84a1f-104">구문</span><span class="sxs-lookup"><span data-stu-id="84a1f-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84a1f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="84a1f-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="84a1f-106">[in] 응용 프로그램의 어셈블리가 저장 되는 도메인을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="84a1f-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="84a1f-107">[in] 응용 프로그램 도메인이 로드 되었는지 여부를 하지 성공적으로 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="84a1f-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84a1f-108">설명</span><span class="sxs-lookup"><span data-stu-id="84a1f-108">Remarks</span></span>  
 <span data-ttu-id="84a1f-109">값 `appDomainId` 후 정보 요청에 유효 하지는 [icorprofilercallback:: Appdomainshutdownstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) 메서드 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84a1f-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="84a1f-110">일부 응용 프로그램 도메인 언로드 후 계속 사용할 수는 `AppDomainCreationFinished` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="84a1f-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="84a1f-111">실패 HRESULT에서 `hrStatus` 오류가 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84a1f-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="84a1f-112">그러나 성공 HRESULT에서 `hrStatus` 응용 프로그램 도메인 언로드 작업의 첫 번째 부분 성공 했다는 것만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84a1f-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84a1f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84a1f-113">Requirements</span></span>  
 <span data-ttu-id="84a1f-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="84a1f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84a1f-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="84a1f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="84a1f-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84a1f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84a1f-117">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84a1f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a1f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84a1f-118">See Also</span></span>  
 [<span data-ttu-id="84a1f-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84a1f-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
