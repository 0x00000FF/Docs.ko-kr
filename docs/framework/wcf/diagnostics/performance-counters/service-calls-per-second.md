---
title: "서비스: Calls Per Second"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0880ce3674f41367c46f4d0268a5391cfda210ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="service-calls-per-second"></a><span data-ttu-id="81ae3-102">서비스: Calls Per Second</span><span class="sxs-lookup"><span data-stu-id="81ae3-102">Service: Calls Per Second</span></span>
<span data-ttu-id="81ae3-103">카운터 이름: Calls Per Second</span><span class="sxs-lookup"><span data-stu-id="81ae3-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="81ae3-104">설명</span><span class="sxs-lookup"><span data-stu-id="81ae3-104">Description</span></span>  
 <span data-ttu-id="81ae3-105">이 서비스에 대한 초당 호출 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="81ae3-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="81ae3-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ae3-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="81ae3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)에서 분자(N)는 마지막 샘플 기간 동안 수행되는 작업 수를 나타내고, 분모(D)는 해당 기간 동안 경과되는 눈금 수를 나타내며 F는 눈금의 주기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="81ae3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
