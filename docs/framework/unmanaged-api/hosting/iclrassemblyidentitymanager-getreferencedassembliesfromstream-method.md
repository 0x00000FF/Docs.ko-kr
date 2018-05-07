---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a5020b387abcdcdc0047de90eb588157eaec08c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a>ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream 메서드
에 대 한 포인터를 가져옵니다는 [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) 에 지정된 된 스트림에 있는 어셈블리에서 참조 하는 어셈블리에 대 한 어셈블리 id 데이터를 포함 하는 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pStream`  
 [in] 에 대 한 인터페이스 포인터는 `IStream` 평가할 어셈블리가 포함 된 합니다.  
  
 `dwFlags`  
 [in] 다음 버전의 확장을 위해 제공. CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT은 공용 언어 런타임 (CLR)의 현재 버전에서는 지원 되는 유일한 값입니다.  
  
 `pExcludeAssembliesList`  
 [in] 에 대 한 포인터는 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 에서 제외할 어셈블리에 대 한 어셈블리 id 데이터를 포함 하는 개체 `ppReferenceEnum`합니다.  
  
 `ppReferenceEnum`  
 [out] 주소에 대 한 포인터는 `ICLRReferenceAssemblyEnum` 에 있는 어셈블리에서 참조 하는 어셈블리에 대 한 어셈블리 id 데이터를 포함 하는 개체 `pStream`, 어셈블리를 제외 하 고 `pExcludeAssembliesList`합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 호출자에 게 반환된 된 목록에서 어셈블리 참조의 집합을 제외 하도록 선택할 수 있습니다. 이 집합 정의한 `pExcludeAssembliesList`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRAssemblyIdentityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [ICLRAssemblyReferenceList 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [ICLRReferenceAssemblyEnum 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
