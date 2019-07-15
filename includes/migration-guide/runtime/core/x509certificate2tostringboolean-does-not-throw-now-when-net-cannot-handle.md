---
ms.openlocfilehash: d48519443aeee05617538cf2cc12bea49ad3e16d
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858480"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a><span data-ttu-id="86049-101">X509Certificate2.ToString(Boolean)은 .NET이 인증서를 처리할 수 없을 때 throw하지 않습니다</span><span class="sxs-lookup"><span data-stu-id="86049-101">X509Certificate2.ToString(Boolean) does not throw now when .NET cannot handle the certificate</span></span>

|   |   |
|---|---|
|<span data-ttu-id="86049-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="86049-102">Details</span></span>|<span data-ttu-id="86049-103">.NET Framework 4.5.2 및 이전 버전에서 verbose 매개 변수에 <code>true</code>가 전달되고 .Net Framework에서 지원하지 않는 인증서가 설치된 경우 이 메서드가 throw되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86049-103">In .NET Framework 4.5.2 and earlier versions, this method would throw if <code>true</code> was passed for the verbose parameter and there were certificates installed that weren't supported by the .NET Framework.</span></span> <span data-ttu-id="86049-104">이제 이 메서드는 성공하고 인증서의 액세스할 수 없는 부분을 생략하는 유효한 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="86049-104">Now, the method will succeed and return a valid string that omits the inaccessible portions of the certificate.</span></span>|
|<span data-ttu-id="86049-105">제안</span><span class="sxs-lookup"><span data-stu-id="86049-105">Suggestion</span></span>|<span data-ttu-id="86049-106"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType>에 종속된 모든 코드는 API가 이전에 throw된 일부 경우에서 반환된 문자열이 일부 인증서 데이터(예: 공개 키, 개인 키 및 확장명)를 제외하도록 업데이트되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86049-106">Any code depending on <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> should be updated to expect that the returned string may exclude some certificate data (such as public key, private key, and extensions) in some cases in which the API would have previously thrown.</span></span>|
|<span data-ttu-id="86049-107">범위</span><span class="sxs-lookup"><span data-stu-id="86049-107">Scope</span></span>|<span data-ttu-id="86049-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="86049-108">Edge</span></span>|
|<span data-ttu-id="86049-109">버전</span><span class="sxs-lookup"><span data-stu-id="86049-109">Version</span></span>|<span data-ttu-id="86049-110">4.6</span><span class="sxs-lookup"><span data-stu-id="86049-110">4.6</span></span>|
|<span data-ttu-id="86049-111">형식</span><span class="sxs-lookup"><span data-stu-id="86049-111">Type</span></span>|<span data-ttu-id="86049-112">런타임</span><span class="sxs-lookup"><span data-stu-id="86049-112">Runtime</span></span>|
|<span data-ttu-id="86049-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="86049-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|

