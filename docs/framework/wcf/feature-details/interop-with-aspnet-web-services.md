---
title: ASP.NET 웹 서비스와의 상호 운용성
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: 16e22a091b88d12abccb063d2407db82460458c6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638603"
---
# <a name="interoperability-with-aspnet-web-services"></a><span data-ttu-id="de2db-102">ASP.NET 웹 서비스와의 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="de2db-102">Interoperability with ASP.NET Web Services</span></span>
<span data-ttu-id="de2db-103">간의 상호 운용성 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 두 기술을 사용 하 여 구현 된 서비스는 WS에 따르는지 확인 하 여 웹 서비스와 Windows Communication Foundation (WCF) 웹 서비스를 달성할 수-Basic Profile 1.1 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="de2db-103">Interoperability between [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services and Windows Communication Foundation (WCF) Web services can be achieved by ensuring that services implemented using both technologies conform to the WS-I Basic Profile 1.1 specification.</span></span> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] <span data-ttu-id="de2db-104">웹 서비스 따르는-는 WCF 시스템 제공 바인딩을 사용 하 여 WCF 클라이언트와 상호 운용 가능한 Basic Profile 1.1 <xref:System.ServiceModel.BasicHttpBinding>합니다.</span><span class="sxs-lookup"><span data-stu-id="de2db-104">Web services that conform to WS-I Basic Profile 1.1 are interoperable with WCF clients by using WCF system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
 <span data-ttu-id="de2db-105">다음 예제 코드에 표시된 것처럼 [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] 및 <xref:System.Web.Services.WebService> 특성을 클래스가 아니라 인터페이스에 추가하고 클래스를 기록하는 <xref:System.Web.Services.WebMethodAttribute> 옵션을 사용하여 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="de2db-105">Use [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] option of adding the <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> attributes to an interface rather than to a class, and writing a class to implement the interface, as shown in the following sample code.</span></span>  
  
```  
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
  
 <span data-ttu-id="de2db-106"><xref:System.Web.Services.WebService> 특성을 가진 인터페이스는 서비스에 의해 수행되는 작업에 대한 계약을 구성하며, 같은 계약을 다른 방식으로 구현하는 다양한 클래스에서 이 서비스를 다시 사용할 수 있으므로 이 옵션을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="de2db-106">Using this option is preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>  
  
 <span data-ttu-id="de2db-107"><xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> HTTP 헤더가 아닌 SOAP 메시지 본문 요소의 정규화된 이름을 기반으로 메서드로 메시지를 라우팅하려면 `SOAPAction` 특성을 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="de2db-107">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the `SOAPAction` HTTP header.</span></span> <span data-ttu-id="de2db-108">WCF를 사용 하는 `SOAPAction` 메시지 라우팅에 대 한 HTTP 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="de2db-108">WCF uses the `SOAPAction` HTTP header for routing messages.</span></span>  
  
 <span data-ttu-id="de2db-109"><xref:System.Xml.Serialization.XmlSerializer>에서 기본적으로 형식을 serialize하는 XML은 해당 XML에 대한 네임스페이스가 명시적으로 정의되어 있는 경우 <xref:System.Runtime.Serialization.DataContractSerializer>에서 형식을 serialize하는 XML과 의미상 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="de2db-109">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="de2db-110">사용에 대 한 데이터 형식을 정의 하는 경우 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]웹 서비스를 WCF를 채택 하기 위해에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="de2db-110">When defining a data type for use with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Web services in anticipation of adopting WCF, do the following:</span></span>  
  
- <span data-ttu-id="de2db-111">XML 스키마가 아닌 .NET Framework 클래스를 사용하여 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="de2db-111">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
- <span data-ttu-id="de2db-112">클래스에는 <xref:System.SerializableAttribute> 및 <xref:System.Xml.Serialization.XmlRootAttribute>만 추가하며, 형식에 대한 네임스페이스를 명시적으로 정의하려면 후자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="de2db-112">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="de2db-113">.NET Framework 클래스를 XML로 변환하는 방법을 제어하려면 <xref:System.Xml.Serialization> 네임스페이스로부터 특성을 추가하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="de2db-113">Do not add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
- <span data-ttu-id="de2db-114">이 방법을 채택하면 전송을 위해 클래스가 serialize되도록 XML을 크게 변경하지 않고 나중에 <xref:System.Runtime.Serialization.DataContractAttribute> 및 <xref:System.Runtime.Serialization.DataMemberAttribute>를 추가하여 .NET 클래스를 데이터 계약으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de2db-114">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="de2db-115">메시지에서 사용 된 형식은 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 서비스 WCF 응용 프로그램에 다른 이점과 함께 WCF 응용 프로그램에서 더 나은 성능으로 데이터 계약으로 처리 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de2db-115">The types used in messages by [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services can be processed as data contracts by WCF applications, yielding, among other benefits, better performance in WCF applications.</span></span>  
  
 <span data-ttu-id="de2db-116">IIS(인터넷 정보 서비스)에서 제공하는 인증 옵션은 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="de2db-116">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="de2db-117">WCF 클라이언트 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de2db-117">WCF clients do not support them.</span></span> <span data-ttu-id="de2db-118">서비스를 보호 해야 하는 경우 이러한 옵션은 강력 하며 표준 프로토콜을 기반으로 하기 때문에 WCF에서 제공 하는 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="de2db-118">If a service must be secured, use the options provided by WCF, because these options are robust and are based on standard protocols.</span></span>  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a><span data-ttu-id="de2db-119">ServiceModel HttpModule 로드에 의한 성능 영향</span><span class="sxs-lookup"><span data-stu-id="de2db-119">Performance impact caused by loading the ServiceModel HttpModule</span></span>  
 <span data-ttu-id="de2db-120">.NET Framework 3.0의 경우 WCF `HttpModule`은 모든 ASP.NET 응용 프로그램에서 WCF를 사용할 수 있도록 루트 Web.config 파일에 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de2db-120">In the .NET Framework 3.0, the WCF `HttpModule` was installed in the root Web.config file such that every ASP.NET application was WCF enabled.</span></span> <span data-ttu-id="de2db-121">이는 성능에 영향을 줄 수 있기 때문에 다음 예제에서처럼 Web.config 파일에 대해 `ServiceModel`을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de2db-121">This might affect performance, so you can remove `ServiceModel` for the Web.config file as shown in the following example.</span></span>  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="de2db-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="de2db-122">See also</span></span>

- [<span data-ttu-id="de2db-123">방법: ASP.NET 웹 서비스 클라이언트와 상호 운용 하도록 WCF 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="de2db-123">How to: Configure WCF Service to Interoperate with ASP.NET Web Service Clients</span></span>](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
