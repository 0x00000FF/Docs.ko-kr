---
title: ICorDebugThread2 Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c348cf28a6330523d1a490c136a3214e37d13f4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423051"
---
# <a name="icordebugthread2-interface1"></a>ICorDebugThread2 Interface1
ICorDebugThread 인터페이스를 논리적으로 확장으로 사용 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetActiveFunctions 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|COR_ACTIVE_FUNCTION 인스턴스 스레드 프레임에서 현재 함수에 대 한 데이터가 포함 된 배열을 가져옵니다.|  
|[GetConnectionID 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|이 대 한 연결 식별자를 가져옵니다 `ICorDebugThread2`합니다.|  
|[GetTaskID 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|이 대 한 작업 id를 가져옵니다 `ICorDebugThread2`합니다.|  
|[GetVolatileOSThreadID 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|이 운영 체제 스레드 식별자를 가져옵니다 `ICorDebugThread2`합니다.|  
|[InterceptCurrentException 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|디버거에서를 스레드에서 현재 예외를 가로챌 수 있습니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
