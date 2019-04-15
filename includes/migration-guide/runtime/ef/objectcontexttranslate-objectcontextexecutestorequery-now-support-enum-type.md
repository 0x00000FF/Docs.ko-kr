---
ms.openlocfilehash: 1d2d6133683360b97569e49402e7c8c4d182b65d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235503"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a><span data-ttu-id="df5b0-101">이제 ObjectContext.Translate와 ObjectContext.ExecuteStoreQuery가 열거형 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="df5b0-101">ObjectContext.Translate and ObjectContext.ExecuteStoreQuery now support enum type</span></span>

|   |   |
|---|---|
|<span data-ttu-id="df5b0-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="df5b0-102">Details</span></span>|<span data-ttu-id="df5b0-103">.NET Framework 4.0에서는 <code>ObjectContext.Translate</code> 및 <code>ObjectContext.ExecuteStoreQuery</code> 메서드의 제네릭 매개 변수 <code>T</code>가 열거형일 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="df5b0-103">In .NET Framework 4.0, the generic parameter <code>T</code> of <code>ObjectContext.Translate</code> and <code>ObjectContext.ExecuteStoreQuery</code> methods could not be an enum.</span></span> <span data-ttu-id="df5b0-104">이제 이 시나리오가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="df5b0-104">That scenario is now supported.</span></span>|
|<span data-ttu-id="df5b0-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="df5b0-105">Suggestion</span></span>|<span data-ttu-id="df5b0-106">.NET Framework 4.0의 열거형 형식에서 좌표 이동 또는 ExecuteStoreQuery가 호출되면 ‘0’이 반환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="df5b0-106">If Translate or ExecuteStoreQuery was called on an enum type in .NET Framework 4.0, '0' was returned.</span></span> <span data-ttu-id="df5b0-107">해당 동작이 필요한 경우 호출은 상수 0(또는 열거형 해당 항목)으로 대체되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df5b0-107">If that behavior was desirable, the calls should be replaced with a constant 0 (or the enum equivalent of it).</span></span>|
|<span data-ttu-id="df5b0-108">범위</span><span class="sxs-lookup"><span data-stu-id="df5b0-108">Scope</span></span>|<span data-ttu-id="df5b0-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="df5b0-109">Edge</span></span>|
|<span data-ttu-id="df5b0-110">버전</span><span class="sxs-lookup"><span data-stu-id="df5b0-110">Version</span></span>|<span data-ttu-id="df5b0-111">4.5</span><span class="sxs-lookup"><span data-stu-id="df5b0-111">4.5</span></span>|
|<span data-ttu-id="df5b0-112">형식</span><span class="sxs-lookup"><span data-stu-id="df5b0-112">Type</span></span>|<span data-ttu-id="df5b0-113">런타임</span><span class="sxs-lookup"><span data-stu-id="df5b0-113">Runtime</span></span>|
|<span data-ttu-id="df5b0-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="df5b0-114">Affected APIs</span></span>|<ul><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|
