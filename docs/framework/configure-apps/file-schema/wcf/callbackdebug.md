---
title: '&lt;callbackDebug&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0bb730a00358f771408ff0431ff2ab77623354a4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltcallbackdebuggt"></a><span data-ttu-id="6ea19-102">&lt;callbackDebug&gt;</span><span class="sxs-lookup"><span data-stu-id="6ea19-102">&lt;callbackDebug&gt;</span></span>
<span data-ttu-id="6ea19-103">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 콜백 개체의 서비스 디버깅을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea19-103">Specifies service debugging for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] callback object.</span></span>  
  
 <span data-ttu-id="6ea19-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6ea19-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6ea19-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="6ea19-105">\<behaviors></span></span>  
<span data-ttu-id="6ea19-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="6ea19-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="6ea19-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="6ea19-107">\<behavior></span></span>  
<span data-ttu-id="6ea19-108">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="6ea19-108">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea19-109">구문</span><span class="sxs-lookup"><span data-stu-id="6ea19-109">Syntax</span></span>  
  
```xml  
<callbackDebug  includeExceptionDetailInFaults="Boolean" />  
```  
  
## <a name="type"></a><span data-ttu-id="6ea19-110">형식</span><span class="sxs-lookup"><span data-stu-id="6ea19-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ea19-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6ea19-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6ea19-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea19-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ea19-113">특성</span><span class="sxs-lookup"><span data-stu-id="6ea19-113">Attributes</span></span>  
  
|<span data-ttu-id="6ea19-114">특성</span><span class="sxs-lookup"><span data-stu-id="6ea19-114">Attribute</span></span>|<span data-ttu-id="6ea19-115">설명</span><span class="sxs-lookup"><span data-stu-id="6ea19-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="6ea19-116">클라이언트 콜백 개체가 관리되는 예외 정보를 SOAP 오류의 형태로 서비스에 반환하는지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea19-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="6ea19-117">이 특성을 프로그래밍 방식으로 `true`로 설정한 경우 클라이언트 콜백 개체에 있는 관리되는 예외 정보 흐름을 디버깅을 위해 다시 서비스로 이동하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea19-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="6ea19-118">**주의:** 관리 되는 예외 정보를 클라이언트에는 보안상 위험할 수 있습니다를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea19-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="6ea19-119">예외 정보가 내부 서비스 구현 정보를 공개하여 권한 없는 클라이언트에서 이를 사용할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea19-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ea19-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6ea19-120">Child Elements</span></span>  
 <span data-ttu-id="6ea19-121">없음</span><span class="sxs-lookup"><span data-stu-id="6ea19-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ea19-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6ea19-122">Parent Elements</span></span>  
  
|<span data-ttu-id="6ea19-123">요소</span><span class="sxs-lookup"><span data-stu-id="6ea19-123">Element</span></span>|<span data-ttu-id="6ea19-124">설명</span><span class="sxs-lookup"><span data-stu-id="6ea19-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ea19-125">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="6ea19-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="6ea19-126">끝점 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea19-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ea19-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ea19-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>  
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>
