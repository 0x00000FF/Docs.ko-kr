---
title: CLR_DEBUGGING_VERSION 구조체
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fecd5af43f4b984a4ab626e9832b3318715c0516
ms.sourcegitcommit: deb9225a55485a5a6e6c7914deb30ccfceb69d3f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2019
ms.locfileid: "54058362"
---
# <a name="clrdebuggingversion-structure"></a>CLR_DEBUGGING_VERSION 구조체
디버깅용 CLR(공용 언어 런타임)의 제품 버전을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`wStructVersion`|구조 버전 번호|  
|`wMajor`|주 버전 번호입니다.|  
|`wMinor`|부 버전 번호입니다.|  
|`wBuild`|빌드 번호입니다.|  
|`wRevision`|수정 번호입니다.|  
  
## <a name="remarks"></a>설명  
 하지만 합니다 `CLR_DEBUGGING_VERSION` 구조체가 COR_VERSION 구조체와 동일, `CLR_DEBUGGING_VERSION` 구조 추가 구조 버전 필드를 제공 (`wStructVersion`). 현재이 필드를 0으로 설정 되어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
