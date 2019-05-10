---
title: 사용자 이름 클라이언트를 사용하는 메시지 보안
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
ms.openlocfilehash: a5e3e96ce8c8bb3304c8abcc93a881998382c6ec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638007"
---
# <a name="message-security-with-a-user-name-client"></a><span data-ttu-id="57200-102">사용자 이름 클라이언트를 사용하는 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="57200-102">Message Security with a User Name Client</span></span>
<span data-ttu-id="57200-103">다음 그림에는 Windows Communication Foundation (WCF) 서비스 및 메시지 수준 보안을 사용 하 여 보호 하는 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="57200-103">The following illustration shows an Windows Communication Foundation (WCF) service and client secured using message-level security.</span></span> <span data-ttu-id="57200-104">서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="57200-104">The service is authenticated with an X.509 certificate.</span></span> <span data-ttu-id="57200-105">클라이언트는 사용자 이름 및 암호를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="57200-105">The client authenticates using a user name and password.</span></span>  
  
 <span data-ttu-id="57200-106">샘플 응용 프로그램을 참조 하세요 [메시지 보안 사용자 이름](../../../../docs/framework/wcf/samples/message-security-user-name.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="57200-106">For a sample application, see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span></span>  
  
 <span data-ttu-id="57200-107">![사용자 이름 인증을 사용 하 여 메시지 보안](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span><span class="sxs-lookup"><span data-stu-id="57200-107">![Message security using username authentication](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span></span>  
  
|<span data-ttu-id="57200-108">특성</span><span class="sxs-lookup"><span data-stu-id="57200-108">Characteristic</span></span>|<span data-ttu-id="57200-109">설명</span><span class="sxs-lookup"><span data-stu-id="57200-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="57200-110">보안 모드</span><span class="sxs-lookup"><span data-stu-id="57200-110">Security Mode</span></span>|<span data-ttu-id="57200-111">메시지</span><span class="sxs-lookup"><span data-stu-id="57200-111">Message</span></span>|  
|<span data-ttu-id="57200-112">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="57200-112">Interoperability</span></span>|<span data-ttu-id="57200-113">Windows Communication Foundation (WCF)만</span><span class="sxs-lookup"><span data-stu-id="57200-113">Windows Communication Foundation (WCF) only</span></span>|  
|<span data-ttu-id="57200-114">인증(서버)</span><span class="sxs-lookup"><span data-stu-id="57200-114">Authentication (Server)</span></span>|<span data-ttu-id="57200-115">최초 협상에는 서버 인증이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="57200-115">Initial negotiation requires server authentication</span></span>|  
|<span data-ttu-id="57200-116">인증(클라이언트)</span><span class="sxs-lookup"><span data-stu-id="57200-116">Authentication (Client)</span></span>|<span data-ttu-id="57200-117">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="57200-117">User name/password</span></span>|  
|<span data-ttu-id="57200-118">무결성</span><span class="sxs-lookup"><span data-stu-id="57200-118">Integrity</span></span>|<span data-ttu-id="57200-119">예, 공유 보안 컨텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="57200-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="57200-120">기밀성</span><span class="sxs-lookup"><span data-stu-id="57200-120">Confidentiality</span></span>|<span data-ttu-id="57200-121">예, 공유 보안 컨텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="57200-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="57200-122">전송</span><span class="sxs-lookup"><span data-stu-id="57200-122">Transport</span></span>|<span data-ttu-id="57200-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="57200-123">HTTP</span></span>|  
|<span data-ttu-id="57200-124">바인딩</span><span class="sxs-lookup"><span data-stu-id="57200-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="57200-125">서비스</span><span class="sxs-lookup"><span data-stu-id="57200-125">Service</span></span>  
 <span data-ttu-id="57200-126">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57200-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="57200-127">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="57200-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="57200-128">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57200-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="57200-129">제공된 구성을 사용하여 서비스를 만들지만 엔드포인트를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57200-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="57200-130">코드</span><span class="sxs-lookup"><span data-stu-id="57200-130">Code</span></span>  
 <span data-ttu-id="57200-131">다음 코드에서는 메시지 보안을 사용하는 서비스 엔드포인트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="57200-131">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a><span data-ttu-id="57200-132">구성</span><span class="sxs-lookup"><span data-stu-id="57200-132">Configuration</span></span>  
 <span data-ttu-id="57200-133">코드 대신 다음 구성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57200-133">The following configuration can be used instead of the code:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My"     
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
                  bindingConfiguration="MessageAndUserName"  
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MessageAndUserName">  
          <security mode="Message">              
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="57200-134">클라이언트</span><span class="sxs-lookup"><span data-stu-id="57200-134">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="57200-135">코드</span><span class="sxs-lookup"><span data-stu-id="57200-135">Code</span></span>  
 <span data-ttu-id="57200-136">다음 코드에서는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57200-136">The following code creates the client.</span></span> <span data-ttu-id="57200-137">바인딩은 메시지 모드 보안으로 설정되며 클라이언트 자격 증명 형식은 `UserName`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="57200-137">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="57200-138">사용자 이름 및 암호는 코드(구성할 수 없음)를 사용해서만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57200-138">The user name and password can only be specified using code (it is not configurable).</span></span> <span data-ttu-id="57200-139">사용자 이름 및 암호를 반환할 코드는 응용 프로그램 수준에서 수행되는 작업이기 때문에 여기에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57200-139">The code to return the user name and password is not shown here because it must be done at the application level.</span></span> <span data-ttu-id="57200-140">예를 들어 데이터에 대한 사용자를 쿼리하려면 Windows Forms 대화 상자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="57200-140">For example, use a Windows Forms dialog box to query the user for the data.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a><span data-ttu-id="57200-141">구성</span><span class="sxs-lookup"><span data-stu-id="57200-141">Configuration</span></span>  
 <span data-ttu-id="57200-142">다음 코드에서는 클라이언트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="57200-142">The following code configures the client.</span></span> <span data-ttu-id="57200-143">바인딩은 메시지 모드 보안으로 설정되며 클라이언트 자격 증명 형식은 `UserName`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="57200-143">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="57200-144">사용자 이름 및 암호는 코드(구성할 수 없음)를 사용해서만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57200-144">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value ="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="57200-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="57200-145">See also</span></span>

- [<span data-ttu-id="57200-146">보안 개요</span><span class="sxs-lookup"><span data-stu-id="57200-146">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="57200-147">메시지 보안 사용자 이름</span><span class="sxs-lookup"><span data-stu-id="57200-147">Message Security User Name</span></span>](../../../../docs/framework/wcf/samples/message-security-user-name.md)
- [<span data-ttu-id="57200-148">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="57200-148">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="57200-149">\<identity></span><span class="sxs-lookup"><span data-stu-id="57200-149">\<identity></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
- [<span data-ttu-id="57200-150">Windows Server appfabric 보안 모델</span><span class="sxs-lookup"><span data-stu-id="57200-150">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
