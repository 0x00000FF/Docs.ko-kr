---
title: 'Windows Communication Foundation 채택에 대한 기대: 향후 마이그레이션 간소화'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: 09bbb11c58992f0fabcb822f5f3d88fef273bea9
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425280"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a><span data-ttu-id="d4200-102">Windows Communication Foundation 채택에 대한 기대: 향후 마이그레이션 간소화</span><span class="sxs-lookup"><span data-stu-id="d4200-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>
<span data-ttu-id="d4200-103">새 ASP.NET 응용 프로그램을 WCF의 향후 마이그레이션이 원활 해지 되도록 앞에서 설명한 권장 뿐만 아니라 다음 권장 사항을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-103">To ensure an easier future migration of new ASP.NET applications to WCF, follow the preceding recommendations as well as the following recommendations.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="d4200-104">프로토콜</span><span class="sxs-lookup"><span data-stu-id="d4200-104">Protocols</span></span>  
 <span data-ttu-id="d4200-105">SOAP 1.2에 대한 ASP.NET 2.0 지원을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-105">Disable ASP.NET 2.0’s support for SOAP 1.2:</span></span>  
  
```xml  
<configuration>  
     <system.web>  
      <webServices >  
          <protocols>  
           <remove name="HttpSoap12"/>  
          </protocols>    
      </webServices>  
     </system.web>   
</configuration>  
```  
  
 <span data-ttu-id="d4200-106">WCF 메시지 SOAP 1.1과 SOAP 1.2 처럼 서로 다른 프로토콜을 따르는 다양 한 끝점을 사용 하 여 이동할 필요 하기 때문에 이렇게 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-106">Doing so is advisable because WCF requires messages conforming to different protocols, like SOAP 1.1 and SOAP 1.2, to go by using different endpoints.</span></span> <span data-ttu-id="d4200-107">ASP.NET 2.0 웹 서비스는 SOAP 1.1과 SOAP 1.2 될 수 없습니다. 기본 구성으로가 모두를 지원 하도록 구성 되어 확실히 수는 원래 주소의 단일 WCF 끝점으로 전달 마이그레이션된 경우 ASP.NET web 모든 호환 되어야 서비스의 기존 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-107">If an ASP.NET 2.0 Web service is configured to support both SOAP 1.1 and SOAP 1.2, which is the default configuration, then it cannot be migrated forward to a single WCF endpoint at the original address that would be certainly be compatible with all of the ASP.NET Web service’s existing clients.</span></span> <span data-ttu-id="d4200-108">또한 SOAP 1.1 대신 1.2를 선택하면 서비스의 클라이언트가 보다 엄격하게 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-108">Also choosing SOAP 1.2 instead of 1.1 will more severely restrict the clientele of the service.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="d4200-109">서비스 개발</span><span class="sxs-lookup"><span data-stu-id="d4200-109">Service Development</span></span>  
 <span data-ttu-id="d4200-110">WCF를 사용 하면 적용 하 여 서비스 계약을 정의 하는 <xref:System.ServiceModel.ServiceContractAttribute> 인터페이스 또는 클래스.</span><span class="sxs-lookup"><span data-stu-id="d4200-110">WCF allows you to define service contracts by applying the <xref:System.ServiceModel.ServiceContractAttribute> either to interfaces or to classes.</span></span> <span data-ttu-id="d4200-111">이 특성을 인터페이스에 적용하면 원하는 수의 클래스에서 다양하게 구현할 수 있는 계약의 정의가 생성되므로 클래스보다는 인터페이스에 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-111">It is recommended to apply the attribute to an interface rather than to a class, because doing so creates a definition of a contract that can be variously implemented by any number of classes.</span></span> <span data-ttu-id="d4200-112">ASP.NET 2.0은 클래스뿐만 아니라 인터페이스에도 <xref:System.Web.Services.WebService> 특성을 적용하는 옵션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-112">ASP.NET 2.0 supports the option of applying the <xref:System.Web.Services.WebService> attribute to interfaces as well as classes.</span></span> <span data-ttu-id="d4200-113">그러나 이미 설명했듯이 ASP.NET 2.0에는 <xref:System.Web.Services.WebService> 특성이 클래스가 아닌 인터페이스에 적용될 경우 이 특성의 Namespace 매개 변수가 아무런 효과가 없다는 결점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-113">However, as mentioned already, there is a defect in ASP.NET 2.0, by which the Namespace parameter of the <xref:System.Web.Services.WebService> attribute has no effect when that attribute is applied to an interface rather than a class.</span></span> <span data-ttu-id="d4200-114">기본값에서 서비스의 네임 스페이스를 수정 하는 것이 일반적으로 좋습니다 이므로 `http://tempuri.org`의 Namespace 매개 변수를 사용 합니다 <xref:System.Web.Services.WebService> 특성을 적용 하 여 ASP.NET 웹 서비스 정의 계속 해야 하나는 <xref:System.ServiceModel.ServiceContractAttribute> 인터페이스 또는 클래스에 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-114">Since it is generally advisable to modify the namespace of a service from the default value, `http://tempuri.org`, using the Namespace parameter of the <xref:System.Web.Services.WebService> attribute, one should continue defining ASP.NET Web Services by applying the <xref:System.ServiceModel.ServiceContractAttribute> attribute either to interfaces or to classes.</span></span>  
  
- <span data-ttu-id="d4200-115">이러한 인터페이스를 정의하는 메서드에 코드를 가능한 한 적게 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-115">Have as little code as possible in the methods by which those interfaces are defined.</span></span> <span data-ttu-id="d4200-116">메서드의 작업을 다른 클래스에 위임하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-116">Have them delegate their work to other classes.</span></span> <span data-ttu-id="d4200-117">새 WCF 서비스 유형 다음 위임할 수도 클래스에는 상당한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-117">New WCF service types could then also delegate their substantive work to those classes.</span></span>  
  
- <span data-ttu-id="d4200-118">`MessageName`의 <xref:System.Web.Services.WebMethodAttribute> 매개 변수를 사용하여 서비스 작업에 명시적 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-118">Provide explicit names for the operations of a service using the `MessageName` parameter of the <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     <span data-ttu-id="d4200-119">ASP.NET에서 작업에 대 한 기본 이름을 WCF에서 제공 된 기본 이름과에서 다르기 때문에 이렇게 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-119">Doing so is important, because the default names for operations in ASP.NET are different from the default names supplied by WCF.</span></span> <span data-ttu-id="d4200-120">명시적 이름을 제공함으로써 기본 이름을 사용하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-120">By providing explicit names, you avoid relying on the default ones.</span></span>  
  
- <span data-ttu-id="d4200-121">WCF의 다형적 메서드를 사용 하 여 구현 작업을 지원 하지 않으므로 다형 메서드로 ASP.NET 웹 서비스 작업을 구현 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-121">Do not implement ASP.NET Web service operations with polymorphic methods, because WCF does not support implementing operations with polymorphic methods.</span></span>  
  
- <span data-ttu-id="d4200-122"><xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>를 사용하여 HTTP 요청을 메서드로 라우트할 SOAPAction HTTP 헤더에 명시적 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-122">Use the <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> to provide explicit values for the SOAPAction HTTP headers by which HTTP requests will be routed to methods.</span></span>  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     <span data-ttu-id="d4200-123">이 접근 방식을 ASP.NET 및 WCF는 동일한 사용 된 SOAPAction 값을 기본값에 의존 하지 우회 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-123">Taking this approach will circumvent having to rely on the default SOAPAction values used by ASP.NET and WCF being the same.</span></span>  
  
- <span data-ttu-id="d4200-124">SOAP 확장을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d4200-124">Avoid using SOAP extensions.</span></span> <span data-ttu-id="d4200-125">SOAP 확장이 필요한 경우 목적이 있는 것으로 간주 되는 WCF에서 이미 제공 하는 기능 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-125">If SOAP extensions are required, then determine whether the purpose for which they are being considered is a feature that is already provided by WCF.</span></span> <span data-ttu-id="d4200-126">실제로 이것이 경우 당장은 바로 WCF를 채택 하지.</span><span class="sxs-lookup"><span data-stu-id="d4200-126">If that is indeed the case, then reconsider the choice to not adopt WCF right away.</span></span>  
  
## <a name="state-management"></a><span data-ttu-id="d4200-127">상태 관리</span><span class="sxs-lookup"><span data-stu-id="d4200-127">State Management</span></span>  
 <span data-ttu-id="d4200-128">서비스의 상태를 유지하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d4200-128">Avoid having to maintain state in services.</span></span> <span data-ttu-id="d4200-129">응용 프로그램의 확장성을 떨어뜨리는 경향이 상태를 유지 하는 할 뿐만 아니라 WCF는 ASP.NET 호환 모드에서 ASP.NET 메커니즘을 지원 하지만 ASP.NET 및 WCF의 상태 관리 메커니즘은 매우 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-129">Not only does maintaining state tend to compromise the scalability of an application, but the state management mechanisms of ASP.NET and WCF are very different, although WCF does support the ASP.NET mechanisms in ASP.NET compatibility mode.</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="d4200-130">예외 처리</span><span class="sxs-lookup"><span data-stu-id="d4200-130">Exception Handling</span></span>  
 <span data-ttu-id="d4200-131">서비스에서 보내고 받을 데이터 형식의 구조를 디자인할 때 클라이언트로 전달하려는 서비스에서 발생할 수 있는 다양한 종류의 예외를 표시하기 위한 구조도 디자인합니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-131">In designing the structures of the data types to be sent and received by a service, also design structures to represent the various types of exceptions that might occur within a service that one might wish to convey to a client.</span></span>  
  
```csharp  
[Serializable]  
[XmlRoot(Namespace="ExplicitNamespace", IsNullable=true)]  
public partial class AnticipatedException 
{ 
    private string anticipatedExceptionInformationField;  

    public string AnticipatedExceptionInformation 
    {  
        get {   
            return this.anticipatedExceptionInformationField;  
        }  
        set {  
            this.anticipatedExceptionInformationField = value;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="d4200-132">다음과 같이 해당 클래스에 자신을 XML로 serialize할 수 있는 기능을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-132">Give such classes the ability to serialize themselves to XML:</span></span>  
  
```csharp  
public XmlNode ToXML()  
{  
     XmlSerializer serializer = new XmlSerializer(  
      typeof(AnticipatedException));  
     MemoryStream memoryStream = new MemoryStream();  
     XmlTextWriter writer = new XmlTextWriter(  
     memoryStream, UnicodeEncoding.UTF8);  
     serializer.Serialize(writer, this);  
     XmlDocument document = new XmlDocument();  
     document.LoadXml(new string(  
     UnicodeEncoding.UTF8.GetChars(  
     memoryStream.GetBuffer())).Trim());  
    return document.DocumentElement;  
}  
```  
  
 <span data-ttu-id="d4200-133">그러면 해당 클래스를 사용하여 명시적으로 throw된 <xref:System.Web.Services.Protocols.SoapException> 인스턴스에 대한 자세한 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-133">The classes can then be used to provide the details for explicitly thrown <xref:System.Web.Services.Protocols.SoapException> instances:</span></span>  
  
```csharp  
AnticipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 <span data-ttu-id="d4200-134">이러한 예외 클래스는 WCF를 사용 하 여 쉽게 다시 사용할 <xref:System.ServiceModel.FaultException%601> 새 시키려면 클래스 `FaultException<AnticipatedException>(anticipatedException);`</span><span class="sxs-lookup"><span data-stu-id="d4200-134">These exception classes will be readily reusable with the WCF <xref:System.ServiceModel.FaultException%601> class to throw a new `FaultException<AnticipatedException>(anticipatedException);`</span></span>  
  
## <a name="security"></a><span data-ttu-id="d4200-135">보안</span><span class="sxs-lookup"><span data-stu-id="d4200-135">Security</span></span>  
 <span data-ttu-id="d4200-136">다음은 몇 가지 보안 권장 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-136">The following are some security recommendations.</span></span>  
  
- <span data-ttu-id="d4200-137">방지 ASP.NET 2.0 프로필을 사용 하 여 사용이 제한 됩니다 ASP.NET 통합 모드의 경우 서비스를 WCF로 마이그레이션 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-137">Avoid using ASP.NET 2.0 Profiles, as using them would restrict the use of ASP.NET Integration Mode if the service was migrated to WCF.</span></span>  
  
- <span data-ttu-id="d4200-138">Acl을 사용 하 여 ASP.NET 웹 서비스에서는 인터넷 정보 서비스 (IIS)를 사용 하 여 Acl 서비스에 대 한 액세스를 제어 하려면 방지, WCF 않습니다-ASP.NET 웹 서비스는 IIS 호스팅의 경우 이므로 WCF는 반드시 IIS에서 호스트할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4200-138">Avoid using ACLs to control access to services, as ASP.NET Web services supports ACLs using Internet Information Services (IIS), WCF does not—because ASP.NET Web services depend on IIS for hosting, and WCF does not necessarily have to be hosted in IIS.</span></span>  
  
- <span data-ttu-id="d4200-139">서비스 리소스에 대한 액세스 권한을 부여할 때 ASP.NET 2.0 역할 공급자를 사용할 것을 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="d4200-139">Do consider using ASP.NET 2.0 Role Providers for authorizing access to the resources of a service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4200-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="d4200-140">See also</span></span>

- [<span data-ttu-id="d4200-141">Windows Communication Foundation 채택 예상: 향후 통합 간소화</span><span class="sxs-lookup"><span data-stu-id="d4200-141">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
