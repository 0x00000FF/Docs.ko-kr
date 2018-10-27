---
title: BindingElement 만들기
ms.date: 03/30/2017
ms.assetid: 01a35307-a41f-4ef6-a3db-322af40afc99
ms.openlocfilehash: 5b7fd3e88fa12a66e086906de6f0d7d6a7d1aa17
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2018
ms.locfileid: "49454462"
---
# <a name="creating-a-bindingelement"></a>BindingElement 만들기
바인딩 및 바인딩 요소 (확장 하는 개체 <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType> 및 <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>각각)은 Windows Communication Foundation (WCF) 응용 프로그램 모델이 채널 팩터리 및 채널 수신기와 연결 되는 장소입니다. 바인딩 없이 사용자 지정 채널을 사용 하 여 필요한 채널 수준 프로그래밍에 설명 된 대로 [서비스 채널 수준 프로그래밍](../../../../docs/framework/wcf/extending/service-channel-level-programming.md) 하 고 [클라이언트 채널 수준 프로그래밍](../../../../docs/framework/wcf/extending/client-channel-level-programming.md)합니다. 이 항목에서는 wcf에서의 개발 채널을 사용 하도록 설정 하려면 최소 요구 사항을 설명 된 <xref:System.ServiceModel.Channels.BindingElement> 채널 및 4 단계에 설명 된 대로 응용 프로그램에서 사용 [개발 채널](../../../../docs/framework/wcf/extending/developing-channels.md)합니다.  
  
## <a name="overview"></a>개요  
 만들기는 <xref:System.ServiceModel.Channels.BindingElement> 채널을 사용 하면 WCF 응용 프로그램에서 사용 하는 개발자에 대 한 합니다. <xref:System.ServiceModel.Channels.BindingElement> 개체에서 사용할 수는 <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> 채널의 정확한 형식 정보가 필요 없이 채널을 WCF 응용 프로그램을 연결 하는 클래스입니다.  
  
 한 번을 <xref:System.ServiceModel.Channels.BindingElement> 되었으면 만들어지면에 설명 된 나머지 채널 개발 단계를 수행 하 여 요구 사항에 따라 더 많은 기능을 설정할 수 있습니다. [개발 채널](../../../../docs/framework/wcf/extending/developing-channels.md)합니다.  
  
## <a name="adding-a-binding-element"></a>바인딩 요소 추가  
 사용자 지정 <xref:System.ServiceModel.Channels.BindingElement>를 구현하려면 <xref:System.ServiceModel.Channels.BindingElement>에서 상속된 클래스를 작성합니다. 예를 들어, 대용량 메시지를 여러 개의 청크로 나누고 반대쪽 끝에서 이를 다시 어셈블할 수 있는 `ChunkingChannel`을 개발한 경우 <xref:System.ServiceModel.Channels.BindingElement>를 구현하여 이를 사용하기 위해 바인딩을 구성하면 모든 바인딩에 이 채널을 사용할 수 있습니다. 이 항목의 나머지 부분에서는 바인딩 요소를 구현하기 위한 요구 사항을 설명하기 위해 `ChunkingChannel`을 사용합니다.  
  
 `ChunkingBindingElement`는 `ChunkingChannelFactory` 및 `ChunkingChannelListener`를 만듭니다. 또한 <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelFactory%2A> 및 <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelListener%2A> 구현을 재정의하고, 형식 매개 변수가<xref:System.ServiceModel.Channels.IDuplexSessionChannel>(이 예제에서는 이 채널 셰이프가 `ChunkingChannel`에서 지원하는 유일한 채널 셰이프임)인지 그리고 바인딩에 있는 다른 바인딩 요소가 이 채널 셰이프를 지원하는지를 확인합니다.  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A>는 요청한 채널 셰이프를 만들 수 있는지 먼저 확인한 다음 청크 분할되는 메시지 동작 목록을 가져옵니다. 그런 다음 새로운 `ChunkingChannelFactory`를 만들고 이를 내부 채널 팩터리에 전달합니다. 전송 바인딩 요소를 만드는 경우 이 요소가 바인딩 스택의 마지막 요소이므로 채널 수신기나 채널 팩터리를 만들어야 합니다.  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A>에서도 `ChunkingChannelListener`를 만들어 내부 채널 수신기에 전달하는 구현 방법이 비슷합니다.  
  
 전송 채널을 사용 하는 또 다른 예로 [전송: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) 샘플에서는 다음 재정의 제공 합니다.  
  
 이 샘플에서 바인딩 요소는 `UdpTransportBindingElement`에서 파생된 <xref:System.ServiceModel.Channels.TransportBindingElement>로, 채널과 연결되는 팩터리 작성을 위한 다음 메서드를 재정의합니다.  
  
```csharp  
public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)  
{  
    return (IChannelFactory<TChannel>)(object)new UdpChannelFactory(this, context);  
}  
  
public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)  
{  
    return (IChannelListener<TChannel>)(object)new UdpChannelListener(this, context);  
}  
```  
  
 이 바인딩 요소에는 `BindingElement`를 복제하고 soap.udp 체계를 반환하는 멤버도 포함됩니다.  
  
#### <a name="protocol-binding-elements"></a>프로토콜 바인딩 요소  
 새 바인딩 요소는 포함된 바인딩 요소를 바꾸거나 확대할 수 있으며 새 전송, 인코딩 또는 더 높은 수준의 프로토콜을 추가할 수 있습니다. 새 프로토콜 바인딩 요소를 만들려면 먼저 <xref:System.ServiceModel.Channels.BindingElement> 클래스를 확장합니다. 최소한 다음을 구현 해야 합니다 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A?displayProperty=nameWithType> 구현 및 합니다 `ChannelProtectionRequirements` 를 사용 하 여 <xref:System.ServiceModel.Channels.IChannel.GetProperty%2A?displayProperty=nameWithType>. 이렇게 하면 이 바인딩 요소에 대해 <xref:System.ServiceModel.Security.ChannelProtectionRequirements>가 반환됩니다.  자세한 내용은 <xref:System.ServiceModel.Security.ChannelProtectionRequirements>을 참조하세요.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>은 이 바인딩 요소의 새 복사본을 반환합니다. 바인딩 요소 작성자는 기본 복사 생성자를 호출한 다음 이 클래스의 추가 필드를 복제하는 복사 생성자를 사용하여 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>을 구현하는 것이 좋습니다.  
  
#### <a name="transport-binding-elements"></a>전송 바인딩 요소  
 새 전송 바인딩 요소를 만들려면 <xref:System.ServiceModel.Channels.TransportBindingElement> 인터페이스를 확장합니다. 그런 다음 최소한 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> 메서드와 <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A?displayProperty=nameWithType> 속성을 구현해야 합니다.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> – 이 바인딩 요소의 새 복사본을 반환합니다.  바인딩 요소 작성자는 기본 복사 생성자를 호출한 다음 이 클래스의 추가 필드를 복제하는 복사 생성자를 통해 Clone을 구현하는 것이 좋습니다.  
  
 <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> – <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> get 속성은 바인딩 요소로 표현되는 전송 프로토콜의 URI 체계를 반환합니다. 예를 들어 합니다 <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> 하며 <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType> 는 각각의 "http" 및 "net.tcp"를 반환 <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> 속성.  
  
#### <a name="encoding-binding-elements"></a>바인딩 요소 인코딩  
 새 인코딩 바인딩 요소를 만들려면 먼저 <xref:System.ServiceModel.Channels.BindingElement> 클래스를 확장하고 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType> 클래스를 구현합니다. 그런 다음 최소한 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>, <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A?displayProperty=nameWithType> 메서드와 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A?displayProperty=nameWithType> 속성을 구현해야 합니다.  
  
-   <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>. 이 바인딩 요소의 새 복사본을 반환합니다. 바인딩 요소 작성자는 기본 복사 생성자를 호출한 다음 이 클래스의 추가 필드를 복제하는 복사 생성자를 사용하여 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>을 구현하는 것이 좋습니다.  
  
-   <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A>. 새 인코더를 구현하는 실제 클래스에 핸들을 제공하고 <xref:System.ServiceModel.Channels.MessageEncoderFactory>를 확장하는 <xref:System.ServiceModel.Channels.MessageEncoder>를 반환합니다. 자세한 내용은 <xref:System.ServiceModel.Channels.MessageEncoderFactory> 및 <xref:System.ServiceModel.Channels.MessageEncoder>를 참조하세요.  
  
-   <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A>. 이 인코딩에 사용되는 <xref:System.ServiceModel.Channels.MessageVersion>을 반환합니다. 이는 사용 중인 SOAP 및 WS-Addressing 버전을 나타냅니다.  
  
 사용자 정의 인코딩 바인딩 요소에 대한 선택적 메서드 및 속성의 전체 목록은 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>를 참조하십시오.  
  
 새 바인딩 요소를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [Creating User-Defined 바인딩](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)합니다.  
  
 채널에 대 한 바인딩 요소를 만든 후에 반환 된 [개발 채널](../../../../docs/framework/wcf/extending/developing-channels.md) 것인지에 바인딩 요소에 구성 파일 지원을 추가 하는 경우 및 메타 데이터 게시 지원을 추가 하는 방법 참조 항목 및 바인딩 요소를 사용 하는 사용자 정의 바인딩 생성 방법 및 여부.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.BindingElement>  
 [채널 개발](../../../../docs/framework/wcf/extending/developing-channels.md)  
 [전송: UDP](../../../../docs/framework/wcf/samples/transport-udp.md)
