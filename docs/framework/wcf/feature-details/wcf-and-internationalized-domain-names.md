---
title: WCF 및 IDN(Internationalized Domain Name)
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: a0d4a5b4fe5dd3bc7cf41c8c6ad320dd83861aec
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187925"
---
# <a name="wcf-and-internationalized-domain-names"></a><span data-ttu-id="56092-102">WCF 및 IDN(Internationalized Domain Name)</span><span class="sxs-lookup"><span data-stu-id="56092-102">WCF and Internationalized Domain Names</span></span>
<span data-ttu-id="56092-103">IDN(Internationalized Domain Name)을 사용하는 WCF 서비스에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="56092-103">Support has been added to allow for WCF services with Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="56092-104">IDN(Internationalized Domain Name)은 비 ASCII 문자가 포함된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="56092-104">An internationalized domain name is a domain name that contains non-ASCII characters.</span></span> <span data-ttu-id="56092-105">이 지원을 통해 IDN 이름을 사용하는 WCF 서비스와 IDN 이름을 사용하는 웹 서비스와 통신하는 WCF 클라이언트를 둘 다 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56092-105">This support includes both the ability to host a WCF service with an IDN name and a WCF client to talk to a web service with an IDN name.</span></span>  
  
## <a name="systemuri-and-idn"></a><span data-ttu-id="56092-106">System.Uri 및 IDN</span><span class="sxs-lookup"><span data-stu-id="56092-106">System.Uri and IDN</span></span>  
 <span data-ttu-id="56092-107"><xref:System.Uri>에는 <xref:System.Uri.Host%2A>와 <xref:System.Uri.DnsSafeHost%2A>라는 두 가지 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56092-107"><xref:System.Uri> has two properties <xref:System.Uri.Host%2A> and <xref:System.Uri.DnsSafeHost%2A>.</span></span> <span data-ttu-id="56092-108">이러한 속성에는 IDN 구성 설정에 따라 유니코드 또는 Punycode 값이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56092-108">These properties contain Unicode or Punycode values depending upon the IDN configuration settings.</span></span>  
  
 <span data-ttu-id="56092-109">IDN은 다음 XML을 사용하여 응용 프로그램의 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56092-109">IDN is enabled in an application’s configuration file using the following XML</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 <span data-ttu-id="56092-110">\<idn > 요소에 다음 값 중 하나로 설정할 수 있는 사용된 특성이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56092-110">The \<idn> element contains the enabled attribute which can be set to one of the following values:</span></span>  
  
1.  <span data-ttu-id="56092-111">"None"</span><span class="sxs-lookup"><span data-stu-id="56092-111">"None"</span></span>  
  
2.  <span data-ttu-id="56092-112">"AllExceptIntranet"</span><span class="sxs-lookup"><span data-stu-id="56092-112">"AllExceptIntranet"</span></span>  
  
3.  <span data-ttu-id="56092-113">"All"</span><span class="sxs-lookup"><span data-stu-id="56092-113">"All"</span></span>  
  
 <span data-ttu-id="56092-114">IDN 설정이 "None"으로 설정 되 면 Uri.Host 또는 Uri.DnsSafeHost에 의해 변환이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56092-114">When the IDN setting is set to "None", no conversions are performed by Uri.Host or Uri.DnsSafeHost.</span></span> <span data-ttu-id="56092-115">IDN 설정이 "All", uri로 설정 하면 합니다. 유니코드 및 uri 호스트에 유지 됩니다. DnsSafeHost은 Punycode로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56092-115">When the IDN setting is set to "All", uri.Host remains Unicode and uri.DnsSafeHost is converted to Punycode.</span></span> <span data-ttu-id="56092-116">IDN 설정이 "AllExceptIntranet", uri 설정 하면 합니다. DnsSafeHost은 인터넷 주소 용인 Punycode로 변환 됩니다 및 인트라넷 주소 용인 유니코드로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56092-116">When the IDN setting is set to "AllExceptIntranet", uri.DnsSafeHost is converted to Punycode for internet addresses, and remains Unicode for intranet addresses.</span></span> <span data-ttu-id="56092-117">이 설정은 정확한 DNS 이름 확인을 위해 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="56092-117">This setting is important for correct DNS name resolution.</span></span> <span data-ttu-id="56092-118">Windows 8 및 최신 버전에서는 이 설정을 구성하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56092-118">Note this setting is not required to be configured for Windows 8 and newer versions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="56092-119">Punycode를 사용하여 주소를 하드 코딩하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="56092-119">You should never hard-code an address using Punycode.</span></span> <span data-ttu-id="56092-120">WCF는 사용자가 적용하는 구성 설정을 기준으로 변환해 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56092-120">WCF will convert it for you based on the configuration settings you apply.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="56092-121">applicationHost.exe.config에 유니코드 문자를 추가하는 경우 파일을 UTF-8 인코딩으로 저장하세요.</span><span class="sxs-lookup"><span data-stu-id="56092-121">When adding Unicode characters to applicationHost.exe.config, save the file using the UTF-8 encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56092-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56092-122">See Also</span></span>  
 <xref:System.Uri?displayProperty=nameWithType>
