---
ms.openlocfilehash: 4e81087431091dfa4d5432d5ea5e2b665be2b130
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234837"
---
### <a name="listtforeach-can-throw-exception-when-modifying-list-item"></a><span data-ttu-id="7e55e-101">List\<T>.ForEach는 목록 항목을 수정할 때 예외를 throw할 수 있음</span><span class="sxs-lookup"><span data-stu-id="7e55e-101">List\<T>.ForEach can throw exception when modifying list item</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7e55e-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="7e55e-102">Details</span></span>|<span data-ttu-id="7e55e-103">.NET Framework 4.5부터는 호출 컬렉션의 요소가 수정되면 <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> 열거자가 <xref:System.InvalidOperationException?displayProperty=name> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="7e55e-103">Beginning in .NET Framework 4.5, a <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> enumerator will throw an <xref:System.InvalidOperationException?displayProperty=name> exception if an element in the calling collection is modified.</span></span> <span data-ttu-id="7e55e-104">이전에는 예외를 throw하지 않고 경합 상태가 발생할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e55e-104">Previously, this would not throw an exception but could lead to race conditions.</span></span>|
|<span data-ttu-id="7e55e-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="7e55e-105">Suggestion</span></span>|<span data-ttu-id="7e55e-106">이상적으로, 안전한 작업을 위해 요소를 열거하는 동안 목록을 수정하지 않도록 코드를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e55e-106">Ideally, code should be fixed to not modify lists while enumerating their elements because that is never a safe operation.</span></span> <span data-ttu-id="7e55e-107">그러나 이전 동작으로 되돌리려면 응용 프로그램이 .NET Framework 4.0을 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e55e-107">To revert to the previous behavior, though, an app may target .NET Framework 4.0.</span></span>|
|<span data-ttu-id="7e55e-108">범위</span><span class="sxs-lookup"><span data-stu-id="7e55e-108">Scope</span></span>|<span data-ttu-id="7e55e-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7e55e-109">Edge</span></span>|
|<span data-ttu-id="7e55e-110">버전</span><span class="sxs-lookup"><span data-stu-id="7e55e-110">Version</span></span>|<span data-ttu-id="7e55e-111">4.5</span><span class="sxs-lookup"><span data-stu-id="7e55e-111">4.5</span></span>|
|<span data-ttu-id="7e55e-112">형식</span><span class="sxs-lookup"><span data-stu-id="7e55e-112">Type</span></span>|<span data-ttu-id="7e55e-113">대상 변경</span><span class="sxs-lookup"><span data-stu-id="7e55e-113">Retargeting</span></span>|
|<span data-ttu-id="7e55e-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="7e55e-114">Affected APIs</span></span>|<ul><li><xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType></li></ul>|
