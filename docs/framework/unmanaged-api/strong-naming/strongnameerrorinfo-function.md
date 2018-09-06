---
title: StrongNameErrorInfo 함수
ms.date: 03/30/2017
api_name:
- StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameErrorInfo
helpviewer_keywords:
- StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ad328d484ba01e22557d7d23d1cfa21813de9c8
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43860339"
---
# <a name="strongnameerrorinfo-function"></a>StrongNameErrorInfo 함수
강력한 이름 함수 중 하나에 의해 발생하는 마지막 오류 코드를 가져옵니다.  
  
 이 함수는 더 이상 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT StrongNameErrorInfo ();   
```  
  
## <a name="return-value"></a>반환 값  
 강력한 이름의 함수 중 하나에서 설정한 마지막 COM 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 강력한 이름 메서드 중 대부분은 간단한 반환 `true` 또는 `false` 완료 여부 표시 합니다. 사용 된 `StrongNameErrorInfo` 강력한 이름의 함수에 의해 생성 된 마지막 오류를 지정 하는 HRESULT를 검색 하는 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [강력한 이름 지정 글로벌 정적 함수](https://msdn.microsoft.com/library/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)
