---
title: '&lt;sessionSecurityTokenCache&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 9f4b87d6c620a07ee831888086bdab75a689875e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsessionsecuritytokencachegt"></a><span data-ttu-id="dc8bb-102">&lt;sessionSecurityTokenCache&gt;</span><span class="sxs-lookup"><span data-stu-id="dc8bb-102">&lt;sessionSecurityTokenCache&gt;</span></span>
<span data-ttu-id="dc8bb-103">세션 토큰에 대 한 캐시 서비스 또는 보안 토큰 처리기 컬렉션에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8bb-103">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="dc8bb-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="dc8bb-104">\<system.identityModel></span></span>  
<span data-ttu-id="dc8bb-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="dc8bb-105">\<identityConfiguration></span></span>  
<span data-ttu-id="dc8bb-106">\<캐시 ></span><span class="sxs-lookup"><span data-stu-id="dc8bb-106">\<caches></span></span>  
<span data-ttu-id="dc8bb-107">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="dc8bb-107">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc8bb-108">구문</span><span class="sxs-lookup"><span data-stu-id="dc8bb-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc8bb-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dc8bb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dc8bb-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8bb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc8bb-111">특성</span><span class="sxs-lookup"><span data-stu-id="dc8bb-111">Attributes</span></span>  
  
|<span data-ttu-id="dc8bb-112">특성</span><span class="sxs-lookup"><span data-stu-id="dc8bb-112">Attribute</span></span>|<span data-ttu-id="dc8bb-113">설명</span><span class="sxs-lookup"><span data-stu-id="dc8bb-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc8bb-114">type</span><span class="sxs-lookup"><span data-stu-id="dc8bb-114">type</span></span>|<span data-ttu-id="dc8bb-115">파생 되는 형식을 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="dc8bb-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc8bb-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dc8bb-116">Child Elements</span></span>  
 <span data-ttu-id="dc8bb-117">없음</span><span class="sxs-lookup"><span data-stu-id="dc8bb-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc8bb-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dc8bb-118">Parent Elements</span></span>  
  
|<span data-ttu-id="dc8bb-119">요소</span><span class="sxs-lookup"><span data-stu-id="dc8bb-119">Element</span></span>|<span data-ttu-id="dc8bb-120">설명</span><span class="sxs-lookup"><span data-stu-id="dc8bb-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc8bb-121">\<캐시 ></span><span class="sxs-lookup"><span data-stu-id="dc8bb-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="dc8bb-122">서비스 또는 보안 토큰 처리기 컬렉션에서 사용 하는 캐시에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8bb-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dc8bb-123">예</span><span class="sxs-lookup"><span data-stu-id="dc8bb-123">Example</span></span>  
 <span data-ttu-id="dc8bb-124">다음 XML에 세션 보안 토큰을 보관 하기 위한 사용자 지정 캐시의 구성을 보여 줍니다 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="dc8bb-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="dc8bb-125">구성에서 가져온 것은 `ClaimsAwareWebFarm` 샘플.</span><span class="sxs-lookup"><span data-stu-id="dc8bb-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="dc8bb-126">이 샘플에 대 한 자세한 내용은 참조 [WIF 코드 샘플 인덱스](../../../../../docs/framework/security/wif-code-sample-index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8bb-126">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc8bb-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc8bb-127">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
