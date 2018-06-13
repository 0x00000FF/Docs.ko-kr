---
title: 순서에 상관없이 메시지 처리
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: a7839b60dbad7919a644c196a1c63f6bc46fb5d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492947"
---
# <a name="out-of-order-message-processing"></a>순서에 상관없이 메시지 처리
워크플로 서비스는 특정 순서로 보내지는 메시지에 따라 달라질 수 있습니다. 워크플로 서비스는 하나 이상의 <xref:System.ServiceModel.Activities.Receive> 활동을 포함하고 각 <xref:System.ServiceModel.Activities.Receive> 활동은 특정 메시지를 기다립니다. 특정 전송 전달 보장이 없으면 클라이언트가 보낸 메시지가 지연되어 워크플로 서비스가 예상할 수 없는 순서로 배달될 수 있습니다. 메시지를 순서에 상관없이 보내도 되는 워크플로 서비스를 구현하는 작업은 일반적으로 병렬 활동을 사용하여 수행됩니다. 복잡한 응용 프로그램 프로토콜의 경우 워크플로가 매우 빠른 속도로 매우 복잡해질 수 있습니다.  Windows Communication Foundation (WCF)의 기능을 처리 하는 순서가 메시지를 사용 하면 중첩 된 병렬 활동의 복잡도 모두 하지 않고 워크플로 만들 수 있습니다. 순서가 메시지 처리를 지 원하는 채널 에서만 지원 됩니다 <xref:System.ServiceModel.Channels.ReceiveContext> WCF MSMQ 바인딩 같은 합니다.  
  
## <a name="enabling-out-of-order-message-processing"></a>메시지를 순서에 상관없이 처리하는 기능 사용  
 메시지를 순서에 상관없이 처리하는 기능을 사용하려면 WorkflowService의 <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> 속성을 `true`로 설정합니다. 다음 예제에서는 코드에서 <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> 속성을 설정하는 방법을 보여 줍니다.  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 또한 다음 예제와 같이 XAML에서 워크플로 서비스에 `AllowBufferedReceive` 특성을 적용할 수도 있습니다.  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!—the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.ReceiveContext>  
 [워크플로 서비스](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [큐 및 신뢰할 수 있는 세션](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
