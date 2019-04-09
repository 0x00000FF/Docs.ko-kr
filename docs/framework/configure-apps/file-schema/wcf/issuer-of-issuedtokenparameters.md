---
title: <issuer> / <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 690ab14ea33ba9bef29788b2eb35f86ed945ce2b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113544"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="8c605-102">\<발급자 >의 \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="8c605-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="8c605-103">보안 토큰을 발급하는 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c605-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="8c605-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8c605-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8c605-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8c605-105">\<bindings></span></span>  
<span data-ttu-id="8c605-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="8c605-106">\<customBinding></span></span>  
<span data-ttu-id="8c605-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="8c605-107">\<binding></span></span>  
<span data-ttu-id="8c605-108">\<security></span><span class="sxs-lookup"><span data-stu-id="8c605-108">\<security></span></span>  
<span data-ttu-id="8c605-109">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="8c605-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="8c605-110">\<issuer></span><span class="sxs-lookup"><span data-stu-id="8c605-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c605-111">구문</span><span class="sxs-lookup"><span data-stu-id="8c605-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c605-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8c605-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8c605-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c605-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c605-114">특성</span><span class="sxs-lookup"><span data-stu-id="8c605-114">Attributes</span></span>  
  
|<span data-ttu-id="8c605-115">특성</span><span class="sxs-lookup"><span data-stu-id="8c605-115">Attribute</span></span>|<span data-ttu-id="8c605-116">설명</span><span class="sxs-lookup"><span data-stu-id="8c605-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c605-117">주소</span><span class="sxs-lookup"><span data-stu-id="8c605-117">address</span></span>|<span data-ttu-id="8c605-118">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8c605-118">Required string.</span></span> <span data-ttu-id="8c605-119">STS의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="8c605-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c605-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8c605-120">Child Elements</span></span>  
  
|<span data-ttu-id="8c605-121">요소</span><span class="sxs-lookup"><span data-stu-id="8c605-121">Element</span></span>|<span data-ttu-id="8c605-122">설명</span><span class="sxs-lookup"><span data-stu-id="8c605-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c605-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="8c605-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="8c605-124">작성기에서 만들 수 있는 엔드포인트의 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8c605-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="8c605-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="8c605-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="8c605-126">발급된 토큰을 사용하는 경우 클라이언트가 서버를 인증할 수 있도록 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c605-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c605-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8c605-127">Parent Elements</span></span>  
  
|<span data-ttu-id="8c605-128">요소</span><span class="sxs-lookup"><span data-stu-id="8c605-128">Element</span></span>|<span data-ttu-id="8c605-129">설명</span><span class="sxs-lookup"><span data-stu-id="8c605-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c605-130">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="8c605-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="8c605-131">현재 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c605-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c605-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="8c605-132">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="8c605-133">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="8c605-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="8c605-134">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="8c605-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8c605-135">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="8c605-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="8c605-136">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="8c605-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8c605-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="8c605-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="8c605-138">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="8c605-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8c605-139">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="8c605-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="8c605-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="8c605-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="8c605-141">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="8c605-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="8c605-142">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="8c605-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
