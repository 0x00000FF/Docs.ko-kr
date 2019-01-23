---
title: ICorDebugClass2 Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb70016560f453caf7a7a3eed3e1aa6b5fc9f0ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557368"
---
# <a name="icordebugclass2-interface1"></a>ICorDebugClass2 Interface1
제네릭 클래스나 <xref:System.Type> 형식의 메서드 매개 변수를 사용하는 클래스를 나타냅니다. 이 인터페이스를 확장 [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetParameterizedType 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|이 클래스에 대 한 형식 선언을 가져옵니다.|  
|[SetJMCStatus 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|이 클래스의 각 메서드의 경우 메서드는 사용자가 정의한 코드 있는지 여부를 나타내는 값을 설정 합니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICorDebugClass Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
