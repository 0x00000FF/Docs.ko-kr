---
title: bypasslist의 <add> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 702aa8ccefcdddee1ffc5a7519a4f955b1dc5dfb
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265664"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="b0bbf-102">\<추가 > bypasslist (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="b0bbf-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="b0bbf-103">프록시 무시 목록에는 IP 주소 또는 DNS 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
 <span data-ttu-id="b0bbf-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b0bbf-104">\<configuration></span></span>  
<span data-ttu-id="b0bbf-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b0bbf-105">\<system.net></span></span>  
<span data-ttu-id="b0bbf-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="b0bbf-106">\<defaultProxy></span></span>  
<span data-ttu-id="b0bbf-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="b0bbf-107">\<bypasslist></span></span>  
<span data-ttu-id="b0bbf-108">\<add></span><span class="sxs-lookup"><span data-stu-id="b0bbf-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0bbf-109">구문</span><span class="sxs-lookup"><span data-stu-id="b0bbf-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0bbf-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b0bbf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b0bbf-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0bbf-112">특성</span><span class="sxs-lookup"><span data-stu-id="b0bbf-112">Attributes</span></span>  
  
|<span data-ttu-id="b0bbf-113">**특성**</span><span class="sxs-lookup"><span data-stu-id="b0bbf-113">**Attribute**</span></span>|<span data-ttu-id="b0bbf-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="b0bbf-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="b0bbf-115">**address**</span><span class="sxs-lookup"><span data-stu-id="b0bbf-115">**address**</span></span>|<span data-ttu-id="b0bbf-116">IP 주소 또는 DNS 이름을 설명 하는 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0bbf-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b0bbf-117">Child Elements</span></span>  
 <span data-ttu-id="b0bbf-118">없음</span><span class="sxs-lookup"><span data-stu-id="b0bbf-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0bbf-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b0bbf-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b0bbf-120">**요소**</span><span class="sxs-lookup"><span data-stu-id="b0bbf-120">**Element**</span></span>|<span data-ttu-id="b0bbf-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="b0bbf-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b0bbf-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="b0bbf-122">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="b0bbf-123">프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0bbf-124">설명</span><span class="sxs-lookup"><span data-stu-id="b0bbf-124">Remarks</span></span>  
 <span data-ttu-id="b0bbf-125">`add` 요소 IP 주소 또는 프록시 서버를 바이패스 하는 주소 목록에 DNS 서버 이름을 설명 하는 정규식을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="b0bbf-126">값을 `address` 특성에는 IP 주소 또는 호스트 이름 집합을 설명 하는 정규식을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="b0bbf-127">이 요소에 대 한 정규식을 지정 하는 경우 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="b0bbf-128">정규식 "[a-z] +\\.contoso\\.com" contoso.com 도메인에 호스트 된 일치 항목의 모든 호스트 contoso.com.cpandl.com 도메인에 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="b0bbf-129">Contoso.com 도메인의 호스트 에서만 일치 하는 앵커 ("$") 사용 하 여: "[a-z] +\\.contoso\\.com$"입니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="b0bbf-130">정규식에 대 한 자세한 내용은 다음을 참조 하세요. [.NET framework 정규식](../../../../../docs/standard/base-types/regular-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b0bbf-131">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b0bbf-131">Configuration Files</span></span>  
 <span data-ttu-id="b0bbf-132">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0bbf-133">예제</span><span class="sxs-lookup"><span data-stu-id="b0bbf-133">Example</span></span>  
 <span data-ttu-id="b0bbf-134">다음 예제에서는 바이패스 목록에 두 개의 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="b0bbf-135">첫 번째는 contoso.com 도메인의 모든 서버에 대 한 프록시를 무시합니다. 두 번째 192.168 사용 하 여 IP 주소가 시작 되는 모든 서버에 대 한 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0bbf-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="b0bbf-136">See also</span></span>
- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="b0bbf-137">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b0bbf-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
