---
title: 보안이 설정되지 않은 인터넷 클라이언트 및 서비스
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97a10d79-3e7d-4bd1-9a99-fd9807fd70bc
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b2c71af169018f272a6ca538bba9191f9ddbc0dd
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44342429"
---
# <a name="internet-unsecured-client-and-service"></a><span data-ttu-id="f4cf7-102">보안이 설정되지 않은 인터넷 클라이언트 및 서비스</span><span class="sxs-lookup"><span data-stu-id="f4cf7-102">Internet Unsecured Client and Service</span></span>
<span data-ttu-id="f4cf7-103">다음 그림에는 공용, 보안 되지 않은 Windows Communication Foundation (WCF) 클라이언트 및 서비스의 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-103">The following illustration shows an example of a public, unsecured Windows Communication Foundation (WCF) client and service.</span></span>  
  
 <span data-ttu-id="f4cf7-104">![보안 되지 않은 인터넷 클라이언트 및 서비스 시나리오](../../../../docs/framework/wcf/feature-details/media/publicunsecured.gif "publicUnsecured")</span><span class="sxs-lookup"><span data-stu-id="f4cf7-104">![Unsecured Internet cleint and service scenario](../../../../docs/framework/wcf/feature-details/media/publicunsecured.gif "publicUnsecured")</span></span>  
  
|<span data-ttu-id="f4cf7-105">특성</span><span class="sxs-lookup"><span data-stu-id="f4cf7-105">Characteristic</span></span>|<span data-ttu-id="f4cf7-106">설명</span><span class="sxs-lookup"><span data-stu-id="f4cf7-106">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="f4cf7-107">보안 모드</span><span class="sxs-lookup"><span data-stu-id="f4cf7-107">Security Mode</span></span>|<span data-ttu-id="f4cf7-108">없음</span><span class="sxs-lookup"><span data-stu-id="f4cf7-108">None</span></span>|  
|<span data-ttu-id="f4cf7-109">전송</span><span class="sxs-lookup"><span data-stu-id="f4cf7-109">Transport</span></span>|<span data-ttu-id="f4cf7-110">HTTP</span><span class="sxs-lookup"><span data-stu-id="f4cf7-110">HTTP</span></span>|  
|<span data-ttu-id="f4cf7-111">바인딩</span><span class="sxs-lookup"><span data-stu-id="f4cf7-111">Binding</span></span>|<span data-ttu-id="f4cf7-112"><xref:System.ServiceModel.BasicHttpBinding> 코드에서 또는 [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) 요소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-112"><xref:System.ServiceModel.BasicHttpBinding> in code, or the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element in configuration.</span></span>|  
|<span data-ttu-id="f4cf7-113">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="f4cf7-113">Interoperability</span></span>|<span data-ttu-id="f4cf7-114">기존 웹 서비스 클라이언트 및 서비스와의 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="f4cf7-114">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="f4cf7-115">인증</span><span class="sxs-lookup"><span data-stu-id="f4cf7-115">Authentication</span></span>|<span data-ttu-id="f4cf7-116">없음</span><span class="sxs-lookup"><span data-stu-id="f4cf7-116">None</span></span>|  
|<span data-ttu-id="f4cf7-117">무결성</span><span class="sxs-lookup"><span data-stu-id="f4cf7-117">Integrity</span></span>|<span data-ttu-id="f4cf7-118">없음</span><span class="sxs-lookup"><span data-stu-id="f4cf7-118">None</span></span>|  
|<span data-ttu-id="f4cf7-119">기밀성</span><span class="sxs-lookup"><span data-stu-id="f4cf7-119">Confidentiality</span></span>|<span data-ttu-id="f4cf7-120">없음</span><span class="sxs-lookup"><span data-stu-id="f4cf7-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="f4cf7-121">서비스</span><span class="sxs-lookup"><span data-stu-id="f4cf7-121">Service</span></span>  
 <span data-ttu-id="f4cf7-122">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="f4cf7-123">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-123">Do one of the following:</span></span>  
  
-   <span data-ttu-id="f4cf7-124">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="f4cf7-125">제공된 구성을 사용하여 서비스를 만들지만 엔드포인트를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f4cf7-126">코드</span><span class="sxs-lookup"><span data-stu-id="f4cf7-126">Code</span></span>  
 <span data-ttu-id="f4cf7-127">다음 코드에서는 보안 없이 엔드포인트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-127">The following code shows how to create an endpoint with no security.</span></span> <span data-ttu-id="f4cf7-128">기본적으로 <xref:System.ServiceModel.BasicHttpBinding>에는 <xref:System.ServiceModel.BasicHttpSecurityMode.None>으로 설정된 보안 모드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-128">By default, the <xref:System.ServiceModel.BasicHttpBinding> has the security mode set to <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span></span>  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### <a name="service-configuration"></a><span data-ttu-id="f4cf7-129">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="f4cf7-129">Service Configuration</span></span>  
 <span data-ttu-id="f4cf7-130">다음 코드에서는 구성을 사용하여 동일한 엔드포인트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-130">The following code sets up the same endpoint using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="basicHttpBinding"  
                  bindingConfiguration="Basic_Unsecured"   
                  name="BasicHttp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="Basic_Unsecured" />  
      </basicHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="f4cf7-131">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f4cf7-131">Client</span></span>  
 <span data-ttu-id="f4cf7-132">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-132">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="f4cf7-133">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-133">Do one of the following:</span></span>  
  
-   <span data-ttu-id="f4cf7-134">이 코드와 클라이언트 코드를 사용하여 독립 실행형 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-134">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="f4cf7-135">엔드포인트 주소를 정의하지 않는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-135">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="f4cf7-136">대신 구성 이름을 인수로 사용하는 클라이언트 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-136">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="f4cf7-137">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-137">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="f4cf7-138">코드</span><span class="sxs-lookup"><span data-stu-id="f4cf7-138">Code</span></span>  
 <span data-ttu-id="f4cf7-139">다음 코드에서는 보안이 설정 되지 않은 끝점에 액세스 하는 기본 WCF 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-139">The following code shows a basic WCF client that accesses an unsecured endpoint.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### <a name="client-configuration"></a><span data-ttu-id="f4cf7-140">클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="f4cf7-140">Client Configuration</span></span>  
 <span data-ttu-id="f4cf7-141">다음 코드에서는 클라이언트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-141">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="BasicHttpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator/Unsecured"  
          binding="basicHttpBinding"   
          bindingConfiguration="BasicHttpBinding_ICalculator"  
          contract="ICalculator"   
          name="BasicHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f4cf7-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4cf7-142">See Also</span></span>  
 [<span data-ttu-id="f4cf7-143">일반적인 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="f4cf7-143">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 [<span data-ttu-id="f4cf7-144">보안 개요</span><span class="sxs-lookup"><span data-stu-id="f4cf7-144">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="f4cf7-145">Windows Server appfabric 보안 모델</span><span class="sxs-lookup"><span data-stu-id="f4cf7-145">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
