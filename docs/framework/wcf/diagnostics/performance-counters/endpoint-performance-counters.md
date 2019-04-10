---
title: 엔드포인트 성능 카운터
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: f07e318e39a68e689ec484b09fa743623cfb51d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158394"
---
# <a name="endpoint-performance-counters"></a><span data-ttu-id="8aa72-102">엔드포인트 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="8aa72-102">Endpoint Performance Counters</span></span>
<span data-ttu-id="8aa72-103">엔드포인트 성능 카운터는 엔드포인트가 메시지를 수신하는 방식을 나타내는 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa72-103">Endpoint performance counters capture data that reveals how an endpoint is accepting messages.</span></span> <span data-ttu-id="8aa72-104">이러한 카운터는 성능 모니터에서 볼 때 `ServiceModelEndpoint 4.0.0.0` 성능 개체 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa72-104">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="8aa72-105">인스턴스 이름은 다음 패턴으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aa72-105">The instances are named using this pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="8aa72-106">데이터는 개별 작업을 위해 수집된 데이터와 비슷하지만 엔드포인트에서만 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aa72-106">The data is similar to that collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="8aa72-107">성능 카운터 인스턴스의 이름 길이에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa72-107">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="8aa72-108">Windows Communication Foundation (WCF) 카운터 인스턴스 이름의 최대 길이 초과 하면 WCF는 인스턴스 이름의 일부를 해시 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8aa72-108">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aa72-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="8aa72-109">See also</span></span>

- [<span data-ttu-id="8aa72-110">성능 카운터</span><span class="sxs-lookup"><span data-stu-id="8aa72-110">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
