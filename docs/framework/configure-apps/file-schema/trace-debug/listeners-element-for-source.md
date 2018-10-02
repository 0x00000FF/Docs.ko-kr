---
title: '&lt;수신기&gt; 요소에 대 한 &lt;원본&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 86b85779f4eff72e8ab910a5ccd32fd369270509
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48027821"
---
# <a name="ltlistenersgt-element-for-ltsourcegt"></a><span data-ttu-id="06d44-102">&lt;수신기&gt; 요소에 대 한 &lt;원본&gt;</span><span class="sxs-lookup"><span data-stu-id="06d44-102">&lt;listeners&gt; Element for &lt;source&gt;</span></span>
<span data-ttu-id="06d44-103">추가 하거나에서 수신기를 제거 합니다 <xref:System.Diagnostics.TraceSource.Listeners%2A> 컬렉션에 대 한는 <xref:System.Diagnostics.TraceSource>합니다.</span><span class="sxs-lookup"><span data-stu-id="06d44-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="06d44-104">수신기는 추적 출력을 로그, 창 또는 텍스트 파일과 같은 적절 한 대상에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="06d44-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="06d44-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="06d44-105">\<configuration></span></span>  
<span data-ttu-id="06d44-106">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="06d44-106">\<system.diagnostics></span></span>  
<span data-ttu-id="06d44-107">\<원본 ></span><span class="sxs-lookup"><span data-stu-id="06d44-107">\<sources></span></span>  
<span data-ttu-id="06d44-108">\<원본 ></span><span class="sxs-lookup"><span data-stu-id="06d44-108">\<source></span></span>  
<span data-ttu-id="06d44-109">\<수신기 > 요소</span><span class="sxs-lookup"><span data-stu-id="06d44-109">\<listeners> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06d44-110">구문</span><span class="sxs-lookup"><span data-stu-id="06d44-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06d44-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="06d44-111">Attributes and Elements</span></span>  
 <span data-ttu-id="06d44-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="06d44-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06d44-113">특성</span><span class="sxs-lookup"><span data-stu-id="06d44-113">Attributes</span></span>  
 <span data-ttu-id="06d44-114">없음</span><span class="sxs-lookup"><span data-stu-id="06d44-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="06d44-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="06d44-115">Child Elements</span></span>  
  
|<span data-ttu-id="06d44-116">요소</span><span class="sxs-lookup"><span data-stu-id="06d44-116">Element</span></span>|<span data-ttu-id="06d44-117">설명</span><span class="sxs-lookup"><span data-stu-id="06d44-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06d44-118">\<add></span><span class="sxs-lookup"><span data-stu-id="06d44-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|<span data-ttu-id="06d44-119">`Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06d44-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="06d44-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="06d44-120">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|<span data-ttu-id="06d44-121">수신기를 제거 합니다 `Listeners` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="06d44-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="06d44-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="06d44-122">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|<span data-ttu-id="06d44-123">추적 소스의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="06d44-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="06d44-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="06d44-124">Parent Elements</span></span>  
  
|<span data-ttu-id="06d44-125">요소</span><span class="sxs-lookup"><span data-stu-id="06d44-125">Element</span></span>|<span data-ttu-id="06d44-126">설명</span><span class="sxs-lookup"><span data-stu-id="06d44-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="06d44-127">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="06d44-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="06d44-128">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="06d44-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="06d44-129">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06d44-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="06d44-130">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="06d44-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06d44-131">설명</span><span class="sxs-lookup"><span data-stu-id="06d44-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="06d44-132">구성 파일</span><span class="sxs-lookup"><span data-stu-id="06d44-132">Configuration File</span></span>  
 <span data-ttu-id="06d44-133">이 요소는 응용 프로그램 구성 파일과 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06d44-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06d44-134">예제</span><span class="sxs-lookup"><span data-stu-id="06d44-134">Example</span></span>  
 <span data-ttu-id="06d44-135">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 `<listeners>` 콘솔 추적 수신기를 추가 하는 요소는 `mySource` 원본 기본 추적 수신기를 제거 하려면.</span><span class="sxs-lookup"><span data-stu-id="06d44-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="06d44-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06d44-136">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="06d44-137">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="06d44-137">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="06d44-138">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="06d44-138">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
