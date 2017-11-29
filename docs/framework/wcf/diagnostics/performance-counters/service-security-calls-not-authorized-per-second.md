---
title: "서비스: Security Calls Not Authorized Per Second"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ad28d6afe26537e7a3eface8be70bcecf15b7aa8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="service-security-calls-not-authorized-per-second"></a><span data-ttu-id="1fcc2-102">서비스: Security Calls Not Authorized Per Second</span><span class="sxs-lookup"><span data-stu-id="1fcc2-102">Service: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="1fcc2-103">카운터 이름: Security Calls Not Authorized Per Second</span><span class="sxs-lookup"><span data-stu-id="1fcc2-103">Counter name: Security Calls Not Authorized Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="1fcc2-104">설명</span><span class="sxs-lookup"><span data-stu-id="1fcc2-104">Description</span></span>  
 <span data-ttu-id="1fcc2-105">올바른 사용자로부터 전송되고 적절하게 보호되지만 해당 사용자에게 특정 작업을 수행할 수 있는 권한이 없는 경우에 초당 들어오는 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1fcc2-105">Number of incoming messages in one second, which are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="1fcc2-106">이 카운터는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 메서드가 `false`를 반환할 때 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="1fcc2-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="1fcc2-107">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkId=94649), 값은 다음과 같은 수식으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fcc2-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkId=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="1fcc2-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="1fcc2-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
