---
title: "ICorProfilerObjectEnum::GetCount 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum.GetCount
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum::GetCount
helpviewer_keywords:
- ICorProfilerObjectEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 166b0761-ed80-4ccd-9973-dc20e61bf8fa
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b7675749a132cffe284d73bab3dba91f6ff7a3fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerobjectenumgetcount-method"></a>ICorProfilerObjectEnum::GetCount 메서드
컬렉션에서 고정된 개체의 총 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcelt`  
 [out] 컬렉션에서 고정 된 개체 수에 대 한 포인터입니다.  
  
 이 메서드는.NET Framework 버전 3.5에서에서 0이 항상 반환 서비스 팩 1 (SP1) 및 이상 버전입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerObjectEnum 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
