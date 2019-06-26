---
title: 대기 중인 응용 프로그램 웹 호스팅
ms.date: 03/30/2017
ms.assetid: c7a539fa-e442-4c08-a7f1-17b7f5a03e88
ms.openlocfilehash: c8584f78b6b31bc95e088b424122a9cf77a17f27
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67402276"
---
# <a name="web-hosting-a-queued-application"></a>대기 중인 응용 프로그램 웹 호스팅
Windows 프로세스 활성화 서비스 (WAS)는 정품 인증 및 호스트 Windows Communication Foundation (WCF) 서비스를 사용 하는 응용 프로그램을 포함 하는 작업자 프로세스의 수명을 관리 합니다. WAS 프로세스 모델은 HTTP에 대 한 종속성을 제거 하 여 HTTP 서버에 대 한 IIS 6.0 프로세스 모델을 일반화 합니다. 이렇게 하면 WCF 서비스가 HTTP 및 net.msmq 및 msmq.formatname 메시지 기반 활성화를 지원 하 고 많은 수의 지정된 된 컴퓨터에서 응용 프로그램을 호스트 하는 기능을 제공 하는 호스팅 환경에서와 같은 HTTP가 아닌 프로토콜을 모두 사용할 수 있습니다.  
  
 WAS에는 대기 중인 응용 프로그램에 사용된 큐 중 하나에 하나 이상의 메시지가 있을 경우 해당 응용 프로그램을 활성화하는 MSMQ(메시지 큐) 활성화 서비스가 포함됩니다. MSMQ 활성화 서비스는 기본적으로 자동 시작되는 NT 서비스입니다.  
  
 WAS 및 그 이점에 대 한 자세한 내용은 참조 하세요. [Windows Process Activation Service에서 호스팅](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)합니다. MSMQ에 대 한 자세한 내용은 참조 하세요. [큐 개요](../../../../docs/framework/wcf/feature-details/queues-overview.md)합니다.
  
## <a name="queue-addressing-in-was"></a>WAS의 큐 주소 지정  
 WAS 응용 프로그램에는 URI(Uniform Resource Identifier) 주소가 있습니다. 응용 프로그램 주소는 기본 URI 접두사와 응용 프로그램별 상대 주소(경로)로 이루어집니다. 이 두 부분은 함께 결합될 경우 응용 프로그램의 외부 주소를 제공합니다. 기본 URI 접두사는 사이트 바인딩에서 생성 하 고 예를 들어, "net.msmq://localhost", "msmq.formatname://localhost" 또는 "net.tcp://localhost" 사이트의 모든 응용 프로그램에 사용 됩니다. 응용 프로그램 주소는 응용 프로그램별 경로 부분을 수행 하 여 생성 됩니다 (같은 "/ applicationOne")에 추가 하 고 기본 URI 접두사를 사용 하 여 전체 응용 프로그램 URI 예를 들어, "net.msmq://localhost/applicationOne" 및 합니다.  
  
 MSMQ 활성화 서비스는 응용 프로그램 URI를 사용하여 MSMQ 활성화 서비스가 메시지를 모니터링해야 하는 큐를 일치시킵니다. MSMQ 활성화 서비스가 시작되면 수신하도록 구성된 컴퓨터의 모든 공개 큐 및 개인 큐를 열거하고 메시지를 모니터링합니다. 10분 간격으로 MSMQ 활성화 서비스는 모니터링할 큐 목록을 새로 고칩니다. 메시지가 큐에 있으면 활성화 서비스가 큐 이름을 net.msmq 바인딩의 가장 긴 일치 응용 프로그램 URI와 일치시키고 응용 프로그램을 활성화합니다.  
  
> [!NOTE]
>  활성화되는 응용 프로그램은 큐 이름의 접두사와 일치해야 합니다(가장 긴 일치).  
  
 예를 들어 큐 이름은 msmqWebHost/orderProcessing/service.svc입니다. Application 1에 가상 디렉터리 /msmqWebHost/orderProcessing이 있고 그 아래에 service.svc가 있으며 Application 2에 가상 디렉터리 /msmqWebHost가 있고 그 아래에 orderProcessing.svc가 있으면 Application 1이 활성화됩니다. Application 1을 삭제하면 Application 2가 활성화됩니다.  
  
> [!NOTE]
>  큐를 만들면 MSMQ 활성화 서비스에서 큐 목록을 새로 고칠 때까지, 즉 큐를 만든 시간부터 최대 10분 동안 해당 큐로 전송된 메시지가 응용 프로그램을 활성화하지 않습니다. 활성화 서비스를 다시 시작하면 큐 목록도 새로 고쳐집니다.  
  
### <a name="the-effect-of-private-and-public-queues-on-addressing"></a>개인 큐와 공개 큐가 주소 지정에 미치는 영향  
 MSMQ 활성화 서비스는 개인 큐 및 공개 큐 모니터링을 구분하지 않습니다. 따라서 동일한 이름의 공개 큐와 개인 큐를 사용할 수 없습니다. 사용하면 웹에 호스트된 응용 프로그램이 큐 중 하나에서 읽는 동안 활성화될 수 있습니다.  
  
### <a name="queue-configuration-for-activation"></a>활성화에 대한 큐 구성  
 MSMQ 활성화 서비스는 NETWORK SERVICE로 실행됩니다. 큐를 모니터링하여 응용 프로그램을 활성화하는 서비스입니다. 큐에서 응용 프로그램을 활성화하려면 큐가 ACL(액세스 제어 목록)에서 메시지를 피킹할 NETWORK SERVICE 권한을 제공해야 합니다.  
  
### <a name="poison-messaging"></a>포이즌 메시징  
 WCF에서 포이즌 메시지 처리 뿐만 아니라는 메시지가 손상 되어 있지만를 사용자 구성에 따라 처리를 선택 하는 검색 하는 채널에 의해 처리 됩니다. 따라서 큐에 하나의 메시지가 있습니다. 웹에 호스트된 응용 프로그램은 연속 시도를 중단하며 메시지가 다시 시도 큐로 이동합니다. 다시 시도 주기 지연에 지정된 시점에서 다시 시도할 메시지가 다시 시도 큐에서 기본 큐로 이동합니다. 그러나 이 경우 대기 중인 채널이 활성 상태여야 합니다. WAS에서 응용 프로그램을 재활용하는 경우 다른 메시지가 기본 큐에 도착하여 대기 중인 응용 프로그램을 활성화할 때까지 메시지가 다시 시도 큐에 남아 있습니다. 이 경우의 해결 방법은 수동으로 메시지를 다시 시도 큐에서 기본 큐로 이동하여 응용 프로그램을 다시 활성화하는 것입니다.  
  
### <a name="subqueue-and-system-queue-caveat"></a>하위 큐 및 시스템 큐 경고  
 시스템 차원의 배달 못 한 큐 등의 시스템 큐나 포이즌 하위 큐 등의 하위 큐에 있는 메시지를 기반으로 WAS에 호스트된 응용 프로그램을 활성화할 수 없습니다. 이 제품 버전의 제한 사항입니다.  
  
## <a name="see-also"></a>참고자료

- [포이즌 메시지 처리](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)
- [서비스 엔드포인트 및 큐 주소 지정](../../../../docs/framework/wcf/feature-details/service-endpoints-and-queue-addressing.md)
