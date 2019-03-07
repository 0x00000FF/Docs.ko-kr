---
title: GUID_ManagedName 특성
ms.date: 03/30/2017
api_name:
- GUID_ManagedName
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GUID_ManagedName
helpviewer_keywords:
- GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48ad6e4d1d03d8362123e65f16907880b18893f9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496393"
---
# <a name="guidmanagedname-attribute"></a>GUID_ManagedName 특성
구성 요소 개체 모델 (COM) 라이브러리에 대 한 관리 되는 네임 스페이스 이름을 지정 하는 사용자 지정 인터페이스 특성을 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a>매개 변수  
 `value`  
 라이브러리에 대 한 관리 되는 네임 스페이스 이름입니다.  
  
## <a name="definition"></a>정의  
 `GUID_ManagedName` Cor.h에서 다음과 같이 정의 됩니다.  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a>설명  
 사용자 지정 인터페이스 특성 형식 라이브러리의 개체에 대 한 메타 데이터를 정의합니다.  
  
 사용 하 여 <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> 또는 <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> 특성에서 관리 되는 이름을 검색할 수 있습니다.  
  
 자세한 내용은 [인터페이스 특성](/cpp/windows/interface-attributes) Visual c + +에서 설명서를 참조 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하 여 라이브러리 정의 `GUID_ManagedName` 특성입니다.  
  
```  
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** Cor.h
