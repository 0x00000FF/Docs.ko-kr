---
title: ICorDebugProcess::IsOSSuspended 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b65a621541f2b4a800f6b3708a6b257374c5866
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocessisossuspended-method"></a>ICorDebugProcess::IsOSSuspended 메서드
이 프로세스를 중지 하는 디버거 결과로 지정 된 스레드가 일시 중단 된 있는지 여부를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `threadID`  
 [in] 해당 스레드의 ID입니다.  
  
 `pbSuspended`  
 [out] 부울 값이에 대 한 포인터 `true` 고, 그렇지 않으면 일시 중단 된 지정된 된 스레드가 되었으면 *`pbSuspended` 은 `false`합니다.  
  
## <a name="remarks"></a>설명  
 지정 된 스레드의 Win32 지정된 된 스레드가으로 일시 중단 된 결과로 디버거가이 프로세스를 중지 하는 경우 일시 중단 횟수가 1 씩 증가 합니다. 디버거 사용자 인터페이스 (UI) 열 수는 운영 체제를 표시 하는 경우 계정에이 정보를 사용자에 게 스레드의 개수를 일시 중단 (OS).  
  
 `IsOSSuspended` 메서드가 관리 되지 않는 디버깅의 경우에만 적합 합니다. 관리 되는 디버깅 하는 동안 스레드는 협조적으로 일시 중단 된 것이 아니라 OS 일시 중단 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
