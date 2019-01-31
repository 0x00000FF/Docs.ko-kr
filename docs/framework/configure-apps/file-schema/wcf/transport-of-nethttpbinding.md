---
title: <transport>의 <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 4d84d99660e4804a5eff2e343ba01c2983520b8f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55280997"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="8c7a4-102">\<전송 >의 \<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="8c7a4-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="8c7a4-103">HTTP 전송의 인증 매개 변수를 제어하는 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="8c7a4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8c7a4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8c7a4-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8c7a4-105">\<bindings></span></span>  
<span data-ttu-id="8c7a4-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="8c7a4-106">\<netHttpBinding></span></span>  
<span data-ttu-id="8c7a4-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="8c7a4-107">\<binding></span></span>  
<span data-ttu-id="8c7a4-108">\<security></span><span class="sxs-lookup"><span data-stu-id="8c7a4-108">\<security></span></span>  
<span data-ttu-id="8c7a4-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="8c7a4-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c7a4-110">구문</span><span class="sxs-lookup"><span data-stu-id="8c7a4-110">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c7a4-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8c7a4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8c7a4-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c7a4-113">특성</span><span class="sxs-lookup"><span data-stu-id="8c7a4-113">Attributes</span></span>  
  
|<span data-ttu-id="8c7a4-114">특성</span><span class="sxs-lookup"><span data-stu-id="8c7a4-114">Attribute</span></span>|<span data-ttu-id="8c7a4-115">설명</span><span class="sxs-lookup"><span data-stu-id="8c7a4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c7a4-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8c7a4-116">clientCredentialType</span></span>|<span data-ttu-id="8c7a4-117">-HTTP 인증을 사용 하 여 클라이언트 인증을 수행할 때 사용할 자격 증명의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="8c7a4-118">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-118">The default is `None`.</span></span> <span data-ttu-id="8c7a4-119">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="8c7a4-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="8c7a4-120">proxyCredentialType</span></span>|<span data-ttu-id="8c7a4-121">-프록시를 사용 하 여 HTTP를 통해 도메인 내에서 클라이언트 인증을 수행할 때 사용할 자격 증명의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="8c7a4-122">이 특성은 부모 `mode` 요소의 `security` 특성이 `Transport` 또는 `TransportCredentialsOnly`일 때만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="8c7a4-123">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="8c7a4-124">realm</span><span class="sxs-lookup"><span data-stu-id="8c7a4-124">realm</span></span>|<span data-ttu-id="8c7a4-125">다이제스트 또는 기본 인증의 HTTP 인증 체계에 사용되는 영역을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="8c7a4-126">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="8c7a4-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="8c7a4-127">policyEnforcement</span></span>|<span data-ttu-id="8c7a4-128">이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="8c7a4-129">1.  Never - 정책이 적용되지 않습니다(확장 보호가 사용되지 않음).</span><span class="sxs-lookup"><span data-stu-id="8c7a4-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="8c7a4-130">2.  WhenSupported – 클라이언트에서 확장 보호를 지원하는 경우에만 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="8c7a4-131">3.  Always – 정책이 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="8c7a4-132">확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="8c7a4-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="8c7a4-133">protectionScenario</span></span>|<span data-ttu-id="8c7a4-134">이 열거형은 정책을 통해 적용되는 보호 시나리오를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="8c7a4-135">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="8c7a4-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="8c7a4-136">값</span><span class="sxs-lookup"><span data-stu-id="8c7a4-136">Value</span></span>|<span data-ttu-id="8c7a4-137">설명</span><span class="sxs-lookup"><span data-stu-id="8c7a4-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8c7a4-138">없음</span><span class="sxs-lookup"><span data-stu-id="8c7a4-138">None</span></span>|<span data-ttu-id="8c7a4-139">메시지가 전송 중에 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="8c7a4-140">Basic</span><span class="sxs-lookup"><span data-stu-id="8c7a4-140">Basic</span></span>|<span data-ttu-id="8c7a4-141">기본 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="8c7a4-142">Digest</span><span class="sxs-lookup"><span data-stu-id="8c7a4-142">Digest</span></span>|<span data-ttu-id="8c7a4-143">다이제스트 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="8c7a4-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="8c7a4-144">Ntlm</span></span>|<span data-ttu-id="8c7a4-145">Windows 인증이 실패할 경우 가능하면 NTLM 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="8c7a4-146">Windows</span><span class="sxs-lookup"><span data-stu-id="8c7a4-146">Windows</span></span>|<span data-ttu-id="8c7a4-147">Windows 통합 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="8c7a4-148">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="8c7a4-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="8c7a4-149">값</span><span class="sxs-lookup"><span data-stu-id="8c7a4-149">Value</span></span>|<span data-ttu-id="8c7a4-150">설명</span><span class="sxs-lookup"><span data-stu-id="8c7a4-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8c7a4-151">없음</span><span class="sxs-lookup"><span data-stu-id="8c7a4-151">None</span></span>|<span data-ttu-id="8c7a4-152">-메시지 전송 하는 동안 보안이 유지 되지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="8c7a4-153">Basic</span><span class="sxs-lookup"><span data-stu-id="8c7a4-153">Basic</span></span>|<span data-ttu-id="8c7a4-154">RFC 2617 – HTTP 인증에 정의 된 대로 기본 인증을 지정 합니다. 기본 및 다이제스트 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="8c7a4-155">Digest</span><span class="sxs-lookup"><span data-stu-id="8c7a4-155">Digest</span></span>|<span data-ttu-id="8c7a4-156">RFC 2617 – HTTP 인증에 정의 된 대로 다이제스트 인증을 지정 합니다. 기본 및 다이제스트 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="8c7a4-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="8c7a4-157">Ntlm</span></span>|<span data-ttu-id="8c7a4-158">Windows 인증이 실패할 경우 가능하면 NTLM 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="8c7a4-159">Windows</span><span class="sxs-lookup"><span data-stu-id="8c7a4-159">Windows</span></span>|<span data-ttu-id="8c7a4-160">Windows 통합 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="8c7a4-161">인증서</span><span class="sxs-lookup"><span data-stu-id="8c7a4-161">Certificate</span></span>|<span data-ttu-id="8c7a4-162">인증서를 사용하여 클라이언트 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="8c7a4-163">이 옵션은 부모 `Mode` 요소의 `security` 특성이 Transport로 설정되어 있을 때만 작동하며 TransportCredentialOnly로 설정된 경우에는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c7a4-164">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8c7a4-164">Child Elements</span></span>  
 <span data-ttu-id="8c7a4-165">없음</span><span class="sxs-lookup"><span data-stu-id="8c7a4-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c7a4-166">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8c7a4-166">Parent Elements</span></span>  
  
|<span data-ttu-id="8c7a4-167">요소</span><span class="sxs-lookup"><span data-stu-id="8c7a4-167">Element</span></span>|<span data-ttu-id="8c7a4-168">설명</span><span class="sxs-lookup"><span data-stu-id="8c7a4-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c7a4-169">\<security></span><span class="sxs-lookup"><span data-stu-id="8c7a4-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|<span data-ttu-id="8c7a4-170">에 대 한 보안 기능을 정의 합니다 [ \<netHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-170">Defines the security capabilities for the [\<netHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8c7a4-171">예제</span><span class="sxs-lookup"><span data-stu-id="8c7a4-171">Example</span></span>  
 <span data-ttu-id="8c7a4-172">다음 예제에서는 기본 바인딩이 있는 SSL 전송 보안을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="8c7a4-173">기본적으로 기본 바인딩은 HTTP 통신을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7a4-173">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"
                     proxyCredentialType="None">
            <extendedProtectionPolicy policyEnforcement="WhenSupported"
                                      protectionScenario="TransportSelected">
              <customServiceNames>
              </customServiceNames>
            </extendedProtectionPolicy>
          </transport>
        </security>
      </binding>
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="8c7a4-174">참고자료</span><span class="sxs-lookup"><span data-stu-id="8c7a4-174">See also</span></span>
- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="8c7a4-175">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="8c7a4-175">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8c7a4-176">바인딩</span><span class="sxs-lookup"><span data-stu-id="8c7a4-176">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="8c7a4-177">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="8c7a4-177">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8c7a4-178">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="8c7a4-178">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8c7a4-179">\<binding></span><span class="sxs-lookup"><span data-stu-id="8c7a4-179">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
