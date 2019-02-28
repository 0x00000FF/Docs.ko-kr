---
title: ICorDebugCode 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ca47eb5508907297a78dba1ab2b0a6d2b8ece0d
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976930"
---
# <a name="icordebugcode-interface"></a>ICorDebugCode 인터페이스

MSIL(Microsoft Intermediate Language) 코드나 네이티브 코드의 세그먼트를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateBreakpoint 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|지정된 된 오프셋에서 중단점을 만듭니다.|  
|[GetAddress 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|코드 세그먼트의 상대 가상 주소 (RVA)을 가져옵니다이 `ICorDebugCode` 나타냅니다.|  
|[GetCode 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|디스어셈블리에 대 한 형식이 지정된 된 함수에 대 한 모든 코드를 가져옵니다. 이 메서드는 더 이상 사용 되지 않습니다. 사용 하 여 [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) 대신 합니다.|  
|[GetEnCRemapSequencePoints 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|구현되지 않았습니다.|  
|[GetFunction 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|와 연결 된 "ICorDebugFunction" 가져옵니다 `ICorDebugCode`합니다.|  
|[GetILToNativeMapping 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|MSIL 오프셋에서 네이티브 오프셋 간의 매핑을 나타내는 "COR_DEBUG_IL_TO_NATIVE_MAP" 인스턴스의 배열을 가져옵니다.|  
|[GetSize 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|크기 (바이트)가 표시 되는 이진 코드의 가져옵니다 `ICorDebugCode`합니다.|  
|[GetVersionNumber 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|코드의 버전을 식별 하는 1부터 번호를 가져옵니다이 `ICorDebugCode` 나타냅니다.|  
|[IsIL 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|나타내는 값을 가져옵니다 여부를이 `ICorDebugCode` MSIL에서 컴파일됩니다.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugCode` MSIL 또는 네이티브 코드를 나타낼 수 있습니다. MSIL 코드를 나타내는 "ICorDebugFunction" 개체는 0 이나 1 있습니다 `ICorDebugCode` 연결 된 개체입니다. 네이티브 코드를 나타내는 "ICorDebugFunction" 개체 개수에 관계 없이 있습니다 `ICorDebugCode` 연결 된 개체입니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorDebugCode3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
