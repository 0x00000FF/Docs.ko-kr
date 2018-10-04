---
title: '&lt;지우기&gt; connectionManagement (네트워크 설정)에 대 한 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, connectionManagement
- connectionManagement, clear element
- clear element, connectionManagement
- <connectionManagement>, clear element
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 9542332085d0b0319c55db63fd98c9dd8eb3f576
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48244817"
---
# <a name="ltcleargt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="b2888-102">&lt;지우기&gt; connectionManagement (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="b2888-102">&lt;clear&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="b2888-103">연결 관리 목록을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="b2888-103">Clears the connection management list.</span></span>  
  
 <span data-ttu-id="b2888-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b2888-104">\<configuration></span></span>  
<span data-ttu-id="b2888-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b2888-105">\<system.net></span></span>  
<span data-ttu-id="b2888-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="b2888-106">\<connectionManagement></span></span>  
<span data-ttu-id="b2888-107">\<지우기 ></span><span class="sxs-lookup"><span data-stu-id="b2888-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2888-108">구문</span><span class="sxs-lookup"><span data-stu-id="b2888-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2888-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b2888-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b2888-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b2888-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2888-111">특성</span><span class="sxs-lookup"><span data-stu-id="b2888-111">Attributes</span></span>  
 <span data-ttu-id="b2888-112">없음</span><span class="sxs-lookup"><span data-stu-id="b2888-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b2888-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b2888-113">Child Elements</span></span>  
 <span data-ttu-id="b2888-114">없음</span><span class="sxs-lookup"><span data-stu-id="b2888-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2888-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b2888-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b2888-116">**요소**</span><span class="sxs-lookup"><span data-stu-id="b2888-116">**Element**</span></span>|<span data-ttu-id="b2888-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="b2888-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b2888-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="b2888-118">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="b2888-119">네트워크 호스트에 대한 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2888-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2888-120">설명</span><span class="sxs-lookup"><span data-stu-id="b2888-120">Remarks</span></span>  
 <span data-ttu-id="b2888-121">`clear` 요소는 연결 관리 목록에서 항목을 모두 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="b2888-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b2888-122">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b2888-122">Configuration Files</span></span>  
 <span data-ttu-id="b2888-123">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2888-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2888-124">예제</span><span class="sxs-lookup"><span data-stu-id="b2888-124">Example</span></span>  
 <span data-ttu-id="b2888-125">다음 예제에서는 연결 관리 목록을 지우고 www.contoso.com 서버 및 다른 모든 네트워크 호스트에 대 한 새 연결 관리 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2888-125">The following example clears the connection management list and then adds new connection management entries for the server www.contoso.com and all other network hosts.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <clear/>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2888-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2888-126">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="b2888-127">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b2888-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
