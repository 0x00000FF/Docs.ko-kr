---
title: '끝점: Security Calls Not Authorized Per Second'
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 0fd7c3ab7abcc374c4ef89f9f5a0650647cf97a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33471706"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a><span data-ttu-id="681f5-102">끝점: Security Calls Not Authorized Per Second</span><span class="sxs-lookup"><span data-stu-id="681f5-102">Endpoint: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="681f5-103">카운터 이름: Security Calls Not Authorized Per Second</span><span class="sxs-lookup"><span data-stu-id="681f5-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="681f5-104">설명</span><span class="sxs-lookup"><span data-stu-id="681f5-104">Description</span></span>  
 <span data-ttu-id="681f5-105">올바른 사용자로부터 전송되고 적절하게 보호되지만 해당 사용자에게 특정 작업을 수행할 수 있는 권한이 없는 경우에 1초당 들어오는 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="681f5-105">Number of incoming messages in a second that are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="681f5-106">이 카운터는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 메서드가 `false`를 반환할 때 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="681f5-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="681f5-107">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="681f5-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="681f5-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="681f5-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
