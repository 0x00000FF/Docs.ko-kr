---
title: ICLRRuntimeHost::ExecuteInAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86348c35a023e22d10c4ad2e08f5cb1104b895a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165497"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a>ICLRRuntimeHost::ExecuteInAppDomain 메서드
지정 된 <xref:System.AppDomain> 지정 된 관리 되는 코드를 실행 하는 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `AppDomainId`  
 [in] 숫자 ID를 <xref:System.AppDomain> 지정 된 메서드를 실행 하는 합니다.  
  
 `pCallback`  
 [in] 지정 된 내에서 실행 하는 함수에 대 한 포인터 <xref:System.AppDomain>합니다.  
  
 `cookie`  
 [in] 불투명 호출자에 게 할당 된 메모리에 대 한 포인터입니다. 이 매개 변수는 CLR (공용 언어 런타임)에서 도메인 콜백에 전달 됩니다. 런타임에서 관리 되는 힙 메모리; 아닙니다. 할당 및 수명이 메모리는 호출자에 의해 제어 됩니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`ExecuteInAppDomain` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다. 메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 `ExecuteInAppDomain` 호스트가 제어할 수 있도록 관리 되는 <xref:System.AppDomain> 에서 지정된 된 관리 되는 메서드를 실행 해야 합니다. 값에 해당 하는 응용 프로그램 도메인 식별자의 값을 가져올 수는 <xref:System.AppDomain.Id%2A> 속성을 호출 하 여 [GetCurrentAppDomainId 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICLRRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
