---
title: "ICorDebugManagedCallback2::FunctionRemapComplete 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.FunctionRemapComplete
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cee712c2ff8acf56049ca9e288fad21e4608da3f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a>ICorDebugManagedCallback2::FunctionRemapComplete 메서드
편집 된 함수의 새 버전으로 코드 실행이 전환 디버거에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pAppDomain`  
 [in] 편집 된 함수를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.  
  
 `pThread`  
 [in] 다시 매핑 중단점 만났습니다 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.  
  
 `pFunction`  
 [in] 현재 스레드에서 실행 하는 함수의 버전을 나타내는 ICorDebugFunction 개체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 콜백은 스텝 이미 존재 하는 다시 만들 수 있는 디버거를 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugManagedCallback2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [ICorDebugManagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
