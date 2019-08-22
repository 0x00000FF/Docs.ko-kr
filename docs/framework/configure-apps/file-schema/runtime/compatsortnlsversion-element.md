---
title: <CompatSortNLSVersion> 요소
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <CompatSortNLSVersion> element
- CompatSortNLSVersion element
ms.assetid: 782cc82e-83f7-404a-80b7-6d3061a8b6e3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ebc4bf703bc22b642b0950fd60471342a615a5c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663847"
---
# <a name="compatsortnlsversion-element"></a><span data-ttu-id="2a754-102">\<CompatSortNLSVersion > 요소</span><span class="sxs-lookup"><span data-stu-id="2a754-102">\<CompatSortNLSVersion> Element</span></span>
<span data-ttu-id="2a754-103">문자열 비교를 수행할 때 런타임에서 레거시 정렬 순서를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-103">Specifies that the runtime should use legacy sort orders when performing string comparisons.</span></span>  
  
 <span data-ttu-id="2a754-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2a754-104">\<configuration></span></span>  
<span data-ttu-id="2a754-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="2a754-105">\<runtime></span></span>  
<span data-ttu-id="2a754-106">\<CompatSortNLSVersion > 요소</span><span class="sxs-lookup"><span data-stu-id="2a754-106">\<CompatSortNLSVersion> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a754-107">구문</span><span class="sxs-lookup"><span data-stu-id="2a754-107">Syntax</span></span>  
  
```xml  
<CompatSortNLSVersion    
   enabled="4096"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a754-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2a754-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2a754-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a754-110">특성</span><span class="sxs-lookup"><span data-stu-id="2a754-110">Attributes</span></span>  
  
|<span data-ttu-id="2a754-111">특성</span><span class="sxs-lookup"><span data-stu-id="2a754-111">Attribute</span></span>|<span data-ttu-id="2a754-112">설명</span><span class="sxs-lookup"><span data-stu-id="2a754-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="2a754-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="2a754-114">정렬 순서를 사용할 로캘 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-114">Specifies the locale ID whose sort order is to be used.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2a754-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="2a754-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="2a754-116">값</span><span class="sxs-lookup"><span data-stu-id="2a754-116">Value</span></span>|<span data-ttu-id="2a754-117">설명</span><span class="sxs-lookup"><span data-stu-id="2a754-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2a754-118">4096</span><span class="sxs-lookup"><span data-stu-id="2a754-118">4096</span></span>|<span data-ttu-id="2a754-119">대체 정렬 순서를 나타내는 로캘 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-119">The locale ID that represents an alternate sort order.</span></span> <span data-ttu-id="2a754-120">이 경우 4096는 .NET Framework 3.5 이전 버전의 정렬 순서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-120">In this case, 4096 represents the sort order of the .NET Framework 3.5 and earlier versions.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a754-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2a754-121">Child Elements</span></span>  
 <span data-ttu-id="2a754-122">없음</span><span class="sxs-lookup"><span data-stu-id="2a754-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2a754-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2a754-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2a754-124">요소</span><span class="sxs-lookup"><span data-stu-id="2a754-124">Element</span></span>|<span data-ttu-id="2a754-125">설명</span><span class="sxs-lookup"><span data-stu-id="2a754-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2a754-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2a754-127">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a754-128">설명</span><span class="sxs-lookup"><span data-stu-id="2a754-128">Remarks</span></span>  
 <span data-ttu-id="2a754-129">.NET Framework 4의 <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> 클래스에서 수행 하는 문자열 비교, 정렬 및 대/소문자 구분 연산은 유니코드 5.1 표준을 따르기 때문에 <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> 및와 같은 문자열 비교 메서드의 결과는와 <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> 다를 수 있습니다. 이전 버전의 .NET Framework입니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-129">Because string comparison, sorting, and casing operations performed by the <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> class in the .NET Framework 4 conform to the Unicode 5.1 standard, the results of string comparison methods such as <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> and <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> may differ from previous versions of the .NET Framework.</span></span> <span data-ttu-id="2a754-130">응용 프로그램이 레거시 동작에 의존 하는 경우 응용 프로그램의 구성 파일에 요소를 `<CompatSortNLSVersion>` 포함 하 여 .NET Framework 3.5 이전 버전에서 사용 되는 문자열 비교 및 정렬 규칙을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-130">If your application depends on legacy behavior, you can restore the string comparison and sorting rules used in the .NET Framework 3.5 and earlier versions by including the `<CompatSortNLSVersion>` element in your application's configuration file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2a754-131">레거시 문자열 비교 복원 및 정렬 규칙을 실행하려면 로컬 시스템에서 sort00001000.dll 동적 링크 라이브러리를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-131">Restoring legacy string comparison and sorting rules also requires the sort00001000.dll dynamic link library to be available on the local system.</span></span>  
  
 <span data-ttu-id="2a754-132">응용 프로그램 도메인을 만들 때 "NetFx40_Legacy20SortingBehavior" 문자열을 <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> 메서드로 전달하여 특정 응용 프로그램 도메인에 레거시 문자열 정렬과 비교 규칙을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-132">You can also use legacy string sorting and comparison rules in a specific application domain by passing the string "NetFx40_Legacy20SortingBehavior" to the <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> method when you create the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a754-133">예제</span><span class="sxs-lookup"><span data-stu-id="2a754-133">Example</span></span>  
 <span data-ttu-id="2a754-134">다음 예제에서는 현재 문화권의 규약을 사용하여 두 가지 <xref:System.String> 개체를 인스턴스화하고 <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> 메서드를 호출하여 두 개체를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-134">The following example instantiates two <xref:System.String> objects and calls the <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> method to compare them by using the conventions of the current culture.</span></span>  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 <span data-ttu-id="2a754-135">.NET Framework 4에서 예제를 실행 하면 다음과 같은 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-135">When you run the example on the .NET Framework 4, it displays the following output.</span></span>  
  
```  
sta follows a in the sort order.  
```  
  
 <span data-ttu-id="2a754-136">이는 .NET Framework 3.5에서 예제를 실행할 때 표시 되는 출력과 완전히 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-136">This is completely different from the output that is displayed when you run the example on the .NET Framework 3.5.</span></span>  
  
```  
sta equals a in the sort order.  
```  
  
 <span data-ttu-id="2a754-137">그러나 다음 구성 파일을 예제 디렉터리에 추가한 다음 .NET Framework 4에서 예제를 실행 하는 경우 출력은 3.5 .NET Framework에서 실행 될 때 예제에 의해 생성 된 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a754-137">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4, the output is identical to that produced by the example when it is run on the .NET Framework 3.5.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a754-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="2a754-138">See also</span></span>

- [<span data-ttu-id="2a754-139">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="2a754-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2a754-140">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="2a754-140">Configuration File Schema</span></span>](../index.md)
