---
title: '&lt;NetFx45_CultureAwareComparerGetHashCode_LongStrings&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67dae26733527a85f4fc13734da896193e53db8a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576891"
---
# <a name="ltnetfx45cultureawarecomparergethashcodelongstringsgt-element"></a><span data-ttu-id="f1484-102">&lt;NetFx45_CultureAwareComparerGetHashCode_LongStrings&gt; Element</span><span class="sxs-lookup"><span data-stu-id="f1484-102">&lt;NetFx45_CultureAwareComparerGetHashCode_LongStrings&gt; Element</span></span>
<span data-ttu-id="f1484-103">런타임이 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드에 대한 해시 코드를 계산하기 위해 고정된 양의 메모리를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1484-103">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="f1484-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f1484-104">\<configuration></span></span>  
<span data-ttu-id="f1484-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="f1484-105">\<runtime></span></span>  
<span data-ttu-id="f1484-106"><NetFx45_CultureAwareComparerGetHashCode_LongStrings></span><span class="sxs-lookup"><span data-stu-id="f1484-106"><NetFx45_CultureAwareComparerGetHashCode_LongStrings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1484-107">구문</span><span class="sxs-lookup"><span data-stu-id="f1484-107">Syntax</span></span>  
  
```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1484-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f1484-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f1484-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1484-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1484-110">특성</span><span class="sxs-lookup"><span data-stu-id="f1484-110">Attributes</span></span>  
  
|<span data-ttu-id="f1484-111">특성</span><span class="sxs-lookup"><span data-stu-id="f1484-111">Attribute</span></span>|<span data-ttu-id="f1484-112">설명</span><span class="sxs-lookup"><span data-stu-id="f1484-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f1484-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f1484-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f1484-114">해시 코드를 계산할 때 공용 언어 런타임에서 고정된 양의 메모리를 할당할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1484-114">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f1484-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="f1484-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="f1484-116">값</span><span class="sxs-lookup"><span data-stu-id="f1484-116">Value</span></span>|<span data-ttu-id="f1484-117">설명</span><span class="sxs-lookup"><span data-stu-id="f1484-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f1484-118">0</span><span class="sxs-lookup"><span data-stu-id="f1484-118">0</span></span>|<span data-ttu-id="f1484-119">공용 언어 런타임은 해시 코드를 계산하기 위해 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드에 가변적인 양의 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f1484-119">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="f1484-120">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="f1484-120">This is the default.</span></span>|  
|<span data-ttu-id="f1484-121">1</span><span class="sxs-lookup"><span data-stu-id="f1484-121">1</span></span>|<span data-ttu-id="f1484-122">공용 언어 런타임은 해시 코드를 계산하기 위해 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드에 고정적인 양의 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f1484-122">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1484-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f1484-123">Child Elements</span></span>  
 <span data-ttu-id="f1484-124">없음</span><span class="sxs-lookup"><span data-stu-id="f1484-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f1484-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f1484-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f1484-126">요소</span><span class="sxs-lookup"><span data-stu-id="f1484-126">Element</span></span>|<span data-ttu-id="f1484-127">설명</span><span class="sxs-lookup"><span data-stu-id="f1484-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f1484-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f1484-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f1484-129">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f1484-129">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1484-130">설명</span><span class="sxs-lookup"><span data-stu-id="f1484-130">Remarks</span></span>  
 <span data-ttu-id="f1484-131">기본적으로, 공용 언어 런타임은 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드에 가변적인 양의 메모리를 할당하고, 이 메서드가 (길이가 수백만 자 이상인) 매우 큰 문자열의 해시 코드를 계산하려고 할 때 <xref:System.ArgumentException> 이 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1484-131">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="f1484-132">이 요소를 애플리케이션 구성 파일에 추가하고 `enabled` 특성을 "1"로 설정하여 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드가 해시 코드의 계산을 위해 고정된 양의 메모리를 할당하는 대체 알고리즘을 사용하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1484-132">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f1484-133">`<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` 요소는 [!INCLUDE[win8](../../../../../includes/win8-md.md)] 이상의 버전에 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1484-133">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in [!INCLUDE[win8](../../../../../includes/win8-md.md)] and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1484-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="f1484-134">See also</span></span>
- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f1484-135">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f1484-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="f1484-136">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="f1484-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
