---
title: "IHostThreadPoolManager::GetMinThreads 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 393400c7a5d9d4d99431cbea4a3c3c82064218f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a>IHostThreadPoolManager::GetMinThreads 메서드
요청에 대비 하 여에서 스레드 풀에서 호스트를 유지 관리 하는 유휴 상태 스레드의 최소 개수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `MinThreads`  
 [out] 호스트에서 현재 유지 하는 유휴 작업자 스레드의 최소 수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`GetMinThreads`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|E_NOTIMPL|호스트의 구현을 제공 하지 않는 `GetMinThreads`합니다.|  
  
## <a name="remarks"></a>설명  
 호스트의 구현을 제공 하지 않아도 됩니다 `GetMinThreads`합니다. 이 경우 E_NOTIMPL HRESULT 값을 반환 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.ThreadPool.GetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [GetMaxThreads 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)  
 [SetMinThreads 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)  
 [IHostThreadPoolManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
