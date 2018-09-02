---
title: Queued Poison Messages Per Second
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: d4c921b105dfd1c1a364d2c86f54ab920078dd4a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43420691"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="6d95b-102">Queued Poison Messages Per Second</span><span class="sxs-lookup"><span data-stu-id="6d95b-102">Queued Poison Messages Per Second</span></span>
<span data-ttu-id="6d95b-103">카운터 이름: Queued Poison Messages Per Second</span><span class="sxs-lookup"><span data-stu-id="6d95b-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6d95b-104">설명</span><span class="sxs-lookup"><span data-stu-id="6d95b-104">Description</span></span>  
 <span data-ttu-id="6d95b-105">1초 동안 이 서비스에 대기 중인 전송에 의해 포이즌으로 표시된 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6d95b-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="6d95b-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음 수식을 사용 하 여 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d95b-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="6d95b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="6d95b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
