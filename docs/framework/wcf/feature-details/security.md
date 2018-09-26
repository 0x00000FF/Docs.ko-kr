---
title: Windows Communication Foundation 보안
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
author: BrucePerlerMS
ms.openlocfilehash: 2d4f2d67c8afd1687d9de506cf8a7616408069d2
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47200791"
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="dc350-102">Windows Communication Foundation 보안</span><span class="sxs-lookup"><span data-stu-id="dc350-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="dc350-103">이 섹션의에서 항목에서는 Windows Communication Foundation (WCF) 보안 기능 및 보안 메시지를 유용 하 게 활용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc350-103">The topics in this section describe Windows Communication Foundation (WCF) security features and how to use them to help secure messages.</span></span>  
  
 <span data-ttu-id="dc350-104">Windows Server AppFabric 및 보안에 대 한 자세한 내용은 참조 하세요. [Windows Server AppFabric 보안 모델](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="dc350-104">For more information about Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dc350-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="dc350-105">In This Section</span></span>  
 [<span data-ttu-id="dc350-106">보안 개요</span><span class="sxs-lookup"><span data-stu-id="dc350-106">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 <span data-ttu-id="dc350-107">WCF의 보안 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc350-107">Describes the security features in WCF.</span></span>  
  
 [<span data-ttu-id="dc350-108">보안 개념</span><span class="sxs-lookup"><span data-stu-id="dc350-108">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 <span data-ttu-id="dc350-109">기본 용어와 WCF 보안에 사용 되는 개념을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc350-109">Describes the basic terminology and concepts used in WCF security.</span></span>  
  
 [<span data-ttu-id="dc350-110">일반적인 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="dc350-110">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 <span data-ttu-id="dc350-111">시나리오 및 WCF를 사용 하 여 구성할 수 있습니다 하는 토폴로지를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc350-111">Describes scenarios and topologies you can configure with WCF.</span></span>  
  
 [<span data-ttu-id="dc350-112">보안 동작</span><span class="sxs-lookup"><span data-stu-id="dc350-112">Security Behaviors</span></span>](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 <span data-ttu-id="dc350-113">보안에 영향을 주는 WCF 동작에 대한 개요를 제공합니다(예: 자격 증명 설정).</span><span class="sxs-lookup"><span data-stu-id="dc350-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="dc350-114">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="dc350-114">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 <span data-ttu-id="dc350-115">사용자 지정 보안 바인딩을 만드는 방법을 보여 주는 항목을 비롯한 바인딩의 보안 지향적인 뷰입니다.</span><span class="sxs-lookup"><span data-stu-id="dc350-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="dc350-116">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="dc350-116">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="dc350-117">WCF 보안 기능을 사용 하 여 메시지를 보호 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc350-117">Describes how to secure messages using WCF security features.</span></span>  
  
 [<span data-ttu-id="dc350-118">인증</span><span class="sxs-lookup"><span data-stu-id="dc350-118">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
 <span data-ttu-id="dc350-119">일반적인 인증 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc350-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="dc350-120">권한 부여</span><span class="sxs-lookup"><span data-stu-id="dc350-120">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 <span data-ttu-id="dc350-121">보안 구현을 사용하여 일반적인 인증 시나리오를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc350-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="dc350-122">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="dc350-122">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 <span data-ttu-id="dc350-123">페더레이션 기본 사항 및 페더레이션 서버와 통신하는 클라이언트를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc350-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="dc350-124">부분 신뢰</span><span class="sxs-lookup"><span data-stu-id="dc350-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 <span data-ttu-id="dc350-125">부분적으로 신뢰할 수 있는 실행 될 때 WCF 제한 사항 및 부분적으로 신뢰할 수 있는 시나리오를 실행 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc350-125">Describes how to run partially-trusted scenarios and WCF limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="dc350-126">감사</span><span class="sxs-lookup"><span data-stu-id="dc350-126">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 <span data-ttu-id="dc350-127">보안 이벤트를 감사하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc350-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="dc350-128">보안 지침 및 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="dc350-128">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 <span data-ttu-id="dc350-129">보안 WCF 응용 프로그램을 만들기 위한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="dc350-129">Guidelines for creating secure WCF applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dc350-130">참조</span><span class="sxs-lookup"><span data-stu-id="dc350-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="dc350-131">관련 단원</span><span class="sxs-lookup"><span data-stu-id="dc350-131">Related Sections</span></span>  
 [<span data-ttu-id="dc350-132">WCF 기능 정보</span><span class="sxs-lookup"><span data-stu-id="dc350-132">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="dc350-133">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="dc350-133">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="dc350-134">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="dc350-134">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="dc350-135">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="dc350-135">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="dc350-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc350-136">See Also</span></span>  
 [<span data-ttu-id="dc350-137">응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="dc350-137">Configuring Your Application</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
