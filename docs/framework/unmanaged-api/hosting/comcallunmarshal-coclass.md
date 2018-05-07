---
title: ComCallUnmarshal Coclass
ms.date: 03/30/2017
api_name:
- ComCallUnmarshal Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ComCallUnmarshal
helpviewer_keywords:
- ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7884d53630ca13a30d7b4efd55d46684a9dd7d30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="comcallunmarshal-coclass"></a>ComCallUnmarshal Coclass
인터페이스 포인터의 마샬링을 관리 하기 위한 인터페이스를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a>인터페이스  
  
|인터페이스|설명|  
|---------------|-----------------|  
|`IMarshal`|초기화, 만들고 관리 하기 위한 클라이언트 프로세스에서 프록시 메서드를 제공 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.idl  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 Coclass](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
