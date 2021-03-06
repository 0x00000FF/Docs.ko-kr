---
title: ASP.NET 웹 서비스와의 상호 운용성
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: 41810d8044e4b7ff3193950a914edbf1e61cffb1
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464086"
---
# <a name="interoperability-with-aspnet-web-services"></a>ASP.NET 웹 서비스와의 상호 운용성
ASP.NET 웹 서비스와 WCF(Windows 통신 재단) 웹 서비스 간의 상호 운용성은 두 기술을 사용하여 구현된 서비스가 WS-I 기본 프로필 1.1 사양을 준수하도록 함으로써 달성될 수 있습니다. WS-I 기본 프로필 1.1을 준수하는 ASP.NET 웹 서비스는 WCF 시스템에서 제공하는 바인딩을 <xref:System.ServiceModel.BasicHttpBinding>사용하여 WCF 클라이언트와 상호 운용할 수 있습니다.  
  
 다음 샘플 코드와 같이 <xref:System.Web.Services.WebService> 클래스가 아닌 인터페이스에 및 <xref:System.Web.Services.WebMethodAttribute> 특성을 추가하고 클래스를 작성하여 인터페이스를 구현하는 ASP.NET 2.0 옵션을 사용합니다.  
  
```csharp
[WebService]  
public interface IEcho  
{  
    [WebMethod]  
    string Echo(string input);  
}  
  
public class Service : IEcho  
{  
  
   public string Echo(string input)  
   {  
        return input;  
    }  
}  
```  
  
 <xref:System.Web.Services.WebService> 특성을 가진 인터페이스는 서비스에 의해 수행되는 작업에 대한 계약을 구성하며, 같은 계약을 다른 방식으로 구현하는 다양한 클래스에서 이 서비스를 다시 사용할 수 있으므로 이 옵션을 사용하는 것이 좋습니다.  
  
 <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> HTTP 헤더가 아닌 SOAP 메시지 본문 요소의 정규화된 이름을 기반으로 메서드로 메시지를 라우팅하려면 `SOAPAction` 특성을 사용하지 마십시오. WCF는 `SOAPAction` 메시지를 라우팅하기 위해 HTTP 헤더를 사용합니다.  
  
 <xref:System.Xml.Serialization.XmlSerializer>에서 기본적으로 형식을 serialize하는 XML은 해당 XML에 대한 네임스페이스가 명시적으로 정의되어 있는 경우 <xref:System.Runtime.Serialization.DataContractSerializer>에서 형식을 serialize하는 XML과 의미상 동일합니다. WCF 를 채택할 때 ASP.NETWeb 서비스에서 사용할 데이터 형식을 정의할 때다음을 수행합니다.  
  
- XML 스키마가 아닌 .NET Framework 클래스를 사용하여 형식을 정의합니다.  
  
- 클래스에는 <xref:System.SerializableAttribute> 및 <xref:System.Xml.Serialization.XmlRootAttribute>만 추가하며, 형식에 대한 네임스페이스를 명시적으로 정의하려면 후자를 사용합니다. .NET Framework 클래스를 XML로 변환하는 방법을 제어하려면 <xref:System.Xml.Serialization> 네임스페이스로부터 특성을 추가하지 마십시오.  
  
- 이 방법을 채택하면 전송을 위해 클래스가 serialize되도록 XML을 크게 변경하지 않고 나중에 <xref:System.Runtime.Serialization.DataContractAttribute> 및 <xref:System.Runtime.Serialization.DataMemberAttribute>를 추가하여 .NET 클래스를 데이터 계약으로 만들 수 있습니다. ASP.NET 웹 서비스에서 메시지에 사용되는 형식은 WCF 응용 프로그램에서 데이터 계약으로 처리될 수 있으며, WCF 응용 프로그램의 성능이 향상됩니다.  
  
 IIS(인터넷 정보 서비스)에서 제공하는 인증 옵션은 사용하지 마십시오. WCF 클라이언트는 지원하지 않습니다. 서비스를 보호해야 하는 경우 이러한 옵션은 견고하고 표준 프로토콜을 기반으로 하므로 WCF에서 제공하는 옵션을 사용합니다.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>ServiceModel HttpModule 로드에 의한 성능 영향  
 .NET Framework 3.0의 경우 WCF `HttpModule`은 모든 ASP.NET 애플리케이션에서 WCF를 사용할 수 있도록 루트 Web.config 파일에 설치되어 있습니다. 이는 성능에 영향을 줄 수 있기 때문에 다음 예제에서처럼 Web.config 파일에 대해 `ServiceModel`을 제거할 수 있습니다.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
</httpModules>
```  
  
## <a name="see-also"></a>참조

- [방법: ASP.NET 웹 서비스 클라이언트와 상호 운용하도록 WCF 서비스 구성](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
