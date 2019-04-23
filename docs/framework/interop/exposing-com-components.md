---
title: .NET Framework에 COM 구성 요소 노출
ms.date: 03/30/2017
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b7aa028afeaf4230ee079f0d4071a5cd6a21c65
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59320914"
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="8cdf2-102">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="8cdf2-102">Exposing COM Components to the .NET Framework</span></span>
<span data-ttu-id="8cdf2-103">이 섹션에서는 프로세스를 기존 COM 구성 요소를 관리 코드에 노출하는 데 필요한 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf2-103">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="8cdf2-104">.NET Framework와 강력하게 통합되는 COM 서버를 작성하는 방법에 대한 자세한 내용은 [상호 운용을 위한 디자인 고려 사항](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8cdf2-104">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span></span>
  
 <span data-ttu-id="8cdf2-105">기존 COM 구성요소는 중간 계층 비즈니스 애플리케이션 또는 격리된 기능으로서 관리 코드의 중요한 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf2-105">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="8cdf2-106">이상적인 구성 요소는 주 interop 어셈블리를 포함하고 COM을 통해 적용되는 프로그래밍 표준을 엄격하게 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf2-106">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="8cdf2-107">.NET Framework에 COM 구성 요소를 노출하려면</span><span class="sxs-lookup"><span data-stu-id="8cdf2-107">To expose COM components to the .NET Framework</span></span>  
  
1. <span data-ttu-id="8cdf2-108">[형식 라이브러리를 어셈블리로 가져옵니다](importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="8cdf2-108">[Import a type library as an assembly](importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="8cdf2-109">공용 언어 런타임에는 COM 형식을 비롯한 모든 형식에 대한 메타데이터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf2-109">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="8cdf2-110">메타데이터로 가져온 COM 형식이 포함된 어셈블리를 가져오는 다양한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf2-110">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2. <span data-ttu-id="8cdf2-111">[관리 코드에서 COM 형식을 사용합니다](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8cdf2-111">[Use COM types in managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>  
  
     <span data-ttu-id="8cdf2-112">관리되는 형식의 경우와 같은 방식으로 COM 형식을 검사하고, 인스턴스를 활성화하고, COM 개체에서 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf2-112">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3. <span data-ttu-id="8cdf2-113">[Interop 프로젝트를 컴파일합니다](compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="8cdf2-113">[Compile an interop project](compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="8cdf2-114">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에서는 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# 및 C++를 포함하여 CLS(공용 언어 사양)와 호환되는 여러 가지 언어용 컴파일러를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf2-114">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] provides compilers for several languages compliant with the Common Language Specification (CLS), including [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#, and C++.</span></span>  
  
4. <span data-ttu-id="8cdf2-115">[Interop 애플리케이션을 배포합니다](deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="8cdf2-115">[Deploy an interop application](deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="8cdf2-116">Interop 애플리케이션은 전역 어셈블리 캐시에 [강력한 이름의](../app-domains/strong-named-assemblies.md) 서명된 어셈블리로서 가장 잘 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf2-116">Interop applications are best deployed as [strong-named](../app-domains/strong-named-assemblies.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cdf2-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8cdf2-117">See also</span></span>

- [<span data-ttu-id="8cdf2-118">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="8cdf2-118">Interoperating with Unmanaged Code</span></span>](index.md)
- <span data-ttu-id="8cdf2-119">[상호 운용을 위한 디자인 고려 사항](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8cdf2-119">[Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span></span>
- [<span data-ttu-id="8cdf2-120">COM Interop 샘플: .NET 클라이언트 및 COM 서버</span><span class="sxs-lookup"><span data-stu-id="8cdf2-120">COM Interop Sample: .NET Client and COM Server</span></span>](com-interop-sample-net-client-and-com-server.md)
- [<span data-ttu-id="8cdf2-121">언어 독립성 및 언어 독립적 구성 요소</span><span class="sxs-lookup"><span data-stu-id="8cdf2-121">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="8cdf2-122">Gacutil.exe(전역 어셈블리 캐시 도구)</span><span class="sxs-lookup"><span data-stu-id="8cdf2-122">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
