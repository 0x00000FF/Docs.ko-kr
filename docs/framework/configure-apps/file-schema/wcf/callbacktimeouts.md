---
title: '&lt;callbackTimeouts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e86b69b7d633fd99728936070e94da964e16de58
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="a40a6-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="a40a6-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="a40a6-103">이중 콜백 계약 시나리오에서 트랜잭션이 서버에서 클라이언트로 이동할 때의 시간 제한 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a40a6-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="a40a6-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a40a6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a40a6-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="a40a6-105">\<behaviors></span></span>  
<span data-ttu-id="a40a6-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a40a6-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="a40a6-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="a40a6-107">\<behavior></span></span>  
<span data-ttu-id="a40a6-108">\<callbackTimeOuts ></span><span class="sxs-lookup"><span data-stu-id="a40a6-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a40a6-109">구문</span><span class="sxs-lookup"><span data-stu-id="a40a6-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="a40a6-110">형식</span><span class="sxs-lookup"><span data-stu-id="a40a6-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a40a6-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a40a6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a40a6-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a40a6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a40a6-113">특성</span><span class="sxs-lookup"><span data-stu-id="a40a6-113">Attributes</span></span>  
  
|<span data-ttu-id="a40a6-114">특성</span><span class="sxs-lookup"><span data-stu-id="a40a6-114">Attribute</span></span>|<span data-ttu-id="a40a6-115">설명</span><span class="sxs-lookup"><span data-stu-id="a40a6-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="a40a6-116">트랜잭션이 완료되어야 하거나, 완료되지 못할 경우 자동으로 종료되어야 하는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a40a6-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="a40a6-117">기본값은 "00: 00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="a40a6-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a40a6-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a40a6-118">Child Elements</span></span>  
 <span data-ttu-id="a40a6-119">없음</span><span class="sxs-lookup"><span data-stu-id="a40a6-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a40a6-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a40a6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a40a6-121">요소</span><span class="sxs-lookup"><span data-stu-id="a40a6-121">Element</span></span>|<span data-ttu-id="a40a6-122">설명</span><span class="sxs-lookup"><span data-stu-id="a40a6-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a40a6-123">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="a40a6-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a40a6-124">끝점 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a40a6-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a40a6-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a40a6-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
