---
title: "IMethodMalloc 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1941a46a60219d9dd56d162f89baf268f220c102
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imethodmalloc-interface"></a>IMethodMalloc 인터페이스
새 Microsoft MSIL (intermediate language) 함수 본문에 대 한 메모리를 할당 하는 방법을 제공 합니다.  
  
> [!NOTE]
>  `IMethodMalloc` 인터페이스는 간단한 메모리 할당자입니다. 해제 해야 하지만 메모리를 할당할 수 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Alloc 메서드](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|새 MSIL 함수 본문에 지정된 된 양의 메모리를 할당 하려고 시도 합니다.|  
  
## <a name="remarks"></a>설명  
 각 할당자는 특정 모듈 및 하면 한 함수 본문 양의 모듈의 기준 오프셋에서 이루어집니다. 모듈의 기준 이상의 메모리 할당자를 사용 하는 함수 본문에만 메모리를 할당 해야 소중한를 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
