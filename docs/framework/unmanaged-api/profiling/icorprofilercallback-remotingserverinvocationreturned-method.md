---
title: ICorProfilerCallback::RemotingServerInvocationReturned 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationReturned
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned method [.NET Framework profiling]
- RemotingServerInvocationReturned method [.NET Framework profiling]
ms.assetid: a4de6805-e159-4280-99e5-3390c86166d0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3a64941c35630e76e05ac982725c9eb3f5583d12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495996"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a>ICorProfilerCallback::RemotingServerInvocationReturned 메서드
프로세스에서 원격 메서드 호출 요청에 대 한 응답에서 메서드를 호출 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
