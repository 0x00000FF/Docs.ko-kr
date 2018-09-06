---
title: 내 첫 번째 클레임 인식 WCF 서비스 구축
ms.date: 03/30/2017
ms.assetid: e0e6d091-9a97-4888-8f2c-cbcee42d90ee
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6dd9ad2a09c7fa587ec82df002d36ed258811fb9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857416"
---
# <a name="building-my-first-claims-aware-wcf-service"></a><span data-ttu-id="f7d21-102">내 첫 번째 클레임 인식 WCF 서비스 구축</span><span class="sxs-lookup"><span data-stu-id="f7d21-102">Building My First Claims-Aware WCF Service</span></span>
## <a name="applies-to"></a><span data-ttu-id="f7d21-103">적용 대상</span><span class="sxs-lookup"><span data-stu-id="f7d21-103">Applies To</span></span>  
  
-   <span data-ttu-id="f7d21-104">WIF(Windows Identity Foundation)</span><span class="sxs-lookup"><span data-stu-id="f7d21-104">Windows Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="f7d21-105">WCF(Windows Communication Foundation)</span><span class="sxs-lookup"><span data-stu-id="f7d21-105">Windows Communication Foundation (WCF)</span></span>  
  
## <a name="overview"></a><span data-ttu-id="f7d21-106">개요</span><span class="sxs-lookup"><span data-stu-id="f7d21-106">Overview</span></span>  
 <span data-ttu-id="f7d21-107">이 항목에서는 WIF를 사용하여 클레임 인식 WCF 서비스를 빌드하는 시나리오에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-107">This topic outlines the scenario of building claims-aware WCF services using WIF.</span></span> <span data-ttu-id="f7d21-108">일반적으로 클레임 인식 웹 서비스 시나리오에는 웹 서비스, 최종 사용자 및 STS(보안 토큰 서비스)와 같은 세 가지 참가 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-108">There are usually three participants in a claims-aware web service scenario: the web service itself, the end user, and the Security Token Service (STS).</span></span> <span data-ttu-id="f7d21-109">다음 그림은 이 시나리오를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-109">The following figure describes this scenario:</span></span>  
  
 <span data-ttu-id="f7d21-110">![WIF 기본 클레임 인식 WCF 서비스](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.gif "WIFBasicClaimsAwareWCFService")</span><span class="sxs-lookup"><span data-stu-id="f7d21-110">![WIF Basic Claims Aware WCF Service](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.gif "WIFBasicClaimsAwareWCFService")</span></span>  
  
1.  <span data-ttu-id="f7d21-111">WCF 서비스 클라이언트(에이전트라고도 함)는 WIF를 사용하여 STS에 자격 증명을 보내고, 성공적으로 인증되면 STS가 에이전트에 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-111">The WCF service client (sometimes called agent) uses WIF to send credentials to the STS and upon successful authentication, the agent is issued a token by the STS.</span></span>  
  
2.  <span data-ttu-id="f7d21-112">에이전트가 STS에서 발급한 토큰을 WCF 서비스에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-112">The agent sends this STS-issued token to the WCF service.</span></span>  
  
3.  <span data-ttu-id="f7d21-113">클레임 인식 WCF 서비스는 STS 및 발급되는 토큰을 신뢰하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-113">The claims-aware WCF service is configured to trust the STS and the tokens it issues.</span></span> <span data-ttu-id="f7d21-114">클레임 인식 WCF 서비스에서는 WIF를 사용하여 토큰의 유효성을 검사하고 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-114">The claims-aware WCF service uses WIF to validate the token and to parse it.</span></span> <span data-ttu-id="f7d21-115">개발자가 인증 구현과 같이 응용 프로그램의 요구에 맞는 적절한 WIF API 및 형식(예: **ClaimsPrincipal**)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-115">Developers use the appropriate WIF API and types, for example, **ClaimsPrincipal** for the application’s needs, such as implementing authorization for it.</span></span>  
  
 <span data-ttu-id="f7d21-116">.NET 4.5부터 WIF가 .NET Framework 패키지의 일부로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-116">Starting from .NET 4.5, WIF is part of the .NET Framework package.</span></span> <span data-ttu-id="f7d21-117">WIF 클래스를 프레임워크에서 직접 사용할 수 있도록 하면 .NET에 클레임 기반 ID를 더욱 심층적으로 통합하여 클레임을 더욱 쉽게 사용하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-117">Having the WIF classes directly available in the framework allows a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="f7d21-118">WIF 4.5를 사용하면 클레임 인식 웹 응용 프로그램 개발을 시작하기 위해 대역 외 구성 요소를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-118">With WIF 4.5, you do not need to install any out-of-band components in order to start developing claims-aware web applications.</span></span> <span data-ttu-id="f7d21-119">현재 WIF 클래스가 다양한 어셈블리에 분산되어 있으며, 주요 클래스는 System.Security.Claims, System.IdentityModel 및 System.IdentityModel.Services입니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-119">WIF classes are now spread across various assemblies, the main ones being System.Security.Claims, System.IdentityModel and System.IdentityModel.Services.</span></span>  
  
 <span data-ttu-id="f7d21-120">STS는 성공적으로 인증되면 토큰을 발급하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-120">STS is a service that issues tokens upon successful authentication.</span></span> <span data-ttu-id="f7d21-121">Microsoft는 다음과 같은 두 가지 업계 표준 STS를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-121">Microsoft offers two industry standard STS’s:</span></span>  
  
-   [<span data-ttu-id="f7d21-122">Active Directory Federation Services (AD FS) 2.0</span><span class="sxs-lookup"><span data-stu-id="f7d21-122">Active Directory Federation Services (AD FS) 2.0</span></span>](https://go.microsoft.com/fwlink/?LinkID=247516)
  
-   [<span data-ttu-id="f7d21-123">Windows Azure Access Control Service (ACS)</span><span class="sxs-lookup"><span data-stu-id="f7d21-123">Windows Azure Access Control Service (ACS)</span></span>](https://go.microsoft.com/fwlink/?LinkID=247517)
  
 <span data-ttu-id="f7d21-124">ADFS 2.0은 Windows Server R2에 속하며, 온-프레미스 시나리오의 STS로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-124">AD FS 2.0 is part of the Windows Server R2 and can be used as an STS for on-premise scenarios.</span></span> <span data-ttu-id="f7d21-125">Azure Active Directory Access Control(Access Control Service 또는 ACS라고도 함)는 Microsoft Azure의 일부로 제공되는 클라우드 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-125">Azure Active Directory Access Control (also known as Access Control Service or ACS) is a cloud service, offered as part of Microsoft Azure.</span></span> <span data-ttu-id="f7d21-126">테스트 또는 교육용으로 클레임 인식 응용 프로그램을 작성하기 위해 다른 STS를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-126">For testing or educational purposes, you can also use other STS’s in order to build your claims-aware applications.</span></span> <span data-ttu-id="f7d21-127">일부인 로컬 개발 STS를 사용할 수는 예를 들어, 합니다 [Id 및 액세스 도구 Visual Studio 용](https://go.microsoft.com/fwlink/?LinkID=245849) 사용할 수 있는 무료 온라인입니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-127">For example, you can use the Local Development STS that is part of the [Identity and Access Tool for Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849) which is freely available online.</span></span>  
  
 <span data-ttu-id="f7d21-128">WIF를 사용 하 여 첫 번째 클레임 인식 WCF 서비스를 빌드하려면 참조 [방법: WCF 웹 서비스 응용 프로그램에 대 한 WIF 사용](../../../docs/framework/security/how-to-enable-wif-for-a-wcf-web-service-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d21-128">To build your first claims-aware WCF service using WIF, see [How To: Enable WIF for a WCF Web Service Application](../../../docs/framework/security/how-to-enable-wif-for-a-wcf-web-service-application.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f7d21-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7d21-129">See Also</span></span>  
 [<span data-ttu-id="f7d21-130">WIF 시작</span><span class="sxs-lookup"><span data-stu-id="f7d21-130">Getting Started With WIF</span></span>](../../../docs/framework/security/getting-started-with-wif.md)
