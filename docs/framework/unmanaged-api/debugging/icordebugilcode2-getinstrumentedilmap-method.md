---
title: "ICorDebugILCode2::GetInstrumentedILMap 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILCode2.GetInstrumentedILMap
api_location: mscordbi.dll
api_type: COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9b740f378b4fd15fe6bf4a9832348869878e2a4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a>ICorDebugILCode2::GetInstrumentedILMap 메서드
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 이 인스턴스에 대해 프로파일러가 계측한 IL(중간 언어) 오프셋에서 원래 메서드 IL 오프셋으로의 맵을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 cMap  
 [in] `map` 배열의 저장소 용량입니다. 자세한 내용은 설명 부분을 참조하십시오.  
  
 pcMap  
 [out] 맵 배열에 기록 COR_IL_MAP 값의 수입니다.  
  
 map  
 [out] 원래 메서드 IL로 매핑에 프로파일러가 계측 한 IL에서 정보를 제공 하는 COR_IL_MAP 값의 배열입니다.  
  
## <a name="remarks"></a>설명  
 프로파일러를 호출 하 여 매핑을 설정 하는 경우는 [icorprofilerinfo:: Setilinstrumentedcodemap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) 메서드를 디버거 매핑을 검색 하 고 스택에 대 한 오프셋을 IL을 계산할 때 내부적으로 매핑을 사용 하도록이 메서드를 호출할 수 추적 및 변수 수명입니다.  
  
 경우 `cMap` 0 및 `pcMap` 이 아닌**null**, `pcMap` 사용 가능한 COR_IL_MAP 값의 수로 설정 합니다. `cMap`는 값이 0이 아닌 경우 `map` 배열의 저장소 용량을 나타냅니다. 메서드가 반환 될 때 `map` 포함 `cMap` 항목 및 `pcMap` 에 실제로 기록 된 COR_IL_MAP 값의 수로 설정 되는 `map` 배열입니다.  
  
 IL이 계측되지 않았거나 프로파일러가 매핑을 제공하지 않은 경우 이 메서드는 `S_OK`를 반환하고 `pcMap`을 0으로 설정합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Icorprofilerinfo:: Setilinstrumentedcodemap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)  
 [ICorDebugILCode2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
