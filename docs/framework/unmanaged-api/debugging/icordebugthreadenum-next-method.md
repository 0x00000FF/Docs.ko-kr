---
title: "ICorDebugThreadEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThreadEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac9ff468f85248631ffd7f3a39a8827b1aef45b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadenumnext-method"></a>ICorDebugThreadEnum::Next 메서드
현재 위치부터 시작 하는 열거형에서 지정 된 ICorDebugThread 인스턴스 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 수가 `ICorDebugThread` 인스턴스를 검색할 수 있습니다.  
  
 `threads`  
 [out] 각각 가리키는 포인터의 배열은 `ICorDebugThread` 스레드를 나타내는 개체입니다.  
  
 `pceltFetched`  
 [out] 수에 대 한 포인터 `ICorDebugThread` 실제로 반환 된 인스턴스. 이 값은 null 일 수 있으면 `celt` 하나입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
