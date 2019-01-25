---
title: '&lt;검색&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing
- http://schemas.microsoft.com/.NetConfiguration/v2.0#probing
helpviewer_keywords:
- <probing> element
- container tags, <probing> element
- probing element
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 711903656d8bcce3a2d213af68160707a55a48e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700002"
---
# <a name="ltprobinggt-element"></a><span data-ttu-id="a59f0-102">&lt;검색&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="a59f0-102">&lt;probing&gt; Element</span></span>
<span data-ttu-id="a59f0-103">공용 언어 런타임에서 어셈블리를 로드할 때 검색할 하위 응용 프로그램 기본 디렉터리를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59f0-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
 <span data-ttu-id="a59f0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a59f0-104">\<configuration></span></span>  
<span data-ttu-id="a59f0-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="a59f0-105">\<runtime></span></span>  
<span data-ttu-id="a59f0-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="a59f0-106">\<assemblyBinding></span></span>  
<span data-ttu-id="a59f0-107">\<probing></span><span class="sxs-lookup"><span data-stu-id="a59f0-107">\<probing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a59f0-108">구문</span><span class="sxs-lookup"><span data-stu-id="a59f0-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a59f0-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a59f0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a59f0-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a59f0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a59f0-111">특성</span><span class="sxs-lookup"><span data-stu-id="a59f0-111">Attributes</span></span>  
  
|<span data-ttu-id="a59f0-112">특성</span><span class="sxs-lookup"><span data-stu-id="a59f0-112">Attribute</span></span>|<span data-ttu-id="a59f0-113">설명</span><span class="sxs-lookup"><span data-stu-id="a59f0-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="a59f0-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a59f0-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="a59f0-115">어셈블리를 포함할 수 있는 응용 프로그램의 기본 디렉터리의 하위 디렉터리를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59f0-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="a59f0-116">각 하위 디렉터리를 세미콜론으로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59f0-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a59f0-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a59f0-117">Child Elements</span></span>  
 <span data-ttu-id="a59f0-118">없음</span><span class="sxs-lookup"><span data-stu-id="a59f0-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a59f0-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a59f0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a59f0-120">요소</span><span class="sxs-lookup"><span data-stu-id="a59f0-120">Element</span></span>|<span data-ttu-id="a59f0-121">설명</span><span class="sxs-lookup"><span data-stu-id="a59f0-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="a59f0-122">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a59f0-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="a59f0-123">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a59f0-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a59f0-124">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a59f0-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a59f0-125">예제</span><span class="sxs-lookup"><span data-stu-id="a59f0-125">Example</span></span>  
 <span data-ttu-id="a59f0-126">다음 예제에서는 런타임에서 어셈블리에 대 한 검색 응용 프로그램 기본 하위 디렉터리를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a59f0-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a59f0-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="a59f0-127">See also</span></span>
- [<span data-ttu-id="a59f0-128">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="a59f0-128">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="a59f0-129">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="a59f0-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="a59f0-130">어셈블리 위치 지정</span><span class="sxs-lookup"><span data-stu-id="a59f0-130">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)
- [<span data-ttu-id="a59f0-131">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="a59f0-131">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
