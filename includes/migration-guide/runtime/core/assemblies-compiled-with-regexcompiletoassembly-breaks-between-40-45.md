---
ms.openlocfilehash: 69b25db88c7580787bbb47fb0902b6bb072f8dde
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235737"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a><span data-ttu-id="32db8-101">Regex.CompileToAssembly로 컴파일된 어셈블리가 4.0과 4.5 사이에서 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="32db8-101">Assemblies compiled with Regex.CompileToAssembly breaks between 4.0 and 4.5</span></span>

|   |   |
|---|---|
|<span data-ttu-id="32db8-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="32db8-102">Details</span></span>|<span data-ttu-id="32db8-103">컴파일된 정규식의 어셈블리가 .NET Framework 4.5로 빌드되었지만 .NET Framework 4를 대상으로 하는 경우, .NET Framework 4가 설치된 시스템에서 해당 어셈블리의 정규식 중 하나를 사용하려고 하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="32db8-103">If an assembly of compiled regular expressions is built with the .NET Framework 4.5 but targets the .NET Framework 4, attempting to use one of the regular expressions in that assembly on a system with .NET Framework 4 installed throws an exception.</span></span>|
|<span data-ttu-id="32db8-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="32db8-104">Suggestion</span></span>|<span data-ttu-id="32db8-105">이 문제를 해결하기 위해서는 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="32db8-105">To work around this problem, you can do either of the following:</span></span><ul><li><span data-ttu-id="32db8-106">.NET Framework 4를 사용하여 정규식이 포함된 어셈블리를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="32db8-106">Build the assembly that contains the regular expressions with the .NET Framework 4.</span></span></li><li><span data-ttu-id="32db8-107">해석된 정규식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="32db8-107">Use an interpreted regular expression.</span></span></li></ul>|
|<span data-ttu-id="32db8-108">범위</span><span class="sxs-lookup"><span data-stu-id="32db8-108">Scope</span></span>|<span data-ttu-id="32db8-109">부</span><span class="sxs-lookup"><span data-stu-id="32db8-109">Minor</span></span>|
|<span data-ttu-id="32db8-110">버전</span><span class="sxs-lookup"><span data-stu-id="32db8-110">Version</span></span>|<span data-ttu-id="32db8-111">4.5</span><span class="sxs-lookup"><span data-stu-id="32db8-111">4.5</span></span>|
|<span data-ttu-id="32db8-112">형식</span><span class="sxs-lookup"><span data-stu-id="32db8-112">Type</span></span>|<span data-ttu-id="32db8-113">런타임</span><span class="sxs-lookup"><span data-stu-id="32db8-113">Runtime</span></span>|
|<span data-ttu-id="32db8-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="32db8-114">Affected APIs</span></span>|<ul><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType></li></ul>|
