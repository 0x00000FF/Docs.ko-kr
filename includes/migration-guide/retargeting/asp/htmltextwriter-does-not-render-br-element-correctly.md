---
ms.openlocfilehash: e600b8249096eecb13f63ea00343a771a8c12b60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804601"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="0713e-101">HtmlTextWriter가 `<br/>` 요소를 올바르게 렌더링하지 않음</span><span class="sxs-lookup"><span data-stu-id="0713e-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0713e-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="0713e-102">Details</span></span>|<span data-ttu-id="0713e-103">.NET Framework 4.6부터 <code>&lt;BR /&gt;</code> 요소로 <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> 및 <xref:System.Web.UI.HtmlTextWriter.RenderEndTag>를 호출하면 (두 개가 아닌) 단 하나의 <code>&lt;BR /&gt;</code>만 올바르게 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="0713e-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a <code>&lt;BR /&gt;</code> element will correctly insert only one <code>&lt;BR /&gt;</code> (instead of two)</span></span>|
|<span data-ttu-id="0713e-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="0713e-104">Suggestion</span></span>|<span data-ttu-id="0713e-105">응용 프로그램이 추가 <code>&lt;BR /&gt;</code> 태그에 종속된 경우 <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)>를 두 번째로 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0713e-105">If an app depended on the extra <code>&lt;BR /&gt;</code> tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="0713e-106">이 동작 변경은 .NET Framework 4.6 이상을 대상으로 하는 응용 프로그램에만 영향을 주므로 다른 옵션은 이전 버전의 .NET Framework를 대상으로 하여 이전 동작을 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0713e-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>|
|<span data-ttu-id="0713e-107">범위</span><span class="sxs-lookup"><span data-stu-id="0713e-107">Scope</span></span>|<span data-ttu-id="0713e-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0713e-108">Edge</span></span>|
|<span data-ttu-id="0713e-109">버전</span><span class="sxs-lookup"><span data-stu-id="0713e-109">Version</span></span>|<span data-ttu-id="0713e-110">4.6</span><span class="sxs-lookup"><span data-stu-id="0713e-110">4.6</span></span>|
|<span data-ttu-id="0713e-111">형식</span><span class="sxs-lookup"><span data-stu-id="0713e-111">Type</span></span>|<span data-ttu-id="0713e-112">대상 변경</span><span class="sxs-lookup"><span data-stu-id="0713e-112">Retargeting</span></span>|
|<span data-ttu-id="0713e-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0713e-113">Affected APIs</span></span>|<ul><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType></li></ul>|
