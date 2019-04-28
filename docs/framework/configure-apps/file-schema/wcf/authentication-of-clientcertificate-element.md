---
title: <authentication> <clientCertificate> 요소
ms.date: 03/30/2017
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
ms.openlocfilehash: e232cde8f6838de734e37aeee3f52cd7f7e7502d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701335"
---
# <a name="authentication-of-clientcertificate-element"></a><span data-ttu-id="184b8-102">\<인증 >의 \<clientCertificate > 요소</span><span class="sxs-lookup"><span data-stu-id="184b8-102">\<authentication> of \<clientCertificate> Element</span></span>
<span data-ttu-id="184b8-103">서비스에서 사용되는 클라이언트 인증서에 대한 인증 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-103">Specifies authentication behaviors for client certificates used by a service.</span></span>  
  
 <span data-ttu-id="184b8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="184b8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="184b8-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="184b8-105">\<behaviors></span></span>  
<span data-ttu-id="184b8-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="184b8-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="184b8-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="184b8-107">\<behavior></span></span>  
<span data-ttu-id="184b8-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="184b8-108">\<serviceCredentials></span></span>  
<span data-ttu-id="184b8-109">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="184b8-109">\<clientCertificate></span></span>  
<span data-ttu-id="184b8-110">\<authentication></span><span class="sxs-lookup"><span data-stu-id="184b8-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="184b8-111">구문</span><span class="sxs-lookup"><span data-stu-id="184b8-111">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                includeWindowsGroups="Boolean"
                mapClientCertificateToWindowsAccount="Boolean"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="184b8-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="184b8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="184b8-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="184b8-114">특성</span><span class="sxs-lookup"><span data-stu-id="184b8-114">Attributes</span></span>  
  
|<span data-ttu-id="184b8-115">특성</span><span class="sxs-lookup"><span data-stu-id="184b8-115">Attribute</span></span>|<span data-ttu-id="184b8-116">설명</span><span class="sxs-lookup"><span data-stu-id="184b8-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="184b8-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="184b8-117">customCertificateValidatorType</span></span>|<span data-ttu-id="184b8-118">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-118">Optional string.</span></span> <span data-ttu-id="184b8-119">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="184b8-120">이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="184b8-121">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="184b8-121">certificateValidationMode</span></span>|<span data-ttu-id="184b8-122">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-122">Optional enumeration.</span></span> <span data-ttu-id="184b8-123">자격 증명의 유효성을 검사하는 데 사용되는 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-123">Specifies one of the modes used to validate credentials.</span></span> <span data-ttu-id="184b8-124">이 특성은 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-124">This attribute is of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> type.</span></span> <span data-ttu-id="184b8-125"><xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>으로 설정되면 `customCertificateValidator`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-125">If set to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="184b8-126">기본값은 <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-126">The default is <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="184b8-127">includeWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="184b8-127">includeWindowsGroups</span></span>|<span data-ttu-id="184b8-128">선택적 부울입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-128">Optional Boolean.</span></span> <span data-ttu-id="184b8-129">Windows 그룹이 보안 컨텍스트에 포함될지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-129">Specifies if Windows groups are included in the security context.</span></span> <span data-ttu-id="184b8-130">이 특성을 `true`로 설정하면 전체 그룹이 확장되므로 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-130">Setting this attribute to `true` has a performance impact, as it results in a full group expansion.</span></span> <span data-ttu-id="184b8-131">사용자가 속한 그룹의 목록을 설정할 필요가 없으면 이 특성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-131">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|<span data-ttu-id="184b8-132">mapClientCertificateToWindowsAcccount</span><span class="sxs-lookup"><span data-stu-id="184b8-132">mapClientCertificateToWindowsAcccount</span></span>|<span data-ttu-id="184b8-133">Boolean입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-133">Boolean.</span></span> <span data-ttu-id="184b8-134">클라이언트가 인증서를 사용하여 Windows ID에 매핑될 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-134">Specifies whether the client can be mapped to a Windows identity using the certificate.</span></span> <span data-ttu-id="184b8-135">이 작업을 위해서는 Active Directory를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-135">Active Directory must be enabled to do this.</span></span>|  
|<span data-ttu-id="184b8-136">revocationMode</span><span class="sxs-lookup"><span data-stu-id="184b8-136">revocationMode</span></span>|<span data-ttu-id="184b8-137">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-137">Optional enumeration.</span></span> <span data-ttu-id="184b8-138">RCL(해지된 인증서 목록)을 검사하는 데 사용되는 모드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-138">One of the modes used to check for a revoked certificate lists (RCL).</span></span> <span data-ttu-id="184b8-139">기본값은 `Online`입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-139">The default is `Online`.</span></span> <span data-ttu-id="184b8-140">이 값은 HTTP 전송 보안을 사용할 때 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-140">This value is ignored when using HTTP transport security.</span></span>|  
|<span data-ttu-id="184b8-141">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="184b8-141">trustedStoreLocation</span></span>|<span data-ttu-id="184b8-142">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-142">Optional enumeration.</span></span> <span data-ttu-id="184b8-143">시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-143">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="184b8-144">서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-144">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="184b8-145">에 대 한 유효성 검사를 수행 합니다 **신뢰할 수 있는 사용자** 지정한 저장소 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-145">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="184b8-146">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-146">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="184b8-147">customCertificateValidatorType 특성</span><span class="sxs-lookup"><span data-stu-id="184b8-147">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="184b8-148">값</span><span class="sxs-lookup"><span data-stu-id="184b8-148">Value</span></span>|<span data-ttu-id="184b8-149">설명</span><span class="sxs-lookup"><span data-stu-id="184b8-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="184b8-150">문자열</span><span class="sxs-lookup"><span data-stu-id="184b8-150">String</span></span>|<span data-ttu-id="184b8-151">형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-151">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="184b8-152">certificateValidationMode 특성</span><span class="sxs-lookup"><span data-stu-id="184b8-152">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="184b8-153">값</span><span class="sxs-lookup"><span data-stu-id="184b8-153">Value</span></span>|<span data-ttu-id="184b8-154">설명</span><span class="sxs-lookup"><span data-stu-id="184b8-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="184b8-155">열거형</span><span class="sxs-lookup"><span data-stu-id="184b8-155">Enumeration</span></span>|<span data-ttu-id="184b8-156">다음 값 중 하나입니다. None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="184b8-156">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="184b8-157">자세한 내용은 [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-157">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="184b8-158">revocationMode 특성</span><span class="sxs-lookup"><span data-stu-id="184b8-158">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="184b8-159">값</span><span class="sxs-lookup"><span data-stu-id="184b8-159">Value</span></span>|<span data-ttu-id="184b8-160">설명</span><span class="sxs-lookup"><span data-stu-id="184b8-160">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="184b8-161">열거형</span><span class="sxs-lookup"><span data-stu-id="184b8-161">Enumeration</span></span>|<span data-ttu-id="184b8-162">다음 값 중 하나입니다. NoCheck, Online, 오프 라인입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-162">One of the following values: NoCheck, Online, Offline.</span></span> <span data-ttu-id="184b8-163">자세한 내용은 [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-163">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="184b8-164">trustedStoreLocation 특성</span><span class="sxs-lookup"><span data-stu-id="184b8-164">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="184b8-165">값</span><span class="sxs-lookup"><span data-stu-id="184b8-165">Value</span></span>|<span data-ttu-id="184b8-166">설명</span><span class="sxs-lookup"><span data-stu-id="184b8-166">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="184b8-167">열거형</span><span class="sxs-lookup"><span data-stu-id="184b8-167">Enumeration</span></span>|<span data-ttu-id="184b8-168">`LocalMachine` 또는 `CurrentUser` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-168">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="184b8-169">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-169">The default is `CurrentUser`.</span></span> <span data-ttu-id="184b8-170">시스템 계정으로 클라이언트 응용 프로그램을 실행하는 경우 인증서는 대개 `LocalMachine`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-170">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="184b8-171">사용자 계정으로 클라이언트 응용 프로그램을 실행하는 경우 인증서는 대개 `CurrentUser`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-171">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="184b8-172">자식 요소</span><span class="sxs-lookup"><span data-stu-id="184b8-172">Child Elements</span></span>  
 <span data-ttu-id="184b8-173">없음</span><span class="sxs-lookup"><span data-stu-id="184b8-173">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="184b8-174">부모 요소</span><span class="sxs-lookup"><span data-stu-id="184b8-174">Parent Elements</span></span>  
  
|<span data-ttu-id="184b8-175">요소</span><span class="sxs-lookup"><span data-stu-id="184b8-175">Element</span></span>|<span data-ttu-id="184b8-176">설명</span><span class="sxs-lookup"><span data-stu-id="184b8-176">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="184b8-177">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="184b8-177">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="184b8-178">서비스에 클라이언트를 인증하는 데 사용되는 X.509 인증서를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-178">Defines an X.509 certificate used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="184b8-179">설명</span><span class="sxs-lookup"><span data-stu-id="184b8-179">Remarks</span></span>  
 <span data-ttu-id="184b8-180">`<authentication>` 요소는 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> 클래스에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-180">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="184b8-181">이것은 클라이언트가 인증되는 방법을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-181">It enables you to customize how clients are authenticated.</span></span> <span data-ttu-id="184b8-182">`certificateValidationMode` 특성을 `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` 또는 `Custom`으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-182">You can set the `certificateValidationMode` attribute to `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, or `Custom`.</span></span> <span data-ttu-id="184b8-183">기본적으로 수준 설정 `ChainTrust`에서 종료 되는 인증서의 계층 구조에서 각 인증서를 찾을 수 해야를 지정 하는 *루트 기관* 체인의 맨 위에 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-183">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a *root authority* at the top of the chain.</span></span> <span data-ttu-id="184b8-184">이 모드가 가장 안전한 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-184">This is the most secure mode.</span></span> <span data-ttu-id="184b8-185">또한 값을 `PeerOrChainTrust`로 설정할 수 있으며, 이는 자체 발급된 인증서(신뢰 피어)가 신뢰 체인에 있는 인증서와 함께 수락됨을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-185">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="184b8-186">자체 발급 인증서를 신뢰할 수 있는 기관에서 구입할 필요 없기 때문에 클라이언트 및 서비스를 개발 및 디버깅하는 경우 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-186">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="184b8-187">클라이언트를 배포하는 경우 `ChainTrust` 값을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-187">When deploying a client, use the `ChainTrust` value instead.</span></span>  
  
 <span data-ttu-id="184b8-188">또한 값을 `Custom`으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-188">You can also set the value to `Custom`.</span></span> <span data-ttu-id="184b8-189">`Custom` 값으로 설정할 경우 `customCertificateValidatorType` 특성도 인증서 유효성을 검사하는 데 사용되는 어셈블리 및 형식으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-189">When set to the `Custom` value, you must also set the `customCertificateValidatorType` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="184b8-190">사용자 지정 유효성 검사기를 만들려면 추상 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 클래스에서 상속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-190">To create your own custom validator, you must inherit from the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="184b8-191">자세한 내용은 [방법: 사용자 지정 인증서 유효성 검사기를 사용 하는 서비스 만들기](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-191">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="184b8-192">예제</span><span class="sxs-lookup"><span data-stu-id="184b8-192">Example</span></span>  
 <span data-ttu-id="184b8-193">다음 코드에서는 X.509 인증서와 `<authentication>` 요소의 사용자 지정 유효성 검사 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="184b8-193">The following code specifies an X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="184b8-194">참고자료</span><span class="sxs-lookup"><span data-stu-id="184b8-194">See also</span></span>

- <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>
- <xref:System.ServiceModel.Security.X509CertificateValidationMode>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>
- [<span data-ttu-id="184b8-195">보안 동작</span><span class="sxs-lookup"><span data-stu-id="184b8-195">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="184b8-196">방법: 사용자 지정 인증서 유효성 검사기를 사용 하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="184b8-196">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="184b8-197">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="184b8-197">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
