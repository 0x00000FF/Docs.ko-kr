---
ms.openlocfilehash: c9efbefc2bce9e21f328680795e72b62bfcd5cbd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235498"
---
### <a name="enumerableemptytresult-always-returns-cached-instance"></a><span data-ttu-id="49f59-101">Enumerable.Empty\<TResult>가 항상 캐시된 인스턴스를 반환</span><span class="sxs-lookup"><span data-stu-id="49f59-101">Enumerable.Empty\<TResult> always returns cached instance</span></span>

|   |   |
|---|---|
|<span data-ttu-id="49f59-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="49f59-102">Details</span></span>|<span data-ttu-id="49f59-103">.NET Framework 4.5부터 <xref:System.Linq.Enumerable.Empty%60%601>는 항상 캐시된 내부 인스턴스 <xref:System.Collections.Generic.IEnumerable%601>를 반환합니다. 이전에는 <xref:System.Linq.Enumerable.Empty%60%601>이 API를 호출할 때 빈 <xref:System.Collections.Generic.IEnumerable%601>을 캐시했으며, 이 말은 즉 <xref:System.Linq.Enumerable.Empty%60%601>가 신속하게 동시에 호출된 일부 조건에서 다른 형식의 인스턴스가 다른 호출에 대해 API로 반환되었다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="49f59-103">Beginning in .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> always returns a cached internal instance <xref:System.Collections.Generic.IEnumerable%601>.Previously, <xref:System.Linq.Enumerable.Empty%60%601> would cache an empty <xref:System.Collections.Generic.IEnumerable%601> at the time the API was called, meaning that in some conditions in which <xref:System.Linq.Enumerable.Empty%60%601> was called rapidly and concurrently, different instances of the type could be returned for different calls to the API.</span></span>|
|<span data-ttu-id="49f59-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="49f59-104">Suggestion</span></span>|<span data-ttu-id="49f59-105">이전 동작이 명확하지 않았으므로 코드가 종속될 가능성이 작습니다.</span><span class="sxs-lookup"><span data-stu-id="49f59-105">Because the previous behavior was non-deterministic, code is unlikely to depend on it.</span></span> <span data-ttu-id="49f59-106">그러나 빈 열거형은 비교되고 때로는 같지 않은 것으로 예상되는 드문 경우에는, <xref:System.Linq.Enumerable.Empty%60%601>를 사용하는 대신 명시적인 빈 배열을 만들어야 합니다(<code>new T[0]</code>).</span><span class="sxs-lookup"><span data-stu-id="49f59-106">However, in the unlikely case that empty enumerables are being compared and expected to sometimes be unequal, explicit empty arrays should be created (<code>new T[0]</code>) instead of using <xref:System.Linq.Enumerable.Empty%60%601>.</span></span>|
|<span data-ttu-id="49f59-107">범위</span><span class="sxs-lookup"><span data-stu-id="49f59-107">Scope</span></span>|<span data-ttu-id="49f59-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="49f59-108">Edge</span></span>|
|<span data-ttu-id="49f59-109">버전</span><span class="sxs-lookup"><span data-stu-id="49f59-109">Version</span></span>|<span data-ttu-id="49f59-110">4.5</span><span class="sxs-lookup"><span data-stu-id="49f59-110">4.5</span></span>|
|<span data-ttu-id="49f59-111">형식</span><span class="sxs-lookup"><span data-stu-id="49f59-111">Type</span></span>|<span data-ttu-id="49f59-112">런타임</span><span class="sxs-lookup"><span data-stu-id="49f59-112">Runtime</span></span>|
|<span data-ttu-id="49f59-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="49f59-113">Affected APIs</span></span>|<ul><li><xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType></li></ul>|
