---
title: '&lt;backupLists&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5fee9e455189d5be1c81fb950eff3882aa8222b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltbackuplistsgt"></a><span data-ttu-id="1321a-102">&lt;backupLists&gt;</span><span class="sxs-lookup"><span data-stu-id="1321a-102">&lt;backupLists&gt;</span></span>
<span data-ttu-id="1321a-103">오류 처리에서 사용되는 백업 서비스 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1321a-103">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="1321a-104">각 자식 요소에는 기본 끝점에 도달할 수 없는 경우 사용 하도록 라우팅 서비스 할 끝점 집합을 열거 하는 백업 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="1321a-104">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="1321a-105">목록의 첫 번째 끝점이 다운되는 경우 라우팅 서비스는 자동으로 목록의 다음 끝점으로 장애 조치(failover)됩니다.</span><span class="sxs-lookup"><span data-stu-id="1321a-105">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="1321a-106">따라서 복잡한 패턴을 처리하는 방법이나 모든 서비스가 배포되는 위치를 클라이언트 응용 프로그램에 지정할 필요 없이 응용 프로그램의 안정성을 빠르게 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1321a-106">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="1321a-107">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="1321a-107">\<system.serviceModel></span></span>  
<span data-ttu-id="1321a-108">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="1321a-108">\<routing></span></span>  
<span data-ttu-id="1321a-109">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="1321a-109">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1321a-110">구문</span><span class="sxs-lookup"><span data-stu-id="1321a-110">Syntax</span></span>  
  
```xml
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1321a-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1321a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1321a-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1321a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1321a-113">특성</span><span class="sxs-lookup"><span data-stu-id="1321a-113">Attributes</span></span>  
 <span data-ttu-id="1321a-114">없음</span><span class="sxs-lookup"><span data-stu-id="1321a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1321a-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1321a-115">Child Elements</span></span>  
  
|<span data-ttu-id="1321a-116">요소</span><span class="sxs-lookup"><span data-stu-id="1321a-116">Element</span></span>|<span data-ttu-id="1321a-117">설명</span><span class="sxs-lookup"><span data-stu-id="1321a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1321a-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="1321a-118">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="1321a-119">라우팅 서비스는 기본 끝점 도달할 수 없는 경우 사용 하도록 선택 하는 끝점의 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1321a-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="1321a-120">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1321a-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1321a-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1321a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1321a-122">요소</span><span class="sxs-lookup"><span data-stu-id="1321a-122">Element</span></span>|<span data-ttu-id="1321a-123">설명</span><span class="sxs-lookup"><span data-stu-id="1321a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1321a-124">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="1321a-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="1321a-125">들어오는 메시지 및 필터가 일치할 때 메시지를 보낼 대상 끝점을 정의하는 라우팅 테이블을 평가할 때 사용되는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> 형식을 결정하는 라우팅 필터 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1321a-125">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1321a-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1321a-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
