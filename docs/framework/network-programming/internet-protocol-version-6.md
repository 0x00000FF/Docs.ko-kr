---
title: 인터넷 프로토콜 버전 6
ms.date: 03/30/2017
helpviewer_keywords:
- IPv6, improvements
- IPv4
- IPv6
- Internet Protocol version 6, improvements
- Internet Protocol version 6
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
ms.openlocfilehash: 0851ad42cd5ce2dd6b49ad7656479d5237fd5874
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647353"
---
# <a name="internet-protocol-version-6"></a><span data-ttu-id="b2444-102">인터넷 프로토콜 버전 6</span><span class="sxs-lookup"><span data-stu-id="b2444-102">Internet Protocol Version 6</span></span>
<span data-ttu-id="b2444-103">IPv6(인터넷 프로토콜 버전 6)은 인터넷 네트워크 계층에 대한 새로운 표준 프로토콜 도구 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-103">The Internet Protocol version 6 (IPv6) is a new suite of standard protocols for the network layer of the Internet.</span></span> <span data-ttu-id="b2444-104">IPv6은 주소 고갈, 보안, 자동 구성, 확장성 등에 관련된 현재 버전 인터넷 프로토콜 도구 모음(IPv4라고 함)의 많은 문제를 해결하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-104">IPv6 is designed to solve many of the problems of the current version of the Internet Protocol suite (known as IPv4) with regard to address depletion, security, auto-configuration, extensibility, and so on.</span></span> <span data-ttu-id="b2444-105">IPv6은 피어 투 피어 및 모바일 애플리케이션을 포함한 새로운 종류의 애플리케이션을 구현하기 위해 인터넷 기능을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-105">IPv6 expands the capabilities of the Internet to enable new kinds of applications, including peer-to-peer and mobile applications.</span></span> <span data-ttu-id="b2444-106">현재 IPv4 프로토콜의 주요 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-106">The following are the main issues of the current IPv4 protocol:</span></span>  
  
- <span data-ttu-id="b2444-107">주소 공간의 빠른 고갈.</span><span class="sxs-lookup"><span data-stu-id="b2444-107">Rapid depletion of the address space.</span></span>  
  
     <span data-ttu-id="b2444-108">이 문제로 인해 여러 개인 주소를 단일 공용 IP 주소에 매핑하는 NAT(Network Address Translator)를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-108">This has led to the use of Network Address Translators (NATs) that map multiple private addresses to a single public IP address.</span></span> <span data-ttu-id="b2444-109">이 메커니즘에서 발생하는 주요 문제는 처리 오버헤드 및 종단 간 연결 부족입니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-109">The main problems created by this mechanism are processing overhead and lack of end-to-end connectivity.</span></span>  
  
- <span data-ttu-id="b2444-110">계층 구조 지원 없음.</span><span class="sxs-lookup"><span data-stu-id="b2444-110">Lack of hierarchy support.</span></span>  
  
     <span data-ttu-id="b2444-111">고유의 미리 정의된 클래스 조직으로 인해 IPv4에는 실제 계층 구조 지원이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-111">Because of its inherent predefined class organization, IPv4 lacks true hierarchical support.</span></span> <span data-ttu-id="b2444-112">실제로 네트워크 토폴로지를 매핑하는 방식으로 IP 주소를 구조화할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-112">It is impossible to structure the IP addresses in a way that truly maps the network topology.</span></span> <span data-ttu-id="b2444-113">이 중대한 설계 결함으로 인해 IPv4 패킷을 인터넷의 임의 위치에 전달하기 위해 큰 라우팅 테이블이 필요하게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-113">This crucial design flaw creates the need for large routing tables to deliver IPv4 packets to any location on the Internet.</span></span>  
  
- <span data-ttu-id="b2444-114">복잡한 네트워크 구성.</span><span class="sxs-lookup"><span data-stu-id="b2444-114">Complex network configuration.</span></span>  
  
     <span data-ttu-id="b2444-115">IPv4를 사용할 경우 주소를 정적으로 할당하거나 주소에 DHCP 등의 구성 프로토콜을 사용 중이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-115">With IPv4, addresses must be assigned statically or using a configuration protocol such as DHCP.</span></span> <span data-ttu-id="b2444-116">이상적인 상황에서는 호스트가 DHCP 인프라의 관리에 의존할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-116">In an ideal situation, hosts would not have to rely on the administration of a DHCP infrastructure.</span></span> <span data-ttu-id="b2444-117">대신에 호스트는 배치되어 있는 네트워크 세그먼트를 기반으로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-117">Instead, they would be able to configure themselves based on the network segment in which they are located.</span></span>  
  
- <span data-ttu-id="b2444-118">기본 제공 인증 및 기밀성 없음.</span><span class="sxs-lookup"><span data-stu-id="b2444-118">Lack of built-in authentication and confidentiality.</span></span>  
  
     <span data-ttu-id="b2444-119">IPv4의 경우 교환된 데이터에 대한 인증이나 암호화를 제공하는 메커니즘을 지원할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-119">IPv4 does not require the support for any mechanism that provides authentication or encryption of the exchanged data.</span></span> <span data-ttu-id="b2444-120">이 내용은 IPv6에서 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-120">This changes with IPv6.</span></span> <span data-ttu-id="b2444-121">IPSec(인터넷 프로토콜 보안)는 IPv6 지원 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-121">Internet Protocol security (IPSec) is an IPv6 support requirement.</span></span>  
  
 <span data-ttu-id="b2444-122">새로운 프로토콜 도구 모음은 다음 기본 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-122">A new protocol suite must satisfy the following basic requirements:</span></span>  
  
- <span data-ttu-id="b2444-123">낮은 오버헤드가 발생하는 대규모 라우팅 및 주소 지정.</span><span class="sxs-lookup"><span data-stu-id="b2444-123">Large-scale routing and addressing with low overhead.</span></span>  
  
- <span data-ttu-id="b2444-124">다양한 연결 상황에 대한 자동 구성.</span><span class="sxs-lookup"><span data-stu-id="b2444-124">Auto-configuration for various connecting situations.</span></span>  
  
- <span data-ttu-id="b2444-125">기본 제공 인증 및 기밀성.</span><span class="sxs-lookup"><span data-stu-id="b2444-125">Built-in authentication and confidentiality.</span></span>  
  
 <span data-ttu-id="b2444-126">자세한 내용은 [IPv6 주소 지정](../../../docs/framework/network-programming/ipv6-addressing.md), [IPv6 라우팅](../../../docs/framework/network-programming/ipv6-routing.md), [IPv6 자동 구성](../../../docs/framework/network-programming/ipv6-auto-configuration.md), [IPv6 사용 및 사용 안 함](../../../docs/framework/network-programming/enabling-and-disabling-ipv6.md) 및 [방법: IPv6 지원을 사용하도록 컴퓨터 구성 파일 수정](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2444-126">For more information, see [IPv6 Addressing](../../../docs/framework/network-programming/ipv6-addressing.md), [IPv6 Routing](../../../docs/framework/network-programming/ipv6-routing.md), [IPv6 Auto-Configuration](../../../docs/framework/network-programming/ipv6-auto-configuration.md), [Enabling and Disabling IPv6](../../../docs/framework/network-programming/enabling-and-disabling-ipv6.md), and [How to: Modify the Computer Configuration File to Enable IPv6 Support](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="b2444-127">참조</span><span class="sxs-lookup"><span data-stu-id="b2444-127">References</span></span>  
 <span data-ttu-id="b2444-128">[IETF(Internet Engineering Task Force)](https://www.ietf.org/) 웹 사이트에서 찾을 수 있는 선택된 RFC 문서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-128">The following are selected RFC documents that you can find at the [Internet Engineering Task Force (IETF)](https://www.ietf.org/) website:</span></span>  
  
- <span data-ttu-id="b2444-129">RFC 1287, Towards the Future Internet Architecture.</span><span class="sxs-lookup"><span data-stu-id="b2444-129">RFC 1287, Towards the Future Internet Architecture.</span></span>  
  
- <span data-ttu-id="b2444-130">RFC 1454, Comparison of Proposals for Next Version of IP.</span><span class="sxs-lookup"><span data-stu-id="b2444-130">RFC 1454, Comparison of Proposals for Next Version of IP.</span></span>  
  
- <span data-ttu-id="b2444-131">RFC 2373, IP Version 6 Addressing Architecture.</span><span class="sxs-lookup"><span data-stu-id="b2444-131">RFC 2373, IP Version 6 Addressing Architecture.</span></span>  
  
- <span data-ttu-id="b2444-132">RFC 2374, An IPv6 Aggregatable Global Unicast Address Format.</span><span class="sxs-lookup"><span data-stu-id="b2444-132">RFC 2374, An IPv6 Aggregatable Global Unicast Address Format.</span></span>  
  
 <span data-ttu-id="b2444-133">또한 [IPv6(IP 버전 6)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd379498%28v=ws.10%29)에서 IPv6 관련 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2444-133">You can also find IPv6-related information on the [IP Version 6 (IPv6)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd379498%28v=ws.10%29).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2444-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2444-134">See also</span></span>

- [<span data-ttu-id="b2444-135">IPv6 소켓 샘플</span><span class="sxs-lookup"><span data-stu-id="b2444-135">IPv6 Sockets Sample</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms180981%28v=vs.85%29)
- [<span data-ttu-id="b2444-136">네트워크 프로그래밍 샘플</span><span class="sxs-lookup"><span data-stu-id="b2444-136">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)
- [<span data-ttu-id="b2444-137">소켓</span><span class="sxs-lookup"><span data-stu-id="b2444-137">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)
