---
title: CorDebugStateChange 열거형
ms.date: 03/30/2017
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f0f692b692628d50755ce813c66823f940dccb8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513787"
---
# <a name="cordebugstatechange-enumeration"></a>CorDebugStateChange 열거형
프로세스에 대한 변경 내용을 기반으로 삭제해야 하는 캐시된 데이터의 양을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorDebugStateChange  
{  
    PROCESS_RUNNING = 0x0000001,   
    FLUSH_ALL       = 0x0000002,   
} CorDebugStateChange;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`PROCESS_RUNNING`|프로세스가 정방향 실행을 통해 새로운 메모리 상태에 도달했습니다.|  
|`SET_CONTEXT_FLAG_UNWIND_FRAME`|프로세스의 메모리가 이전과 임의적으로 달라질 수 있습니다.|  
  
## <a name="remarks"></a>설명  
 멤버는 `CorDebugStateChange` 디버거를 호출 하는 경우 열거를 인수로 제공 되는 [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) 메서드  
  
> [!NOTE]
>  이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고자료
- [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
