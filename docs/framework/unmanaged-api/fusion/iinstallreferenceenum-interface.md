---
title: IInstallReferenceEnum 인터페이스
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum
helpviewer_keywords:
- IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2aed89008dd2fa86b38f243c8e7cca1bdda901e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497776"
---
# <a name="iinstallreferenceenum-interface"></a>IInstallReferenceEnum 인터페이스
참조 된 어셈블리가 전역 어셈블리 캐시에 설치에 대 한 열거자를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetNextInstallReferenceItem 메서드](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|다음에 대 한 포인터를 가져옵니다 `IInstallReferenceItem` 이 포함 된 `IInstallReferenceEnum`합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Fusion.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [IInstallReferenceItem 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
