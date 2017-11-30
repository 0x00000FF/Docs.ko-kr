---
title: "IMetaDataEmit::SetHandler 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetHandler
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d4a56db43f932a155b4251f019e39dc5640eb014
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsethandler-method"></a>IMetaDataEmit::SetHandler 메서드
지정 된에서 참조 하는 방법을 설정 `IUnknown` 토큰 다시 매핑에 대 한 알림 콜백 포인터입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pUnk`  
 [in] 등록 하는 처리기입니다.  
  
## <a name="remarks"></a>설명  
 메타 데이터 엔진에서 제공 되는 메서드를 사용 하 여 알림을 보내는 `SetHandler`, 최적화 된 방식에서 레코드를 생성 하지 않는 저장 된 레코드를 최적화 하 고 컴파일러에 있습니다.  
  
 콜백 메서드를 통해 제공 되지 않은 경우 `SetHandler`, 없습니다 최적화가 수행에 저장 여러 가져오기 제외 하 고 범위 병합 된를 사용 하 여 `IMapToken` 각 범위에 대 한 병합 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
