---
title: "보안 세션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 65a54c06efffb2e3167c77bd109a50a31b971add
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="secure-sessions"></a><span data-ttu-id="b3501-102">보안 세션</span><span class="sxs-lookup"><span data-stu-id="b3501-102">Secure Sessions</span></span>
<span data-ttu-id="b3501-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 기능은 메시지를 보낸 순서로 받았음을 보장하는 신뢰할 수 있는 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="b3501-103">A feature of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="b3501-104">이 단원의 항목에서는 신뢰할 수 있는 세션을 만들 때 고려해야 할 보안 관련 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b3501-104">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="b3501-105">신뢰할 수 있는 세션 참조 [를 사용 하 여 세션](../../../../docs/framework/wcf/using-sessions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3501-105"> reliable sessions, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3501-106">Windows XP에서 가장이 필요한 경우 상태 저장 SCT(보안 컨텍스트 토큰) 없이 보안 세션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b3501-106">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="b3501-107">상태 저장 SCT가 가장과 함께 사용되는 경우 <xref:System.InvalidOperationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3501-107">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="b3501-108">[지원 되지 않는 시나리오](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3501-108"> [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b3501-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="b3501-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="b3501-110">보안 대화 및 보안 세션</span><span class="sxs-lookup"><span data-stu-id="b3501-110">Secure Conversations and Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|<span data-ttu-id="b3501-111">보안 대화 및 보안 세션은 동의어입니다.</span><span class="sxs-lookup"><span data-stu-id="b3501-111">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="b3501-112">이 항목에서는 보안 대화가 작동하는 방식과 패턴을 사용하는 시기와 이유에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b3501-112">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="b3501-113">방법: 보안 세션 만들기</span><span class="sxs-lookup"><span data-stu-id="b3501-113">How to: Create a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|<span data-ttu-id="b3501-114">기본적인 보안 세션 만들기에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b3501-114">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="b3501-115">방법: 보안 세션에 대한 보안 컨텍스트 토큰 만들기</span><span class="sxs-lookup"><span data-stu-id="b3501-115">How to: Create a Security Context Token for a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="b3501-116">클라이언트로 상태 및 세션을 관리할 웹 팜을 만드는 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b3501-116">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="b3501-117">보안 세션에 대한 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="b3501-117">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|<span data-ttu-id="b3501-118">보안 세션에 대해 고려할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b3501-118">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="b3501-119">참조</span><span class="sxs-lookup"><span data-stu-id="b3501-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="b3501-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="b3501-120">Related Sections</span></span>  
 [<span data-ttu-id="b3501-121">세션, 인스턴스 및 동시성</span><span class="sxs-lookup"><span data-stu-id="b3501-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="b3501-122">서비스 디자인 및 구현</span><span class="sxs-lookup"><span data-stu-id="b3501-122">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="b3501-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3501-123">See Also</span></span>  
 [<span data-ttu-id="b3501-124">방법: 메시지 재생을 검색하도록 설정</span><span class="sxs-lookup"><span data-stu-id="b3501-124">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 [<span data-ttu-id="b3501-125">재생 공격</span><span class="sxs-lookup"><span data-stu-id="b3501-125">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 [<span data-ttu-id="b3501-126">방법: 세션이 필요한 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="b3501-126">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
