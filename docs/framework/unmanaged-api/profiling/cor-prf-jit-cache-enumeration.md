---
title: COR_PRF_JIT_CACHE 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_JIT_CACHE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_JIT_CACHE
helpviewer_keywords:
- COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6aaa334c83aff18886c0c2db4462d6baaa4cd70f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687416"
---
# <a name="corprfjitcache-enumeration"></a>COR_PRF_JIT_CACHE 열거형
캐시된 함수 검색의 결과를 나타냅니다.  
  
> [!NOTE]
>  `COR_PRF_CACHED_FUNCTION_FOUND` 값이 0 이면 높으므로 `COR_PRF_JIT_CACHE` 를 부울 대신 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|검색 함수를 찾을 수 있습니다.|  
|`COR_PRF_FUNCTION_NOT_FOUND`|검색 함수를 찾을 수 없습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [프로파일링 열거형](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
