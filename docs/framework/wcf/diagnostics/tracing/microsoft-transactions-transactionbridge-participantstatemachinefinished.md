---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 845b344cee6c47a0c2f125caab7965ef8f65f336
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="e97cf-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="e97cf-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="e97cf-103">참가자 인리스트먼트에 대한 상태 시스템이 완료 상태가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e97cf-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e97cf-104">설명</span><span class="sxs-lookup"><span data-stu-id="e97cf-104">Description</span></span>  
 <span data-ttu-id="e97cf-105">하위 참여 인리스트먼트에서 2PC(2단계 커밋) 처리를 완료한 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="e97cf-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="e97cf-106">인리스트먼트 결과는 커밋됨 또는 중단됨입니다.</span><span class="sxs-lookup"><span data-stu-id="e97cf-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="e97cf-107">참가자가 준비 과정에서 ReadOnly를 선택하는 경우에도 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="e97cf-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e97cf-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e97cf-108">See Also</span></span>  
 [<span data-ttu-id="e97cf-109">추적</span><span class="sxs-lookup"><span data-stu-id="e97cf-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="e97cf-110">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="e97cf-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="e97cf-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="e97cf-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
