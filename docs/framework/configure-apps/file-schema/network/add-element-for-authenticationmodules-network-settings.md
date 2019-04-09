---
title: <add> AuthenticationModules (네트워크 설정)에 대 한 요소
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
ms.openlocfilehash: a46e6af97f37974805812fb0d19801d618eee4d4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105874"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="79ed2-102">\<추가 > authenticationModules (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="79ed2-102">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="79ed2-103">응용 프로그램에 인증 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="79ed2-103">Adds an authentication module to the application.</span></span>  
  
 <span data-ttu-id="79ed2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="79ed2-104">\<configuration></span></span>  
<span data-ttu-id="79ed2-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="79ed2-105">\<system.net></span></span>  
<span data-ttu-id="79ed2-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="79ed2-106">\<authenticationModules></span></span>  
<span data-ttu-id="79ed2-107">\<add></span><span class="sxs-lookup"><span data-stu-id="79ed2-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79ed2-108">구문</span><span class="sxs-lookup"><span data-stu-id="79ed2-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79ed2-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="79ed2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="79ed2-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79ed2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79ed2-111">특성</span><span class="sxs-lookup"><span data-stu-id="79ed2-111">Attributes</span></span>  
  
|**<span data-ttu-id="79ed2-112">특성</span><span class="sxs-lookup"><span data-stu-id="79ed2-112">Attribute</span></span>**|**<span data-ttu-id="79ed2-113">설명</span><span class="sxs-lookup"><span data-stu-id="79ed2-113">Description</span></span>**|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="79ed2-114">정규화 된 형식 이름을 (나타난를 <xref:System.Type.FullName%2A> 속성)와 어셈블리 이름 (나타난는 <xref:System.Reflection.Assembly.FullName%2A> 속성)을 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ed2-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79ed2-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="79ed2-115">Child Elements</span></span>  
 <span data-ttu-id="79ed2-116">없음</span><span class="sxs-lookup"><span data-stu-id="79ed2-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79ed2-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="79ed2-117">Parent Elements</span></span>  
  
|**<span data-ttu-id="79ed2-118">요소</span><span class="sxs-lookup"><span data-stu-id="79ed2-118">Element</span></span>**|**<span data-ttu-id="79ed2-119">설명</span><span class="sxs-lookup"><span data-stu-id="79ed2-119">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="79ed2-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="79ed2-120">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="79ed2-121">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ed2-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79ed2-122">설명</span><span class="sxs-lookup"><span data-stu-id="79ed2-122">Remarks</span></span>  
 <span data-ttu-id="79ed2-123">`add` 요소는 등록된 인증 모듈 목록의 끝에 인증 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="79ed2-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="79ed2-124">인증 모듈 목록에 추가 된 순서 대로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79ed2-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="79ed2-125">에 대 한 값을 `type` 특성은 유효한 형식 이름 및 쉼표로 구분 하 여 해당 어셈블리 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ed2-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="79ed2-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="79ed2-126">Configuration Files</span></span>  
 <span data-ttu-id="79ed2-127">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79ed2-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="79ed2-128">예제</span><span class="sxs-lookup"><span data-stu-id="79ed2-128">Example</span></span>  
 <span data-ttu-id="79ed2-129">다음 예제에서는 기본 인증 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="79ed2-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="79ed2-130">지정된 된 모듈에 대 한 올바른 값을 사용 하 여 PublicKeyToken 및 버전에 대 한 값을 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ed2-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="79ed2-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="79ed2-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="79ed2-132">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="79ed2-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
