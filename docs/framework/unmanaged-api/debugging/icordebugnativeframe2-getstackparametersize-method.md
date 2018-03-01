---
title: "ICorDebugNativeFrame2::GetStackParameterSize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fa7e67c252f2ece16c072e22d0333e085fbc4f65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a>ICorDebugNativeFrame2::GetStackParameterSize 메서드
X86 운영 체제에 대 한 스택에 매개 변수의 누적 크기를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pSize`  
 [out] 매개 변수는 스택에 누적 크기에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|스택 크기를 성공적으로 반환 되었습니다.|  
|S_FALSE|`GetStackParameterSize`비 x86 플랫폼에서 호출 되었습니다.|  
|E_FAIL|`The size of the parameters could not be returned`.|  
|E_INVALIDARG|`pSize``null`합니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>설명  
 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 메서드는 스택에서 푸시됩니다 매개 변수에 대 한 스택 포인터를 조정 하지 마십시오. 대신, 반환 값을 사용할 수 있습니다 `GetStackParameterSize` 매개 변수를 조정 하는 네이티브 언에 대 한 스택 포인터를 조정 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugNativeFrame2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
