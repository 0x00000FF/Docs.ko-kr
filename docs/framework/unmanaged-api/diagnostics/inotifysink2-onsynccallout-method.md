---
title: INotifySink2::OnSyncCallOut 메서드
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a38c35f0acd47c9183c043e1c436413a309b138
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426077"
---
# <a name="inotifysink2onsynccallout-method"></a>INotifySink2::OnSyncCallOut 메서드
되 면 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `in_CallID`  
 [in] 이 호출의 ID입니다. 참조 [CALL_ID 구조체](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)합니다.  
  
 `out_ppBuffer`  
 [out] 버퍼를 호출 합니다.  
  
 `out_pBufferSize`  
 [out] 호출 버퍼의 바이트의 크기입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>참고 항목  
 [INotifySink2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [INotifySource2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [INotifyConnection2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
