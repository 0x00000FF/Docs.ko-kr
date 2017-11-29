---
title: "ICorPublishEnum 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishEnum
helpviewer_keywords: ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7034945824e439b42134f8ea3c13bfaf73dbb649
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishenum-interface"></a>ICorPublishEnum 인터페이스
한 프로세스 및 응용 프로그램 도메인에 대 한 정보를 게시에 사용 되는 열거자에 대 한 추상 기본 인터페이스로 사용 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Clone 메서드](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|이 파일의 복사본을 만듭니다 `ICorPublishEnum` 개체입니다.|  
|[GetCount 메서드](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|열거형에서 항목의 수를 가져옵니다.|  
|[Reset 메서드](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|열거형의 시작 부분으로 커서를 이동합니다.|  
|[Skip 메서드](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|열거형에 커서를 앞으로 항목의 지정한 수 만큼 이동 합니다.|  
  
## <a name="remarks"></a>설명  
 파생 된 다음 열거자 `ICorPublishEnum`:  
  
-   [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorPub.idl, CorPub.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [CorpubPublish Coclass](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
