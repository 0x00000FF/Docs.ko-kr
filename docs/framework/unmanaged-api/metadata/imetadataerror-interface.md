---
title: IMetaDataError 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError
helpviewer_keywords:
- IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 37f1f6055ec8fa68fe804780d2893d20c978e6bd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188632"
---
# <a name="imetadataerror-interface"></a>IMetaDataError 인터페이스
메타 데이터를 병합 하는 동안 오류를 보고 하는 콜백 메커니즘을 제공 합니다.  
  
> [!NOTE]
>  `IMetaDataError` 클라이언트에서 인터페이스를 구현 해야 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[OnError 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|메타 데이터를 병합 하는 동안 발생 하는 오류에 대 한 알림을 제공 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [메타데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
