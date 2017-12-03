---
title: "&lt;defaultPorts&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2aa63c7a5e730b2fb45f614cb2fe5f88444cee4a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a><span data-ttu-id="1dc3e-102">&lt;defaultPorts&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="1dc3e-102">&lt;add&gt; of &lt;defaultPorts&gt;</span></span>
<span data-ttu-id="1dc3e-103">클라이언트 응용 프로그램에서 수신하는 기본 통신 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="1dc3e-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="1dc3e-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1dc3e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1dc3e-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="1dc3e-105">\<behaviors></span></span>  
<span data-ttu-id="1dc3e-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1dc3e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1dc3e-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="1dc3e-107">\<behavior></span></span>  
<span data-ttu-id="1dc3e-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="1dc3e-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="1dc3e-109">\<a d d ></span><span class="sxs-lookup"><span data-stu-id="1dc3e-109">\<defaultPorts></span></span>  
<span data-ttu-id="1dc3e-110">\<add></span><span class="sxs-lookup"><span data-stu-id="1dc3e-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dc3e-111">구문</span><span class="sxs-lookup"><span data-stu-id="1dc3e-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>   <defaultPorts>      <add port="Integer" scheme="String" />   </defaultPorts></useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dc3e-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1dc3e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1dc3e-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1dc3e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dc3e-114">특성</span><span class="sxs-lookup"><span data-stu-id="1dc3e-114">Attributes</span></span>  
  
|<span data-ttu-id="1dc3e-115">특성</span><span class="sxs-lookup"><span data-stu-id="1dc3e-115">Attribute</span></span>|<span data-ttu-id="1dc3e-116">설명</span><span class="sxs-lookup"><span data-stu-id="1dc3e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1dc3e-117">포트</span><span class="sxs-lookup"><span data-stu-id="1dc3e-117">port</span></span>|<span data-ttu-id="1dc3e-118">기본 통신 포트 번호를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="1dc3e-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="1dc3e-119">scheme</span><span class="sxs-lookup"><span data-stu-id="1dc3e-119">scheme</span></span>|<span data-ttu-id="1dc3e-120">통신 포트와 연결된 프로토콜 설정 그룹을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1dc3e-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1dc3e-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1dc3e-121">Child Elements</span></span>  
 <span data-ttu-id="1dc3e-122">없음</span><span class="sxs-lookup"><span data-stu-id="1dc3e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1dc3e-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1dc3e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1dc3e-124">요소</span><span class="sxs-lookup"><span data-stu-id="1dc3e-124">Element</span></span>|<span data-ttu-id="1dc3e-125">설명</span><span class="sxs-lookup"><span data-stu-id="1dc3e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dc3e-126">\<a d d ></span><span class="sxs-lookup"><span data-stu-id="1dc3e-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="1dc3e-127">클라이언트 응용 프로그램에서 수신하는 기본 통신 끝점을 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1dc3e-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1dc3e-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1dc3e-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>
