---
title: pInvokeLog MDA
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe1d783017369a78074e5abf278ac2facf6ee32b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734067"
---
# <a name="pinvokelog-mda"></a>pInvokeLog MDA
`pInvokeLog` MDA(관리 디버깅 도우미)는 실행 중에 사용되는 고유한 각 플랫폼 호출을 위해 활성화됩니다.  
  
## <a name="effect-on-the-runtime"></a>런타임에 대한 영향  
 이 MDA는 CLR에 아무런 영향을 미치지 않습니다.  
  
## <a name="output"></a>출력  
 실행 중에 사용된 플랫폼 호출 시그니처를 나타내는 메시지.  
  
## <a name="configuration"></a>구성하기  
 일치하는 각 요소는 플랫폼 호출을 수행하는 .dll 파일을 필터링합니다.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>참고자료
- [관리 디버깅 도우미를 사용하여 오류 진단](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [관리되지 않는 DLL 함수 사용](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
