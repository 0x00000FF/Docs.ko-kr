---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 0addf987eac62c750a3c418e1b1c431d3f9bc1b0
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2018
ms.locfileid: "46586638"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="9566f-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="9566f-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="9566f-103">MSMQ에서 메시지를 거부했습니다.</span><span class="sxs-lookup"><span data-stu-id="9566f-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9566f-104">설명</span><span class="sxs-lookup"><span data-stu-id="9566f-104">Description</span></span>  
 <span data-ttu-id="9566f-105">이 추적은 MSMQ 메시지가 거부되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9566f-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="9566f-106">Windows Communication Foundation (WCF) (NetMsmqBinding 또는 MsmqIntegrationBinding을 사용 하 여 사용)를 처리할 수 없는 경우에 MSMQ 메시지가 거부 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9566f-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="9566f-107">이러한 메시지를 포이즌 메시지라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9566f-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="9566f-108">포이즌 메시지는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Reject`로 설정할 경우 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="9566f-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="9566f-109">거부 된 메시지를 보낸 사람에 게 배달 됩니다 [배달 못 한 편지 큐](https://go.microsoft.com/fwlink/?LinkID=99544)합니다.</span><span class="sxs-lookup"><span data-stu-id="9566f-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkID=99544).</span></span>  
  
 <span data-ttu-id="9566f-110">참조 [포이즌 메시지 처리](https://go.microsoft.com/fwlink/?LinkID=99546) 메시지는 포이즌 메시지가 될 경우 및이 적절히 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="9566f-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
 <span data-ttu-id="9566f-111">참조 [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) MSMQ에서 거부 된 메시지가 의미 하는 바를 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="9566f-111">See [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9566f-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9566f-112">See Also</span></span>  
 [<span data-ttu-id="9566f-113">추적</span><span class="sxs-lookup"><span data-stu-id="9566f-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="9566f-114">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="9566f-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="9566f-115">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="9566f-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="9566f-116">포이즌 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="9566f-116">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)  
 [<span data-ttu-id="9566f-117">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="9566f-117">MQMarkMessageRejected</span></span>](https://go.microsoft.com/fwlink/?LinkID=99548)
