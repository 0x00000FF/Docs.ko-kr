---
title: 클라이언트에 보안 설정
ms.date: 03/30/2017
helpviewer_keywords:
- clients [WCF], security considerations
ms.assetid: 44c8578c-9a5b-4acd-8168-1c30a027c4c5
ms.openlocfilehash: 7f9a02bc650f54338dfcb1d3f41397e745483430
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959531"
---
# <a name="securing-clients"></a><span data-ttu-id="475a5-102">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="475a5-102">Securing Clients</span></span>
<span data-ttu-id="475a5-103">WCF (Windows Communication Foundation)에서 서비스는 클라이언트에 대 한 보안 요구 사항을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-103">In Windows Communication Foundation (WCF), the service dictates the security requirements for clients.</span></span> <span data-ttu-id="475a5-104">즉, 서비스는 사용할 보안 모드 및 클라이언트가 자격 증명을 제공해야 하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-104">That is, the service specifies what security mode to use, and whether or not the client must provide a credential.</span></span> <span data-ttu-id="475a5-105">따라서 클라이언트 보안 설정 프로세스는 간단합니다. 서비스에서 가져온 메타데이터를 사용하여(게시된 경우) 클라이언트를 빌드하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-105">The process of securing a client, therefore, is simple: use the metadata obtained from the service (if it is published) and build a client.</span></span> <span data-ttu-id="475a5-106">메타데이터는 클라이언트를 구성하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-106">The metadata specifies how to configure the client.</span></span> <span data-ttu-id="475a5-107">서비스에서 클라이언트가 자격 증명을 제공해야 하는 경우 요구 사항에 맞는 자격 증명을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-107">If the service requires that the client supply a credential, then you must obtain a credential that fits the requirement.</span></span> <span data-ttu-id="475a5-108">이 항목에서는 이 과정을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-108">This topic discusses the process in further detail.</span></span> <span data-ttu-id="475a5-109">보안 서비스를 만드는 방법에 대 한 자세한 내용은 [서비스 보안](../../../docs/framework/wcf/securing-services.md)설정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="475a5-109">For more information about creating a secure service, see [Securing Services](../../../docs/framework/wcf/securing-services.md).</span></span>  
  
## <a name="the-service-specifies-security"></a><span data-ttu-id="475a5-110">서비스에서 보안 지정</span><span class="sxs-lookup"><span data-stu-id="475a5-110">The Service Specifies Security</span></span>  
 <span data-ttu-id="475a5-111">기본적으로 WCF 바인딩에는 보안 기능이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-111">By default, WCF bindings have security features enabled.</span></span> <span data-ttu-id="475a5-112"><xref:System.ServiceModel.BasicHttpBinding>은 예외입니다. 따라서 WCF를 사용 하 여 서비스를 만든 경우 인증, 기밀성 및 무결성을 보장 하기 위해 보안을 구현할 가능성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-112">(The exception is the <xref:System.ServiceModel.BasicHttpBinding>.) Therefore, if the service was created using WCF, there is a greater chance that it will implement security to ensure authentication, confidentiality, and integrity.</span></span> <span data-ttu-id="475a5-113">이러한 경우 서비스가 제공하는 메타데이터는 보안 통신 채널을 설정하는 데 필요한 사항을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-113">In that case, the metadata the service provides will indicate what it requires to establish a secure communication channel.</span></span> <span data-ttu-id="475a5-114">서비스 메타데이터에 보안 요구 사항이 없는 경우 서비스에 SSL(Secure Sockets Layer) over HTTP와 같은 보안 스키마를 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-114">If the service metadata does not include any security requirements, there is no way to impose a security scheme, such as Secure Sockets Layer (SSL) over HTTP, on a service.</span></span> <span data-ttu-id="475a5-115">그러나 서비스에서 클라이언트가 자격 증명을 제공해야 하는 경우 클라이언트 개발자, 배포자 또는 관리자는 클라이언트가 서비스에게 자신을 인증하는 데 사용할 실제 자격 증명을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-115">If, however, the service requires the client to supply a credential, then the client developer, deployer, or administrator must supply the actual credential that the client will use to authenticate itself to the service.</span></span>  
  
## <a name="obtaining-metadata"></a><span data-ttu-id="475a5-116">메타데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="475a5-116">Obtaining Metadata</span></span>  
 <span data-ttu-id="475a5-117">클라이언트를 만들 때 첫 번째 단계는 클라이언트가 통신할 서비스에 대한 메타데이터를 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-117">When creating a client, the first step is to obtain the metadata for the service that the client will communicate with.</span></span> <span data-ttu-id="475a5-118">이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-118">This can be done in two ways.</span></span> <span data-ttu-id="475a5-119">첫째, 서비스가 MEX (metadata exchange) 끝점을 게시 하거나 HTTP 또는 HTTPS를 통해 메타 데이터를 사용할 수 있도록 설정 하는 경우 클라이언트에 대 한 코드 파일을 모두 생성 하는 [ServiceModel Metadata 유틸리티 도구 (svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용 하 여 메타 데이터를 다운로드할 수 있습니다. 구성 파일을 비롯 하 여</span><span class="sxs-lookup"><span data-stu-id="475a5-119">First, if the service publishes a metadata exchange (MEX) endpoint or makes its metadata available over HTTP or HTTPS, you can download the metadata using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), which generates both code files for a client as well as a configuration file.</span></span> <span data-ttu-id="475a5-120">도구를 사용 하는 방법에 대 한 자세한 내용은 [WCF 클라이언트를 사용 하 여 서비스 액세스](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)를 참조 하세요. 서비스가 MEX 엔드포인트를 게시하지 않고 또한 HTTP 또는 HTTPS를 통해 메타데이터를 사용할 수 있도록 하지 않은 경우, 보안 요구 사항 및 메타데이터를 설명하는 설명서에 대한 서비스 작성자에게 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-120">(For more information about using the tool, see [Accessing Services Using a WCF Client](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).) If the service does not publish a MEX endpoint and also does not make its metadata available over HTTP or HTTPS, you must contact the service creator for documentation that describes the security requirements and the metadata.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="475a5-121">메타데이터는 신뢰할 수 있는 소스에서 가져오고 변경하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-121">It is recommended that the metadata come from a trusted source and that it not be tampered with.</span></span> <span data-ttu-id="475a5-122">HTTP 프로토콜을 사용하여 검색한 메타데이터는 일반 텍스트로 전송되며 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-122">Metadata retrieved using the HTTP protocol is sent in clear text and can be tampered with.</span></span> <span data-ttu-id="475a5-123">서비스가 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> 및 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> 속성을 사용하는 경우 서비스 작성자가 제공하는 URL을 통해 HTTPS 프로토콜을 사용하여 데이터를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-123">If the service uses the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> and <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> properties, use the URL the service creator supplied to download the data using the HTTPS protocol.</span></span>  
  
## <a name="validating-security"></a><span data-ttu-id="475a5-124">보안 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="475a5-124">Validating Security</span></span>  
 <span data-ttu-id="475a5-125">메타데이터 소스는 크게 신뢰할 수 있는 소스와 신뢰할 수 없는 소스의 두 가지 범주로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-125">Metadata sources can be divided into two broad categories: trust sources and untrusted sources.</span></span> <span data-ttu-id="475a5-126">소스를 신뢰하고 소스의 보안 MEX 엔드포인트에서 클라이언트 코드 및 다른 메타데이터를 다운로드한 경우, 해당 클라이언트를 빌드하여 올바른 자격 증명을 제공하고 다른 문제 없이 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-126">If you trust a source and have downloaded the client code and other metadata from that source's secure MEX endpoint, then you can build the client, supply it with the right credentials, and run it with no other concerns.</span></span>  
  
 <span data-ttu-id="475a5-127">그러나 잘 모르는 소스에서 클라이언트 및 메타데이터를 다운로드하려는 경우 코드가 사용하는 보안 방법의 유효성을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-127">However, if you elect to download a client and metadata from a source that you know little about, be sure to validate the security measures the code uses.</span></span> <span data-ttu-id="475a5-128">예를 들어, 서비스가 최소한의 수준에서 기밀성 및 무결성을 요구하지 않는 한 단순히 개인 정보 또는 재무 정보를 서비스에 보내는 클라이언트를 만들지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-128">For example, you must not simply create a client that sends your personal or financial information to a service unless the service demands confidentiality and integrity (at the very least).</span></span> <span data-ttu-id="475a5-129">이러한 정보가 서비스 소유자에게 표시되기 때문에 이러한 정보를 공개할 정도로 서비스 소유자를 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-129">You should trust the owner of the service to the extent that you are willing to disclose such information because such information will be visible to him or her.</span></span>  
  
 <span data-ttu-id="475a5-130">따라서 일반적으로 신뢰할 수 없는 소스에서 코드 및 메타데이터를 사용하는 경우 필요한 보안 수준을 충족하는지 코드 및 메타데이터를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-130">As a rule, therefore, when using code and metadata from an untrusted source, check the code and metadata to ensure that it meets the security level that you require.</span></span>  
  
## <a name="setting-a-client-credential"></a><span data-ttu-id="475a5-131">클라이언트 자격 증명 설정</span><span class="sxs-lookup"><span data-stu-id="475a5-131">Setting a Client Credential</span></span>  
 <span data-ttu-id="475a5-132">클라이언트에 대한 클라이언트 자격 증명 설정은 다음 두 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-132">Setting a client credential on a client consists of two steps:</span></span>  
  
1. <span data-ttu-id="475a5-133">서비스에 필요한 *클라이언트 자격 증명 형식을* 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-133">Determine the *client credential type* the service requires.</span></span> <span data-ttu-id="475a5-134">이 방법은 두 개의 메서드 중 하나에 의해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-134">This is accomplished by one of two methods.</span></span> <span data-ttu-id="475a5-135">첫째로, 서비스 작성자의 설명서가 있는 경우 서비스에서 필요한 클라이언트 자격 증명 형식(있는 경우)을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-135">First, if you have documentation from the service creator, it should specify the client credential type (if any) the service requires.</span></span> <span data-ttu-id="475a5-136">둘째로, Svcutil.exe 도구로 생성된 구성 파일만 있는 경우 개별 바인딩을 검사하여 필요한 자격 증명 형식을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-136">Second, if you have only a configuration file generated by the Svcutil.exe tool, you can examine the individual bindings to determine what credential type is required.</span></span>  
  
2. <span data-ttu-id="475a5-137">실제 클라이언트 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-137">Specify an actual client credential.</span></span> <span data-ttu-id="475a5-138">실제 클라이언트 자격 증명을 형식과 구분 하기 위해 *클라이언트 자격 증명 값* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-138">The actual client credential is called a *client credential value* to distinguish it from the type.</span></span> <span data-ttu-id="475a5-139">예를 들어, 클라이언트 자격 증명 형식이 인증서를 지정할 경우 서비스가 신뢰하는 인증 기관에서 발급한 X.509 인증서를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-139">For example, if the client credential type specifies a certificate, you must supply an X.509 certificate that is issued by a certification authority the service trusts.</span></span>  
  
### <a name="determining-the-client-credential-type"></a><span data-ttu-id="475a5-140">클라이언트 자격 증명 형식 결정</span><span class="sxs-lookup"><span data-stu-id="475a5-140">Determining the Client Credential Type</span></span>  
 <span data-ttu-id="475a5-141">Svcutil.exe 도구를 통해 구성 파일을 생성 한 경우 [ \<바인딩 >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 섹션을 검토 하 여 필요한 클라이언트 자격 증명 형식을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-141">If you have the configuration file the Svcutil.exe tool generated, examine the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) section to determine what client credential type is required.</span></span> <span data-ttu-id="475a5-142">이 단원에는 보안 요구 사항을 지정하는 바인딩 요소가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-142">Within the section are binding elements that specify the security requirements.</span></span> <span data-ttu-id="475a5-143">특히 각 바인딩의 \<보안 > 요소를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-143">Specifically, examine the \<security> Element of each binding.</span></span> <span data-ttu-id="475a5-144">해당 요소에는 `mode` 특성이 포함되어 있으며, 이 특성은 세 가지 가능한 값 즉, `Message`, `Transport` 또는 `TransportWithMessageCredential` 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-144">That element includes the `mode` attribute, which you can set to one of three possible values (`Message`, `Transport`, or `TransportWithMessageCredential`).</span></span> <span data-ttu-id="475a5-145">특성 값은 모드를 결정하고 모드는 자식 요소 중 중요한 요소를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-145">The value of the attribute determines the mode, and the mode determines which of the child elements is significant.</span></span>  
  
 <span data-ttu-id="475a5-146">`<security>` 요소는 `<transport>` 또는 `<message>` 요소 중 하나, 또는 둘 다를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-146">The `<security>` element can contain either a `<transport>` or `<message>` element, or both.</span></span> <span data-ttu-id="475a5-147">중요한 요소는 보안 모드와 일치하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-147">The significant element is the one that matches the security mode.</span></span> <span data-ttu-id="475a5-148">예를 들어 다음 코드는 보안 모드를 `"Message"`, `<message>` 요소의 클라이언트 자격 증명 형식은 `"Certificate"` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-148">For example, the following code specifies that the security mode is `"Message"`, and the client credential type for the `<message>` element is `"Certificate"`.</span></span> <span data-ttu-id="475a5-149">이런 경우 `<transport>` 요소는 무시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-149">In this case, the `<transport>` element can be ignored.</span></span> <span data-ttu-id="475a5-150">그러나 `<message>` 요소는 X.509 인증서를 제공해야 하는 것으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-150">However, the `<message>` element specifies that an X.509 certificate must be supplied.</span></span>  

```xml  
<wsHttpBinding>  
    <binding name="WSHttpBinding_ICalculator">  
       <security mode="Message">  
           <transport clientCredentialType="Windows"   
                      realm="" />  
           <message clientCredentialType="Certificate"   
                    negotiateServiceCredential="true"  
                    algorithmSuite="Default"   
                    establishSecurityContext="true" />  
       </security>  
    </binding>  
</wsHttpBinding>  
```  

 <span data-ttu-id="475a5-151">다음 예제와 같이 `clientCredentialType` 특성이 `"Windows"`로 설정된 경우 실제 자격 증명 값을 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-151">Note that if the `clientCredentialType` attribute is set to `"Windows"`, as shown in the following example, you do not need to supply an actual credential value.</span></span> <span data-ttu-id="475a5-152">Windows 통합 보안이 클라이언트를 실행하는 사용자의 실제 자격 증명(Kerberos 토큰)을 제공하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-152">This is because the Windows integrated security provides the actual credential (a Kerberos token) of the person who is running the client.</span></span>  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows "   
        realm="" />  
</security>  
```  
  
### <a name="setting-the-client-credential-value"></a><span data-ttu-id="475a5-153">클라이언트 자격 증명 값 설정</span><span class="sxs-lookup"><span data-stu-id="475a5-153">Setting the Client Credential Value</span></span>  
 <span data-ttu-id="475a5-154">클라이언트가 자격 증명을 제공해야 하는 경우 적절한 메서드를 사용하여 클라이언트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-154">If it is determined that the client must supply a credential, use the appropriate method to configure the client.</span></span> <span data-ttu-id="475a5-155">예를 들어, 클라이언트 인증서를 설정하려면 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-155">For example, to set a client certificate, use the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method.</span></span>  
  
 <span data-ttu-id="475a5-156">자격 증명의 일반 양식은 X.509 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-156">A common form of credential is the X.509 certificate.</span></span> <span data-ttu-id="475a5-157">다음 두 가지 방법으로 자격 증명을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-157">You can supply the credential in two ways:</span></span>  
  
- <span data-ttu-id="475a5-158">클라이언트 코드에서 자격 증명 프로그래밍(`SetCertificate` 메서드 사용).</span><span class="sxs-lookup"><span data-stu-id="475a5-158">By programming it in your client code (using the `SetCertificate` method).</span></span>  
  
 <span data-ttu-id="475a5-159">클라이언트에 대 한 구성 파일의 [ \<동작 >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 섹션을 추가 하 고 아래와 같이 요소를사용합니다.`clientCredentials`</span><span class="sxs-lookup"><span data-stu-id="475a5-159">By adding a [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) section of the configuration file for the client and using the `clientCredentials` element (shown below).</span></span>  
  
#### <a name="setting-a-clientcredentials-value-in-code"></a><span data-ttu-id="475a5-160">코드에서 \<clientCredentials > 값 설정</span><span class="sxs-lookup"><span data-stu-id="475a5-160">Setting a \<clientCredentials> Value in Code</span></span>  
 <span data-ttu-id="475a5-161">ClientCredentials > 값을 코드에 설정 <xref:System.ServiceModel.ClientBase%601> [ \<](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 하려면 클래스의 속성에 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-161">To set a [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) value in code, you must access the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class.</span></span> <span data-ttu-id="475a5-162">다음 표에 설명한 것처럼 속성은 다양한 자격 증명 형식에 액세스할 수 있는 <xref:System.ServiceModel.Description.ClientCredentials> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-162">The property returns a <xref:System.ServiceModel.Description.ClientCredentials> object that allows access to various credential types, as shown in the following table.</span></span>  
  
|<span data-ttu-id="475a5-163">ClientCredential 속성</span><span class="sxs-lookup"><span data-stu-id="475a5-163">ClientCredential Property</span></span>|<span data-ttu-id="475a5-164">Description</span><span class="sxs-lookup"><span data-stu-id="475a5-164">Description</span></span>|<span data-ttu-id="475a5-165">참고</span><span class="sxs-lookup"><span data-stu-id="475a5-165">Notes</span></span>|  
|-------------------------------|-----------------|-----------|  
|<xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>|<span data-ttu-id="475a5-166"><xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-166">Returns an <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential></span></span>|<span data-ttu-id="475a5-167">서비스에게 자신을 인증하기 위해 클라이언트가 제공하는 X.509 인증서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-167">Represents an X.509 certificate provided by the client to authenticate itself to the service.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>|<span data-ttu-id="475a5-168"><xref:System.ServiceModel.Security.HttpDigestClientCredential>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-168">Returns an <xref:System.ServiceModel.Security.HttpDigestClientCredential></span></span>|<span data-ttu-id="475a5-169">HTTP digest 자격 증명을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-169">Represents an HTTP digest credential.</span></span> <span data-ttu-id="475a5-170">자격 증명은 사용자 이름 및 암호에 대한 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-170">The credential is a hash of the user name and password.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>|<span data-ttu-id="475a5-171"><xref:System.ServiceModel.Security.IssuedTokenClientCredential>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-171">Returns an <xref:System.ServiceModel.Security.IssuedTokenClientCredential></span></span>|<span data-ttu-id="475a5-172">보안 토큰 서비스에서 발급한 사용자 지정 보안 토큰을 나타내며 일반적으로 페더레이션 시나리오에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-172">Represents a custom security token issued by a Security Token Service, commonly used in federation scenarios.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>|<span data-ttu-id="475a5-173"><xref:System.ServiceModel.Security.PeerCredential>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-173">Returns a <xref:System.ServiceModel.Security.PeerCredential></span></span>|<span data-ttu-id="475a5-174">Windows 도메인의 피어 메시 참가를 위해 사용할 피어 자격 증명을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-174">Represents a Peer credential for participation in a Peer mesh on a Windows domain.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>|<span data-ttu-id="475a5-175"><xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-175">Returns an <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential></span></span>|<span data-ttu-id="475a5-176">out-of-band 협상에서 서비스가 제공하는 X.509 인증서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-176">Represents an X.509 certificate provided by the service in an out-of-band negotiation.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.UserName%2A>|<span data-ttu-id="475a5-177"><xref:System.ServiceModel.Security.UserNamePasswordClientCredential>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-177">Returns a <xref:System.ServiceModel.Security.UserNamePasswordClientCredential></span></span>|<span data-ttu-id="475a5-178">사용자 이름 및 암호 쌍을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-178">Represents a user name and password pair.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>|<span data-ttu-id="475a5-179"><xref:System.ServiceModel.Security.WindowsClientCredential>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-179">Returns a <xref:System.ServiceModel.Security.WindowsClientCredential></span></span>|<span data-ttu-id="475a5-180">Windows 클라이언트 자격 증명(Kerberos 자격 증명)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-180">Represents a Windows client credential (a Kerberos credential).</span></span> <span data-ttu-id="475a5-181">클래스의 속성은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-181">The properties of the class are read-only.</span></span>|  
  
#### <a name="setting-a-clientcredentials-value-in-configuration"></a><span data-ttu-id="475a5-182">구성에서 \<clientCredentials > 값 설정</span><span class="sxs-lookup"><span data-stu-id="475a5-182">Setting a \<clientCredentials> Value in Configuration</span></span>  
 <span data-ttu-id="475a5-183">자격 증명 값은 endpoint 동작을 [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소의 자식 요소로 사용 하 여 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-183">Credential values are specified by using an endpoint behavior as child elements of the [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span> <span data-ttu-id="475a5-184">사용되는 요소는 클라이언트 자격 증명 형식에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-184">The element used depends on the client credential type.</span></span> <span data-ttu-id="475a5-185">예를 들어 다음 예제에서는 <[\<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)를 사용 하 여 x.509 인증서를 설정 하는 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-185">For example, the following example shows the configuration to set an X.509 certificate using the <[\<clientCertificate>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="myEndpointBehavior">  
          <clientCredentials>  
            <clientCertificate findvalue="myMachineName"   
            storeLocation="Current" X509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>              
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="475a5-186">구성에서 클라이언트 자격 증명을 설정 하려면 [ \<endpointbehaviors >](../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) 요소를 구성 파일에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-186">To set the client credential in configuration, add an [\<endpointBehaviors>](../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) element to the configuration file.</span></span> <span data-ttu-id="475a5-187">또한 다음 예제와 같이 `behaviorConfiguration` [ \< \<클라이언트 > 요소의 끝점 >](../configure-apps/file-schema/wcf/endpoint-of-client.md) 특성을 사용 하 여 추가 된 동작 요소를 서비스의 끝점에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-187">Additionally, the added behavior element must be linked to the service's endpoint using the `behaviorConfiguration` attribute of the [\<endpoint> of \<client>](../configure-apps/file-schema/wcf/endpoint-of-client.md) element as shown in the following example.</span></span> <span data-ttu-id="475a5-188">`behaviorConfiguration` 특성 값은 동작 `name` 특성 값과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-188">The value of the `behaviorConfiguration` attribute must match the value of the behavior `name` attribute.</span></span>  

```xml
<configuration>
  <system.serviceModel>
    <client>
      <endpoint address="http://localhost/servicemodelsamples/service.svc"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                behaviorConfiguration="myEndpointBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </client>
  </system.serviceModel>
</configuration>
```
  
> [!NOTE]
> <span data-ttu-id="475a5-189">예를 들어 사용자 이름 및 암호 또는 Windows 사용자 및 암호 값과 같은 일부 클라이언트 자격 증명 값은 애플리케이션 구성 파일을 사용하여 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-189">Some of the client credential values cannot be set using application configuration files, for example, user name and password, or Windows user and password values.</span></span> <span data-ttu-id="475a5-190">이러한 자격 증명 값은 코드에서만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-190">Such credential values can be specified only in code.</span></span>  
  
 <span data-ttu-id="475a5-191">클라이언트 자격 증명을 [설정 하는 방법에 대 한 자세한 내용은 방법: 클라이언트 자격 증명 값](../../../docs/framework/wcf/how-to-specify-client-credential-values.md)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-191">For more information about setting the client credential, see [How to: Specify Client Credential Values](../../../docs/framework/wcf/how-to-specify-client-credential-values.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="475a5-192">다음 예제 구성과 같이 `ClientCredentialType`가 `SecurityMode`로 설정된 경우 `"TransportWithMessageCredential",`은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="475a5-192">`ClientCredentialType` is ignored when `SecurityMode` is set to `"TransportWithMessageCredential",` as shown in the following sample configuration.</span></span>  
  
```xml  
<wsHttpBinding>  
    <binding name="PingBinding">  
        <security mode="TransportWithMessageCredential"  >  
           <message  clientCredentialType="UserName"   
               establishSecurityContext="false"    
               negotiateServiceCredential="false" />  
           <transport clientCredentialType="Certificate"  />  
         </security>  
    </binding>  
</wsHttpBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="475a5-193">참고자료</span><span class="sxs-lookup"><span data-stu-id="475a5-193">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>
- [<span data-ttu-id="475a5-194">\<bindings></span><span class="sxs-lookup"><span data-stu-id="475a5-194">\<bindings></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)
- [<span data-ttu-id="475a5-195">Configuration Editor 도구(SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="475a5-195">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [<span data-ttu-id="475a5-196">서비스에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="475a5-196">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)
- [<span data-ttu-id="475a5-197">WCF 클라이언트를 사용하여 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="475a5-197">Accessing Services Using a WCF Client</span></span>](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)
- [<span data-ttu-id="475a5-198">방법: 클라이언트 자격 증명 값 지정</span><span class="sxs-lookup"><span data-stu-id="475a5-198">How to: Specify Client Credential Values</span></span>](../../../docs/framework/wcf/how-to-specify-client-credential-values.md)
- [<span data-ttu-id="475a5-199">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="475a5-199">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="475a5-200">방법: 클라이언트 자격 증명 형식 지정</span><span class="sxs-lookup"><span data-stu-id="475a5-200">How to: Specify the Client Credential Type</span></span>](../../../docs/framework/wcf/how-to-specify-the-client-credential-type.md)
