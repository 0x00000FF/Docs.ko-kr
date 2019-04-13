---
title: IAssemblyName 인터페이스
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d8d59ef282818dd9852d0ff8d2ec2abd40986d0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097137"
---
# <a name="iassemblyname-interface"></a>IAssemblyName 인터페이스
설명 하 고 어셈블리의 고유 id를 사용 하 여 작업에 대 한 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Clone 메서드](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|이 항목의 단순 복사본을 만듭니다 `IAssemblyName` 개체입니다.|  
|[Finalize 메서드](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|이 허용 `IAssemblyName` 리소스를 해제 하 고 소멸자가 호출 되기 전에 다른 정리 작업을 수행 하는 개체입니다.|  
|[GetDisplayName 메서드](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|이 참조 되는 어셈블리의 알기 쉬운 이름을 가져옵니다 `IAssemblyName` 개체입니다.|  
|[GetName 메서드](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|이 참조 되는 어셈블리의 간단 하 고 암호화 되지 않은 이름을 가져옵니다 `IAssemblyName` 개체입니다.|  
|[GetProperty 메서드](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|지정 된 참조 하는 속성에 대 한 포인터를 가져옵니다 `PropertyId`합니다.|  
|[GetVersion 메서드](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|이 참조 되는 어셈블리에 대 한 버전 정보를 가져옵니다 `IAssemblyName` 개체입니다.|  
|[IsEqual 메서드](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|지정 된 결정 `IAssemblyName` 개체와 같으면이 `IAssemblyName`지정된 된 비교 플래그에 따라 합니다.|  
|[SetProperty 메서드](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|지정 된 참조 하는 속성의 값을 설정 `PropertyId`합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Fusion.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [IAssemblyEnum 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
