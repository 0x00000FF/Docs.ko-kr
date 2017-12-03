---
title: "&lt;extensions&gt; 섹션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06c8106f004a25f1e4547e9629b881e5bf216490
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltextensionsgt-section"></a><span data-ttu-id="2834c-102">&lt;extensions&gt; 섹션</span><span class="sxs-lookup"><span data-stu-id="2834c-102">&lt;extensions&gt; section</span></span>
<span data-ttu-id="2834c-103">이 구성 섹션에는 사용자 정의 바인딩, 동작 및 확장의 기타 측면을 만들 수 있도록 하는 확장명 컬렉션이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2834c-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="2834c-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2834c-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2834c-105">구문</span><span class="sxs-lookup"><span data-stu-id="2834c-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <extensions>  
    <bindingExtensions>  
    </bindingExtensions>  
    <behaviorExtensions>  
    </behaviorExtensions>  
    <bindingElementExtensions>  
    </bindingElementExtensions>
    <endpointExtensions>
    </endpointExtensions>
  </extensions>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2834c-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2834c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="2834c-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2834c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2834c-108">특성</span><span class="sxs-lookup"><span data-stu-id="2834c-108">Attributes</span></span>  
 <span data-ttu-id="2834c-109">없음</span><span class="sxs-lookup"><span data-stu-id="2834c-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2834c-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2834c-110">Child Elements</span></span>  
  
|<span data-ttu-id="2834c-111">요소</span><span class="sxs-lookup"><span data-stu-id="2834c-111">Element</span></span>|<span data-ttu-id="2834c-112">설명</span><span class="sxs-lookup"><span data-stu-id="2834c-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2834c-113">\<behaviorExtensions ></span><span class="sxs-lookup"><span data-stu-id="2834c-113">\<behaviorExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md)|<span data-ttu-id="2834c-114">이 섹션에는 서비스 또는 끝점 동작을 사용자 지정할 수 있도록 하는 동작 확장을 지정하는 자식 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2834c-114">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="2834c-115">\<t e x ></span><span class="sxs-lookup"><span data-stu-id="2834c-115">\<bindingElementExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md)|<span data-ttu-id="2834c-116">이 섹션은 시스템 또는 응용 프로그램 구성 파일의 사용자 지정 요소를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2834c-116">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="2834c-117">\<bindingExtensions ></span><span class="sxs-lookup"><span data-stu-id="2834c-117">\<bindingExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingextensions.md)|<span data-ttu-id="2834c-118">이 섹션에는 바인딩을 사용자 지정할 수 있도록 하는 바인딩 확장을 지정하는 자식 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2834c-118">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="2834c-119">\<endpointExtensions ></span><span class="sxs-lookup"><span data-stu-id="2834c-119">\<endpointExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointextensions.md)|<span data-ttu-id="2834c-120">이 섹션에는 표준 끝점을 등록하는 자식 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2834c-120">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2834c-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2834c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2834c-122">요소</span><span class="sxs-lookup"><span data-stu-id="2834c-122">Element</span></span>|<span data-ttu-id="2834c-123">설명</span><span class="sxs-lookup"><span data-stu-id="2834c-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2834c-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2834c-124">system.ServiceModel</span></span>|<span data-ttu-id="2834c-125">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2834c-125">The root element of all WCF configuration elements.</span></span>|
