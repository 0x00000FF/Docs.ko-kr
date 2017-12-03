---
title: Reliable Messaging Messages Dropped Per Second
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64ced36369bfb44b6b0cef4af500da5e4796e64d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="5d186-102">Reliable Messaging Messages Dropped Per Second</span><span class="sxs-lookup"><span data-stu-id="5d186-102">Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="5d186-103">카운터 이름: Reliable Messaging Sessions Dropped Per Second.</span><span class="sxs-lookup"><span data-stu-id="5d186-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5d186-104">설명</span><span class="sxs-lookup"><span data-stu-id="5d186-104">Description</span></span>  
 <span data-ttu-id="5d186-105">이 서비스에서 초당 손실된 신뢰할 수 있는 메시징 메시지의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d186-105">Total number of reliable messaging messages that have been dropped in this service in a second.</span></span>  
  
 <span data-ttu-id="5d186-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d186-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="5d186-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="5d186-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
