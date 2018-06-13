---
title: ICorDebugGenericValue Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0081f020da673023e2c35f9599e9682215e2c9d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415066"
---
# <a name="icordebuggenericvalue-interface1"></a>ICorDebugGenericValue Interface1
모든 값에 적용 되는 "ICorDebugValue"의 하위 클래스입니다. 이 인터페이스에서는 값의 Get 및 Set 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetValue 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|지정된 된 버퍼에 값을 복사합니다.|  
|[SetValue 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|지정된 된 버퍼에서 새 값을 복사합니다.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugGenericValue` 비 원격 이기 때문에 하위 인터페이스입니다.  
  
 참조 형식에 대 한 값이 참조의 내용을 보다는 참조 합니다.  
  
 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
    
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
