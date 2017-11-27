---
title: "전송 보안"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86c94153-e48d-4539-b6cf-cd8060582e7f
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: d9576321ca44d568633fcba40e56f9582d3f5db5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="transport-security"></a><span data-ttu-id="2a78e-102">전송 보안</span><span class="sxs-lookup"><span data-stu-id="2a78e-102">Transport Security</span></span>
<span data-ttu-id="2a78e-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 전송 보안은 선택한 바인딩에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2a78e-103">Transport security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] depends on the binding selected.</span></span> <span data-ttu-id="2a78e-104">바인딩이 구현하는 전송은 실제 보안 메커니즘을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a78e-104">The transport that the binding implements determines the actual security mechanism.</span></span> <span data-ttu-id="2a78e-105">이 단원의 항목에서는 구현된 메커니즘 및 해당 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a78e-105">The topics in this section explain the mechanisms that are implemented and their options.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a78e-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="2a78e-106">In This Section</span></span>  
 [<span data-ttu-id="2a78e-107">전송 보안 개요</span><span class="sxs-lookup"><span data-stu-id="2a78e-107">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="2a78e-108">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 전송 보안 기본 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a78e-108">Explains the basics of transport security in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="2a78e-109">HTTP 전송 보안</span><span class="sxs-lookup"><span data-stu-id="2a78e-109">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)  
 <span data-ttu-id="2a78e-110">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 SSL(Secure Sockets Layer) 또는 HTTPS를 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a78e-110">Explains how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implements Secure Sockets Layer (SSL, or HTTPS).</span></span>  
  
 [<span data-ttu-id="2a78e-111">HTTP 인증 이해</span><span class="sxs-lookup"><span data-stu-id="2a78e-111">Understanding HTTP Authentication</span></span>](../../../../docs/framework/wcf/feature-details/understanding-http-authentication.md)  
 <span data-ttu-id="2a78e-112">기본, 다이제스트, NTLM(NT LAN Manager) 등과 같은 HTTP 인증 스키마에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a78e-112">Describes HTTP authentication schemes, such as Basic, Digest, NT LAN Manager (NTLM), and others.</span></span>  
  
 [<span data-ttu-id="2a78e-113">전송 보안으로 가장 사용</span><span class="sxs-lookup"><span data-stu-id="2a78e-113">Using Impersonation with Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/using-impersonation-with-transport-security.md)  
 <span data-ttu-id="2a78e-114">전송 보안 모드를 사용하여 수행할 수 있는 5가지 가장 수준에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a78e-114">Explains the five levels of impersonation that are possible with transport security mode.</span></span>  
  
 [<span data-ttu-id="2a78e-115">방법: SSL 인증서로 포트 구성</span><span class="sxs-lookup"><span data-stu-id="2a78e-115">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 <span data-ttu-id="2a78e-116">SSL(전송) 보안용 X.509 인증서가 있는 컴퓨터에서의 포트 구성 기본 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a78e-116">Walks through the basics of configuring a port on a machine with an X.509 certificate for SSL (transport) security.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2a78e-117">참조</span><span class="sxs-lookup"><span data-stu-id="2a78e-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="2a78e-118">관련 단원</span><span class="sxs-lookup"><span data-stu-id="2a78e-118">Related Sections</span></span>  
 [<span data-ttu-id="2a78e-119">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="2a78e-119">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="2a78e-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a78e-120">See Also</span></span>  
 [<span data-ttu-id="2a78e-121">WCF 보안 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="2a78e-121">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
