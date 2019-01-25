---
title: ICorDebugCode::GetFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd544619f9e5fb85a0b08b91ead8231ea25743cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651231"
---
# <a name="icordebugcodegetfunction-method"></a>ICorDebugCode::GetFunction 메서드
"ICorDebugFunction을"이 "ICorDebugCode"를 사용 하 여 연결을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppFunction`  
 [out] 함수 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `ICorDebugCode` 및 `ICorDebugFunction` 한 일 관계를 유지 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

