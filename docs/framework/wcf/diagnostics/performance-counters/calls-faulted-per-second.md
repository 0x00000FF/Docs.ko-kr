---
title: Calls Faulted Per Second
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81c88073-8e32-4520-a71a-2c56b71ee515
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2e60ad3d7e9155eecfead38aca080a3044b0efce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="calls-faulted-per-second"></a>Calls Faulted Per Second
카운터 이름: Calls Faulted Per Second  
  
## <a name="description"></a>설명  
 초당 이 작업에 오류를 반환한 호출의 수입니다.  
  
 이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 응용 프로그램에서 서비스 메서드는 SOAP 오류 메시지를 사용하여 처리 오류 정보를 전달합니다. SOAP 오류는 서비스 작업의 메타데이터에 포함된 메시지 유형이므로 클라이언트가 실행을 더욱 견고하게 만들거나 대화형으로 만드는 데 사용할 수 있는 오류 계약을 만듭니다. SOAP 오류는 XML 형식으로 클라이언트에 표현되므로 상호 운용성이 매우 높습니다.  
  
## <a name="see-also"></a>참고 항목  
 [계약 및 서비스에서 오류 지정 및 처리](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
