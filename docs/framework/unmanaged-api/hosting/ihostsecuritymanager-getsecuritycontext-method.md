---
title: IHostSecurityManager::GetSecurityContext 메서드
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.GetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e11b447ebd03746730a86dbbcda31edd4196f13b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644952"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a>IHostSecurityManager::GetSecurityContext 메서드
요청 된 가져옵니다 [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) 호스트에서 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `eContextType`  
 [in] 중 하나는 [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) 유형을 반환 하는 보안 컨텍스트를 나타내는 값입니다.  
  
 `ppSecurityContext`  
 [out] 에 대 한 인터페이스 포인터의 주소를 `IHostSecurityContext` 의 `eContextType`합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`GetSecurityContext` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다. 메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 호스트는 CLR과 사용자 코드에서 스레드 토큰에 대 한 모든 코드 액세스를 제어할 수 있습니다. 전체 보안을 보장할 수도 있습니다 비동기 작업이 나 제한 된 코드 액세스를 사용 하 여 코드 포인트 컨텍스트 정보가 전달 됩니다. `IHostSecurityContext` CLR에 불투명이 보안 컨텍스트 정보를 캡슐화 합니다. CLR이이 정보를 캡처하고 스레드 풀 작업자 항목 디스패치, 종료자 실행 및 모듈 및 클래스 생성으로 이동 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [EContextType 열거형](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [IHostSecurityContext 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [IHostSecurityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
