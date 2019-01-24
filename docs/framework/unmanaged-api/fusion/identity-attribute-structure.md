---
title: IDENTITY_ATTRIBUTE 구조체
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e26a90b6725d53774053293c04842b761da6ab12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717677"
---
# <a name="identityattribute-structure"></a>IDENTITY_ATTRIBUTE 구조체
에 대 한 메타 데이터 특성 정보를 [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) 인스턴스.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`pszNamespace`|네임 스페이스를 포함 하는 null로 끝나는 문자열에 대 한 포인터에서 특성이입니다.|  
|`pszName`|특성의 이름이 포함 된 null로 끝나는 문자열에 대 한 포인터입니다.|  
|`pszValue`|특성의 값이 포함 된 null로 끝나는 문자열에 대 한 포인터입니다.|  
  
## <a name="remarks"></a>설명  
 `IDENTITY_ATTRIBUTE` 구조 null로 끝나는 문자열에 대 한 세 포인터를 포함 합니다. 이러한 세 가지 문자열 특성 하나를 설명합니다.  
  
 인스턴스를 `IDENTITY_ATTRIBUTE` 구조체의 인스턴스를 사용 하 여 연결 된를 [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) 구조입니다. 합니다 `IDENTITY_ATTRIBUTE` 실제 문자열 및 해당 구조에 포함 되어 있습니다 `IDENTITY_ATTRIBUTE_BLOB` 구조에 나열 된 세 개의 문자열에 오프셋을 나열 합니다 `IDENTITY_ATTRIBUTE` 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Isolation.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [IDefinitionIdentity 인터페이스](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
- [IDENTITY_ATTRIBUTE_BLOB 구조체](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)
- [Fusion 구조체](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
