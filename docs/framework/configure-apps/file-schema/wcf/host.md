---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 8a8f9db96281d8d775ff5c2923018228b3a9c1e5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269031"
---
# <a name="host"></a><span data-ttu-id="07421-101">\<host></span><span class="sxs-lookup"><span data-stu-id="07421-101">\<host></span></span>
<span data-ttu-id="07421-102">서비스 호스트의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="07421-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="07421-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="07421-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="07421-104">\<services></span><span class="sxs-lookup"><span data-stu-id="07421-104">\<services></span></span>  
<span data-ttu-id="07421-105">\<service></span><span class="sxs-lookup"><span data-stu-id="07421-105">\<service></span></span>  
<span data-ttu-id="07421-106">\<host></span><span class="sxs-lookup"><span data-stu-id="07421-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07421-107">구문</span><span class="sxs-lookup"><span data-stu-id="07421-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="07421-108">형식</span><span class="sxs-lookup"><span data-stu-id="07421-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07421-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="07421-109">Attributes and Elements</span></span>  
 <span data-ttu-id="07421-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07421-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07421-111">특성</span><span class="sxs-lookup"><span data-stu-id="07421-111">Attributes</span></span>  
 <span data-ttu-id="07421-112">없음</span><span class="sxs-lookup"><span data-stu-id="07421-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="07421-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="07421-113">Child Elements</span></span>  
  
|<span data-ttu-id="07421-114">요소</span><span class="sxs-lookup"><span data-stu-id="07421-114">Element</span></span>|<span data-ttu-id="07421-115">설명</span><span class="sxs-lookup"><span data-stu-id="07421-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07421-116">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="07421-116">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="07421-117">서비스 호스트에서 사용하는 기본 주소를 지정하는 `baseAddress` 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="07421-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="07421-118">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="07421-118">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="07421-119">서비스 호스트가 열리거나 닫히는 데 허용되는 시간 간격을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="07421-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="07421-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="07421-120">Parent Elements</span></span>  
  
|<span data-ttu-id="07421-121">요소</span><span class="sxs-lookup"><span data-stu-id="07421-121">Element</span></span>|<span data-ttu-id="07421-122">설명</span><span class="sxs-lookup"><span data-stu-id="07421-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07421-123">\<service></span><span class="sxs-lookup"><span data-stu-id="07421-123">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="07421-124">Windows Communication Foundation (WCF) 서비스에 대 한 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="07421-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07421-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="07421-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="07421-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="07421-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
