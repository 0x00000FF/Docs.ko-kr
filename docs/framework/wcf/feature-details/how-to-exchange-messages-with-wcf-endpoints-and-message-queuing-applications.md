---
title: '방법: WCF 엔드포인트 및 메시지 큐 애플리케이션과 메시지 교환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 7463f9cfc37c2bf4f271f6e59896a7d77f3f65cd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310308"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a><span data-ttu-id="9abd1-102">방법: WCF 엔드포인트 및 메시지 큐 애플리케이션과 메시지 교환</span><span class="sxs-lookup"><span data-stu-id="9abd1-102">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>
<span data-ttu-id="9abd1-103">WCF 메시지에서 MSMQ 메시지를 변환 하려면 MSMQ 통합 바인딩을 사용 하 여 Windows Communication Foundation (WCF) 응용 프로그램과 기존 메시지 큐 (MSMQ) 응용 프로그램을 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9abd1-103">You can integrate existing Message Queuing (MSMQ) applications with Windows Communication Foundation (WCF) applications by using the MSMQ integration binding to convert MSMQ messages to and from WCF messages.</span></span> <span data-ttu-id="9abd1-104">이 옵션을 사용 하면 WCF 클라이언트에서 MSMQ 수신자 응용 프로그램에 호출 수 있을 뿐만 아니라 MSMQ 발신자 응용 프로그램에서 WCF 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9abd1-104">This allows you to call into MSMQ receiver applications from WCF clients as well as call into WCF services from MSMQ sender applications.</span></span>  
  
 <span data-ttu-id="9abd1-105">이 섹션에서는 사용 하는 방법을 설명할 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> (1) WCF 클라이언트와 System.Messaging 및 (2) MSMQ 응용 프로그램 클라이언트와 WCF 서비스를 사용 하 여 작성 하는 MSMQ 응용 프로그램 서비스 간에 대기 중인 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abd1-105">In this section, we explain how to use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> for queued communication between (1) a WCF client and an MSMQ application service written using System.Messaging and (2) an MSMQ application client and a WCF service.</span></span>  
  
 <span data-ttu-id="9abd1-106">WCF 클라이언트에서 MSMQ 수신자 응용 프로그램을 호출 하는 방법을 보여 주는 전체 샘플을 참조 하세요. 합니다 [Windows Communication Foundation에서 메시지 큐로](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="9abd1-106">For a complete sample that demonstrates how to call a MSMQ receiver application from a WCF client, see the [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) sample.</span></span>  
  
 <span data-ttu-id="9abd1-107">MSMQ 클라이언트에서 WCF 서비스를 호출 하는 방법을 보여 주는 전체 샘플을 참조 하세요. 합니다 [메시지 큐를 Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="9abd1-107">For a complete sample that demonstrates how to call a WCF service from a MSMQ client, see the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) sample.</span></span>  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a><span data-ttu-id="9abd1-108">MSMQ 클라이언트로부터 메시지를 수신하는 WCF 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9abd1-108">To create a WCF service that receives messages from a MSMQ client</span></span>  
  
1. <span data-ttu-id="9abd1-109">다음 예제 코드에 나와 있는 것 처럼 MSMQ 발신자 응용 프로그램에서 대기 중인된 메시지를 수신 하는 WCF 서비스에 대 한 서비스 계약을 정의 하는 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abd1-109">Define an interface that defines the service contract for the WCF service that receives queued messages from a MSMQ sender application, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2. <span data-ttu-id="9abd1-110">다음 예제 코드에 표시된 것처럼 인터페이스를 구현하고 <xref:System.ServiceModel.ServiceBehaviorAttribute> 특성을 클래스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9abd1-110">Implement the interface and apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the class, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3. <span data-ttu-id="9abd1-111"><xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>을 지정하는 구성 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9abd1-111">Create a configuration file that specifies the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span></span>  

4. <span data-ttu-id="9abd1-112">구성된 바인딩을 사용하는 <xref:System.ServiceModel.ServiceHost> 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="9abd1-112">Instantiate a <xref:System.ServiceModel.ServiceHost> object that uses the configured binding.</span></span>  

### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a><span data-ttu-id="9abd1-113">MSMQ 수신자 응용 프로그램에 메시지를 보내는 WCF 클라이언트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9abd1-113">To create a WCF client that sends messages to a MSMQ receiver application</span></span>  
  
1. <span data-ttu-id="9abd1-114">다음 예제 코드와 같이 대기 중인 MSMQ 수신자에 게 메시지를 보냅니다는 WCF 클라이언트에 대 한 서비스 계약을 정의 하는 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abd1-114">Define an interface that defines the service contract for the WCF client that sends queued messages to the MSMQ receiver, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2. <span data-ttu-id="9abd1-115">WCF 클라이언트에서 MSMQ 수신자를 호출 하는 데는 클라이언트 클래스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abd1-115">Define a client class that the WCF client uses to call the MSMQ receiver.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3. <span data-ttu-id="9abd1-116">MsmqIntegrationBinding 바인딩을 사용하도록 지정하는 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9abd1-116">Create a configuration that specifies use of the MsmqIntegrationBinding binding.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4. <span data-ttu-id="9abd1-117">클라이언트 클래스의 인스턴스를 만들고 메시지 수신 서비스에 의해 정의된 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9abd1-117">Create an instance of the client class and call the method defined by the message receiving service.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="9abd1-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="9abd1-118">See also</span></span>

- [<span data-ttu-id="9abd1-119">큐 개요</span><span class="sxs-lookup"><span data-stu-id="9abd1-119">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)
- [<span data-ttu-id="9abd1-120">방법: WCF 엔드포인트와 대기 중인 메시지 교환</span><span class="sxs-lookup"><span data-stu-id="9abd1-120">How to: Exchange Queued Messages with WCF Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [<span data-ttu-id="9abd1-121">Windows Communication Foundation에서 메시지 큐로</span><span class="sxs-lookup"><span data-stu-id="9abd1-121">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)
- [<span data-ttu-id="9abd1-122">메시지 큐(MSMQ) 설치</span><span class="sxs-lookup"><span data-stu-id="9abd1-122">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)
- [<span data-ttu-id="9abd1-123">Windows Communication Foundation로 메시지 큐</span><span class="sxs-lookup"><span data-stu-id="9abd1-123">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)
- [<span data-ttu-id="9abd1-124">메시지 큐에 대한 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="9abd1-124">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
