---
title: <filter>의 <add>에 대한 <listeners>의 <source> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 7207e72c537e8338f8c646750016c9b6c810bf9a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260582"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="eecb0-102">\<필터 > 요소에 대 한 \<추가 >에 대 한 \<수신기 >에 대 한 \<소스 ></span><span class="sxs-lookup"><span data-stu-id="eecb0-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="eecb0-103">추적 소스의 `Listeners` 컬렉션에 있는 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="eecb0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="eecb0-104">\<configuration></span></span>  
<span data-ttu-id="eecb0-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="eecb0-105">\<system.diagnostics></span></span>  
<span data-ttu-id="eecb0-106">\<sources></span><span class="sxs-lookup"><span data-stu-id="eecb0-106">\<sources></span></span>  
<span data-ttu-id="eecb0-107">\<source></span><span class="sxs-lookup"><span data-stu-id="eecb0-107">\<source></span></span>  
<span data-ttu-id="eecb0-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="eecb0-108">\<listeners></span></span>  
<span data-ttu-id="eecb0-109">\<add></span><span class="sxs-lookup"><span data-stu-id="eecb0-109">\<add></span></span>  
<span data-ttu-id="eecb0-110">\<filter></span><span class="sxs-lookup"><span data-stu-id="eecb0-110">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eecb0-111">구문</span><span class="sxs-lookup"><span data-stu-id="eecb0-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eecb0-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="eecb0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="eecb0-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eecb0-114">특성</span><span class="sxs-lookup"><span data-stu-id="eecb0-114">Attributes</span></span>  
  
|<span data-ttu-id="eecb0-115">특성</span><span class="sxs-lookup"><span data-stu-id="eecb0-115">Attribute</span></span>|<span data-ttu-id="eecb0-116">설명</span><span class="sxs-lookup"><span data-stu-id="eecb0-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="eecb0-117">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="eecb0-118">상속 해야 하는 필터의 유형을 지정 합니다 <xref:System.Diagnostics.TraceFilter> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="eecb0-119">형식에 해당 하는 형식의 정규화 된 네임 스페이스 이름을 사용할 수 있습니다 <xref:System.Type.FullName%2A> 속성에 해당 하는 어셈블리 정보를 포함 한 정규화 된 형식 이름을 사용할 수는 <xref:System.Type.AssemblyQualifiedName%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="eecb0-120">정규화 된 형식 이름에 대 한 자세한 내용은 [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="eecb0-121">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="eecb0-122">지정 된 필터 클래스에 대 한 생성자에 전달 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eecb0-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="eecb0-123">Child Elements</span></span>  
 <span data-ttu-id="eecb0-124">없음</span><span class="sxs-lookup"><span data-stu-id="eecb0-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eecb0-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="eecb0-125">Parent Elements</span></span>  
  
|<span data-ttu-id="eecb0-126">요소</span><span class="sxs-lookup"><span data-stu-id="eecb0-126">Element</span></span>|<span data-ttu-id="eecb0-127">설명</span><span class="sxs-lookup"><span data-stu-id="eecb0-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="eecb0-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="eecb0-129">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="eecb0-130">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="eecb0-131">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="eecb0-132">수집, 저장 하 고 메시지를 라우팅하는 수신기를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="eecb0-133">수신기는 추적 출력을 적절 한 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="eecb0-134">추적 소스의 `Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eecb0-135">설명</span><span class="sxs-lookup"><span data-stu-id="eecb0-135">Remarks</span></span>  
 <span data-ttu-id="eecb0-136">합니다 `<filter>` 요소에 포함 되어야 합니다는 `<add>` 수신기의 유형을 지정 하는 추적 원본 수신기에 대 한 요소에 정의 된 수신기의 이름 뿐 아니라는 [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="eecb0-137">수신기에 정의 된 경우는 [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)를 해당 수신기에 대 한 필터는 해당 요소에 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-137">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="eecb0-138">이 요소는 응용 프로그램 구성 파일과 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eecb0-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eecb0-139">예제</span><span class="sxs-lookup"><span data-stu-id="eecb0-139">Example</span></span>  
 <span data-ttu-id="eecb0-140">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 `<filter>` 수신기에 필터를 추가 하는 요소 `console` 에 `Listeners` 추적 소스에 대 한 컬렉션 `myTraceSource`,으로 필터 이벤트 수준을 지정 하 `Error`.</span><span class="sxs-lookup"><span data-stu-id="eecb0-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eecb0-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="eecb0-141">See also</span></span>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="eecb0-142">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="eecb0-142">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
