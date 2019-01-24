---
title: ICorProfilerCallback::RemotingClientSendingMessage 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientSendingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 424e0323c018367560d4cf3542e9e8668575a03f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675203"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="14494-102">ICorProfilerCallback::RemotingClientSendingMessage 메서드</span><span class="sxs-lookup"><span data-stu-id="14494-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="14494-103">클라이언트가 서버 요청을 보내는 지 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="14494-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14494-104">구문</span><span class="sxs-lookup"><span data-stu-id="14494-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="14494-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="14494-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="14494-106">[in] 에 제공 된 값을 사용 하 여 해당 하는 값 [icorprofilercallback:: Remotingserverreceivingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) 이러한 조건에서:</span><span class="sxs-lookup"><span data-stu-id="14494-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="14494-107">원격 GUID 쿠키 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14494-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="14494-108">채널은 메시지 전송에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14494-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="14494-109">GUID 쿠키는 서버 쪽 프로세스에서 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="14494-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="14494-110">따라서 쉽게 페어링 원격 호출 및 논리 호출 스택 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="14494-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="14494-111">[in] 값을 `true` 호출이 고, 그렇지 않으면 비동기 이면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="14494-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14494-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="14494-112">Requirements</span></span>  
 <span data-ttu-id="14494-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="14494-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14494-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="14494-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="14494-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14494-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14494-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14494-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14494-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="14494-117">See also</span></span>
- [<span data-ttu-id="14494-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="14494-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
