---
title: "ICorProfilerCallback::COMClassicVTableCreated 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.COMClassicVTableCreated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::COMClassicVTableCreated
helpviewer_keywords:
- COMClassicVTableCreated method [.NET Framework profiling]
- ICorProfilerCallback::COMClassicVTableCreated method [.NET Framework profiling]
ms.assetid: 6e1834ab-c359-498a-b10b-984ae23cdda4
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 39fa655065c2af10750b1285ef047678874723ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a>ICorProfilerCallback::COMClassicVTableCreated 메서드
지정 된 IID 및 클래스에 대 한 COM interop vtable을 만들었는지 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `wrappedClasId`  
 [in] Vtable 생성 된 클래스의 ID입니다.  
  
 `implementedIID`  
 [in] 클래스에서 구현 된 인터페이스의 ID입니다. 이 값이 인터페이스는 내부 에서만 경우 NULL이 될 수 있습니다.  
  
 `pVTable`  
 [in] Vtable의 시작 부분에 대 한 포인터입니다.  
  
 `cSlots`  
 [in] Vtable에 있는 슬롯 수를 지정 합니다.  
  
## <a name="remarks"></a>설명  
 스택 가비지 수집을 허용 하는 상태가 아닐 수 있습니다 때문에이 메서드의 구현에서 프로파일러 차단 하지 않아야 하 고 따라서 선점형 가비지 수집을 사용할 수 없습니다. 이때 프로파일러가 차단 하는 경우 가비지 수집을 시도 하 고, 런타임이이 콜백이 반환 될 때까지 차단 됩니다.  
  
 이 메서드는 프로파일러 구현에는 관리 코드에 또는 관리 되는 메모리 할당에서 호출 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [COMClassicVTableDestroyed 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)
