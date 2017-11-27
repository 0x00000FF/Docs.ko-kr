---
title: '&lt;clientCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a8a1b3f5f7e8eea555be10870bc00f9b975c57a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientcredentialsgt"></a><span data-ttu-id="7aefc-102">&lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="7aefc-102">&lt;clientCredentials&gt;</span></span>
<span data-ttu-id="7aefc-103">클라이언트를 서비스에 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-103">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="7aefc-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7aefc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7aefc-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="7aefc-105">\<behaviors></span></span>  
<span data-ttu-id="7aefc-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7aefc-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="7aefc-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="7aefc-107">\<behavior></span></span>  
<span data-ttu-id="7aefc-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="7aefc-108">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aefc-109">구문</span><span class="sxs-lookup"><span data-stu-id="7aefc-109">Syntax</span></span>  
  
```xml  
<clientCredentials type="String"  
      supportInteractive="Boolean" >  
   <clientCertificate>  
   </clientCertificate>  
   <digest>  
   </digest>  
   <isuedToken>  
   </isuedToken>  
   <peer>  
   </peer>  
   <serviceCertificate>  
   </serviceCertificate>  
   <windowsAuthentication>  
   </windowsAuthentication>  
</clientCredentials>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7aefc-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7aefc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7aefc-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7aefc-112">특성</span><span class="sxs-lookup"><span data-stu-id="7aefc-112">Attributes</span></span>  
  
|<span data-ttu-id="7aefc-113">특성</span><span class="sxs-lookup"><span data-stu-id="7aefc-113">Attribute</span></span>|<span data-ttu-id="7aefc-114">설명</span><span class="sxs-lookup"><span data-stu-id="7aefc-114">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="7aefc-115">런타임에 클라이언트 자격 증명을 선택할 때 대화형 사용자가 포함될 수 있는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-115">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="7aefc-116">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-116">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="7aefc-117">이 구성 요소의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-117">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7aefc-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7aefc-118">Child Elements</span></span>  
  
|<span data-ttu-id="7aefc-119">요소</span><span class="sxs-lookup"><span data-stu-id="7aefc-119">Element</span></span>|<span data-ttu-id="7aefc-120">설명</span><span class="sxs-lookup"><span data-stu-id="7aefc-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7aefc-121">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="7aefc-121">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="7aefc-122">클라이언트를 서비스에 인증하는 데 사용되는 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-122">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="7aefc-123">이 요소는 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-123">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="7aefc-124">\<httpDigest ></span><span class="sxs-lookup"><span data-stu-id="7aefc-124">\<httpDigest></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|<span data-ttu-id="7aefc-125">클라이언트를 서비스에 인증하는 데 사용되는 다이제스트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-125">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="7aefc-126">이 요소는 <xref:System.ServiceModel.Configuration.HttpDigestClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-126">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="7aefc-127">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="7aefc-127">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="7aefc-128">클라이언트를 STS(보안 토큰 서비스)에 인증하는 데 사용되는 사용자 지정 토큰 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-128">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="7aefc-129">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-129">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="7aefc-130">\<피어 ></span><span class="sxs-lookup"><span data-stu-id="7aefc-130">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="7aefc-131">현재 피어 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-131">Specifies a current peer credential.</span></span> <span data-ttu-id="7aefc-132">이 요소는 <xref:System.ServiceModel.Configuration.PeerCredentialElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-132">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="7aefc-133">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="7aefc-133">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="7aefc-134">서비스를 클라이언트에 인증하는 데 사용되는 인증서를 지정하고 인증서 옵션을 설정하기 위한 구조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-134">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="7aefc-135">이 인증서는 서비스로부터 클라이언트에게 out-of-band로 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-135">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="7aefc-136">이 요소는 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-136">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="7aefc-137">\<windows ></span><span class="sxs-lookup"><span data-stu-id="7aefc-137">\<windows></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|<span data-ttu-id="7aefc-138">Windows 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-138">Specifies a Windows credential.</span></span> <span data-ttu-id="7aefc-139">기본값은 현재 스레드의 자격 증명입니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-139">The default is the credential of the current thread.</span></span> <span data-ttu-id="7aefc-140">이 요소는 <xref:System.ServiceModel.Configuration.WindowsClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7aefc-141">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7aefc-141">Parent Elements</span></span>  
  
|<span data-ttu-id="7aefc-142">요소</span><span class="sxs-lookup"><span data-stu-id="7aefc-142">Element</span></span>|<span data-ttu-id="7aefc-143">설명</span><span class="sxs-lookup"><span data-stu-id="7aefc-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7aefc-144">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="7aefc-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="7aefc-145">끝점 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-145">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7aefc-146">설명</span><span class="sxs-lookup"><span data-stu-id="7aefc-146">Remarks</span></span>  
 <span data-ttu-id="7aefc-147">클라이언트 자격 증명은 상호 인증이 필요한 경우 서비스에 대해 클라이언트를 인증하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-147">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="7aefc-148">또한 이 구성 섹션은 클라이언트가 서비스 인증서를 사용하여 서비스에 대한 메시지 보안을 유지해야 하는 경우 서비스 인증서를 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aefc-148">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aefc-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7aefc-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 [<span data-ttu-id="7aefc-150">보안 동작</span><span class="sxs-lookup"><span data-stu-id="7aefc-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="7aefc-151">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="7aefc-151">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
