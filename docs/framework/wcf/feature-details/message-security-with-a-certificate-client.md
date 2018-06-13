---
title: 인증서 클라이언트를 사용하는 메시지 보안
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99770573-c815-4428-a38c-e4335c8bd7ce
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 570c7763da912de4e0d2729e7579a200f35c4941
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33494695"
---
# <a name="message-security-with-a-certificate-client"></a><span data-ttu-id="591d3-102">인증서 클라이언트를 사용하는 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="591d3-102">Message Security with a Certificate Client</span></span>
<span data-ttu-id="591d3-103">다음 시나리오는 Windows Communication Foundation (WCF) 클라이언트 및 서비스 메시지 보안 모드를 사용 하 여 보안을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured using message security mode.</span></span> <span data-ttu-id="591d3-104">클라이언트 및 서비스는 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-104">Both the client and the service are authenticated with certificates.</span></span> <span data-ttu-id="591d3-105">자세한 내용은 참조 [분산 응용 프로그램 보안](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-105">For more information, see [Distributed Application Security](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).</span></span>  
  
 <span data-ttu-id="591d3-106">샘플 응용 프로그램에 대 한 참조 [메시지 보안 인증서](../../../../docs/framework/wcf/samples/message-security-certificate.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-106">For a sample application, see [Message Security Certificate](../../../../docs/framework/wcf/samples/message-security-certificate.md).</span></span>  
  
 <span data-ttu-id="591d3-107">![인증서를 사용 하 여 클라이언트](../../../../docs/framework/wcf/feature-details/media/clientwithcertificate.gif "ClientWithCertificate")</span><span class="sxs-lookup"><span data-stu-id="591d3-107">![Client with certificate](../../../../docs/framework/wcf/feature-details/media/clientwithcertificate.gif "ClientWithCertificate")</span></span>  
  
|<span data-ttu-id="591d3-108">특성</span><span class="sxs-lookup"><span data-stu-id="591d3-108">Characteristic</span></span>|<span data-ttu-id="591d3-109">설명</span><span class="sxs-lookup"><span data-stu-id="591d3-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="591d3-110">보안 모드</span><span class="sxs-lookup"><span data-stu-id="591d3-110">Security Mode</span></span>|<span data-ttu-id="591d3-111">메시지</span><span class="sxs-lookup"><span data-stu-id="591d3-111">Message</span></span>|  
|<span data-ttu-id="591d3-112">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="591d3-112">Interoperability</span></span>|<span data-ttu-id="591d3-113">WCF만</span><span class="sxs-lookup"><span data-stu-id="591d3-113">WCF only</span></span>|  
|<span data-ttu-id="591d3-114">인증(서버)</span><span class="sxs-lookup"><span data-stu-id="591d3-114">Authentication (Server)</span></span>|<span data-ttu-id="591d3-115">서비스 인증서 사용</span><span class="sxs-lookup"><span data-stu-id="591d3-115">Using service certificate</span></span>|  
|<span data-ttu-id="591d3-116">인증(클라이언트)</span><span class="sxs-lookup"><span data-stu-id="591d3-116">Authentication (Client)</span></span>|<span data-ttu-id="591d3-117">클라이언트 인증서 사용</span><span class="sxs-lookup"><span data-stu-id="591d3-117">Using client certificate</span></span>|  
|<span data-ttu-id="591d3-118">무결성</span><span class="sxs-lookup"><span data-stu-id="591d3-118">Integrity</span></span>|<span data-ttu-id="591d3-119">예</span><span class="sxs-lookup"><span data-stu-id="591d3-119">Yes</span></span>|  
|<span data-ttu-id="591d3-120">기밀성</span><span class="sxs-lookup"><span data-stu-id="591d3-120">Confidentiality</span></span>|<span data-ttu-id="591d3-121">예</span><span class="sxs-lookup"><span data-stu-id="591d3-121">Yes</span></span>|  
|<span data-ttu-id="591d3-122">전송</span><span class="sxs-lookup"><span data-stu-id="591d3-122">Transport</span></span>|<span data-ttu-id="591d3-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="591d3-123">HTTP</span></span>|  
|<span data-ttu-id="591d3-124">바인딩</span><span class="sxs-lookup"><span data-stu-id="591d3-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="591d3-125">서비스</span><span class="sxs-lookup"><span data-stu-id="591d3-125">Service</span></span>  
 <span data-ttu-id="591d3-126">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="591d3-127">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="591d3-128">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="591d3-129">제공된 구성을 사용하여 서비스를 만들지만 끝점을 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="591d3-130">코드</span><span class="sxs-lookup"><span data-stu-id="591d3-130">Code</span></span>  
 <span data-ttu-id="591d3-131">다음 코드에서는 안전한 컨텍스트를 설정하기 위해 메시지 보안을 사용하는 서비스 끝점을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-131">The following code shows how to create a service endpoint that uses message security to establish a secure context.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#10)]
 [!code-vb[C_SecurityScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#10)]  
  
### <a name="configuration"></a><span data-ttu-id="591d3-132">구성</span><span class="sxs-lookup"><span data-stu-id="591d3-132">Configuration</span></span>  
 <span data-ttu-id="591d3-133">코드 대신 다음 구성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-133">The following configuration can be used instead of the code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"  
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndCerficiateClient"   
                  name="SecuredByClientCertificate"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="591d3-134">클라이언트</span><span class="sxs-lookup"><span data-stu-id="591d3-134">Client</span></span>  
 <span data-ttu-id="591d3-135">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-135">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="591d3-136">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-136">Do one of the following:</span></span>  
  
-   <span data-ttu-id="591d3-137">이 코드와 클라이언트 코드를 사용하여 독립 실행형 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-137">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="591d3-138">끝점 주소를 정의하지 않는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-138">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="591d3-139">대신 구성 이름을 인수로 사용하는 클라이언트 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-139">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="591d3-140">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-140">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="591d3-141">코드</span><span class="sxs-lookup"><span data-stu-id="591d3-141">Code</span></span>  
 <span data-ttu-id="591d3-142">다음 코드에서는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-142">The following code creates the client.</span></span> <span data-ttu-id="591d3-143">바인딩은 메시지 모드 보안으로 설정되며 클라이언트 자격 증명 형식은 `Certificate`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-143">The binding is to message mode security, and the client credential type is set to `Certificate`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#17)]
 [!code-vb[C_SecurityScenarios#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#17)]  
  
### <a name="configuration"></a><span data-ttu-id="591d3-144">구성</span><span class="sxs-lookup"><span data-stu-id="591d3-144">Configuration</span></span>  
 <span data-ttu-id="591d3-145">다음 구성에서는 끝점 동작을 사용하는 클라이언트 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-145">The following configuration specifies the client certificate using an endpoint behavior.</span></span> <span data-ttu-id="591d3-146">자세한 내용은 [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="591d3-146">For more information about certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="591d3-147">코드는 또한 사용 하 여는 <`identity`>는 DNS 도메인 이름 ()의 예상 되는 서버 id 지정 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-147">The code also uses an <`identity`> element to specify a Domain Name System (DNS) of the expected server identity.</span></span> <span data-ttu-id="591d3-148">Id에 대 한 자세한 내용은 참조 [서비스 Id 및 인증](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="591d3-148">For more information about identity, see [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"   
               storeLocation="LocalMachine"  
              x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                behaviorConfiguration="endpointCredentialsBehavior"  
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="591d3-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="591d3-149">See Also</span></span>  
 [<span data-ttu-id="591d3-150">보안 개요</span><span class="sxs-lookup"><span data-stu-id="591d3-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="591d3-151">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="591d3-151">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="591d3-152">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="591d3-152">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="591d3-153">Windows Server App Fabric에 대 한 보안 모델</span><span class="sxs-lookup"><span data-stu-id="591d3-153">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
