---
title: <ipv6> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: d89c2e2c6943aca38f8a71092ba3121447a77574
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664096"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="0fcef-102">\<ipv6> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="0fcef-102">\<ipv6> Element (Network Settings)</span></span>
<span data-ttu-id="0fcef-103"><xref:System.Net.Dns> 클래스의 사용 되지 않는 멤버에서 IPv6 (인터넷 프로토콜 버전 6) 응답을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fcef-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  
  
 <span data-ttu-id="0fcef-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0fcef-104">\<configuration></span></span>  
<span data-ttu-id="0fcef-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="0fcef-105">\<system.net></span></span>  
<span data-ttu-id="0fcef-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="0fcef-106">\<settings></span></span>  
<span data-ttu-id="0fcef-107">\<ipv6></span><span class="sxs-lookup"><span data-stu-id="0fcef-107">\<ipv6></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fcef-108">구문</span><span class="sxs-lookup"><span data-stu-id="0fcef-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0fcef-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0fcef-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0fcef-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0fcef-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0fcef-111">특성</span><span class="sxs-lookup"><span data-stu-id="0fcef-111">Attributes</span></span>  
  
|<span data-ttu-id="0fcef-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="0fcef-112">**Attribute**</span></span>|<span data-ttu-id="0fcef-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="0fcef-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="0fcef-114"><xref:System.Net.Dns> 클래스의 멤버가 IPv6 (인터넷 프로토콜 버전 6) 주소를 반환 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fcef-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="0fcef-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="0fcef-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0fcef-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0fcef-116">Child Elements</span></span>  
 <span data-ttu-id="0fcef-117">없음</span><span class="sxs-lookup"><span data-stu-id="0fcef-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0fcef-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0fcef-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0fcef-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="0fcef-119">**Element**</span></span>|<span data-ttu-id="0fcef-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="0fcef-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0fcef-121">settings</span><span class="sxs-lookup"><span data-stu-id="0fcef-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="0fcef-122"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0fcef-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fcef-123">설명</span><span class="sxs-lookup"><span data-stu-id="0fcef-123">Remarks</span></span>  
 <span data-ttu-id="0fcef-124">이 <xref:System.Net.Dns> 설정은 ,<xref:System.Net.Dns.EndGetHostByName%2A> ,,<xref:System.Net.Dns.BeginGetHostByName%2A>,, 및<xref:System.Net.Dns.Resolve%2A>클래스의 사용 되지 않는 멤버에 대 한 IPv6 지원을 사용 하도록 설정 합니다. <xref:System.Net.Dns.BeginResolve%2A> <xref:System.Net.Dns.EndResolve%2A> <xref:System.Net.Dns.GetHostByAddress%2A> <xref:System.Net.Dns.GetHostByName%2A></span><span class="sxs-lookup"><span data-stu-id="0fcef-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="0fcef-125"><xref:System.Net?displayProperty=nameWithType> 네임 스페이스의 다른 구성원의 경우 ipv6 주소가 운영 체제에서 사용 하도록 설정 된 경우 ipv6 주소가 반환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fcef-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0fcef-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="0fcef-126">Configuration Files</span></span>  
 <span data-ttu-id="0fcef-127">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fcef-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fcef-128">예제</span><span class="sxs-lookup"><span data-stu-id="0fcef-128">Example</span></span>  
 <span data-ttu-id="0fcef-129">다음 예제에서는 <xref:System.Net.Dns> 클래스에 대 한 IPv6 지원을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0fcef-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0fcef-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="0fcef-130">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0fcef-131">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="0fcef-131">Network Settings Schema</span></span>](index.md)
