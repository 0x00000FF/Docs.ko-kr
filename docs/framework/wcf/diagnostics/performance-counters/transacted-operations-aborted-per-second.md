---
title: Transacted Operations Aborted Per Second
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a54b84f2fa0ab9c7531a17e69b10f78c725255ef
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="transacted-operations-aborted-per-second"></a><span data-ttu-id="ac843-102">Transacted Operations Aborted Per Second</span><span class="sxs-lookup"><span data-stu-id="ac843-102">Transacted Operations Aborted Per Second</span></span>
<span data-ttu-id="ac843-103">카운터 이름: Transacted Operations Aborted Per Second</span><span class="sxs-lookup"><span data-stu-id="ac843-103">Counter Name: Transacted Operations Aborted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ac843-104">설명</span><span class="sxs-lookup"><span data-stu-id="ac843-104">Description</span></span>  
 <span data-ttu-id="ac843-105">초당 이 서비스에서 중단된 트랜잭션 작업 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ac843-105">Number of transactional operations that have been aborted in this service in a second.</span></span>  
  
 <span data-ttu-id="ac843-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac843-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="ac843-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="ac843-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
