---
title: CreateALink 함수
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b494b8b776f4cb0eb534233c5a03ab2d34a698ef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115624"
---
# <a name="createalink-function"></a>CreateALink 함수
어셈블리 링커의 인스턴스를 만들고 지정된 된 인터페이스에 대 한 포인터를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`riid`|어셈블리 링커 인터페이스 중 하나의 물리적 이름입니다.|  
|`ppInterface`|성공적으로 완료에 대 한 포인터를 포함 하는 위치는 `riid` 인터페이스입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **라이브러리**: alink.dll  
  
## <a name="see-also"></a>참고자료

- [Al.exe(어셈블리 링커)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
