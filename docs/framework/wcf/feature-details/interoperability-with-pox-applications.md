---
title: POX 응용 프로그램과의 상호 운용성
ms.date: 03/30/2017
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
ms.openlocfilehash: 7522233723b6b91d5a7b27d3f82ca328e29ce3f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33494202"
---
# <a name="interoperability-with-pox-applications"></a>POX 응용 프로그램과의 상호 운용성
"Plain Old XML" (POX) 응용 프로그램은 SOAP 봉투 내에 포함 되지 않은 XML 응용 프로그램 데이터만 포함 하는 원시 HTTP 메시지를 교환 하 여 통신 합니다. Windows Communication Foundation (WCF) 서비스와 POX 메시지를 사용 하는 클라이언트에 제공할 수 있습니다. 서비스에서 WCF 웹 브라우저 같은 클라이언트에 끝점을 노출 하는 서비스 및 스크립팅 언어 POX 메시지를 구현 하 사용할 수 있습니다. 클라이언트에서 POX 기반 서비스와 통신 하는 클라이언트를 구현 하는 WCF 프로그래밍 모델을 사용할 수 있습니다.  
  
> [!NOTE]
>  이 문서는 원래 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0용으로 작성되었습니다.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.5는 POX 응용 프로그램 작업에 대한 지원을 기본적으로 제공합니다. 참조에 대 한 자세한 내용은 [WCF 웹 HTTP 프로그래밍 모델](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
  
## <a name="pox-programming-with-wcf"></a>WCF를 사용한 POX 프로그래밍  
 POX 메시지를 사용 하 여 HTTP를 통해 통신 하는 WCF 서비스는 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)합니다.  
  
```xml  
<customBinding>  
   <binding name="poxServerBinding">  
       <textMessageEncoding messageVersion="None" />  
       <httpTransport />  
   </binding>  
</customBinding>  
```  
  
 이 사용자 지정 바인딩에는 다음과 같은 두 가지 요소가 포함되어 있습니다.  
  
-   [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) 및  
  
-   [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)합니다.  
  
 WCF 텍스트 메시지 인코더는 특별히 사용 하도록 구성 하는 표준은 <xref:System.ServiceModel.Channels.MessageVersion.None%2A> 값으로, XML 메시지 페이로드를 도착 하지 않으면 SOAP 봉투에 래핑됩니다 처리할 수 있습니다.  
  
 POX 메시지를 사용 하 여 HTTP를 통해 통신 하는 WCF 클라이언트 (다음 명령 코드에 표시) 하는 유사한 바인딩을 사용 합니다.  
  
```  
private static Binding CreatePoxBinding()  
{  
    TextMessageEncodingBindingElement encoder =   
    new TextMessageEncodingBindingElement( MessageVersion.None, Encoding.UTF8 );  
    HttpTransportBindingElement transport = new HttpTransportBindingElement();  
    transport.ManualAddressing = true;  
    return new CustomBinding( new BindingElement[] { encoder, transport } );  
}   
```  
  
 POX 클라이언트는 메시지를 보내는 대상 URI를 명시적으로 지정해야 하기 때문에 일반적으로 POX 클라이언트는 요소에서 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> 속성을 <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A>로 설정하여 `true`를 수동 주소 지정 모드로 구성해야 합니다. 이를 통해 메시지 주소를 응용 프로그램 코드에 따라 명시적으로 지정할 수 있으며 응용 프로그램이 메시지를 다른 HTTP URI로 보낼 때마다 새 <xref:System.ServiceModel.ChannelFactory>를 만들 필요가 없습니다.  
  
 POX 메시지는 중요한 프로토콜 정보를 전달하기 위해 SOAP 헤더를 사용하지 않기 때문에 POX 클라이언트 및 서비스가 메시지를 보내거나 받는 데 사용되는 기본 HTTP 요청 일부를 종종 조작해야 합니다. HTTP 헤더 및 상태 코드와 같은 HTTP 관련 프로토콜 정보는 두 개의 클래스를 통해 WCF 프로그래밍 모델에 표시 됩니다.  
  
-   <xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, 여기에는 HTTP 메서드 및 요청 헤더와 같은 HTTP 요청에 대한 정보가 포함됩니다.  
  
-   <xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, 여기에는 HTTP 응답 헤더뿐만 아니라 HTTP 상태 코드 및 상태 설명과 같은 HTTP 응답에 대한 정보가 포함됩니다.  
  
 다음 코드 예제에서는 주소가 지정 된 HTTP GET 요청 메시지를 만드는 방법을 보여 줍니다. http://localhost:8100/customers합니다.  
  
```  
Message request = Message.CreateMessage( MessageVersion.None, String.Empty );  
request.Headers.To = "http://localhost:8100/customers";  
  
HttpRequestMessageProperty property = new HttpRequestMessageProperty();  
property.Method = "GET";  
property.SuppressEntityBody = true;  
request.Properties.Add( HttpRequestMessageProperty.Name, property );  
```  
  
 먼저 <xref:System.ServiceModel.Channels.Message>를 호출하여 빈 요청 <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>가 만들어집니다. <xref:System.ServiceModel.Channels.MessageVersion.None%2A> 매개 변수는 SOAP 봉투가 필요 없음을 나타내는 데 사용되며 <xref:System.String.Empty> 매개 변수는 작업으로 전달됩니다. 그런 다음 <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> 헤더를 원하는 URI로 설정하여 요청 메시지의 주소가 지정됩니다. 그런 후 <xref:System.ServiceModel.Channels.HttpRequestMessageProperty>가 만들어지고 <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A>가 HTTP verb GET 메서드로 설정되며, <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A>가 `true`로 설정되어 나가는 HTTP 요청 메시지의 본문에 보낼 데이터가 없어야 함을 나타냅니다. 마지막으로, HTTP 전송이 요청을 보내는 방법에 영향을 줄 수 있도록 요청 속성이 요청 메시지의 <xref:System.ServiceModel.Channels.Message.Properties%2A> 컬렉션에 추가됩니다. 그런 다음 메시지를 <xref:System.ServiceModel.Channels.IRequestChannel>의 해당 인스턴스를 통해 보낼 준비를 완료합니다.  
  
 서비스에 대해 유사한 방법을 사용하여 들어오는 메시지에서 <xref:System.ServiceModel.Channels.HttpRequestMessageProperty>를 추출하고 응답을 생성할 수 있습니다.
