---
title: '&lt;지우기&gt; webRequestModules (네트워크 설정)에 대 한 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
ms.openlocfilehash: 39d4a184972036677aaa9fdb33e672521033d35f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50190530"
---
# <a name="ltcleargt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="59b6b-102">&lt;지우기&gt; webRequestModules (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="59b6b-102">&lt;clear&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="59b6b-103">응용 프로그램에서 등록 된 모든 웹 요청 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="59b6b-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="59b6b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="59b6b-104">\<configuration></span></span>  
<span data-ttu-id="59b6b-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="59b6b-105">\<system.net></span></span>  
<span data-ttu-id="59b6b-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="59b6b-106">\<webRequestModules></span></span>  
<span data-ttu-id="59b6b-107">\<지우기 ></span><span class="sxs-lookup"><span data-stu-id="59b6b-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b6b-108">구문</span><span class="sxs-lookup"><span data-stu-id="59b6b-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59b6b-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="59b6b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="59b6b-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="59b6b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59b6b-111">특성</span><span class="sxs-lookup"><span data-stu-id="59b6b-111">Attributes</span></span>  
 <span data-ttu-id="59b6b-112">없음</span><span class="sxs-lookup"><span data-stu-id="59b6b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="59b6b-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="59b6b-113">Child Elements</span></span>  
 <span data-ttu-id="59b6b-114">없음</span><span class="sxs-lookup"><span data-stu-id="59b6b-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59b6b-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="59b6b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="59b6b-116">**요소**</span><span class="sxs-lookup"><span data-stu-id="59b6b-116">**Element**</span></span>|<span data-ttu-id="59b6b-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="59b6b-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="59b6b-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="59b6b-118">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="59b6b-119">네트워크 호스트에서 정보를 요청 하는 데는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="59b6b-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59b6b-120">설명</span><span class="sxs-lookup"><span data-stu-id="59b6b-120">Remarks</span></span>  
 <span data-ttu-id="59b6b-121">`clear` 요소 또는 구성 계층 구조의 상위 수준 구성 파일에서 이전에 정의 된 등록 된 모든 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="59b6b-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="59b6b-122">구성 파일</span><span class="sxs-lookup"><span data-stu-id="59b6b-122">Configuration Files</span></span>  
 <span data-ttu-id="59b6b-123">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59b6b-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59b6b-124">예제</span><span class="sxs-lookup"><span data-stu-id="59b6b-124">Example</span></span>  
 <span data-ttu-id="59b6b-125">다음 예제에서는 모든 웹 요청 모듈을 지우고 http 웹 요청 모듈을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="59b6b-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="59b6b-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59b6b-126">See Also</span></span>  
- <xref:System.Net.WebRequest>  
- [<span data-ttu-id="59b6b-127">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="59b6b-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
