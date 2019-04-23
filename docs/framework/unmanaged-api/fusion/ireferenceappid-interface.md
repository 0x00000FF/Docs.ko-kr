---
title: IReferenceAppId 인터페이스
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25733e459423500352595d6be0eee26ef75ca7e2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157198"
---
# <a name="ireferenceappid-interface"></a>IReferenceAppId 인터페이스
현재 범위에서 응용 프로그램에 대 한 고유 식별자에 대 한 참조를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|이 참조 응용 프로그램에 대 한 코드 식별자의 문자열 표현으로 포인터를 가져옵니다 `IReferenceAppId`합니다.|  
|`IReferenceAppId::put_CodeBase`|이 참조 응용 프로그램에 대 한 코드 식별자를 설정 `IReferenceAppId`합니다.|  
|`IReferenceAppId::EnumAppPath`|한 인터페이스 포인터를 가져옵니다는 `IEnumReferenceIdentity` 인스턴스를 포함 하는 `IReferenceIdentity` 의 멤버를 나타내는 인스턴스 `IReferenceAppId`합니다.|  
|`IReferenceAppId::get_SubscriptionId`|이 구독에 대 한 토큰 식별자의 문자열 표현으로 포인터를 가져옵니다 `IReferenceAppId`합니다.|  
|`IReferenceAppId::put_SubscriptionId`|이 구독에 대 한 토큰 식별자를 설정 하는 `IReferenceAppId` 지정 된 문자열 값입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Isolation.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [IEnumReferenceIdentity 인터페이스](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)
- [IReferenceIdentity 인터페이스](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
