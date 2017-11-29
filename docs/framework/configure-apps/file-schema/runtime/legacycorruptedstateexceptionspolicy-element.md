---
title: "&lt;legacyCorruptedStateExceptionsPolicy&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e4379f6f38c886504905483cefd7c7a6bbd519ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltlegacycorruptedstateexceptionspolicygt-element"></a><span data-ttu-id="ffb8c-102">&lt;legacyCorruptedStateExceptionsPolicy&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="ffb8c-102">&lt;legacyCorruptedStateExceptionsPolicy&gt; Element</span></span>
<span data-ttu-id="ffb8c-103">공용 언어 런타임에서 액세스 위반 및 기타 손상 된 상태 예외를 catch 하는 관리 되는 코드를 허용 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="ffb8c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ffb8c-104">\<configuration></span></span>  
<span data-ttu-id="ffb8c-105">\<런타임 ></span><span class="sxs-lookup"><span data-stu-id="ffb8c-105">\<runtime></span></span>  
<span data-ttu-id="ffb8c-106">\<legacyCorruptedStateExceptionsPolicy ></span><span class="sxs-lookup"><span data-stu-id="ffb8c-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffb8c-107">구문</span><span class="sxs-lookup"><span data-stu-id="ffb8c-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ffb8c-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ffb8c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ffb8c-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ffb8c-110">특성</span><span class="sxs-lookup"><span data-stu-id="ffb8c-110">Attributes</span></span>  
  
|<span data-ttu-id="ffb8c-111">특성</span><span class="sxs-lookup"><span data-stu-id="ffb8c-111">Attribute</span></span>|<span data-ttu-id="ffb8c-112">설명</span><span class="sxs-lookup"><span data-stu-id="ffb8c-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ffb8c-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ffb8c-114">응용 프로그램은 catch 지정 액세스 위반과 같이 손상 된 상태 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ffb8c-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="ffb8c-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="ffb8c-116">값</span><span class="sxs-lookup"><span data-stu-id="ffb8c-116">Value</span></span>|<span data-ttu-id="ffb8c-117">설명</span><span class="sxs-lookup"><span data-stu-id="ffb8c-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="ffb8c-118">응용 프로그램이 검색 되지 것입니다 액세스 위반과 같이 손상 된 상태 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="ffb8c-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="ffb8c-120">응용 프로그램은 catch 액세스 위반과 같이 손상 된 상태 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ffb8c-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ffb8c-121">Child Elements</span></span>  
 <span data-ttu-id="ffb8c-122">없음</span><span class="sxs-lookup"><span data-stu-id="ffb8c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ffb8c-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ffb8c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ffb8c-124">요소</span><span class="sxs-lookup"><span data-stu-id="ffb8c-124">Element</span></span>|<span data-ttu-id="ffb8c-125">설명</span><span class="sxs-lookup"><span data-stu-id="ffb8c-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ffb8c-126">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ffb8c-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffb8c-128">설명</span><span class="sxs-lookup"><span data-stu-id="ffb8c-128">Remarks</span></span>  
 <span data-ttu-id="ffb8c-129">.NET Framework 버전 3.5 및 이전 버전에서는 공용 언어 런타임 손상 된 프로세스 상태에 의해 발생 된 예외를 catch 하는 관리 되는 코드를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="ffb8c-130">액세스 위반은 이러한 유형의 예외의 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="ffb8c-131">부터는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], 관리 되는 코드는 더 이상 이러한 유형의 예외를 catch `catch` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-131">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="ffb8c-132">그러나 이러한 변경 내용을 재정의 수 있고 두 가지 방법으로 손상 된 상태 예외 처리를 유지 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
-   <span data-ttu-id="ffb8c-133">설정의 `<legacyCorruptedStateExceptionsPolicy>` 요소의 `enabled` 특성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="ffb8c-134">이 구성 설정은 프로세스 전체에 적용된 되 고 모든 메서드에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="ffb8c-135">또는</span><span class="sxs-lookup"><span data-stu-id="ffb8c-135">-or-</span></span>  
  
-   <span data-ttu-id="ffb8c-136">적용 된 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> 특성을 제외 하 고 포함 된 메서드에 `catch` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="ffb8c-137">이 구성 요소는 에서만 사용할 수는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 이상.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-137">This configuration element is available only in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffb8c-138">예제</span><span class="sxs-lookup"><span data-stu-id="ffb8c-138">Example</span></span>  
 <span data-ttu-id="ffb8c-139">다음 예제에서는 앞의 동작으로 응용 프로그램을 되돌려야 함을 지정 하는 방법을 보여 줍니다는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], 모든 손상 된 상태 예외 오류를 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb8c-139">The following example shows how to specify that the application should revert to the behavior before the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ffb8c-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ffb8c-140">See Also</span></span>  
 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>  
 [<span data-ttu-id="ffb8c-141">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ffb8c-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="ffb8c-142">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="ffb8c-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
