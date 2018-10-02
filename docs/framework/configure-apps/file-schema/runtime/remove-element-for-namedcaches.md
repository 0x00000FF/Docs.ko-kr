---
title: '&lt;제거할&gt; 요소에 대 한 &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f885416629ae58949cc688f4e6fbd41e77e872aa
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47861901"
---
# <a name="ltremovegt-element-for-ltnamedcachesgt"></a><span data-ttu-id="123d8-102">&lt;제거할&gt; 요소에 대 한 &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="123d8-102">&lt;remove&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="123d8-103">메모리 캐시용으로 명명된 캐시 항목을 `namedCaches` 컬렉션에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="123d8-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="123d8-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="123d8-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="123d8-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="123d8-105">\<memoryCache></span></span>  
<span data-ttu-id="123d8-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="123d8-106">\<namedCaches></span></span>  
<span data-ttu-id="123d8-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="123d8-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="123d8-108">구문</span><span class="sxs-lookup"><span data-stu-id="123d8-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="123d8-109">형식</span><span class="sxs-lookup"><span data-stu-id="123d8-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="123d8-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="123d8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="123d8-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="123d8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="123d8-112">특성</span><span class="sxs-lookup"><span data-stu-id="123d8-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="123d8-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="123d8-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="123d8-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="123d8-114">Parent Elements</span></span>  
  
|<span data-ttu-id="123d8-115">요소</span><span class="sxs-lookup"><span data-stu-id="123d8-115">Element</span></span>|<span data-ttu-id="123d8-116">설명</span><span class="sxs-lookup"><span data-stu-id="123d8-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="123d8-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="123d8-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="123d8-118">명명 된 구성 설정의 컬렉션을 포함 <xref:System.Runtime.Caching.MemoryCache> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="123d8-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="123d8-119">설명</span><span class="sxs-lookup"><span data-stu-id="123d8-119">Remarks</span></span>  
 <span data-ttu-id="123d8-120">합니다 `remove` 요소를 제거는 `namedCache` 메모리 캐시에 대 한 명명 된 캐시 컬렉션에서 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="123d8-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="123d8-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="123d8-121">See Also</span></span>  
 [<span data-ttu-id="123d8-122">\<namedCaches > 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="123d8-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
