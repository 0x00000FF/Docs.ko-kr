---
title: "ICorDebugChain::GetCallee 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetCallee
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ed2bf8d8e91799fd0b01012d5d6e212d26a526be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetcallee-method"></a>ICorDebugChain::GetCallee 메서드
이 체인에 의해 호출 된 체인을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppChain`  
 [out] 호출된 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다. 이 체인은 현재 실행 중인 경우 (즉,이 체인 반환할 호출된 체인에 대 한 기다리고 있지 않으면), `ppChain` null이 됩니다.  
  
## <a name="remarks"></a>설명  
 이 체인 호출된 체인이 실행을 다시 시작 하기 전에 반환할 되기를 기다립니다. 마샬링된 크로스 스레드 호출의 경우 다른 스레드에서 호출된 체인이 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
