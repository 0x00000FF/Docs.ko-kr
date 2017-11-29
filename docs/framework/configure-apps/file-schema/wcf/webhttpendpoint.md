---
title: '&lt;webHttpEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5c8d75c457c4f8ec427480afd0e4d3e7335ff981
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltwebhttpendpointgt"></a><span data-ttu-id="2cb6d-102">&lt;webHttpEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="2cb6d-102">&lt;webHttpEndpoint&gt;</span></span>
<span data-ttu-id="2cb6d-103">이 구성 요소는 고정 되어 있는 표준 끝점을 정의 [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) 바인딩에 자동으로 추가 하는 [ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb6d-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="2cb6d-104">REST 서비스를 작성할 때는 이 끝점을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb6d-104">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="2cb6d-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2cb6d-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="2cb6d-106">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="2cb6d-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cb6d-107">구문</span><span class="sxs-lookup"><span data-stu-id="2cb6d-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String" 
                        defaultOutgoingResponseFormat="Xml/Json" 
                        helpEnabled="Boolean" 
                        webEndpointType="String"/>
    </webHttpEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cb6d-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2cb6d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2cb6d-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb6d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cb6d-110">특성</span><span class="sxs-lookup"><span data-stu-id="2cb6d-110">Attributes</span></span>  
  
|<span data-ttu-id="2cb6d-111">특성</span><span class="sxs-lookup"><span data-stu-id="2cb6d-111">Attribute</span></span>|<span data-ttu-id="2cb6d-112">설명</span><span class="sxs-lookup"><span data-stu-id="2cb6d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2cb6d-113">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="2cb6d-113">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="2cb6d-114">자동 서식 선택을 사용하는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb6d-114">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="2cb6d-115">자동 서식 선택을 사용하면 인프라에서 요청 메시지의 `Accept` 헤더를 구문 분석하여 가장 적합한 응답 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb6d-115">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="2cb6d-116">`Accept` 헤더에서 적합한 응답 형식을 지정하지 않는 경우 인프라에서 요청 메시지의 `Content-Type`이나 작업의 기본 응답 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb6d-116">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="2cb6d-117">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="2cb6d-117">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="2cb6d-118">나가는 응답의 기본 형식을 지정하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb6d-118">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="2cb6d-119">이 특성은 <xref:System.ServiceModel.Web.WebMessageFormat> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb6d-119">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="2cb6d-120">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="2cb6d-120">helpEnabled</span></span>|<span data-ttu-id="2cb6d-121">끝점에 대해 HTTP 도움말 페이지가 사용되는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb6d-121">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="2cb6d-122">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="2cb6d-122">webEndpointType</span></span>|<span data-ttu-id="2cb6d-123">끝점의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb6d-123">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2cb6d-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2cb6d-124">Child Elements</span></span>  
 <span data-ttu-id="2cb6d-125">없음</span><span class="sxs-lookup"><span data-stu-id="2cb6d-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2cb6d-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2cb6d-126">Parent Elements</span></span>  
  
|<span data-ttu-id="2cb6d-127">요소</span><span class="sxs-lookup"><span data-stu-id="2cb6d-127">Element</span></span>|<span data-ttu-id="2cb6d-128">설명</span><span class="sxs-lookup"><span data-stu-id="2cb6d-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2cb6d-129">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="2cb6d-129">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="2cb6d-130">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 끝점인 표준 끝점의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb6d-130">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2cb6d-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cb6d-131">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
