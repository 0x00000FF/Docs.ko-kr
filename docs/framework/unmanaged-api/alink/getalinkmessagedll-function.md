---
title: GetALinkMessageDll 함수
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 632f19e0ead57d5508265fece578bb22f18ba54a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722727"
---
# <a name="getalinkmessagedll-function"></a>GetALinkMessageDll 함수
페이지를 찾아서 메시지 DLL을 로드 합니다. 메시지 DLL 찾거나 로드할 수 없습니다 경우 0을 반환 합니다. 메시지 DLL 이름이 되는 언어 ID, 하위 디렉터리 또는 현재 디렉터리에 있어야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** alink.h  
  
 **라이브러리**: alink.dll  
  
## <a name="see-also"></a>참고자료
- [Al.exe(어셈블리 링커)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
