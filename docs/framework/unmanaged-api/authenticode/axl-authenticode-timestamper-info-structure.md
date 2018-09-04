---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7f4fff4f2c2b3dd04625f4cf50b8b19a0ef6f39
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525083"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a>AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조
Authenticode 타임스탬퍼 정보를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`cbSize`|이 구조체의 크기입니다.|  
|`dwError`|오류 코드입니다.|  
|`algHash`|해시 알고리즘입니다.|  
|`ftTimestamp`|타임스탬프의 시간입니다.|  
|`pChainContext`|타임스탬퍼의 체인 컨텍스트입니다.  참조 된 [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) 구조입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
