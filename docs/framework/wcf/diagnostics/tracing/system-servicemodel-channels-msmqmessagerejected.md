---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b433e5e3c0a961098f82ad601d127290b1d6bd73
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="cf769-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="cf769-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="cf769-103">MSMQ에서 메시지를 거부했습니다.</span><span class="sxs-lookup"><span data-stu-id="cf769-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="cf769-104">설명</span><span class="sxs-lookup"><span data-stu-id="cf769-104">Description</span></span>  
 <span data-ttu-id="cf769-105">이 추적은 MSMQ 메시지가 거부되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cf769-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="cf769-106">NetMsmqBinding 또는 MsmqIntegrationBinding과 함께 사용되는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]에서 MSMQ 메시지를 처리할 수 없는 경우 MSMQ 메시지가 거부될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf769-106">MSMQ messages can be rejected when [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="cf769-107">이러한 메시지를 포이즌 메시지라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf769-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="cf769-108">포이즌 메시지는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Reject`로 설정할 경우 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf769-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="cf769-109">거부 된 메시지가 보낸 사람의에 다시 배달 [배달 못 한 편지 큐](http://go.microsoft.com/fwlink/?LinkID=99544)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf769-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](http://go.microsoft.com/fwlink/?LinkID=99544).</span></span>  
  
 <span data-ttu-id="cf769-110">참조 [포이즌 메시지 처리](http://go.microsoft.com/fwlink/?LinkID=99546) 경우 메시지가 포이즌이 되 고 적절히 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf769-110">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
 <span data-ttu-id="cf769-111">참조 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) MSMQ의 의미는 거부 된 메시지에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf769-111">See [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf769-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf769-112">See Also</span></span>  
 [<span data-ttu-id="cf769-113">추적</span><span class="sxs-lookup"><span data-stu-id="cf769-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="cf769-114">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="cf769-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="cf769-115">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="cf769-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="cf769-116">포이즌 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="cf769-116">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkID=99546)  
 [<span data-ttu-id="cf769-117">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="cf769-117">MQMarkMessageRejected</span></span>](http://go.microsoft.com/fwlink/?LinkID=99548)
