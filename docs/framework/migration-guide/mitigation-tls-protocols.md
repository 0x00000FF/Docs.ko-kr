---
title: '완화: TLS 프로토콜'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
ms.openlocfilehash: 45225d73ac60564d3e22c73270faab6b4e04d697
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457830"
---
# <a name="mitigation-tls-protocols"></a><span data-ttu-id="59658-102">완화: TLS 프로토콜</span><span class="sxs-lookup"><span data-stu-id="59658-102">Mitigation: TLS Protocols</span></span>
<span data-ttu-id="59658-103">.NET Framework 4.6부터 <xref:System.Net.ServicePointManager?displayProperty=nameWithType> 및 <xref:System.Net.Security.SslStream?displayProperty=nameWithType> 클래스에서 다음 세 개의 프로토콜 중 하나를 사용할 수 있습니다. Tls1.0, Tls1.1 또는 Tls 1.2.</span><span class="sxs-lookup"><span data-stu-id="59658-103">Starting with the .NET Framework 4.6, the <xref:System.Net.ServicePointManager?displayProperty=nameWithType> and <xref:System.Net.Security.SslStream?displayProperty=nameWithType> classes are allowed to use one of the following three protocols: Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="59658-104">SSL3.0 프로토콜 및 RC4 암호화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59658-104">The SSL3.0 protocol and RC4 cipher are not supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="59658-105">영향</span><span class="sxs-lookup"><span data-stu-id="59658-105">Impact</span></span>  
 <span data-ttu-id="59658-106">이러한 변경 내용은 다음 앱에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59658-106">This change affects:</span></span>  
  
- <span data-ttu-id="59658-107">HTTPS 서버 또는 <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> 및 <xref:System.Net.Security.SslStream> 유형 중 하나를 사용하는 소켓 서버와 통신하는 데 SSL을 사용하는 모든 앱</span><span class="sxs-lookup"><span data-stu-id="59658-107">Any app that uses SSL to talk to an HTTPS server or a socket server using any of the following types: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient>, and <xref:System.Net.Security.SslStream>.</span></span>  
  
- <span data-ttu-id="59658-108">Tls1.0, Tls1.1 또는 Tls 1.2를 지원하기 위해 업그레이드할 수 없는 모든 서버 쪽 앱</span><span class="sxs-lookup"><span data-stu-id="59658-108">Any server-side app that cannot be upgraded to support Tls1.0, Tls1.1, or Tls 1.2..</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="59658-109">완화</span><span class="sxs-lookup"><span data-stu-id="59658-109">Mitigation</span></span>  
 <span data-ttu-id="59658-110">권장되는 완화 방법은 Tls1.0, Tls1.1 또는 Tls 1.2로 서버 쪽 앱을 업그레이드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="59658-110">The recommended mitigation is to upgrade the sever-side app to Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="59658-111">이 작업이 불가능하거나 클라이언트 앱이 손상된 경우 <xref:System.AppContext> 클래스를 사용하여 다음 두 방법 중 하나로 이 기능을 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59658-111">If this is not feasible, or if client apps are broken, the <xref:System.AppContext> class can be used to opt out of this feature in either of two ways:</span></span>  
  
- <span data-ttu-id="59658-112">다음과 같은 코드 조각을 사용하여 프로그래밍 방식으로</span><span class="sxs-lookup"><span data-stu-id="59658-112">Programmatically, by using a code snippet like the following:</span></span>  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     <span data-ttu-id="59658-113"><xref:System.Net.ServicePointManager> 개체는 한 번만 초기화되므로 먼저 애플리케이션에서 이러한 호환성 설정을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59658-113">Because the <xref:System.Net.ServicePointManager> object is initialized only once, defining these compatibility settings must be the first thing the application does.</span></span>  
  
- <span data-ttu-id="59658-114">다음 줄을 app.config 파일의 [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) 섹션에 추가</span><span class="sxs-lookup"><span data-stu-id="59658-114">By adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 <span data-ttu-id="59658-115">그러나 애플리케이션 보안 수준이 낮아지므로 기본 동작은 옵트아웃(opt out)하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="59658-115">Note, however, that opting out of the default behavior is not recommended, since it makes the application less secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59658-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59658-116">See also</span></span>

- [<span data-ttu-id="59658-117">애플리케이션 호환성</span><span class="sxs-lookup"><span data-stu-id="59658-117">Application compatibility</span></span>](application-compatibility.md)
