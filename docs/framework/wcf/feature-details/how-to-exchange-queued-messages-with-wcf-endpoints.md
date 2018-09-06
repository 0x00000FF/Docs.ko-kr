---
title: '방법: 대기 중인 메시지와 WCF 엔드포인트 교환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
ms.openlocfilehash: 185bcb64522115d0c60ae90ee22a73610139c8c3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865597"
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a>방법: 대기 중인 메시지와 WCF 엔드포인트 교환
큐는 서비스의 통신 시 사용할 수 없는 경우에 Windows Communication Foundation (WCF) 서비스와 클라이언트 간에 신뢰할 수 있는 메시징 발생할 수 있다고 확인 합니다. 다음 절차에는 WCF 서비스를 구현 하는 경우 클라이언트와 표준을 사용 하 여 서비스 간 통신을 지 속하는 큐 바인딩을 확인 하는 방법을 보여 줍니다.  
  
 이 섹션에서는 사용 하는 방법에 설명 <xref:System.ServiceModel.NetMsmqBinding> WCF 클라이언트와 WCF 서비스 간에 대기 중인 통신 합니다.  
  
### <a name="to-use-queuing-in-a-wcf-service"></a>WCF 서비스에서 큐를 사용하려면  
  
1.  <xref:System.ServiceModel.ServiceContractAttribute>로 표시된 인터페이스를 사용하여 서비스 계약을 정의합니다. <xref:System.ServiceModel.OperationContractAttribute>가 있는 서비스 계약의 일부인 인터페이스에서 작업을 표시하고, 메서드에 대한 응답이 반환되지 않으므로 해당 작업을 단방향으로 지정합니다. 다음 코드에서는 예제 서비스 계약 및 작업 정의를 제공합니다.  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2.  서비스 계약에서 사용자 정의 형식을 전달하는 경우 해당 형식의 데이터 계약을 정의해야 합니다. 다음 코드에서는 `PurchaseOrder` 및 `PurchaseOrderLineItem`의 두 데이터 계약을 보여 줍니다. 이 두 형식은 서비스로 전송되는 데이터를 정의합니다. 또한 이 데이터 계약을 정의하는 클래스에서 여러 메서드도 정의합니다. 이러한 메서드는 데이터 계약의 일부로 간주되지 않습니다. `DataMember` 특성을 사용하여 선언된 해당 멤버만이 데이터 계약의 일부가 됩니다.  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3.  클래스에서 인터페이스에 정의된 서비스 계약의 메서드를 구현합니다.  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     <xref:System.ServiceModel.OperationBehaviorAttribute>는 `SubmitPurchaseOrder` 메서드에 배치됩니다. 따라서 이 작업은 트랜잭션 내에서 호출해야 하며 메서드가 완료되면 트랜잭션도 자동으로 완료되도록 지정됩니다.  
  
4.  <xref:System.Messaging>을 사용하여 트랜잭션 큐를 만듭니다. MSMQ(Microsoft Message Queuing) MMC(Microsoft Management Console)를 대신 사용하여 큐를 만들 수 있습니다. 이 경우에는 트랜잭션 큐를 만들어야 합니다.  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5.  서비스 주소를 지정하고 표준 <xref:System.ServiceModel.Description.ServiceEndpoint> 바인딩을 사용하는 구성에 <xref:System.ServiceModel.NetMsmqBinding>를 정의합니다. WCF 구성을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [Windows Communication Foundation 응용 프로그램 구성](https://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)합니다.  
  
  
  
6.  큐에서 메시지를 읽어 이를 처리하는 `OrderProcessing`를 사용하여 <xref:System.ServiceModel.ServiceHost> 서비스의 호스트를 만듭니다. 서비스를 사용할 수 있도록 서비스 호스트를 엽니다. 사용자에게 아무 키나 누르면 서비스를 종료할 수 있음을 알리는 메시지를 표시합니다. `ReadLine`을 호출하여 키를 누를 때까지 기다린 후에 서비스를 닫습니다.  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a>대기 중인 서비스의 클라이언트를 만들려면  
  
1.  다음 예제에서는 호스팅 응용 프로그램을 실행 하 고 Svcutil.exe 도구를 사용 하 여 WCF 클라이언트를 만드는 방법을 보여 줍니다.  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2.  다음 예제와 같이 주소를 지정하고 표준 <xref:System.ServiceModel.Description.ServiceEndpoint> 바인딩을 사용하는 구성에서 <xref:System.ServiceModel.NetMsmqBinding>를 정의합니다.  
  
  
  
3.  호출 하는 트랜잭션 큐에 쓸 트랜잭션 범위를 만듭니다는 `SubmitPurchaseOrder` 작업 닫은 다음 예제에서와 같이 WCF 클라이언트입니다.  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 이 예제에 포함된 서비스 코드, 호스팅 응용 프로그램, App.config 파일 및 클라이언트 코드를 보여 줍니다.  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  
  
  
  
 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  
  
  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.NetMsmqBinding>  
 [트랜잭션된 MSMQ 바인딩](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
 [WCF의 큐](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [방법: WCF 엔드포인트 및 메시지 큐 응용 프로그램과 메시지 교환](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [Windows Communication Foundation에서 메시지 큐로](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [메시지 큐(MSMQ) 설치](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [메시지 큐 통합 바인딩 샘플](https://msdn.microsoft.com/library/997d11cb-f2c5-4ba0-9209-92843d4d0e1a)  
 [메시지 큐에서 indows Communication Foundation으로](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [메시지 큐에 대한 메시지 보안](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
