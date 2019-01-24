---
title: IDebuggerThreadControl::StartBlockingForDebugger 메서드
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 746b61a303869ff03d41cd6005ca0f5635ac0fd5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521723"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a>IDebuggerThreadControl::StartBlockingForDebugger 메서드
디버깅 서비스 시작 모든 스레드를 차단 하려는 호스트에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwUnused`  
 [in] 사용 하도록 예약 합니다.  
  
## <a name="remarks"></a>설명  
 `StartBlockingForDebugger` 런타임 스레드에서 메서드를 호출할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [IDebuggerThreadControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
