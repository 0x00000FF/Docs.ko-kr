---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 1867e307ba004af821045e7d1b5775c470d8a3e8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266756"
---
# <a name="endtoendtracing"></a><span data-ttu-id="35a30-101">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="35a30-101">\<endToEndTracing></span></span>
<span data-ttu-id="35a30-102">서비스 응용 프로그램 실행 중에 종단 간 추적의 다양한 측면을 사용하거나 사용하지 않도록 설정할 수 있는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="35a30-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="35a30-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="35a30-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="35a30-104">\<diagnostic></span><span class="sxs-lookup"><span data-stu-id="35a30-104">\<diagnostic></span></span>  
<span data-ttu-id="35a30-105">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="35a30-105">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a30-106">구문</span><span class="sxs-lookup"><span data-stu-id="35a30-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35a30-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="35a30-107">Attributes and Elements</span></span>  
 <span data-ttu-id="35a30-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="35a30-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35a30-109">특성</span><span class="sxs-lookup"><span data-stu-id="35a30-109">Attributes</span></span>  
  
|<span data-ttu-id="35a30-110">특성</span><span class="sxs-lookup"><span data-stu-id="35a30-110">Attribute</span></span>|<span data-ttu-id="35a30-111">설명</span><span class="sxs-lookup"><span data-stu-id="35a30-111">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="35a30-112">활동 추적 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="35a30-112">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="35a30-113">메시지 흐름 추적 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="35a30-113">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="35a30-114">propagate 특성을 true로 설정할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="35a30-114">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35a30-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="35a30-115">Child Elements</span></span>  
 <span data-ttu-id="35a30-116">없음</span><span class="sxs-lookup"><span data-stu-id="35a30-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35a30-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="35a30-117">Parent Elements</span></span>  
  
|<span data-ttu-id="35a30-118">요소</span><span class="sxs-lookup"><span data-stu-id="35a30-118">Element</span></span>|<span data-ttu-id="35a30-119">설명</span><span class="sxs-lookup"><span data-stu-id="35a30-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35a30-120">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="35a30-120">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="35a30-121">관리자의 런타임 검사 및 제어를 위한 WCF 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="35a30-121">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35a30-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="35a30-122">See also</span></span>
- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="35a30-123">종단 간 추적</span><span class="sxs-lookup"><span data-stu-id="35a30-123">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
