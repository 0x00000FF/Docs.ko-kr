---
title: "스트리밍 메시지 전송"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72a47a51-e5e7-4b76-b24a-299d51e0ae5a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ff5fbf570c826f5c430109d9f79b3d5f39382f6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="streaming-message-transfer"></a>스트리밍 메시지 전송
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 전송에서는 다음과 같은 두 가지 메시지 전송 모드를 지원합니다.  
  
-   버퍼링 전송에서는 전송이 완료될 때까지 전체 메시지를 메모리 버퍼에 보관합니다. 버퍼링된 메시지는 수신기에서 읽기 전에 완전히 전달되어야 합니다.  
  
-   스트리밍 전송에서는 메시지를 스트림으로 노출합니다. 수신기는 전달이 완료되기 전에 메시지 처리를 시작합니다.  
  
-   스트리밍 전송은 대용량 메모리 버퍼에 대한 요구 사항을 제거하여 서비스 확장성을 향상시킬 수 있습니다. 전송 모드를 변경하면 확장성이 향상되는지 여부는 전송할 메시지의 크기에 따라 다릅니다. 메시지의 크기가 클수록 스트리밍 전송을 사용하는 것이 좋습니다.  
  
 기본적으로 HTTP, TCP/IP 및 명명된 파이프 전송에서는 버퍼링 전송을 사용합니다. 이 문서에서는 이러한 전송을 버퍼링 전송 모드에서 스트리밍 전송 모드로 전환하는 방법과 그 결과에 대해 설명합니다.  
  
## <a name="enabling-streamed-transfers"></a>스트리밍 전송 사용  
 버퍼링 전송 모드와 스트리밍 전송 모드의 선택은 전송의 바인딩 요소에서 수행됩니다. 바인딩 요소에는 <xref:System.ServiceModel.TransferMode>, `Buffered`, `Streamed` 또는 `StreamedRequest`로 설정할 수 있는 `StreamedResponse` 속성이 있습니다. 전송 모드를 `Streamed`로 설정하면 양방향 스트리밍 통신이 가능합니다. 전송 모드를 `StreamedRequest` 또는 `StreamedResponse`로 설정하면 표시된 방향으로만 스트리밍 통신이 가능합니다.  
  
 <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.NetTcpBinding> 및 <xref:System.ServiceModel.NetNamedPipeBinding> 바인딩은 <xref:System.ServiceModel.TransferMode> 속성을 노출합니다. 다른 전송의 경우 전송 모드를 설정하려면 사용자 지정 바인딩을 만들어야 합니다.  
  
 버퍼링 또는 스트리밍 전송 중 어느 것을 사용할 것인지를 결정하는 것은 끝점의 로컬 결정입니다. HTTP 전송의 경우 전송 모드는 연결 전체 또는 서버 및 다른 매개로 전파되지 않습니다. 서비스 인터페이스의 설명에 전송 모드 설정이 반영되지 않았습니다. 서비스에 대한 클라이언트 클래스를 생성하고 나면 스트리밍 전송에서 모드 설정에 사용할 서비스의 구성 파일을 편집해야 합니다. TCP 및 명명된 파이프 전송의 경우에는 전송 모드가 정책 어설션으로 전파됩니다.  
  
 코드 예제를 참조 하십시오. [하는 방법: 스트리밍 사용](../../../../docs/framework/wcf/feature-details/how-to-enable-streaming.md)합니다.  
  
## <a name="enabling-asynchronous-streaming"></a>비동기 스트리밍 사용  
 비동기 스트리밍을 사용하려면 <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior> 끝점 동작을 서비스 호스트에 추가하고 <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.AsynchronousSendEnabled%2A> 속성을 `true`로 설정합니다.  
  
 이 WCF 버전은 전송 측에 진정한 의미의 비동기 스트리밍 기능을 추가합니다. 이에 따라 메시지를 복수 클라이언트로 스트리밍하고 그 중 일부는 네트워크 혼잡으로 인해 읽는 속도가 느리거나 전혀 읽고 있지 않은 시나리오에서 서비스 확장성이 향상되었습니다. 이러한 시나리오에서는 WCF가 클라이언트당 서비스에서 개별 스레드를 차단하지 않습니다. 그러므로 서비스가 훨씬 더 많은 클라이언트를 처리해서 서비스 확장성이 향상됩니다.  
  
## <a name="restrictions-on-streamed-transfers"></a>스트리밍 전송에 대한 제한 사항  
 스트리밍 전송 모드를 사용하면 런타임에 추가 제한 사항이 적용됩니다.  
  
 스트리밍 전송을 통해 발생하는 작업에서 계약은 입력 또는 출력 매개 변수를 최대 하나만 가질 수 있습니다. 해당 매개 변수는 메시지의 전체 본문에 해당하며 <xref:System.ServiceModel.Channels.Message>, <xref:System.IO.Stream>의 파생 형식 또는 <xref:System.Xml.Serialization.IXmlSerializable> 구현이어야 합니다. 작업에 대한 반환 값을 지정하는 것은 출력 매개 변수를 지정하는 것과 같습니다.  
  
 신뢰할 수 있는 메시징, 트랜잭션 및 SOAP 메시지 수준 보안과 같은 일부 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 기능은 버퍼링 메시지를 사용하여 전송합니다. 이러한 기능을 사용하면 스트리밍을 통해 얻는 성능 이점이 감소되거나 제거될 수 있습니다. 스트리밍 전송을 보안하려면 전송 수준 보안만 사용하거나 전송 수준 보안과 인증 전용 메시지 보안을 함께 사용합니다.  
  
 SOAP 헤더는 전송 모드가 스트리밍으로 설정되어 있더라도 항상 버퍼링됩니다. 메시지 헤더는 `MaxBufferSize` 전송 할당량 크기를 초과할 수 없습니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]이 참조 설정을 [전송 할당량](../../../../docs/framework/wcf/feature-details/transport-quotas.md)합니다.  
  
## <a name="differences-between-buffered-and-streamed-transfers"></a>버퍼링 전송과 스트리밍 전송 사이의 차이점  
 전송 모드를 버퍼링 전송에서 스트리밍 전송으로 변경하면 TCP 및 명명된 파이프 전송의 기본 채널 셰이프도 함께 변경됩니다. 버퍼링 전송의 기본 채널 셰이프는 <xref:System.ServiceModel.Channels.IDuplexSessionChannel>입니다. 스트리밍 전송의 기본 채널은 <xref:System.ServiceModel.Channels.IRequestChannel> 및 <xref:System.ServiceModel.Channels.IReplyChannel>입니다. 서비스 계약을 통하지 않고 이러한 전송을 직접 사용하는 기존 응용 프로그램에서 전송 모드를 변경하려면 채널 팩터리 및 수신기에 대한 예상 채널 셰이프를 변경해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 스트리밍 사용](../../../../docs/framework/wcf/feature-details/how-to-enable-streaming.md)
