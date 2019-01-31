---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: ca6d401109d14ce11dcd40c393cd079170e4d20d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259873"
---
# <a name="webhttp"></a><span data-ttu-id="ca3dd-101">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="ca3dd-101">\<webHttp></span></span>
<span data-ttu-id="ca3dd-102">이 요소는 구성을 통해 엔드포인트에서 <xref:System.ServiceModel.Description.WebHttpBehavior>를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="ca3dd-103">이 동작을 함께 사용 하는 경우는 [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) 표준 바인딩 Windows Communication Foundation (WCF) 서비스에 대 한 웹 프로그래밍 모델을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-103">This behavior, when used in conjunction with the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="ca3dd-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ca3dd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ca3dd-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ca3dd-105">\<behaviors></span></span>  
<span data-ttu-id="ca3dd-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="ca3dd-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="ca3dd-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ca3dd-107">\<behavior></span></span>  
<span data-ttu-id="ca3dd-108">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="ca3dd-108">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca3dd-109">구문</span><span class="sxs-lookup"><span data-stu-id="ca3dd-109">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca3dd-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ca3dd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ca3dd-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca3dd-112">특성</span><span class="sxs-lookup"><span data-stu-id="ca3dd-112">Attributes</span></span>  
  
|<span data-ttu-id="ca3dd-113">특성</span><span class="sxs-lookup"><span data-stu-id="ca3dd-113">Attribute</span></span>|<span data-ttu-id="ca3dd-114">설명</span><span class="sxs-lookup"><span data-stu-id="ca3dd-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca3dd-115">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="ca3dd-115">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="ca3dd-116">이 속성이 `true`로 설정되면 WCF 인프라가 사용할 가장 적절한 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-116">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="ca3dd-117">기본적으로 자동 형식 선택은 이전 버전과의 호환성을 위해 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-117">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="ca3dd-118">자동 형식 선택은 프로그래밍 방식이나 구성을 통해 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-118">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="ca3dd-119">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="ca3dd-119">defaultBodyStyle</span></span>|<span data-ttu-id="ca3dd-120">반환된 메시지의 기본 본문 스타일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-120">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="ca3dd-121">자세한 내용은 <xref:System.ServiceModel.Web.WebMessageBodyStyle> 하 고 [WCF 웹 HTTP 형식 지정](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-121">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="ca3dd-122">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="ca3dd-122">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="ca3dd-123">메시지의 나가는 기본 응답 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-123">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="ca3dd-124">자세한 내용은 [WCF 웹 HTTP 형식 지정](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-124">For more information, see [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="ca3dd-125">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="ca3dd-125">faultExceptionEnabled</span></span>|<span data-ttu-id="ca3dd-126">내부 서버 오류(HTTP 상태 코드: 500)가 발생할 때 FaultException이 생성되는지 여부를 지정하는 플래그를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-126">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="ca3dd-127">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="ca3dd-127">helpEnabled</span></span>|<span data-ttu-id="ca3dd-128">도움말 페이지를 사용할 수 있는지 여부를 결정하는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-128">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca3dd-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ca3dd-129">Child Elements</span></span>  
 <span data-ttu-id="ca3dd-130">없음</span><span class="sxs-lookup"><span data-stu-id="ca3dd-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca3dd-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ca3dd-131">Parent Elements</span></span>  
  
|<span data-ttu-id="ca3dd-132">요소</span><span class="sxs-lookup"><span data-stu-id="ca3dd-132">Element</span></span>|<span data-ttu-id="ca3dd-133">설명</span><span class="sxs-lookup"><span data-stu-id="ca3dd-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca3dd-134">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ca3dd-134">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="ca3dd-135">엔드포인트 동작 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-135">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca3dd-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="ca3dd-136">See also</span></span>
- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="ca3dd-137">AJAX 통합 및 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="ca3dd-137">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="ca3dd-138">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="ca3dd-138">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
