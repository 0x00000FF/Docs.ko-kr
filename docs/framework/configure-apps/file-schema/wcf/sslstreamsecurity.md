---
title: '&lt;sslStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
author: BrucePerlerMS
ms.openlocfilehash: 6eacf1833ecf980696d75c5dbcaaba3ba6403d92
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47087452"
---
# <a name="ltsslstreamsecuritygt"></a><span data-ttu-id="3b5fd-102">&lt;sslStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="3b5fd-102">&lt;sslStreamSecurity&gt;</span></span>
<span data-ttu-id="3b5fd-103">SSL 스트림을 사용한 채널 보안을 지원하는 사용자 지정 바인딩 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3b5fd-103">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="3b5fd-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3b5fd-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3b5fd-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="3b5fd-105">\<bindings></span></span>  
<span data-ttu-id="3b5fd-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3b5fd-106">\<customBinding></span></span>  
<span data-ttu-id="3b5fd-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="3b5fd-107">\<binding></span></span>  
<span data-ttu-id="3b5fd-108">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="3b5fd-108">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b5fd-109">구문</span><span class="sxs-lookup"><span data-stu-id="3b5fd-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"      sslProtocols="Ssl3|Tls|Tls11|Tls12" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b5fd-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3b5fd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3b5fd-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3b5fd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b5fd-112">특성</span><span class="sxs-lookup"><span data-stu-id="3b5fd-112">Attributes</span></span>  
  
|<span data-ttu-id="3b5fd-113">특성</span><span class="sxs-lookup"><span data-stu-id="3b5fd-113">Attribute</span></span>|<span data-ttu-id="3b5fd-114">설명</span><span class="sxs-lookup"><span data-stu-id="3b5fd-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3b5fd-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="3b5fd-115">requireClientCertificate</span></span>|<span data-ttu-id="3b5fd-116">이 바인딩에 클라이언트 인증서가 필요한지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3b5fd-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="3b5fd-117">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="3b5fd-117">The default is `false`.</span></span>|  
|<span data-ttu-id="3b5fd-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="3b5fd-118">sslProtocols</span></span>|<span data-ttu-id="3b5fd-119">지원되는 SslProtocols를 지정하는 SslProtocols 열거형 플래그 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3b5fd-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="3b5fd-120">기본값은 Ssl3&#124;Tls&#124;Tls11&#124;Tls12 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b5fd-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b5fd-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3b5fd-121">Child Elements</span></span>  
 <span data-ttu-id="3b5fd-122">없음</span><span class="sxs-lookup"><span data-stu-id="3b5fd-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3b5fd-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3b5fd-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3b5fd-124">요소</span><span class="sxs-lookup"><span data-stu-id="3b5fd-124">Element</span></span>|<span data-ttu-id="3b5fd-125">설명</span><span class="sxs-lookup"><span data-stu-id="3b5fd-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b5fd-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="3b5fd-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="3b5fd-127">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3b5fd-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3b5fd-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b5fd-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
 [<span data-ttu-id="3b5fd-129">바인딩</span><span class="sxs-lookup"><span data-stu-id="3b5fd-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3b5fd-130">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="3b5fd-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="3b5fd-131">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="3b5fd-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="3b5fd-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3b5fd-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
