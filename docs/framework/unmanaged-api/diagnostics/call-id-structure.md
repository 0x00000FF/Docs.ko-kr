---
title: "CALL_ID 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 71fd69cbcced1440839b9eedf8fbe3d8f5b90646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="callid-structure"></a>CALL_ID 구조체
디버거에 호출 되는 함수에 대 한 정보를 제공 합니다. 참조는 [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) 자세한 정보에 대 한 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`szMachine`|이 호출 하는 컴퓨터를 식별 합니다.|  
|`dwPid`|컴퓨터 프로세서를 식별합니다.|  
|`pUserThread`|호출을 실행 하는 스레드를 식별 합니다.|  
|`addrStackPointer`|호출 스택의 주소를 지정합니다.|  
|`szEntryPoint`|호출의 주소를 지정합니다.|  
|`szDestinationMachine`|호출을 실행할 컴퓨터를 식별 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>참고 항목  
 [INotifySink2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [진단 기호 저장소 구조체](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
