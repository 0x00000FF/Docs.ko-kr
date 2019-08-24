---
title: 채널 개발
ms.date: 03/30/2017
ms.assetid: 0513af9f-a0c2-457b-9a50-5b6bfee48513
ms.openlocfilehash: 44fb0da52c60b900c41b7b497861c12ed72d8ffc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61858067"
---
# <a name="developing-channels"></a>채널 개발
Windows Communication Foundation (WCF)를 사용 하 여 사용할 수 있는 프로토콜 또는 전송 채널을 개발 하려면 응용 프로그램 계층에는 여러 단계가 필요 합니다. 이 항목에서는 이러한 단계에 대해 설명하고 자세한 내용을 참조할 수 있는 구체적인 항목을 알려 줍니다. 이 항목에 나와 있는 다양 한 형식과 채널 모델을 이해 하려면 [채널 모델 개요](../../../../docs/framework/wcf/extending/channel-model-overview.md)합니다. 완전 한 전송 채널 샘플을 보려면 [전송 합니다. UDP](../../../../docs/framework/wcf/samples/transport-udp.md).  
  
## <a name="the-channel-development-task-list"></a>채널 개발 작업 목록  
 사용자 정의 채널을 만드는 단계는 다음과 같습니다. 모든 채널에 대해 다음을 수행해야 합니다.  
  
1. <xref:System.ServiceModel.Channels.IOutputChannel> 및 <xref:System.ServiceModel.Channels.IInputChannel>에서 지원할 채널 메시지 교환 패턴(<xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IRequestChannel>, <xref:System.ServiceModel.Channels.IReplyChannel>, <xref:System.ServiceModel.Channels.IChannelFactory> 또는 <xref:System.ServiceModel.Channels.IChannelListener>)과 이러한 인터페이스의 세션 변형에 대한 지원 여부를 결정합니다. 자세한 내용은 참조 하세요 [메시지 교환 패턴 선택](../../../../docs/framework/wcf/extending/choosing-a-message-exchange-pattern.md)합니다.  
  
2. 메시지 교환 패턴을 지원하는 채널 팩터리와 수신기(<xref:System.ServiceModel.Channels.IChannelFactory> 및 <xref:System.ServiceModel.Channels.IChannelListener>)를 만듭니다. 팩터리 개발에 대 한 자세한 내용은 참조 하세요. [클라이언트: 채널 팩터리 및 채널](../../../../docs/framework/wcf/extending/client-channel-factories-and-channels.md)합니다. 수신기 개발에 대 한 자세한 내용은 참조 하세요. [서비스: 채널 수신기 및 채널](../../../../docs/framework/wcf/extending/service-channel-listeners-and-channels.md)합니다.  
  
3. 네트워크 관련 예외가 <xref:System.TimeoutException?displayProperty=nameWithType> 또는 <xref:System.ServiceModel.CommunicationException>의 올바른 파생 클래스로 정규화되는지 확인합니다. 자세한 내용은 참조 하세요 [예외 처리 및 오류](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)합니다.  
  
4. 애플리케이션 계층에서 사용할 수 있도록 하려면 사용자 지정 채널을 채널 스택에 추가하는 <xref:System.ServiceModel.Channels.BindingElement>를 추가합니다. 자세한 내용은 [BindingElement 만들기](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md)합니다.  
  
 애플리케이션 계층에서 좀 더 완벽한 지원이 가능하게 하려면 다음의 단계를 추가로 수행해야 합니다.  
  
1. 새 바인딩 요소가 구성 시스템에 노출되도록 바인딩 요소 확장명 섹션을 추가합니다. 자세한 내용은 [구성 및 메타 데이터 지원을](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)합니다.  
  
2. 기능을 다른 엔드포인트에 전달하도록 메타데이터 확장을 추가합니다. 자세한 내용은 [구성 및 메타 데이터 지원을](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)합니다.  
  
3. 올바르게 정의된 프로필에 따라 바인딩 요소 스택을 미리 구성하는 바인딩을 추가합니다. 자세한 내용은 [Creating User-Defined 바인딩](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)합니다.  
  
4. 바인딩이 구성 시스템에 노출되도록 바인딩 섹션 및 바인딩 구성 요소를 추가합니다. 자세한 내용은 [구성 및 메타 데이터 지원을](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [바인딩 확장](../../../../docs/framework/wcf/extending/extending-bindings.md)
