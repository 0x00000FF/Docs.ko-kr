---
title: connectionManagement의 <remove> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
ms.openlocfilehash: 8ab7a43fbb3e8df5bb0c99b5947f2fafb362399a
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664039"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="a052a-102">\<connectionManagement의 > 요소 제거 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="a052a-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="a052a-103">연결 관리 목록에서 IP 주소 또는 DNS 이름을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a052a-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="a052a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a052a-104">\<configuration></span></span>  
<span data-ttu-id="a052a-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a052a-105">\<system.net></span></span>  
<span data-ttu-id="a052a-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="a052a-106">\<connectionManagement></span></span>  
<span data-ttu-id="a052a-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="a052a-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a052a-108">구문</span><span class="sxs-lookup"><span data-stu-id="a052a-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a052a-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a052a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a052a-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a052a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a052a-111">특성</span><span class="sxs-lookup"><span data-stu-id="a052a-111">Attributes</span></span>  
  
|<span data-ttu-id="a052a-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="a052a-112">**Attribute**</span></span>|<span data-ttu-id="a052a-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="a052a-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="a052a-114">IP 주소 또는 DNS 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a052a-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a052a-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a052a-115">Child Elements</span></span>  
 <span data-ttu-id="a052a-116">없음</span><span class="sxs-lookup"><span data-stu-id="a052a-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a052a-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a052a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a052a-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="a052a-118">**Element**</span></span>|<span data-ttu-id="a052a-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="a052a-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a052a-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="a052a-120">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="a052a-121">네트워크 호스트에 대한 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a052a-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a052a-122">설명</span><span class="sxs-lookup"><span data-stu-id="a052a-122">Remarks</span></span>  
 <span data-ttu-id="a052a-123">요소 `remove` 는 지정 된 서버에 대 한 연결 관리 목록 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a052a-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="a052a-124">`address` 특성 값은 올바른 IP 주소 또는 호스트 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a052a-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a052a-125">구성 파일</span><span class="sxs-lookup"><span data-stu-id="a052a-125">Configuration Files</span></span>  
 <span data-ttu-id="a052a-126">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a052a-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a052a-127">예제</span><span class="sxs-lookup"><span data-stu-id="a052a-127">Example</span></span>  
 <span data-ttu-id="a052a-128">다음 예에서는 서버 `www.adventure-works.com` 에 대 한 연결 관리 목록 항목을 제거한 다음 서버 `www.contoso.com` 에 대 한 4 개의 연결과 다른 모든 서버에 대 한 두 개의 연결을 사용 하도록 응용 프로그램을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a052a-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a052a-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="a052a-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="a052a-130">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="a052a-130">Network Settings Schema</span></span>](index.md)
