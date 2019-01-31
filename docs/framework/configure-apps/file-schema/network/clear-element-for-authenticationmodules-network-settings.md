---
title: authenticationModules의 <clear> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, authenticationModules
- <authenticationModules>, clear element
- <clear> element, authenticationModules
- authenticationModules, clear element
ms.assetid: dc522c45-4a80-4831-8955-f7b68a47edfd
ms.openlocfilehash: d6760d05a8c2368cd20cae416b0b4b428b6588db
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279073"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="b20af-102">\<지우기 > authenticationModules (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="b20af-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="b20af-103">응용 프로그램에서 인증 모듈을 모두 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-103">Clears all authentication modules from the application.</span></span>  
  
 <span data-ttu-id="b20af-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b20af-104">\<configuration></span></span>  
<span data-ttu-id="b20af-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b20af-105">\<system.net></span></span>  
<span data-ttu-id="b20af-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="b20af-106">\<authenticationModules></span></span>  
<span data-ttu-id="b20af-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="b20af-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b20af-108">구문</span><span class="sxs-lookup"><span data-stu-id="b20af-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b20af-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b20af-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b20af-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b20af-111">특성</span><span class="sxs-lookup"><span data-stu-id="b20af-111">Attributes</span></span>  
 <span data-ttu-id="b20af-112">없음</span><span class="sxs-lookup"><span data-stu-id="b20af-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b20af-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b20af-113">Child Elements</span></span>  
 <span data-ttu-id="b20af-114">없음</span><span class="sxs-lookup"><span data-stu-id="b20af-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b20af-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b20af-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b20af-116">**요소**</span><span class="sxs-lookup"><span data-stu-id="b20af-116">**Element**</span></span>|<span data-ttu-id="b20af-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="b20af-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b20af-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="b20af-118">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="b20af-119">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b20af-120">설명</span><span class="sxs-lookup"><span data-stu-id="b20af-120">Remarks</span></span>  
 <span data-ttu-id="b20af-121">`clear` 요소 또는 구성 계층 구조의 상위 수준 구성 파일에서 이전에 정의 된 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b20af-122">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b20af-122">Configuration Files</span></span>  
 <span data-ttu-id="b20af-123">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b20af-124">예제</span><span class="sxs-lookup"><span data-stu-id="b20af-124">Example</span></span>  
 <span data-ttu-id="b20af-125">다음 예제에서는 모든 구성 된 인증 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b20af-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="b20af-126">See also</span></span>
- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="b20af-127">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b20af-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
