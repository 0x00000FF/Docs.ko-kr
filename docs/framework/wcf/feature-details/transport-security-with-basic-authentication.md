---
title: 기본 인증을 사용하는 전송 보안
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b54f491d-196b-4279-876c-76b83ec0442c
author: BrucePerlerMS
ms.openlocfilehash: 4a6ad2746bea9dfea1999e272796d44f0341e64d
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086611"
---
# <a name="transport-security-with-basic-authentication"></a><span data-ttu-id="89115-102">기본 인증을 사용하는 전송 보안</span><span class="sxs-lookup"><span data-stu-id="89115-102">Transport Security with Basic Authentication</span></span>
<span data-ttu-id="89115-103">다음 그림에는 Windows Communication Foundation (WCF) 서비스 및 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89115-103">The following illustration shows a Windows Communication Foundation (WCF) service and client.</span></span> <span data-ttu-id="89115-104">서버에 SSL(Secure Sockets Layer)에 사용할 유효한 X.509 인증서가 있어야 하며 클라이언트에서 서버의 인증서를 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89115-104">The server needs a valid X.509 certificate that can be used for Secure Sockets Layer (SSL), and the clients must trust the server’s certificate.</span></span> <span data-ttu-id="89115-105">또한 웹 서비스에는 이미 사용할 수 있는 SSL 구현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89115-105">Further, the Web service already has an SSL implementation that can be used.</span></span> <span data-ttu-id="89115-106">자세한 내용은 기본 인증을 사용 하는 방법에 대 한 인터넷 정보 서비스 (IIS)에 대해서 [ https://go.microsoft.com/fwlink/?LinkId=83822 ](https://go.microsoft.com/fwlink/?LinkId=83822)합니다.</span><span class="sxs-lookup"><span data-stu-id="89115-106">For more information about enabling basic authentication on Internet Information Services (IIS), see [https://go.microsoft.com/fwlink/?LinkId=83822](https://go.microsoft.com/fwlink/?LinkId=83822).</span></span>  
  
 <span data-ttu-id="89115-107">![전송 보안 기본 인증을 사용 하 여](../../../../docs/framework/wcf/feature-details/media/securedbyusername.gif "SecuredbyUsername")</span><span class="sxs-lookup"><span data-stu-id="89115-107">![Transport security with basic authentication](../../../../docs/framework/wcf/feature-details/media/securedbyusername.gif "SecuredbyUsername")</span></span>  
  
|<span data-ttu-id="89115-108">특성</span><span class="sxs-lookup"><span data-stu-id="89115-108">Characteristic</span></span>|<span data-ttu-id="89115-109">설명</span><span class="sxs-lookup"><span data-stu-id="89115-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="89115-110">보안 모드</span><span class="sxs-lookup"><span data-stu-id="89115-110">Security Mode</span></span>|<span data-ttu-id="89115-111">전송</span><span class="sxs-lookup"><span data-stu-id="89115-111">Transport</span></span>|  
|<span data-ttu-id="89115-112">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="89115-112">Interoperability</span></span>|<span data-ttu-id="89115-113">기존 웹 서비스 클라이언트 및 서비스와의 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="89115-113">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="89115-114">인증(서버)</span><span class="sxs-lookup"><span data-stu-id="89115-114">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="89115-115">인증(클라이언트)</span><span class="sxs-lookup"><span data-stu-id="89115-115">Authentication (Client)</span></span>|<span data-ttu-id="89115-116">예(HTTPS 사용)</span><span class="sxs-lookup"><span data-stu-id="89115-116">Yes (using HTTPS)</span></span><br /><br /> <span data-ttu-id="89115-117">예(사용자 이름/암호 사용)</span><span class="sxs-lookup"><span data-stu-id="89115-117">Yes (through User name/Password)</span></span>|  
|<span data-ttu-id="89115-118">무결성</span><span class="sxs-lookup"><span data-stu-id="89115-118">Integrity</span></span>|<span data-ttu-id="89115-119">예</span><span class="sxs-lookup"><span data-stu-id="89115-119">Yes</span></span>|  
|<span data-ttu-id="89115-120">기밀성</span><span class="sxs-lookup"><span data-stu-id="89115-120">Confidentiality</span></span>|<span data-ttu-id="89115-121">예</span><span class="sxs-lookup"><span data-stu-id="89115-121">Yes</span></span>|  
|<span data-ttu-id="89115-122">전송</span><span class="sxs-lookup"><span data-stu-id="89115-122">Transport</span></span>|<span data-ttu-id="89115-123">HTTPS</span><span class="sxs-lookup"><span data-stu-id="89115-123">HTTPS</span></span>|  
|<span data-ttu-id="89115-124">바인딩</span><span class="sxs-lookup"><span data-stu-id="89115-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="89115-125">서비스</span><span class="sxs-lookup"><span data-stu-id="89115-125">Service</span></span>  
 <span data-ttu-id="89115-126">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89115-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="89115-127">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="89115-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="89115-128">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="89115-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="89115-129">제공된 구성을 사용하여 서비스를 만들지만 엔드포인트를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89115-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="89115-130">코드</span><span class="sxs-lookup"><span data-stu-id="89115-130">Code</span></span>  
 <span data-ttu-id="89115-131">다음 코드에서는 전송 보안에 Windows 도메인 사용자 이름과 암호를 사용하는 서비스 엔드포인트를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="89115-131">The following code shows how to create a service endpoint that uses a Windows domain user name and password for transfer security.</span></span> <span data-ttu-id="89115-132">서비스에서 X.509 인증서를 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89115-132">Note that the service requires an X.509 certificate to authenticate to the client.</span></span> <span data-ttu-id="89115-133">자세한 내용은 참조 하세요. [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) 하 고 [방법: SSL 인증서로 포트 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="89115-133">For more information, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 [!code-csharp[C_SecurityScenarios#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#1)]
 [!code-vb[C_SecurityScenarios#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#1)]  
  
## <a name="configuration"></a><span data-ttu-id="89115-134">구성</span><span class="sxs-lookup"><span data-stu-id="89115-134">Configuration</span></span>  
 <span data-ttu-id="89115-135">다음에서는 전송 수준 보안이 설정된 기본 인증을 사용하도록 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="89115-135">The following configures a service to use basic authentication with transport-level security:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <wsHttpBinding>  
                <binding name="UsernameWithTransport">  
                    <security mode="Transport">  
                        <transport clientCredentialType="Basic" />  
                    </security>  
                </binding>  
            </wsHttpBinding>  
        </bindings>  
        <services>  
            <service name="BasicAuthentication.Calculator">  
                <endpoint address="https://localhost/Calculator"  
                          binding="wsHttpBinding"   
                          bindingConfiguration="UsernameWithTransport"  
                          name="BasicEndpoint"   
                          contract="BasicAuthentication.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="89115-136">클라이언트</span><span class="sxs-lookup"><span data-stu-id="89115-136">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="89115-137">코드</span><span class="sxs-lookup"><span data-stu-id="89115-137">Code</span></span>  
 <span data-ttu-id="89115-138">다음 코드에서는 사용자 이름 및 암호를 포함한 클라이언트 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89115-138">The following code shows the client code that includes the user name and password.</span></span> <span data-ttu-id="89115-139">사용자는 유효한 Windows 사용자 이름과 암호를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89115-139">Note that the user must provide a valid Windows user name and password.</span></span> <span data-ttu-id="89115-140">사용자 이름과 암호를 반환하는 코드는 여기에 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89115-140">The code to return the user name and password is not shown here.</span></span> <span data-ttu-id="89115-141">대화 상자나 다른 인터페이스를 사용하여 사용자에게 정보를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="89115-141">Use a dialog box or other interface to query the user for the information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89115-142">사용자 이름 및 암호는 코드를 사용해야만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89115-142">User name and password can only be set using code.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#2)]
 [!code-vb[C_SecurityScenarios#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="89115-143">구성</span><span class="sxs-lookup"><span data-stu-id="89115-143">Configuration</span></span>  
 <span data-ttu-id="89115-144">다음 코드에서는 클라이언트 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89115-144">The following code shows the client configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89115-145">구성을 사용하여 사용자 이름 및 암호를 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89115-145">You cannot use configuration to set the user name and password.</span></span> <span data-ttu-id="89115-146">여기 표시된 구성은 사용자 이름 및 암호를 설정하는 코드를 사용하여 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89115-146">The configuration shown here must be augmented using code to set the user name and password.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Basic" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="https://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="89115-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89115-147">See Also</span></span>  
 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>  
 [<span data-ttu-id="89115-148">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="89115-148">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="89115-149">방법: SSL 인증서로 포트 구성</span><span class="sxs-lookup"><span data-stu-id="89115-149">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 [<span data-ttu-id="89115-150">보안 개요</span><span class="sxs-lookup"><span data-stu-id="89115-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="89115-151">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="89115-151">\<clientCredentials></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)  
 [<span data-ttu-id="89115-152">Windows Server appfabric 보안 모델</span><span class="sxs-lookup"><span data-stu-id="89115-152">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
