---
title: IBindingDisplay::GetCurrentDisplay 메서드
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 472e06c3a00762a7bb012fbcb525d8e0b3a9271a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599522"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a>IBindingDisplay::GetCurrentDisplay 메서드
현재 바인딩 표시 정보를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `display`  
 [out, retval] 바인딩 표시 정보를 포함 하는 safearray에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 합니다 [ibindingdisplay:: Initializeforprocess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) 메서드 분명히 성공 했을 이전에, 및는 디버거에서 프로그램을 중지 해야 합니다.  
  
 호출자는 반환 된 할당 취소 해야 `SAFEARRAY` 를 사용 하 여 메모리 [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** BindingDisplay.h  
  
 **라이브러리:** BindingDisplay.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IBindingDisplay 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
- [InitializeForProcess 메서드](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
