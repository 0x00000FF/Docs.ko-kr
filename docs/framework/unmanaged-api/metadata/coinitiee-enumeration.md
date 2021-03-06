---
title: COINITIEE 열거형
ms.date: 03/30/2017
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
ms.openlocfilehash: 2ccc038b4420040779dae70f15e3a8827ba94180
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444108"
---
# <a name="coinitiee-enumeration"></a>COINITIEE 열거형
공용 언어 런타임을 초기화할 때 [Coinitializeee](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) 에서 사용 하는 상수를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|기본 초기화 모드입니다. 이렇게 하면 런타임이 초기화 되 고 기본 <xref:System.AppDomain>만들어집니다.|  
|`COINITEE_DLL`|관리 되는 DLL을 실행 하도록 초기화 합니다.|  
|`COINITEE_MAIN`|관리 되는 EXE를 실행 하도록 초기화 합니다. 이는 런타임을 초기화 하지만 EXE의 기본 루틴을 입력 한 후 만들어지는 기본 <xref:System.AppDomain>를 만들지 않습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
