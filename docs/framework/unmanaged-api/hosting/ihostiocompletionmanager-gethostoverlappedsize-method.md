---
title: IHostIoCompletionManager::GetHostOverlappedSize 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6713fdb822babf607752c1823a32dae43a7d567e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439607"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a>IHostIoCompletionManager::GetHostOverlappedSize 메서드
호스트에서 I/O 요청에 추가 하려는 사용자 지정 데이터의 크기를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcbSize`  
 [out] Win32의 크기와 공용 언어 런타임 (CLR)를 할당 해야 하는 바이트 수에 대 한 포인터 `OVERLAPPED` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`GetHostOverlappedSize` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 Windows 플랫폼 Api에 있는 모든 비동기 I/O 호출 걸릴 Win32 `OVERLAPPED` 파일 포인터 위치 등의 정보를 제공 하는 개체입니다. 상태를 유지 하기 위해 일반적으로 비동기 I/O 호출을 수행 하는 응용 프로그램 구조를 사용자 지정 데이터를 추가 합니다. `GetHostOverlappedSize` 및 [ihostiocompletionmanager:: Initializehostoverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) 등의 사용자 지정 데이터를 호스트에 대 한 기회를 제공 합니다.  
  
 CLR에서는 `GetHostOverlappedSize` 호스트에 추가 하려는 사용자 지정 데이터의 크기를 결정 하는 메서드는 `OVERLAPPED` 개체입니다.  
  
> [!NOTE]
>  `GetHostOverlappedSize` 한 번만 호출 됩니다. 호스트의 사용자 지정 데이터에는 모든 I/O 요청에 대해 동일한 크기 여야 합니다.  
  
> [!IMPORTANT]
>  크기는 `OVERLAPPED` 개체 자체의 값에 포함 되지 않은 `pcbSize`합니다.  
  
 에 대 한 자세한 내용은 `OVERLAPPED` 구조 Windows 플랫폼 설명서를 참조 하십시오.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.NativeOverlapped>  
 [ICLRIoCompletionManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [IHostIoCompletionManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
