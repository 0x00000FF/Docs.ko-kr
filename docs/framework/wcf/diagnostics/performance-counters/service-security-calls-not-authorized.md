---
title: "서비스: Security Calls Not Authorized"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3024b20a-5250-4bd1-a38c-c6d79f89610b
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 5dae370d90082c9efe89f9d523740fc25ece21ab
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="service-security-calls-not-authorized"></a><span data-ttu-id="1134e-102">서비스: Security Calls Not Authorized</span><span class="sxs-lookup"><span data-stu-id="1134e-102">Service: Security Calls Not Authorized</span></span>
<span data-ttu-id="1134e-103">카운터 이름: Security Calls Not Authorized</span><span class="sxs-lookup"><span data-stu-id="1134e-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1134e-104">설명</span><span class="sxs-lookup"><span data-stu-id="1134e-104">Description</span></span>  
 <span data-ttu-id="1134e-105">이 카운터는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 메서드가 `false`를 반환할 때 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="1134e-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="1134e-106">들어오는 메시지가 올바른 사용자로부터 전송되고 적절하게 보호되지만 해당 사용자에게 특정 작업을 수행할 수 있는 권한이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1134e-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>
