---
title: ICorProfilerInfo5::GetEventMask2 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
ms.openlocfilehash: f3943eef969f777b40dc51c4900b190561f14887
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868397"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a>ICorProfilerInfo5::GetEventMask2 메서드
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 프로파일러가 CLR(공용 언어 런타임)에서 알림을 받으려는 현재 이벤트 범주를 가져옵니다.  [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) 메서드에서 제공 하지 않는 기능을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pdwEventsLow`  
 [out] 이벤트 범주를 지정하는 4바이트 값에 대한 포인터입니다. 각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다. 비트는 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형에 설명 되어 있습니다.  
  
 `pdwEventsHigh`  
 [out] 이벤트 범주를 지정하는 4바이트 값에 대한 포인터입니다.  각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다. 비트는 [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) 열거형에 설명 되어 있습니다.  
  
## <a name="remarks"></a>주의  
 `GetEventMask2` 메서드를 사용하여 프로파일러가 구독한 콜백을 확인합니다. 일반적으로 `pdwEventsLow` 논리 OR를 수행 하 고 `pdwEventsHigh` 값 및 설정 하려는 새 비트를 수행한 다음 [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) 메서드를 호출 합니다.  
  
 [Geteventmask](icorprofilerinfo-geteventmask-method.md) 메서드 대신이 방법을 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo5 인터페이스](icorprofilerinfo5-interface.md)
- [SetEventMask2 메서드](icorprofilerinfo5-seteventmask2-method.md)
