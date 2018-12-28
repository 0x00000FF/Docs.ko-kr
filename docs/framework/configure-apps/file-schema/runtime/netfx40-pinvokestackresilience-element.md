---
title: '&lt;NetFx40_PInvokeStackResilience&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49dc991fd1f30bce6c328725a794750c753145cd
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613286"
---
# <a name="ltnetfx40pinvokestackresiliencegt-element"></a><span data-ttu-id="961a9-102">&lt;NetFx40_PInvokeStackResilience&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="961a9-102">&lt;NetFx40_PInvokeStackResilience&gt; Element</span></span>
<span data-ttu-id="961a9-103">런타임이 잘못된 플랫폼 호출 선언을 실행 시간에 자동으로 수정할지를 지정합니다. 자동 수정을 수행하는 경우 관리 코드와 비관리 코드 간 전환 속도가 느려집니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="961a9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="961a9-104">\<configuration></span></span>  
<span data-ttu-id="961a9-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="961a9-105">\<runtime></span></span>  
<span data-ttu-id="961a9-106">< NetFx40_PInvokeStackResilience ></span><span class="sxs-lookup"><span data-stu-id="961a9-106"><NetFx40_PInvokeStackResilience></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="961a9-107">구문</span><span class="sxs-lookup"><span data-stu-id="961a9-107">Syntax</span></span>  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="961a9-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="961a9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="961a9-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="961a9-110">특성</span><span class="sxs-lookup"><span data-stu-id="961a9-110">Attributes</span></span>  
  
|<span data-ttu-id="961a9-111">특성</span><span class="sxs-lookup"><span data-stu-id="961a9-111">Attribute</span></span>|<span data-ttu-id="961a9-112">설명</span><span class="sxs-lookup"><span data-stu-id="961a9-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="961a9-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="961a9-114">런타임이 잘못 된 플랫폼 검색 여부를 지정 합니다. 호출 선언 및 32 비트 플랫폼에서 런타임 시 스택의 자동으로 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="961a9-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="961a9-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="961a9-116">값</span><span class="sxs-lookup"><span data-stu-id="961a9-116">Value</span></span>|<span data-ttu-id="961a9-117">설명</span><span class="sxs-lookup"><span data-stu-id="961a9-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="961a9-118">런타임에서 사용 하는 빠른 interop 마샬링에 도입 된 아키텍처는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], 검색 하지는 않으며 수정 잘못 된 플랫폼 호출 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-118">The runtime uses the faster interop marshaling architecture introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="961a9-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="961a9-120">검색 하 고 잘못 된 플랫폼을 수정 하는 런타임을 사용 하 여 느린 전환 호출 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="961a9-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="961a9-121">Child Elements</span></span>  
 <span data-ttu-id="961a9-122">없음</span><span class="sxs-lookup"><span data-stu-id="961a9-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="961a9-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="961a9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="961a9-124">요소</span><span class="sxs-lookup"><span data-stu-id="961a9-124">Element</span></span>|<span data-ttu-id="961a9-125">설명</span><span class="sxs-lookup"><span data-stu-id="961a9-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="961a9-126">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="961a9-127">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="961a9-128">설명</span><span class="sxs-lookup"><span data-stu-id="961a9-128">Remarks</span></span>  
 <span data-ttu-id="961a9-129">이 요소를 사용 하면 빠른 interop 마샬링을 런타임 시에도 잘못 된 플랫폼 호출 선언에 대 한 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>  
  
 <span data-ttu-id="961a9-130">부터 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], 간소화 된 interop 마샬링 아키텍처는 관리 코드에서 비관리 코드로 전환 성능이 크게 향상을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="961a9-131">.NET Framework의 이전 버전에서는 마샬링 계층 검색 된 잘못 된 플랫폼 32 비트 플랫폼에서 선언을 호출 하 고 스택의 자동으로 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="961a9-132">새로운 마샬링 아키텍처는이 단계를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="961a9-133">결과적으로 전이 매우 빠르며 있지만 잘못 된 플랫폼 호출 선언 프로그램 오류를 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>  
  
 <span data-ttu-id="961a9-134">쉽게 개발 하는 동안 잘못 된 선언을 감지 Visual Studio 디버깅 환경을 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="961a9-135">합니다 [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) MDA (관리 디버깅 도우미) 디버거가 연결 된 응용 프로그램이 실행 중일 때의 잘못 된 플랫폼 호출 선언에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-135">The [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>  
  
 <span data-ttu-id="961a9-136">응용 프로그램에서 다시 컴파일할 수를 사용할 수 있는 잘못 된 플랫폼 호출 선언, 구성 요소를 사용 하는 경우 시나리오를 처리 하는 `NetFx40_PInvokeStackResilience` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="961a9-137">이 요소를 사용 하 여 응용 프로그램 구성 파일 추가 `enabled="1"` 전환 속도가 느려집니다.NET Framework의 이전 버전의 동작을 사용 하 여 호환성 모드를 옵트인 합니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="961a9-138">이전 버전의.NET Framework에 대해 컴파일된 어셈블리는 호환성 모드로이 자동으로 옵트인 및이 요소가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="961a9-139">구성 파일</span><span class="sxs-lookup"><span data-stu-id="961a9-139">Configuration File</span></span>  
 <span data-ttu-id="961a9-140">이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="961a9-140">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="961a9-141">예제</span><span class="sxs-lookup"><span data-stu-id="961a9-141">Example</span></span>  
 <span data-ttu-id="961a9-142">다음 예제에서는 플랫폼 호출 간 전환 속도가 느려집니다 응용 프로그램에 대 한 선언에 대해 잘못 된 복원 력 증가 옵트인 하는 방법을 코드와 비관리 코드.</span><span class="sxs-lookup"><span data-stu-id="961a9-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="961a9-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="961a9-143">See Also</span></span>  
- [<span data-ttu-id="961a9-144">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="961a9-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="961a9-145">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="961a9-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="961a9-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="961a9-146">pInvokeStackImbalance</span></span>](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
