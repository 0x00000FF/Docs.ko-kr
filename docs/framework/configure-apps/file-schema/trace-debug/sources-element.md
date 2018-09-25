---
title: '&lt;원본&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
author: mcleblanc
ms.author: markl
ms.openlocfilehash: a9c5c5529e349eca2ba089ed6fb71da4bd48430a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084451"
---
# <a name="ltsourcesgt-element"></a><span data-ttu-id="9b749-102">&lt;원본&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="9b749-102">&lt;sources&gt; Element</span></span>
<span data-ttu-id="9b749-103">추적 메시지를 시작 하는 추적 소스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b749-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
 <span data-ttu-id="9b749-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9b749-104">\<configuration></span></span>  
<span data-ttu-id="9b749-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="9b749-105">\<system.diagnostics></span></span>  
<span data-ttu-id="9b749-106">\<원본 ></span><span class="sxs-lookup"><span data-stu-id="9b749-106">\<sources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b749-107">구문</span><span class="sxs-lookup"><span data-stu-id="9b749-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b749-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9b749-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9b749-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9b749-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b749-110">특성</span><span class="sxs-lookup"><span data-stu-id="9b749-110">Attributes</span></span>  
 <span data-ttu-id="9b749-111">없음</span><span class="sxs-lookup"><span data-stu-id="9b749-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9b749-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9b749-112">Child Elements</span></span>  
  
|<span data-ttu-id="9b749-113">요소</span><span class="sxs-lookup"><span data-stu-id="9b749-113">Element</span></span>|<span data-ttu-id="9b749-114">설명</span><span class="sxs-lookup"><span data-stu-id="9b749-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b749-115">\<source></span><span class="sxs-lookup"><span data-stu-id="9b749-115">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|<span data-ttu-id="9b749-116">필수적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9b749-116">Required element.</span></span><br /><br /> <span data-ttu-id="9b749-117">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b749-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9b749-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9b749-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9b749-119">요소</span><span class="sxs-lookup"><span data-stu-id="9b749-119">Element</span></span>|<span data-ttu-id="9b749-120">설명</span><span class="sxs-lookup"><span data-stu-id="9b749-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9b749-121">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9b749-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="9b749-122">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b749-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b749-123">설명</span><span class="sxs-lookup"><span data-stu-id="9b749-123">Remarks</span></span>  
 <span data-ttu-id="9b749-124">이 요소는 응용 프로그램 구성 파일과 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b749-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b749-125">예제</span><span class="sxs-lookup"><span data-stu-id="9b749-125">Example</span></span>  
 <span data-ttu-id="9b749-126">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 `<sources>` 추적 소스를 추가할 요소의 `mySource` 명명 된 소스 스위치의 수준을 설정 하 고 `sourceSwitch`입니다.</span><span class="sxs-lookup"><span data-stu-id="9b749-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="9b749-127">콘솔 추적 수신기는 추적 정보를 콘솔에 쓰는 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b749-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"   
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
         <add name="sourceSwitch" value="Warning" />  
      </switches>    
   </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b749-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b749-128">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.XmlWriterTraceListener>  
 [<span data-ttu-id="9b749-129">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9b749-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="9b749-130">\<source></span><span class="sxs-lookup"><span data-stu-id="9b749-130">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)
