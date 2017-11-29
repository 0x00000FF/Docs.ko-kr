---
title: '&lt;useManagedPresentation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f99879ab80acddf1d50f5e5c734b8d6c975cb348
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltusemanagedpresentationgt"></a><span data-ttu-id="96e69-102">&lt;useManagedPresentation&gt;</span><span class="sxs-lookup"><span data-stu-id="96e69-102">&lt;useManagedPresentation&gt;</span></span>
<span data-ttu-id="96e69-103">WS-Trust의 CardSpace 프로필을 지원하는 CardSpace 보안 토큰 서비스와 통신하는 데 사용되는 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="96e69-103">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="96e69-104">이 요소는 특성이 없고 빈 스위치로 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="96e69-104">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="96e69-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="96e69-105">\<system.serviceModel></span></span>  
<span data-ttu-id="96e69-106">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="96e69-106">\<bindings></span></span>  
<span data-ttu-id="96e69-107">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="96e69-107">\<customBinding></span></span>  
<span data-ttu-id="96e69-108">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="96e69-108">\<binding></span></span>  
<span data-ttu-id="96e69-109">\<useManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="96e69-109">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96e69-110">구문</span><span class="sxs-lookup"><span data-stu-id="96e69-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96e69-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="96e69-111">Attributes and Elements</span></span>  
 <span data-ttu-id="96e69-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96e69-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96e69-113">특성</span><span class="sxs-lookup"><span data-stu-id="96e69-113">Attributes</span></span>  
 <span data-ttu-id="96e69-114">없음</span><span class="sxs-lookup"><span data-stu-id="96e69-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="96e69-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="96e69-115">Child Elements</span></span>  
 <span data-ttu-id="96e69-116">없음</span><span class="sxs-lookup"><span data-stu-id="96e69-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="96e69-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="96e69-117">Parent Elements</span></span>  
  
|<span data-ttu-id="96e69-118">요소</span><span class="sxs-lookup"><span data-stu-id="96e69-118">Element</span></span>|<span data-ttu-id="96e69-119">설명</span><span class="sxs-lookup"><span data-stu-id="96e69-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96e69-120">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="96e69-120">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="96e69-121">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96e69-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96e69-122">설명</span><span class="sxs-lookup"><span data-stu-id="96e69-122">Remarks</span></span>  
 <span data-ttu-id="96e69-123">이 요소는 ID 공급자가 정책에서 WS-Trust의 CardSpace 프로필을 지원함을 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96e69-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="96e69-124">그러한 정책 어설션을 게시하는 ID 공급자는 해당 CardSpace 프로필을 기반으로 토큰을 발급할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96e69-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e69-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96e69-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>  
 <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="96e69-126">바인딩</span><span class="sxs-lookup"><span data-stu-id="96e69-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="96e69-127">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="96e69-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="96e69-128">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="96e69-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="96e69-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="96e69-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
