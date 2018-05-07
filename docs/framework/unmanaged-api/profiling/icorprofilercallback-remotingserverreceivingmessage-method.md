---
title: ICorProfilerCallback::RemotingServerReceivingMessage 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1874b5bea465eb31bcaad2d912b90d35cfc711b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a>ICorProfilerCallback::RemotingServerReceivingMessage 메서드
프로세스에서 원격 메서드 호출 또는 정품 인증 요청을 받았음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pCookie`  
 [in] 에 제공 된 값과 일치 하는 값 [icorprofilercallback:: Remotingclientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) 이러한 조건:  
  
-   원격 GUID 쿠키가 활성화 되어 있습니다.  
  
-   채널에서 메시지를 전송 하는 데 성공 합니다.  
  
-   GUID 쿠키는 클라이언트 프로세스에서 활성 상태입니다.  
  
 이렇게 하면 원격 호출 및 논리 호출 스택의 만드는 쉽게 쌍 있습니다.  
  
 `fIsAsync`  
 [in] 값을 `true` 는 호출이 고, 그렇지 않으면 비동기 경우 `false`합니다.  
  
## <a name="remarks"></a>설명  
 메시지 요청을 비동기 경우 임의의 스레드에서 요청을 처리할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
