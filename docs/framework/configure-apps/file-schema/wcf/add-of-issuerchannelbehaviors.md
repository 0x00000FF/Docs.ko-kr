---
title: "&lt;issuerChannelBehaviors&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ea76a96597796b10c97ea57ca38c3bda453468c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a><span data-ttu-id="9075c-102">&lt;issuerChannelBehaviors&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="9075c-102">&lt;add&gt; of &lt;issuerChannelBehaviors&gt;</span></span>
<span data-ttu-id="9075c-103">STS와 통신할 때 사용할 끝점 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9075c-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9075c-104">어떤 끝점 동작을 포함 하는 경우는 [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소에서 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9075c-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="9075c-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9075c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="9075c-106">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="9075c-106">\<behaviors></span></span>  
<span data-ttu-id="9075c-107">endpointBehaviors 섹션</span><span class="sxs-lookup"><span data-stu-id="9075c-107">endpointBehaviors section</span></span>  
<span data-ttu-id="9075c-108">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="9075c-108">\<behavior></span></span>  
<span data-ttu-id="9075c-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="9075c-109">\<clientCredentials></span></span>  
<span data-ttu-id="9075c-110">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="9075c-110">\<issuedToken></span></span>  
<span data-ttu-id="9075c-111">\<issuerChannelBehaviors > 요소</span><span class="sxs-lookup"><span data-stu-id="9075c-111">\<issuerChannelBehaviors> Element</span></span>  
<span data-ttu-id="9075c-112">\<add></span><span class="sxs-lookup"><span data-stu-id="9075c-112">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9075c-113">구문</span><span class="sxs-lookup"><span data-stu-id="9075c-113">Syntax</span></span>  
  
```xml  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9075c-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9075c-114">Attributes and Elements</span></span>  
 <span data-ttu-id="9075c-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9075c-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9075c-116">특성</span><span class="sxs-lookup"><span data-stu-id="9075c-116">Attributes</span></span>  
  
|<span data-ttu-id="9075c-117">특성</span><span class="sxs-lookup"><span data-stu-id="9075c-117">Attribute</span></span>|<span data-ttu-id="9075c-118">설명</span><span class="sxs-lookup"><span data-stu-id="9075c-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9075c-119">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="9075c-119">issuerAddress</span></span>|<span data-ttu-id="9075c-120">통신할 보안 토큰 발급자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9075c-120">The URI of the security token issuer to communicate with.</span></span>|  
|<span data-ttu-id="9075c-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="9075c-121">behaviorConfiguration</span></span>|<span data-ttu-id="9075c-122">동일한 구성 파일에 정의된 끝점 동작 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9075c-122">The name of an endpoint behavior defined in the same configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9075c-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9075c-123">Child Elements</span></span>  
 <span data-ttu-id="9075c-124">없음</span><span class="sxs-lookup"><span data-stu-id="9075c-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9075c-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9075c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9075c-126">요소</span><span class="sxs-lookup"><span data-stu-id="9075c-126">Element</span></span>|<span data-ttu-id="9075c-127">설명</span><span class="sxs-lookup"><span data-stu-id="9075c-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9075c-128">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9075c-128">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="9075c-129">지정한 서비스 토큰 서비스와 통신할 때 사용할 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 클라이언트 끝점 동작 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9075c-129">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9075c-130">설명</span><span class="sxs-lookup"><span data-stu-id="9075c-130">Remarks</span></span>  
 <span data-ttu-id="9075c-131">`issuerAddress`는 클라이언트가 통신하려는 보안 토큰 서비스의 URI를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9075c-131">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="9075c-132">`behaviorConfiguration`은 발급된 토큰을 보안 토큰 서비스에서 가져오기 위해 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]가 만든 채널에서 응용 프로그램이 사용하는 끝점 동작을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="9075c-132">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] to get the issued tokens from the Security Token Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9075c-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9075c-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="9075c-134">서비스 Id 및 인증</span><span class="sxs-lookup"><span data-stu-id="9075c-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="9075c-135">보안 동작</span><span class="sxs-lookup"><span data-stu-id="9075c-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="9075c-136">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="9075c-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="9075c-137">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="9075c-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="9075c-138">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="9075c-138">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="9075c-139">방법: 페더레이션된 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="9075c-139">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="9075c-140">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="9075c-140">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="9075c-141">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="9075c-141">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="9075c-142">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9075c-142">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
