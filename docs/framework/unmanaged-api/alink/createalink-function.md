---
title: "CreateALink 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateALink
api_location: alink.dll
api_type: DLLExport
f1_keywords: CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a102e9601f751ee8c7e325293e83467b1314ff41
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
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
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`riid`|어셈블리 링커 인터페이스 중 하나의 물리적 이름입니다.|  
|`ppInterface`|성공적으로 완료에 대 한 포인터를 포함 하는 위치는 `riid` 인터페이스입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **라이브러리**: alink.dll  
  
## <a name="see-also"></a>참고 항목  
 [Al.exe(어셈블리 링커)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
