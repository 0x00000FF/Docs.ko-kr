---
title: "ICLRDataTarget::GetMachineType 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetMachineType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetMachineType
helpviewer_keywords:
- ICLRDataTarget::GetMachineType method [.NET Framework debugging]
- GetMachineType method [.NET Framework debugging]
ms.assetid: 5f1f9c61-3e3b-48b2-b111-a4395f7623a7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 56fabfd2bb929e40c60903ad7b5e86e2b18d7d93
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetgetmachinetype-method"></a>ICLRDataTarget::GetMachineType 메서드
대상 프로세스를 사용 하는 명령 집합의 종류에 대 한 식별자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `machineType`  
 [out] 대상 프로세스는 명령 집합을 표시 하는 값에 대 한 포인터 사용 중입니다. 반환 된 `machineType` WinNT.h 헤더 파일에 정의 된 IMAGE_FILE_MACHINE 상수 중 하나입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** ClrData.idl, ClrData.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRDataTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
