---
title: '서비스: Calls Failed Per Second'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: 9cd649788e1304c68caa1bbf4b5fd27e6fc9d508
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43396420"
---
# <a name="service-calls-failed-per-second"></a>서비스: Calls Failed Per Second
카운터 이름: Calls Failed Per Second  
  
## <a name="description"></a>설명  
 초당 이 서비스에서 받은, 처리되지 않은 예외가 있는 호출 수입니다.  
  
 이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음 수식을 사용 하 여 계산 됩니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 관리 코드에서 오류 조건이 발생하면 예외가 throw됩니다.  
  
 관리 코드에서 오류 조건이 발생하면 예외가 throw됩니다.  
  
 이 서비스에 처리되지 않은 예외가 있을 때마다 이 카운터가 증가합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계약 및 서비스에서 오류 지정 및 처리](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
