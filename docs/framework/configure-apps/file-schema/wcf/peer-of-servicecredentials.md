---
title: "&lt;serviceCredentials&gt;의 &lt;peer&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d04c6121c5d106f5877517e9f72d1b533480dfb7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltpeergt-of-ltservicecredentialsgt"></a><span data-ttu-id="91723-102">&lt;serviceCredentials&gt;의 &lt;peer&gt;</span><span class="sxs-lookup"><span data-stu-id="91723-102">&lt;peer&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="91723-103">피어 노드에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91723-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="91723-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="91723-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="91723-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="91723-105">\<behaviors></span></span>  
<span data-ttu-id="91723-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="91723-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="91723-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="91723-107">\<behavior></span></span>  
<span data-ttu-id="91723-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="91723-108">\<serviceCredentials></span></span>  
<span data-ttu-id="91723-109">\<피어 ></span><span class="sxs-lookup"><span data-stu-id="91723-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91723-110">구문</span><span class="sxs-lookup"><span data-stu-id="91723-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91723-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="91723-111">Attributes and Elements</span></span>  
 <span data-ttu-id="91723-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91723-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91723-113">특성</span><span class="sxs-lookup"><span data-stu-id="91723-113">Attributes</span></span>  
 <span data-ttu-id="91723-114">없음</span><span class="sxs-lookup"><span data-stu-id="91723-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="91723-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="91723-115">Child Elements</span></span>  
  
|<span data-ttu-id="91723-116">요소</span><span class="sxs-lookup"><span data-stu-id="91723-116">Element</span></span>|<span data-ttu-id="91723-117">설명</span><span class="sxs-lookup"><span data-stu-id="91723-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91723-118">\<인증서 ></span><span class="sxs-lookup"><span data-stu-id="91723-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|<span data-ttu-id="91723-119">피어 투 피어 서비스의 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91723-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="91723-120">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91723-120">.</span></span>|  
|[<span data-ttu-id="91723-121">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="91723-121">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|<span data-ttu-id="91723-122">메시지 발신자에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91723-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="91723-123">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="91723-123">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|<span data-ttu-id="91723-124">피어 서비스의 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91723-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91723-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="91723-125">Parent Elements</span></span>  
  
|<span data-ttu-id="91723-126">요소</span><span class="sxs-lookup"><span data-stu-id="91723-126">Element</span></span>|<span data-ttu-id="91723-127">설명</span><span class="sxs-lookup"><span data-stu-id="91723-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91723-128">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="91723-128">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="91723-129">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91723-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91723-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91723-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="91723-131">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="91723-131">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="91723-132">피어 채널 메시지 인증</span><span class="sxs-lookup"><span data-stu-id="91723-132">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="91723-133">피어 채널 사용자 지정 인증</span><span class="sxs-lookup"><span data-stu-id="91723-133">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="91723-134">피어 채널 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="91723-134">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="91723-135">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="91723-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
