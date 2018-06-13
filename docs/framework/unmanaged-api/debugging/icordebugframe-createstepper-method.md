---
title: ICorDebugFrame::CreateStepper 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3662ed8a3fda5881b0e0929a830d19b0d805299f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411033"
---
# <a name="icordebugframecreatestepper-method"></a>ICorDebugFrame::CreateStepper 메서드
디버거에서이 ICorDebugFrame 기준으로 단계별 실행 작업을 수행할 수 있도록 스텝을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppStepper`  
 [out] 디버거는 현재 프레임을 기준으로 단계별 실행 작업을 수행할 수 있도록 ICorDebugStepper 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 프레임 활성 상태 이면 해당 단계가 완료 되기 전에 프레임으로 돌아가려면 스텝 퍼 개체 일반적으로 갖습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
