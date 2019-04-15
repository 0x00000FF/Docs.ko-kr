---
ms.openlocfilehash: 6dc3669433804a4524c18d5a932f9879343ab508
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235458"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="312f8-101">OData URL의 Replace 메서드는 기본적으로 비활성화되어 있음</span><span class="sxs-lookup"><span data-stu-id="312f8-101">The Replace method in OData URLs is disabled by default</span></span>

|   |   |
|---|---|
|<span data-ttu-id="312f8-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="312f8-102">Details</span></span>|<span data-ttu-id="312f8-103">.NET Framework 4.5를 시작할 때 OData URL의 Replace 메서드는 기본적으로 비활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="312f8-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="312f8-104">OData Replace가 비활성화되면(기본값) Replace 기능(일반적이지 않음)을 포함한 모든 사용자 요청이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="312f8-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>|
|<span data-ttu-id="312f8-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="312f8-105">Suggestion</span></span>|<span data-ttu-id="312f8-106">Replace 메서드가 필요한 경우(일반적이지 않음) 구성 설정(<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>)을 통해 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="312f8-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>).</span></span> <span data-ttu-id="312f8-107">그러나 활성화된 Replace 메서드는 보안 취약점을 열 수 있어 신중하게 검토한 후에 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="312f8-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>|
|<span data-ttu-id="312f8-108">범위</span><span class="sxs-lookup"><span data-stu-id="312f8-108">Scope</span></span>|<span data-ttu-id="312f8-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="312f8-109">Edge</span></span>|
|<span data-ttu-id="312f8-110">버전</span><span class="sxs-lookup"><span data-stu-id="312f8-110">Version</span></span>|<span data-ttu-id="312f8-111">4.5</span><span class="sxs-lookup"><span data-stu-id="312f8-111">4.5</span></span>|
|<span data-ttu-id="312f8-112">형식</span><span class="sxs-lookup"><span data-stu-id="312f8-112">Type</span></span>|<span data-ttu-id="312f8-113">런타임</span><span class="sxs-lookup"><span data-stu-id="312f8-113">Runtime</span></span>|
|<span data-ttu-id="312f8-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="312f8-114">Affected APIs</span></span>|<ul><li><xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
