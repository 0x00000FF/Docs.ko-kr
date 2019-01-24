---
title: ICorProfilerCallback::RemotingClientInvocationStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c0cc27bd6a5c0cb85f4822a4481d9588705b71bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575962"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="fda34-102">ICorProfilerCallback::RemotingClientInvocationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="fda34-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="fda34-103">원격 호출을 시작한 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fda34-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fda34-104">구문</span><span class="sxs-lookup"><span data-stu-id="fda34-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="fda34-105">설명</span><span class="sxs-lookup"><span data-stu-id="fda34-105">Remarks</span></span>  
 <span data-ttu-id="fda34-106">이 이벤트는 동기 및 비동기 호출에 대해 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda34-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="fda34-107">각 콜백의 다음 쌍 동일한 스레드에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda34-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
-   <span data-ttu-id="fda34-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="fda34-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
-   <span data-ttu-id="fda34-109">[Icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) 고 [icorprofilercallback:: Remotingclientinvocationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="fda34-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
-   <span data-ttu-id="fda34-110">[Icorprofilercallback:: Remotingserverinvocationreturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) 고 [icorprofilercallback:: Remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="fda34-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="fda34-111">원격 콜백 사용 하 여 다음 문제를 파악 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda34-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
-   <span data-ttu-id="fda34-112">클라이언트에서 호출 되 고 서버에서 실행 되는 함수에 대 한 알림을 올바르게 수신 되지 않습니다 있도록 remoting 함수 실행 API 프로파일러에 의해 반영 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fda34-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="fda34-113">프록시 개체를 통해 발생 하는 실제 호출 프로파일러, 특정 함수는 JIT 컴파일 되었지만 사용 되지는 않습니다 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="fda34-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
-   <span data-ttu-id="fda34-114">프로파일러는 비동기 원격 서비스 이벤트에 대 한 정확한 알림을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fda34-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fda34-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fda34-115">Requirements</span></span>  
 <span data-ttu-id="fda34-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fda34-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fda34-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fda34-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fda34-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fda34-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fda34-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fda34-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fda34-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="fda34-120">See also</span></span>
- [<span data-ttu-id="fda34-121">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fda34-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
