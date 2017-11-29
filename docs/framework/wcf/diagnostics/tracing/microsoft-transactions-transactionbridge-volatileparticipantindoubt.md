---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3b497231326c640b93b96500df39732104e0f0c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="55ded-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="55ded-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="55ded-103">WS-AT 프로토콜 서비스가 인식할 수 없는 일시적 참가자로부터 Prepared 또는 Replay 메시지를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="55ded-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="55ded-104">트랜잭션 결과가 확실하지 않음을 선언하는 결함을 참가자에게 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="55ded-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="55ded-105">설명</span><span class="sxs-lookup"><span data-stu-id="55ded-105">Description</span></span>  
 <span data-ttu-id="55ded-106">로컬 트랜잭션 관리자가 이미 잊어 버린 일시적인 인리스트먼트로부터 Prepared 또는 Replay 메시지를 받는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="55ded-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="55ded-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="55ded-107">Troubleshooting</span></span>  
 <span data-ttu-id="55ded-108">일시적 참가자가 보내는 최신 메시지의 잠재적 원인을 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="55ded-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55ded-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55ded-109">See Also</span></span>  
 [<span data-ttu-id="55ded-110">추적</span><span class="sxs-lookup"><span data-stu-id="55ded-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="55ded-111">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="55ded-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="55ded-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="55ded-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
