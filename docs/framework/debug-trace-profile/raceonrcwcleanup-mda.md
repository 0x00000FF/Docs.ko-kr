---
title: raceOnRCWCleanup MDA
ms.date: 03/30/2017
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 628790bb8229dc519589c122235f07a38ba57c1c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100238"
---
# <a name="raceonrcwcleanup-mda"></a>raceOnRCWCleanup MDA
`raceOnRCWCleanup` MDA(관리 디버깅 도우미)는 CLR(공용 언어 런타임)에서 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> 메서드와 같은 명령을 사용하여 해제 호출을 수행할 때 RCW( [런타임 호출 가능 래퍼](../../../docs/framework/interop/runtime-callable-wrapper.md))가 사용 중임을 발견할 경우 활성화됩니다.  
  
## <a name="symptoms"></a>증상  
 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> 또는 이와 비슷한 메서드를 사용하여 RCW를 해제하는 중이나 그 이후에 액세스 위반 또는 메모리 손상이 발생합니다.  
  
## <a name="cause"></a>원인  
 RCW가 다른 스레드나 해제 스레드 스택에서 사용 중입니다.  사용 중인 RCW는 해제할 수 없습니다.  
  
## <a name="resolution"></a>해결  
 현재 스레드나 다른 스레드에서 사용 중일 수 있는 RCW는 해제하지 마세요.  
  
## <a name="effect-on-the-runtime"></a>런타임에 대한 영향  
 이 MDA는 CLR에 아무런 영향을 미치지 않습니다.  
  
## <a name="output"></a>출력  
 오류를 설명하는 메시지입니다.  
  
## <a name="configuration"></a>구성  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [관리 디버깅 도우미를 사용하여 오류 진단](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)
