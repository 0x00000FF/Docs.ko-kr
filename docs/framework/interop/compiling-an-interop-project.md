---
title: "Interop 프로젝트 컴파일"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1668961e383532de832b538e57eedb681a26ed52
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="compiling-an-interop-project"></a><span data-ttu-id="6ecd5-102">Interop 프로젝트 컴파일</span><span class="sxs-lookup"><span data-stu-id="6ecd5-102">Compiling an Interop Project</span></span>
<span data-ttu-id="6ecd5-103">가져온 COM 형식이 포함된 하나 이상의 어셈블리를 참조하는 COM interop 프로젝트는 다른 관리되는 프로젝트와 마찬가지로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ecd5-103">COM interop projects that reference one or more assemblies containing imported COM types are compiled like any other managed project.</span></span> <span data-ttu-id="6ecd5-104">Visual Studio 등의 개발 환경에서 interop 어셈블리를 참조하거나, 명령줄 컴파일러를 사용할 때 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecd5-104">You can reference interop assemblies in a development environment such as Visual Studio, or you can reference them when you use a command-line compiler.</span></span> <span data-ttu-id="6ecd5-105">두 경우 모두, 제대로 컴파일하려면 interop 어셈블리가 다른 프로젝트 파일과 동일한 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ecd5-105">In either case, to compile properly, the interop assembly must be in the same directory as the other project files.</span></span>  
  
 <span data-ttu-id="6ecd5-106">Interop 어셈블리를 참조하는 방법에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecd5-106">There are two ways to reference interop assemblies:</span></span>  
  
-   <span data-ttu-id="6ecd5-107">포함된 interop 형식: [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 및 [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)]부터 interop 어셈블리의 형식 정보를 실행 파일에 포함하도록 컴파일러에 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecd5-107">Embedded interop types: Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], you can instruct the compiler to embed type information from an interop assembly into your executable.</span></span> <span data-ttu-id="6ecd5-108">이것이 권장되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6ecd5-108">This is the recommended technique.</span></span>  
  
-   <span data-ttu-id="6ecd5-109">Interop 어셈블리 배포: interop 어셈블리에 대한 표준 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecd5-109">Deploying interop assemblies: You can create a standard reference to an interop assembly.</span></span> <span data-ttu-id="6ecd5-110">이 경우 interop 어셈블리를 응용 프로그램에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ecd5-110">In this case, the interop assembly must be deployed with your application.</span></span>  
  
 <span data-ttu-id="6ecd5-111">이러한 두 방법 간의 차이점은 [관리 코드에서 COM 형식 사용](http://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ecd5-111">The differences between these two techniques are discussed in greater detail in [Using COM Types in Managed Code](http://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).</span></span>  
  
 <span data-ttu-id="6ecd5-112">Visual Studio를 사용하여 interop 형식을 포함하는 방법은 [연습: Microsoft Office 어셈블리의 형식 정보 포함](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3) 및 [연습: 관리되는 어셈블리의 형식 포함](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ecd5-112">Embedding interop types with Visual Studio is demonstrated in [Walkthrough: Embedding Type Information from Microsoft Office Assemblies](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3) and [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>  
  
 <span data-ttu-id="6ecd5-113">명령줄 컴파일러를 사용하여 interop 어셈블리를 참조하고 실행 파일에 형식 정보를 포함하려면 [/link(C# 컴파일러 옵션)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) 또는 [/link(Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) 컴파일러 스위치를 사용하고 interop 어셈블리의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ecd5-113">To reference an interop assembly with a command-line compiler and embed type information in your executables, use the [/link (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) or the [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) compiler switch and specify the name of the interop assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ecd5-114">Visual C++ 응용 프로그램은 형식 정보를 포함할 수 없지만 포함하는 응용 프로그램이나 추가 기능과 상호 운용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecd5-114">Visual C++ applications cannot embed type information, but they can interoperate with applications or add-ins that do.</span></span>  
  
 <span data-ttu-id="6ecd5-115">배포될 때 주 interop 어셈블리를 포함하는 응용 프로그램을 컴파일하려면 **/reference** 컴파일러 스위치를 사용하고 interop 어셈블리의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ecd5-115">To compile an application that includes a primary interop assembly when it is deployed, use the **/reference** compiler switch and specify the name of the interop assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ecd5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ecd5-116">See Also</span></span>  
 [<span data-ttu-id="6ecd5-117">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="6ecd5-117">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 [<span data-ttu-id="6ecd5-118">언어 독립성 및 언어 독립적 구성 요소</span><span class="sxs-lookup"><span data-stu-id="6ecd5-118">Language Independence and Language-Independent Components</span></span>](../../../docs/standard/language-independence-and-language-independent-components.md)  
 [<span data-ttu-id="6ecd5-119">관리 코드에서 COM 형식을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="6ecd5-119">Using COM Types in Managed Code</span></span>](http://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)  
 [<span data-ttu-id="6ecd5-120">연습: Microsoft Office 어셈블리의 형식 정보 포함</span><span class="sxs-lookup"><span data-stu-id="6ecd5-120">Walkthrough: Embedding Type Information from Microsoft Office Assemblies</span></span>](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3)  
 [<span data-ttu-id="6ecd5-121">연습: 관리되는 어셈블리의 형식 포함</span><span class="sxs-lookup"><span data-stu-id="6ecd5-121">Walkthrough: Embedding Types from Managed Assemblies</span></span>](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [<span data-ttu-id="6ecd5-122">형식 라이브러리를 어셈블리로 가져오기</span><span class="sxs-lookup"><span data-stu-id="6ecd5-122">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)
