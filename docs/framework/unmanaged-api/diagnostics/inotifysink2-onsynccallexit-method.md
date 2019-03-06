---
title: INotifySink2::OnSyncCallExit 메서드
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallExit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallExit
helpviewer_keywords:
- INotifySink2::OnSyncCallExit method [.NET Framework debugging]
- OnSyncCallExit method [.NET Framework debugging]
ms.assetid: d9d7600e-a8f5-443a-96de-67d26e130f2d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8124af428d68606382e4449db3f68b0b61eb432c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500267"
---
# <a name="inotifysink2onsynccallexit-method"></a>INotifySink2::OnSyncCallExit 메서드
호출을 종료할 때 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `in_CallID`  
 [in] 종료 된 호출의 ID입니다. 참조 [CALL_ID 구조체](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)합니다.  
  
 `out_ppBuffer`  
 [out] 버퍼를 호출 합니다.  
  
 `out_pBufferSize`  
 [out] 호출 버퍼 바이트의 크기입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>참고자료
- [INotifySink2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [INotifySource2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [INotifyConnection2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
