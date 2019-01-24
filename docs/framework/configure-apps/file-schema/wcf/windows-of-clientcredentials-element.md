---
title: '&lt;clientCredentials&gt; 요소의 &lt;windows&gt;'
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 1331456f6defc24511064684181f615451be5b93
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610749"
---
# <a name="ltwindowsgt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="df5d4-102">&lt;clientCredentials&gt; 요소의 &lt;windows&gt;</span><span class="sxs-lookup"><span data-stu-id="df5d4-102">&lt;windows&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="df5d4-103">클라이언트를 나타내는 데 사용되는 Windows 자격 증명의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="df5d4-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
 <span data-ttu-id="df5d4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="df5d4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="df5d4-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="df5d4-105">\<behaviors></span></span>  
<span data-ttu-id="df5d4-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="df5d4-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="df5d4-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="df5d4-107">\<behavior></span></span>  
<span data-ttu-id="df5d4-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="df5d4-108">\<clientCredentials></span></span>  
<span data-ttu-id="df5d4-109">\<windows></span><span class="sxs-lookup"><span data-stu-id="df5d4-109">\<windows></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df5d4-110">구문</span><span class="sxs-lookup"><span data-stu-id="df5d4-110">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df5d4-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="df5d4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="df5d4-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df5d4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df5d4-113">특성</span><span class="sxs-lookup"><span data-stu-id="df5d4-113">Attributes</span></span>  
  
|<span data-ttu-id="df5d4-114">특성</span><span class="sxs-lookup"><span data-stu-id="df5d4-114">Attribute</span></span>|<span data-ttu-id="df5d4-115">설명</span><span class="sxs-lookup"><span data-stu-id="df5d4-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="df5d4-116">클라이언트가 서버에 전달하는 가장 기본 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="df5d4-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="df5d4-117">클라이언트에서 선택하는 가장 모드는 서버에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df5d4-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="df5d4-118">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="df5d4-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="df5d4-119">식별: 서버 id 및 클라이언트의 권한을 가져올 수는 있지만 클라이언트를 가장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df5d4-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="df5d4-120">가장 합니다. 서버는 로컬 시스템에서 클라이언트의 보안 컨텍스트를 가장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df5d4-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="df5d4-121">-위임 합니다. 서버는 원격 시스템에서 클라이언트의 보안 컨텍스트를 가장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df5d4-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="df5d4-122">익명: 서버를 가장 하거나 클라이언트를 식별할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df5d4-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="df5d4-123">-None. 가장 수준이 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df5d4-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="df5d4-124">기본값은 Identification입니다.</span><span class="sxs-lookup"><span data-stu-id="df5d4-124">The default is Identification.</span></span> <span data-ttu-id="df5d4-125">이 특성은 <xref:System.Security.Principal.TokenImpersonationLevel> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="df5d4-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="df5d4-126">이 속성을 `true`로 설정하면 Kerberos를 사용할 수 없는 경우 NTLM으로 인증을 다운그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df5d4-126">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="df5d4-127">이 속성을 설정 `false` 하면 NTLM이 사용 하는 경우 예외를 throw 하는 최상의 노력을 하도록 Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="df5d4-127">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="df5d4-128">이 속성을 `false`로 설정하면 유선을 통해 NTLM 자격 증명을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df5d4-128">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df5d4-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="df5d4-129">Child Elements</span></span>  
 <span data-ttu-id="df5d4-130">없음</span><span class="sxs-lookup"><span data-stu-id="df5d4-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="df5d4-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="df5d4-131">Parent Elements</span></span>  
  
|<span data-ttu-id="df5d4-132">요소</span><span class="sxs-lookup"><span data-stu-id="df5d4-132">Element</span></span>|<span data-ttu-id="df5d4-133">설명</span><span class="sxs-lookup"><span data-stu-id="df5d4-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df5d4-134">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="df5d4-134">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="df5d4-135">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="df5d4-135">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df5d4-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="df5d4-136">See also</span></span>
- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="df5d4-137">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="df5d4-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="df5d4-138">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="df5d4-138">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="df5d4-139">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="df5d4-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
