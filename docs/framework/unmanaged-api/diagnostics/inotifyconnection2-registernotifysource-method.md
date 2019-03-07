---
title: INotifyConnection2::RegisterNotifySource 메서드
ms.date: 03/30/2017
api_name:
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c08cac6fd6b467fe365989cb4d6780325bdaa90
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501619"
---
# <a name="inotifyconnection2registernotifysource-method"></a>INotifyConnection2::RegisterNotifySource 메서드
지정 된 알림 소스를 설치합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `in_pNotifySource`  
 [in] 알림 소스로 사용할 개체를 지정 합니다.  
  
 `out_ppNotifySink`  
 [out] 알림 싱크로 사용할 개체를 받습니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>참고자료
- [INotifyConnection2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [INotifySource2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [INotifySink2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [UnregisterNotifySource 메서드](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-unregisternotifysource-method.md)
