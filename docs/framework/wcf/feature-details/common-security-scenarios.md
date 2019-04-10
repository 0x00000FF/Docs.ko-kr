---
title: 일반적인 보안 시나리오
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: af58d6b529fba32380bedb9a892a2b1fd4807d96
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199273"
---
# <a name="common-security-scenarios"></a><span data-ttu-id="d83dd-102">일반적인 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="d83dd-102">Common Security Scenarios</span></span>
<span data-ttu-id="d83dd-103">이 단원의 항목에서는 많은 수의 가능한 클라이언트 및 서비스 보안 구성을 카탈로그로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-103">The topics in this section catalog a number of possible client and service security configurations.</span></span> <span data-ttu-id="d83dd-104">구성은 요소 수에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-104">Configurations vary according to a number of factors.</span></span> <span data-ttu-id="d83dd-105">예를 들어 서비스 또는 클라이언트가 인트라넷에 있는지, 보안이 Windows에서 제공되는지 아니면 HTTPS와 같은 전송에 의해 제공되는지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-105">For example, whether a service or client is on an intranet, or whether the security is provided by Windows or transport (such as HTTPS).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d83dd-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d83dd-106">In This Section</span></span>  
 [<span data-ttu-id="d83dd-107">보안이 설정되지 않은 인터넷 클라이언트 및 서비스</span><span class="sxs-lookup"><span data-stu-id="d83dd-107">Internet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/internet-unsecured-client-and-service.md)  
 <span data-ttu-id="d83dd-108">보안되지 않은 공용 클라이언트 및 서비스의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-108">An example of a public, unsecured client and service.</span></span>  
  
 [<span data-ttu-id="d83dd-109">보안이 설정되지 않은 인트라넷 클라이언트 및 서비스</span><span class="sxs-lookup"><span data-stu-id="d83dd-109">Intranet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/intranet-unsecured-client-and-service.md)  
 <span data-ttu-id="d83dd-110">WCF 응용 프로그램에 안전한 개인 네트워크에서 정보를 제공 하는 기본 Windows Communication Foundation (WCF) 서비스를 개발 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-110">A basic Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span>  
  
 [<span data-ttu-id="d83dd-111">기본 인증을 사용하는 전송 보안</span><span class="sxs-lookup"><span data-stu-id="d83dd-111">Transport Security with Basic Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 <span data-ttu-id="d83dd-112">클라이언트는 해당 응용 프로그램을 통해 사용자 지정 인증을 사용하여 로그온할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-112">The application allows clients to log on using custom authentication.</span></span>  
  
 [<span data-ttu-id="d83dd-113">Windows 인증을 사용하는 전송 보안</span><span class="sxs-lookup"><span data-stu-id="d83dd-113">Transport Security with Windows Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)  
 <span data-ttu-id="d83dd-114">Windows 보안을 사용하여 보안하는 클라이언트 및 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-114">Shows a client and service secured by Windows security.</span></span>  
  
 [<span data-ttu-id="d83dd-115">익명 클라이언트를 사용하는 전송 보안</span><span class="sxs-lookup"><span data-stu-id="d83dd-115">Transport Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-an-anonymous-client.md)  
 <span data-ttu-id="d83dd-116">이 시나리오에서는 기밀성 및 무결성 확보를 위해 전송 보안(예: HTTPS)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-116">This scenario uses transport security (such as HTTPS) to ensure confidentiality and integrity.</span></span>  
  
 [<span data-ttu-id="d83dd-117">인증서 인증을 사용하는 전송 보안</span><span class="sxs-lookup"><span data-stu-id="d83dd-117">Transport Security with Certificate Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-certificate-authentication.md)  
 <span data-ttu-id="d83dd-118">인증서를 사용하여 보안하는 클라이언트 및 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-118">Shows a client and service secured by a certificate.</span></span>  
  
 [<span data-ttu-id="d83dd-119">익명 클라이언트를 사용하는 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="d83dd-119">Message Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-an-anonymous-client.md)  
 <span data-ttu-id="d83dd-120">클라이언트와 WCF 메시지 보안에 의해 보호 되는 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-120">Shows a client and service secured by WCF message security.</span></span>  
  
 [<span data-ttu-id="d83dd-121">사용자 이름 클라이언트를 사용하는 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="d83dd-121">Message Security with a User Name Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-user-name-client.md)  
 <span data-ttu-id="d83dd-122">클라이언트는 도메인 사용자 이름 및 암호를 사용하여 클라이언트가 로그온할 수 있도록 허용하는 Windows Forms 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-122">The client is a Windows Forms application that allows clients to log on using a domain user name and password.</span></span>  
  
 [<span data-ttu-id="d83dd-123">인증서 클라이언트를 사용하는 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="d83dd-123">Message Security with a Certificate Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-certificate-client.md)  
 <span data-ttu-id="d83dd-124">서버에는 여러 인증서가 있으며, 각 클라이언트에는 하나의 인증서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-124">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="d83dd-125">보안 컨텍스트는 TLS(전송 계층 보안) 협상을 통해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-125">A security context is established through Transport Layer Security (TLS) negotiation.</span></span>  
  
 [<span data-ttu-id="d83dd-126">Windows 클라이언트를 사용하는 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="d83dd-126">Message Security with a Windows Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)  
 <span data-ttu-id="d83dd-127">인증서 클라이언트의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-127">A variation of the certificate client.</span></span> <span data-ttu-id="d83dd-128">서버에는 여러 인증서가 있으며, 각 클라이언트에는 하나의 인증서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-128">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="d83dd-129">보안 컨텍스트는 TLS 협상을 통해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-129">A security context is established through TLS negotiation.</span></span>  
  
 [<span data-ttu-id="d83dd-130">자격 증명 협상 없이 Windows 클라이언트를 사용하는 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="d83dd-130">Message Security with a Windows Client without Credential Negotiation</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client-without-credential-negotiation.md)  
 <span data-ttu-id="d83dd-131">Kerberos 도메인을 사용하여 보안하는 클라이언트 및 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-131">Shows a client and service secured by a Kerberos domain.</span></span>  
  
 [<span data-ttu-id="d83dd-132">상호 인증서를 사용하는 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="d83dd-132">Message Security with Mutual Certificates</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-mutual-certificates.md)  
 <span data-ttu-id="d83dd-133">서버에는 여러 인증서가 있으며, 각 클라이언트에는 하나의 인증서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-133">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="d83dd-134">서버 인증서는 응용 프로그램과 함께 분산되며 대역 외에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-134">The server certificate is distributed with the application and is available out of band.</span></span>  
  
 [<span data-ttu-id="d83dd-135">발급된 토큰을 사용하는 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="d83dd-135">Message Security with Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-issued-tokens.md)  
 <span data-ttu-id="d83dd-136">독립 도메인 간에 신뢰를 설정할 수 있도록 해주는 페더레이션 보안입니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-136">Federated security that enables the establishment of trust between independent domains.</span></span>  
  
 [<span data-ttu-id="d83dd-137">신뢰할 수 있는 하위 시스템</span><span class="sxs-lookup"><span data-stu-id="d83dd-137">Trusted Subsystem</span></span>](../../../../docs/framework/wcf/feature-details/trusted-subsystem.md)  
 <span data-ttu-id="d83dd-138">클라이언트는 네트워크에 분산되어 있는 하나 이상의 웹 서비스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-138">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="d83dd-139">웹 서비스는 데이터베이스 또는 기타 웹 서비스와 같은 보안이 필요한 추가 리소스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="d83dd-139">The Web services access additional resources (such as databases or other Web services) that must be secured.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d83dd-140">참조</span><span class="sxs-lookup"><span data-stu-id="d83dd-140">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="d83dd-141">관련 단원</span><span class="sxs-lookup"><span data-stu-id="d83dd-141">Related Sections</span></span>  
 [<span data-ttu-id="d83dd-142">권한 부여</span><span class="sxs-lookup"><span data-stu-id="d83dd-142">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="d83dd-143">보안 개요</span><span class="sxs-lookup"><span data-stu-id="d83dd-143">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
 [<span data-ttu-id="d83dd-144">보안</span><span class="sxs-lookup"><span data-stu-id="d83dd-144">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="d83dd-145">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="d83dd-145">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="d83dd-146">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="d83dd-146">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
 [<span data-ttu-id="d83dd-147">인증</span><span class="sxs-lookup"><span data-stu-id="d83dd-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="d83dd-148">권한 부여</span><span class="sxs-lookup"><span data-stu-id="d83dd-148">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="d83dd-149">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="d83dd-149">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="d83dd-150">감사</span><span class="sxs-lookup"><span data-stu-id="d83dd-150">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
## <a name="see-also"></a><span data-ttu-id="d83dd-151">참고자료</span><span class="sxs-lookup"><span data-stu-id="d83dd-151">See also</span></span>

- [<span data-ttu-id="d83dd-152">보안 지침 및 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="d83dd-152">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)
- [<span data-ttu-id="d83dd-153">Windows Server AppFabric 보안 모델</span><span class="sxs-lookup"><span data-stu-id="d83dd-153">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
