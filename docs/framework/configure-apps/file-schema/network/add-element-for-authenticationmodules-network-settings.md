---
title: '&lt;추가&gt; authenticationModules (네트워크 설정)에 대 한 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add
helpviewer_keywords:
- authenticationModules, add element
- add element, authenticationModules
- <authenticationModules>, add element
- <add> element, authenticationModules
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 4a9bcc6cd5d2bbf30f463da0a51e1bccbcd5a3f1
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48873062"
---
# <a name="ltaddgt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="e13be-102">&lt;추가&gt; authenticationModules (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="e13be-102">&lt;add&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="e13be-103">응용 프로그램에 인증 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e13be-103">Adds an authentication module to the application.</span></span>  
  
 <span data-ttu-id="e13be-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e13be-104">\<configuration></span></span>  
<span data-ttu-id="e13be-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e13be-105">\<system.net></span></span>  
<span data-ttu-id="e13be-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="e13be-106">\<authenticationModules></span></span>  
<span data-ttu-id="e13be-107">\<add></span><span class="sxs-lookup"><span data-stu-id="e13be-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e13be-108">구문</span><span class="sxs-lookup"><span data-stu-id="e13be-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e13be-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e13be-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e13be-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e13be-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e13be-111">특성</span><span class="sxs-lookup"><span data-stu-id="e13be-111">Attributes</span></span>  
  
|<span data-ttu-id="e13be-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="e13be-112">**Attribute**</span></span>|<span data-ttu-id="e13be-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="e13be-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="e13be-114">정규화 된 형식 이름을 (나타난를 <xref:System.Type.FullName%2A> 속성)와 어셈블리 이름 (나타난는 <xref:System.Reflection.Assembly.FullName%2A> 속성)을 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="e13be-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e13be-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e13be-115">Child Elements</span></span>  
 <span data-ttu-id="e13be-116">없음</span><span class="sxs-lookup"><span data-stu-id="e13be-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e13be-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e13be-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e13be-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="e13be-118">**Element**</span></span>|<span data-ttu-id="e13be-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="e13be-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e13be-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="e13be-120">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="e13be-121">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e13be-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e13be-122">설명</span><span class="sxs-lookup"><span data-stu-id="e13be-122">Remarks</span></span>  
 <span data-ttu-id="e13be-123">`add` 요소는 등록된 인증 모듈 목록의 끝에 인증 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e13be-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="e13be-124">인증 모듈 목록에 추가 된 순서 대로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e13be-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="e13be-125">에 대 한 값을 `type` 특성은 유효한 형식 이름 및 쉼표로 구분 하 여 해당 어셈블리 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e13be-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e13be-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="e13be-126">Configuration Files</span></span>  
 <span data-ttu-id="e13be-127">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e13be-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e13be-128">예제</span><span class="sxs-lookup"><span data-stu-id="e13be-128">Example</span></span>  
 <span data-ttu-id="e13be-129">다음 예제에서는 기본 인증 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="e13be-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="e13be-130">지정된 된 모듈에 대 한 올바른 값을 사용 하 여 PublicKeyToken 및 버전에 대 한 값을 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e13be-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e13be-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e13be-131">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="e13be-132">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="e13be-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
