---
title: "&lt;호스트&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d498190e7d7c3a6e879c50324e3b973f0f8e8fa6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="lthostgt"></a><span data-ttu-id="1b5fa-102">&lt;호스트&gt;</span><span class="sxs-lookup"><span data-stu-id="1b5fa-102">&lt;host&gt;</span></span>
<span data-ttu-id="1b5fa-103">서비스 호스트의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5fa-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="1b5fa-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1b5fa-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1b5fa-105">\<서비스 ></span><span class="sxs-lookup"><span data-stu-id="1b5fa-105">\<services></span></span>  
<span data-ttu-id="1b5fa-106">\<서비스 ></span><span class="sxs-lookup"><span data-stu-id="1b5fa-106">\<service></span></span>  
<span data-ttu-id="1b5fa-107">\<호스트 ></span><span class="sxs-lookup"><span data-stu-id="1b5fa-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b5fa-108">구문</span><span class="sxs-lookup"><span data-stu-id="1b5fa-108">Syntax</span></span>  
  
```xml  
<host>  
      <baseAddresses>  
         <baseAddress baseAddress="string" />  
      </baseAddresses>  
      <timeOuts closeTimeout="TimeSpan"  
         openTimeout="TimeSpan" >  
</host>  
```  
  
## <a name="type"></a><span data-ttu-id="1b5fa-109">형식</span><span class="sxs-lookup"><span data-stu-id="1b5fa-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b5fa-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1b5fa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1b5fa-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5fa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b5fa-112">특성</span><span class="sxs-lookup"><span data-stu-id="1b5fa-112">Attributes</span></span>  
 <span data-ttu-id="1b5fa-113">없음</span><span class="sxs-lookup"><span data-stu-id="1b5fa-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1b5fa-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1b5fa-114">Child Elements</span></span>  
  
|<span data-ttu-id="1b5fa-115">요소</span><span class="sxs-lookup"><span data-stu-id="1b5fa-115">Element</span></span>|<span data-ttu-id="1b5fa-116">설명</span><span class="sxs-lookup"><span data-stu-id="1b5fa-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b5fa-117">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="1b5fa-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="1b5fa-118">서비스 호스트에서 사용하는 기본 주소를 지정하는 `baseAddress` 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1b5fa-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="1b5fa-119">\<제한 시간 ></span><span class="sxs-lookup"><span data-stu-id="1b5fa-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="1b5fa-120">서비스 호스트가 열리거나 닫히는 데 허용되는 시간 간격을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1b5fa-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1b5fa-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1b5fa-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1b5fa-122">요소</span><span class="sxs-lookup"><span data-stu-id="1b5fa-122">Element</span></span>|<span data-ttu-id="1b5fa-123">설명</span><span class="sxs-lookup"><span data-stu-id="1b5fa-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b5fa-124">\<서비스 ></span><span class="sxs-lookup"><span data-stu-id="1b5fa-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="1b5fa-125">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5fa-125">Specifies the settings for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b5fa-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b5fa-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="1b5fa-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="1b5fa-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
