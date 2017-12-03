---
title: '&lt;transportConfigurationTypes&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa136f75fda4a87171a8ca3e369e7cb8621ac398
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="d7b20-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="d7b20-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="d7b20-103">특정 전송의 형식을 식별하는 구성 요소 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d7b20-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="d7b20-104">사용자 지정 WAS 프로토콜을 추가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7b20-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="d7b20-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d7b20-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d7b20-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="d7b20-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="d7b20-107">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="d7b20-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7b20-108">구문</span><span class="sxs-lookup"><span data-stu-id="d7b20-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7b20-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d7b20-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d7b20-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7b20-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7b20-111">특성</span><span class="sxs-lookup"><span data-stu-id="d7b20-111">Attributes</span></span>  
  
|<span data-ttu-id="d7b20-112">특성</span><span class="sxs-lookup"><span data-stu-id="d7b20-112">Attribute</span></span>|<span data-ttu-id="d7b20-113">설명</span><span class="sxs-lookup"><span data-stu-id="d7b20-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7b20-114">name</span><span class="sxs-lookup"><span data-stu-id="d7b20-114">name</span></span>|<span data-ttu-id="d7b20-115">전송의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d7b20-115">The name of the transport</span></span>|  
|<span data-ttu-id="d7b20-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="d7b20-116">transportConfigurationType</span></span>|<span data-ttu-id="d7b20-117">전송을 구현하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d7b20-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7b20-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d7b20-118">Child Elements</span></span>  
  
|<span data-ttu-id="d7b20-119">요소</span><span class="sxs-lookup"><span data-stu-id="d7b20-119">Element</span></span>|<span data-ttu-id="d7b20-120">설명</span><span class="sxs-lookup"><span data-stu-id="d7b20-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7b20-121">\<add></span><span class="sxs-lookup"><span data-stu-id="d7b20-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="d7b20-122">특정 전송의 형식을 식별하는 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d7b20-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d7b20-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d7b20-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d7b20-124">요소</span><span class="sxs-lookup"><span data-stu-id="d7b20-124">Element</span></span>|<span data-ttu-id="d7b20-125">설명</span><span class="sxs-lookup"><span data-stu-id="d7b20-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7b20-126">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="d7b20-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="d7b20-127">특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d7b20-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7b20-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7b20-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>  
 [<span data-ttu-id="d7b20-129">호스팅</span><span class="sxs-lookup"><span data-stu-id="d7b20-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
