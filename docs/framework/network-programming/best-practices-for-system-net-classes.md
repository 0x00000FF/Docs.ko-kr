---
title: "System.Net 클래스에 대한 모범 사례"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sending data, best practices
- requesting data from Internet, best practices
- WebRequest class, best practices
- data requests, best practices
- WebResponse class, best practices
- best practices, data requests
- receiving data, best practices
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 90722abbdb4568be115c0ac77007d5f18984df6f
ms.sourcegitcommit: 32172ca05d5dcce7ef3d327b9c8639c736e0fe2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2018
---
# <a name="best-practices-for-systemnet-classes"></a><span data-ttu-id="c3acf-102">System.Net 클래스에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="c3acf-102">Best Practices for System.Net Classes</span></span>
<span data-ttu-id="c3acf-103">다음 권장 사항은 <xref:System.Net>에 포함된 클래스를 최대한 활용하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3acf-103">The following recommendations will help you use the classes contained in <xref:System.Net> to their best advantage:</span></span>  
  
-   <span data-ttu-id="c3acf-104">보안 TLS (전송 계층) 모범 사례를 참조 하십시오. [보안 TLS (전송 계층).NET Framework와 함께 유용한](tls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3acf-104">For Transport Layer Security (TLS) best practices, see [Transport Layer Security (TLS) best practices with .NET Framework](tls.md).</span></span>

-   <span data-ttu-id="c3acf-105">가능한 경우 하위 클래스에 대한 형식 캐스팅 대신 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c3acf-105">Use <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> whenever possible instead of type casting to descendant classes.</span></span> <span data-ttu-id="c3acf-106">**WebRequest** 및 **WebResponse**를 사용하는 응용 프로그램은 광범위한 코드 변경 없이 새 인터넷 프로토콜을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3acf-106">Applications that use **WebRequest** and **WebResponse** can take advantage of new Internet protocols without needing extensive code changes.</span></span>  
  
-   <span data-ttu-id="c3acf-107">**System.Net** 클래스를 사용하여 서버에서 실행되는 ASP.NET 응용 프로그램을 작성할 때는 성능 관점에서 대체로 <xref:System.Net.WebRequest.GetResponse%2A> 및 <xref:System.Net.WebResponse.GetResponseStream%2A>에 대해 비동기 메서드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c3acf-107">When writing ASP.NET applications that run on a server using the **System.Net** classes, it is often better, from a performance standpoint, to use the asynchronous methods for <xref:System.Net.WebRequest.GetResponse%2A> and <xref:System.Net.WebResponse.GetResponseStream%2A>.</span></span>  
  
-   <span data-ttu-id="c3acf-108">인터넷 리소스에 대해 열린 연결 수는 네트워크 성능 및 처리량에 상당한 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3acf-108">The number of connections opened to an Internet resource can have a significant impact on network performance and throughput.</span></span> <span data-ttu-id="c3acf-109">**System.Net**은 기본적으로 호스트당 응용 프로그램마다 두 개의 연결을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c3acf-109">**System.Net** uses two connections per application per host by default.</span></span> <span data-ttu-id="c3acf-110">응용 프로그램에 대한 <xref:System.Net.ServicePoint>의 <xref:System.Net.ServicePoint.ConnectionLimit%2A> 속성을 설정하면 특정 호스트에 대해 이 개수를 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3acf-110">Setting the <xref:System.Net.ServicePoint.ConnectionLimit%2A> property in the <xref:System.Net.ServicePoint> for your application can increase this number for a particular host.</span></span> <span data-ttu-id="c3acf-111"><xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=nameWithType> 속성을 설정하면 모든 호스트에 대해 이 기본값을 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3acf-111">Setting the <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=nameWithType> property can increase this default for all hosts.</span></span>  
  
-   <span data-ttu-id="c3acf-112">소켓 수준 프로토콜을 작성할 때는 가능한 경우 <xref:System.Net.Sockets.Socket>에 직접 작성하는 대신 <xref:System.Net.Sockets.TcpClient> 또는 <xref:System.Net.Sockets.UdpClient>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c3acf-112">When writing socket-level protocols, try to use <xref:System.Net.Sockets.TcpClient> or <xref:System.Net.Sockets.UdpClient> whenever possible instead of writing directly to a <xref:System.Net.Sockets.Socket>.</span></span> <span data-ttu-id="c3acf-113">이러한 두 클라이언트 클래스는 연결의 세부 정보를 처리할 필요 없이 TCP 및 UDP 소켓 생성을 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="c3acf-113">These two client classes encapsulate the creation of TCP and UDP sockets without requiring you to handle the details of the connection.</span></span>  
  
-   <span data-ttu-id="c3acf-114">자격 증명을 요구하는 사이트에 액세스하는 경우 요청할 때마다 자격 증명을 제공하는 대신 <xref:System.Net.CredentialCache> 클래스를 사용하여 자격 증명 캐시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c3acf-114">When accessing sites that require credentials, use the <xref:System.Net.CredentialCache> class to create a cache of credentials rather than supplying them with every request.</span></span> <span data-ttu-id="c3acf-115">**CredentialCache** 클래스는 캐시를 검색하여 요청과 함께 제공할 적절한 자격 증명을 찾아 URL을 기준으로 자격 증명을 만들고 제공해야 하는 부담을 덜어줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3acf-115">The **CredentialCache** class searches the cache to find the appropriate credential to present with a request, relieving you of the responsibility of creating and presenting credentials based on the URL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3acf-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3acf-116">See Also</span></span>  
 [<span data-ttu-id="c3acf-117">.NET Framework의 네트워크 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="c3acf-117">Network Programming in the .NET Framework</span></span>](../../../docs/framework/network-programming/index.md)
