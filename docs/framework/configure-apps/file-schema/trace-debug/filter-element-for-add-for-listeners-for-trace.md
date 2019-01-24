---
title: '&lt;필터&gt; 요소에 대 한 &lt;추가할&gt; 에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 85d81beead84be48730ba3a4469e8efdff1bbb0b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523693"
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="83df0-102">&lt;필터&gt; 요소에 대 한 &lt;추가할&gt; 에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;</span><span class="sxs-lookup"><span data-stu-id="83df0-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="83df0-103">수신기에 필터를 추가 합니다 `Listeners` 추적에 대 한 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
 <span data-ttu-id="83df0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="83df0-104">\<configuration></span></span>  
<span data-ttu-id="83df0-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="83df0-105">\<system.diagnostics></span></span>  
<span data-ttu-id="83df0-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="83df0-106">\<trace></span></span>  
<span data-ttu-id="83df0-107">\<listeners></span><span class="sxs-lookup"><span data-stu-id="83df0-107">\<listeners></span></span>  
<span data-ttu-id="83df0-108">\<add></span><span class="sxs-lookup"><span data-stu-id="83df0-108">\<add></span></span>  
<span data-ttu-id="83df0-109">\<filter></span><span class="sxs-lookup"><span data-stu-id="83df0-109">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83df0-110">구문</span><span class="sxs-lookup"><span data-stu-id="83df0-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83df0-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="83df0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="83df0-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83df0-113">특성</span><span class="sxs-lookup"><span data-stu-id="83df0-113">Attributes</span></span>  
  
|<span data-ttu-id="83df0-114">특성</span><span class="sxs-lookup"><span data-stu-id="83df0-114">Attribute</span></span>|<span data-ttu-id="83df0-115">설명</span><span class="sxs-lookup"><span data-stu-id="83df0-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="83df0-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="83df0-117">상속 해야 하는 필터의 유형을 지정 합니다 <xref:System.Diagnostics.TraceFilter> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="83df0-118">형식에 해당 하는 형식의 정규화 된 네임 스페이스 이름을 사용할 수 있습니다 <xref:System.Type.FullName%2A> 속성에 해당 하는 어셈블리 정보를 포함 한 정규화 된 형식 이름을 사용할 수는 <xref:System.Type.AssemblyQualifiedName%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="83df0-119">정규화 된 형식 이름에 대 한 자세한 내용은 [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="83df0-120">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="83df0-121">지정 된 필터 클래스에 대 한 생성자에 전달 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83df0-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="83df0-122">Child Elements</span></span>  
 <span data-ttu-id="83df0-123">없음</span><span class="sxs-lookup"><span data-stu-id="83df0-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83df0-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="83df0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="83df0-125">요소</span><span class="sxs-lookup"><span data-stu-id="83df0-125">Element</span></span>|<span data-ttu-id="83df0-126">설명</span><span class="sxs-lookup"><span data-stu-id="83df0-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="83df0-127">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="83df0-128">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="83df0-129">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="83df0-130">수집, 저장 하 고 메시지를 라우팅하는 수신기를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="83df0-131">수신기는 추적 출력을 적절 한 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="83df0-132">`Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83df0-133">설명</span><span class="sxs-lookup"><span data-stu-id="83df0-133">Remarks</span></span>  
 <span data-ttu-id="83df0-134">합니다 `<filter>` 요소에 포함 되어야 합니다는 `<add>` 수신기의 형식을 지정 하는 추적 수신기에 대 한 요소에 정의 된 수신기의 이름 뿐 아니라는 [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="83df0-135">수신기에 정의 된 경우는 [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)를 해당 수신기에 대 한 필터는 해당 요소에 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-135">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="83df0-136">이 요소는 응용 프로그램 구성 파일과 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83df0-137">예제</span><span class="sxs-lookup"><span data-stu-id="83df0-137">Example</span></span>  
 <span data-ttu-id="83df0-138">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 `<filter>` 수신기에 필터를 추가 하는 요소 `console` 에 `Listeners` 추적용으로 필터 이벤트 수준을 지정 하는 컬렉션 `Error`합니다.</span><span class="sxs-lookup"><span data-stu-id="83df0-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="83df0-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="83df0-139">See also</span></span>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="83df0-140">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="83df0-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
