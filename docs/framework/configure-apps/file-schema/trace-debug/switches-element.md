---
title: '&lt;스위치&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
ms.openlocfilehash: ed5d30408b2c0f45f3bef091f4828bd812a63a7a
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083355"
---
# <a name="ltswitchesgt-element"></a><span data-ttu-id="1597d-102">&lt;스위치&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="1597d-102">&lt;switches&gt; Element</span></span>
<span data-ttu-id="1597d-103">추적 스위치 및 추적 스위치가 설정된 수준이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1597d-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
 <span data-ttu-id="1597d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1597d-104">\<configuration></span></span>  
<span data-ttu-id="1597d-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="1597d-105">\<system.diagnostics></span></span>  
<span data-ttu-id="1597d-106">\<switches></span><span class="sxs-lookup"><span data-stu-id="1597d-106">\<switches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1597d-107">구문</span><span class="sxs-lookup"><span data-stu-id="1597d-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1597d-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1597d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1597d-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1597d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1597d-110">특성</span><span class="sxs-lookup"><span data-stu-id="1597d-110">Attributes</span></span>  
 <span data-ttu-id="1597d-111">없음</span><span class="sxs-lookup"><span data-stu-id="1597d-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1597d-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1597d-112">Child Elements</span></span>  
  
|<span data-ttu-id="1597d-113">요소</span><span class="sxs-lookup"><span data-stu-id="1597d-113">Element</span></span>|<span data-ttu-id="1597d-114">설명</span><span class="sxs-lookup"><span data-stu-id="1597d-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1597d-115">\<add></span><span class="sxs-lookup"><span data-stu-id="1597d-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="1597d-116">추적 스위치를 설정하는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1597d-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1597d-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1597d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1597d-118">요소</span><span class="sxs-lookup"><span data-stu-id="1597d-118">Element</span></span>|<span data-ttu-id="1597d-119">설명</span><span class="sxs-lookup"><span data-stu-id="1597d-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1597d-120">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1597d-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="1597d-121">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1597d-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1597d-122">설명</span><span class="sxs-lookup"><span data-stu-id="1597d-122">Remarks</span></span>  
 <span data-ttu-id="1597d-123">구성 파일에 배치 하 여 추적 스위치의 수준을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1597d-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="1597d-124">스위치가 <xref:System.Diagnostics.BooleanSwitch>를 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1597d-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="1597d-125">스위치가 <xref:System.Diagnostics.TraceSwitch>, 추적의 유형을 지정 하 고 다른 수준을 할당할 수 있습니다 또는 디버그 메시지 응용 프로그램에서 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1597d-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1597d-126">예제</span><span class="sxs-lookup"><span data-stu-id="1597d-126">Example</span></span>  
 <span data-ttu-id="1597d-127">다음 예제에서는 사용 하는 방법을 보여 줍니다는  **\<전환 >** 설정할 요소입니다를 `General` 추적 스위치를를 <xref:System.Diagnostics.TraceLevel> 수준 및 사용을 `Data` Boolean 추적 스위치.</span><span class="sxs-lookup"><span data-stu-id="1597d-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1597d-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="1597d-128">See also</span></span>
- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="1597d-129">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="1597d-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
