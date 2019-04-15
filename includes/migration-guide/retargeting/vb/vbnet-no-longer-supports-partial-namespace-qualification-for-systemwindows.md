---
ms.openlocfilehash: 8db115a46df3fcea103e8fa6896542d0116aa256
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236730"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="c2282-101">VB.NET가 System.Windows API에 대한 부분 네임스페이스 한정을 더 이상 지원하지 않음</span><span class="sxs-lookup"><span data-stu-id="c2282-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c2282-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="c2282-102">Details</span></span>|<span data-ttu-id="c2282-103">.NET Framework 4.5.2부터 VB.NET 프로젝트는 부분적으로 정규화된 네임스페이스를 사용하는 System.Windows API를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2282-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="c2282-104">예를 들어 <code>Windows.Forms.DialogResult</code>를 참조하면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="c2282-104">For example, referring to <code>Windows.Forms.DialogResult</code> will fail.</span></span> <span data-ttu-id="c2282-105">대신, 코드는 정규화된 이름(<xref:System.Windows.Forms.DialogResult>)을 참조하거나 특정 네임스페이스를 가져오고 간단히 <xref:System.Windows.Forms.DialogResult?displayProperty=name>를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2282-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span></span>|
|<span data-ttu-id="c2282-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="c2282-106">Suggestion</span></span>|<span data-ttu-id="c2282-107">코드는 간단한 이름(및 관련 네임스페이스를 가져오는) 또는 정규화된 이름을 사용하는 <code>System.Windows</code> API를 참조하도록 업데이트되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2282-107">Code should be updated to refer to <code>System.Windows</code> APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>|
|<span data-ttu-id="c2282-108">범위</span><span class="sxs-lookup"><span data-stu-id="c2282-108">Scope</span></span>|<span data-ttu-id="c2282-109">부</span><span class="sxs-lookup"><span data-stu-id="c2282-109">Minor</span></span>|
|<span data-ttu-id="c2282-110">버전</span><span class="sxs-lookup"><span data-stu-id="c2282-110">Version</span></span>|<span data-ttu-id="c2282-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="c2282-111">4.5.2</span></span>|
|<span data-ttu-id="c2282-112">형식</span><span class="sxs-lookup"><span data-stu-id="c2282-112">Type</span></span>|<span data-ttu-id="c2282-113">대상 변경</span><span class="sxs-lookup"><span data-stu-id="c2282-113">Retargeting</span></span>|
