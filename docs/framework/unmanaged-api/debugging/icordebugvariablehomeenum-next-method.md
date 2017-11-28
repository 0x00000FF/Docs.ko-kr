---
title: "ICorDebugVariableHomeEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHomeEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 480317a4ec0515411f1ca8156a5bc4d06aa3f38a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehomeenumnext-method"></a>ICorDebugVariableHomeEnum::Next 메서드
지정된 된 수의 가져옵니다 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 로컬 변수 및 인수는 함수에 대 한 정보가 포함 된 인스턴스.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 검색할 개체 수입니다.  
  
 `homes`  
 각각 가리키는 포인터의 배열은 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 지역 변수 또는 함수 '의 인수에 대 한 정보를 제공 하는 개체입니다.  
  
 `pceltFetched`  
 [out] 개체에 실제로 반환 된 인스턴스 수를 지정 합니다.  
  
## <a name="return-value"></a>반환 값  
 메서드는 다음 값을 반환 합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|메서드가 완료되었습니다.|  
|`S_FALSE`|실제 인스턴스 수 검색에 반영 된 대로 `pceltFetched`, 요청 된 인스턴스의 수보다 적습니다.|  
  
## <a name="remarks"></a>설명  
 [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) 메서드 검색 최대 `celt` 열거자의 현재 위치부터 시작 하는 개체입니다. 메서드가 반환 될 때 `pceltFetched` 검색 된 개체의 실제 수를 포함 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugVariableHomeEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 [ICorDebugVariableHome 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
