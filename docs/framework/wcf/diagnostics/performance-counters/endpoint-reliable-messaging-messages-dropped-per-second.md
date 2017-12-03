---
title: "끝점: Reliable Messaging Messages Dropped Per Second"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: df6db86febeb88fe934bbd509f6fe8130fd1c811
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="8cc37-102">끝점: Reliable Messaging Messages Dropped Per Second</span><span class="sxs-lookup"><span data-stu-id="8cc37-102">Endpoint: Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="8cc37-103">카운터 이름: Reliable Messaging Sessions Dropped Per Second.</span><span class="sxs-lookup"><span data-stu-id="8cc37-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8cc37-104">설명</span><span class="sxs-lookup"><span data-stu-id="8cc37-104">Description</span></span>  
 <span data-ttu-id="8cc37-105">이 끝점에서 삭제된 신뢰할 수 있는 메시징 메시지의 초당 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc37-105">Total number of reliable messaging messages that have been dropped at this endpoint in a second.</span></span>  
  
 <span data-ttu-id="8cc37-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc37-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="8cc37-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="8cc37-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
