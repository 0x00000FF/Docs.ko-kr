---
title: ICorDebugHeapSegmentEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c3b99936315c949fa9920c7d17dc01d9bcc53b2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485046"
---
# <a name="icordebugheapsegmentenumnext-method"></a>ICorDebugHeapSegmentEnum::Next 메서드
지정 된 개수를 가져옵니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 관리 되는 힙의 메모리 영역에 대 한 정보를 포함 하는 인스턴스.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 celt  
 [in] 검색할 세그먼트 수입니다.  
  
 세그먼트  
 [out] 각각 가리키는 포인터 배열을 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 관리 되는 힙의 메모리 영역에 대 한 정보를 제공 하는 개체입니다.  
  
 pceltFetched  
 [out] 개수에 대 한 포인터 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 개체에 실제로 반환 된 `segments`합니다. 
  `celt`가 1이면 이 값은 `null`일 수 있습니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICorDebugHeapSegmentEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
