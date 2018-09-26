---
title: '&lt;authenticationModules&gt; 요소 (네트워크 설정)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 394a686fe07036d6c3ac2bc51fb3503e1ee4a9e6
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170810"
---
# <a name="ltauthenticationmodulesgt-element-network-settings"></a><span data-ttu-id="ec98b-102">&lt;authenticationModules&gt; 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="ec98b-102">&lt;authenticationModules&gt; Element (Network Settings)</span></span>
<span data-ttu-id="ec98b-103">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec98b-103">Specifies modules used to authenticate network requests.</span></span>  
  
 <span data-ttu-id="ec98b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ec98b-104">\<configuration></span></span>  
<span data-ttu-id="ec98b-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ec98b-105">\<system.net></span></span>  
<span data-ttu-id="ec98b-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="ec98b-106">\<authenticationModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec98b-107">구문</span><span class="sxs-lookup"><span data-stu-id="ec98b-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec98b-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ec98b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ec98b-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec98b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec98b-110">특성</span><span class="sxs-lookup"><span data-stu-id="ec98b-110">Attributes</span></span>  
 <span data-ttu-id="ec98b-111">없음</span><span class="sxs-lookup"><span data-stu-id="ec98b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ec98b-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ec98b-112">Child Elements</span></span>  
  
|<span data-ttu-id="ec98b-113">**요소**</span><span class="sxs-lookup"><span data-stu-id="ec98b-113">**Element**</span></span>|<span data-ttu-id="ec98b-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="ec98b-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ec98b-115">add</span><span class="sxs-lookup"><span data-stu-id="ec98b-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="ec98b-116">응용 프로그램에 인증 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ec98b-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="ec98b-117">clear</span><span class="sxs-lookup"><span data-stu-id="ec98b-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="ec98b-118">응용 프로그램에서 인증 모듈을 모두 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="ec98b-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="ec98b-119">remove</span><span class="sxs-lookup"><span data-stu-id="ec98b-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="ec98b-120">응용 프로그램에서 인증 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ec98b-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ec98b-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ec98b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ec98b-122">**요소**</span><span class="sxs-lookup"><span data-stu-id="ec98b-122">**Element**</span></span>|<span data-ttu-id="ec98b-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="ec98b-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ec98b-124">system.net</span><span class="sxs-lookup"><span data-stu-id="ec98b-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="ec98b-125">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ec98b-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec98b-126">설명</span><span class="sxs-lookup"><span data-stu-id="ec98b-126">Remarks</span></span>  
 <span data-ttu-id="ec98b-127">`authenticationModule` 요소는 서버를 사용 하 여 인증 프로세스를 수행 하는 인증 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec98b-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="ec98b-128">인증 모듈을 구현 해야 합니다는 <xref:System.Net.IAuthenticationModule> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ec98b-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ec98b-129">구성 파일</span><span class="sxs-lookup"><span data-stu-id="ec98b-129">Configuration Files</span></span>  
 <span data-ttu-id="ec98b-130">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec98b-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec98b-131">예제</span><span class="sxs-lookup"><span data-stu-id="ec98b-131">Example</span></span>  
 <span data-ttu-id="ec98b-132">다음 예제에서는 인증 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="ec98b-132">The following example enables an authentication module.</span></span> <span data-ttu-id="ec98b-133">지정된 된 모듈에 대 한 올바른 값을 사용 하 여 PublicKeyToken 및 버전에 대 한 값을 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec98b-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec98b-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec98b-134">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="ec98b-135">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ec98b-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
