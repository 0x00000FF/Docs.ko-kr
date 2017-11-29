---
title: "방법: 형식 라이브러리에 참조 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e5bbc99c3c40b0864a7c1c25cb79a3d7c26e3a86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-references-to-type-libraries"></a><span data-ttu-id="e7e9b-102">방법: 형식 라이브러리에 참조 추가</span><span class="sxs-lookup"><span data-stu-id="e7e9b-102">How to: Add References to Type Libraries</span></span>
<span data-ttu-id="e7e9b-103">Visual Studio에서는 형식 라이브러리에 참조를 추가하면 메타데이터가 포함된 interop 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e9b-103">Visual Studio generates an interop assembly containing metadata when you add a reference to a type library.</span></span> <span data-ttu-id="e7e9b-104">주 interop 어셈블리를 사용할 수 있는 경우 Visual Studio는 새 interop 어셈블리를 생성하기 전에 기존 어셈블리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e9b-104">If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a><span data-ttu-id="e7e9b-105">Visual Studio에서 형식 라이브러리에 대한 참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="e7e9b-105">To add a reference to a type library in Visual Studio</span></span>  
  
1.  <span data-ttu-id="e7e9b-106">Windows Setup.exe 파일이 자동으로 설치를 수행하는 경우가 아니라면 컴퓨터에 COM DLL 또는 EXE 파일을 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="e7e9b-106">Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.</span></span>  
  
2.  <span data-ttu-id="e7e9b-107">**프로젝트**, **참조 추가**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e9b-107">Choose **Project**, **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="e7e9b-108">참조 관리자에서 **COM**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e9b-108">In the Reference Manager, choose **COM**.</span></span>  
  
4.  <span data-ttu-id="e7e9b-109">목록에서 형식 라이브러리를 선택하거나 .tlb 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e9b-109">Select the type library from the list, or browse for the .tlb file.</span></span>  
  
5.  <span data-ttu-id="e7e9b-110">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e9b-110">Choose **OK**.</span></span>  
  
6.  <span data-ttu-id="e7e9b-111">솔루션 탐색기에서 방금 추가한 참조에 대한 바로 가기 메뉴를 열고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e9b-111">In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.</span></span>  
  
7.  <span data-ttu-id="e7e9b-112">**속성** 창에서 **Interop 형식 포함** 속성이 **True**로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e9b-112">In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**.</span></span> <span data-ttu-id="e7e9b-113">이 경우 Visual Studio가 COM 형식에 대한 형식 정보를 실행 파일에 포함하므로 앱과 함께 주 interop 어셈블리를 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e9b-113">This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7e9b-114">메뉴 및 대화 상자 옵션은 사용 중인 Visual Studio 버전에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e9b-114">The menu and dialog box options may vary depending on the version of Visual Studio you're using.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a><span data-ttu-id="e7e9b-115">명령줄 컴파일용으로 형식 라이브러리에 대한 참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="e7e9b-115">To add a reference to a type library for command-line compilation</span></span>  
  
1.  <span data-ttu-id="e7e9b-116">[방법: 형식 라이브러리에서 Interop 어셈블리 생성](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md)의 설명에 따라 interop 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e9b-116">Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
2.  <span data-ttu-id="e7e9b-117">interop 어셈블리 이름을 포함한 [/link(C# 컴파일러 옵션)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) 또는 [/link(Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) 컴파일러 옵션을 사용하여 COM 형식에 대한 형식 정보를 실행 파일에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e9b-117">Use the [/link (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) or [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) compiler option with the interop assembly name to embed type information for COM types in your executables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e9b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7e9b-118">See Also</span></span>  
 [<span data-ttu-id="e7e9b-119">형식 라이브러리를 어셈블리로 가져오기</span><span class="sxs-lookup"><span data-stu-id="e7e9b-119">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)  
 [<span data-ttu-id="e7e9b-120">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="e7e9b-120">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 [<span data-ttu-id="e7e9b-121">연습: Microsoft Office 어셈블리의 형식 정보 포함</span><span class="sxs-lookup"><span data-stu-id="e7e9b-121">Walkthrough: Embedding Type Information from Microsoft Office Assemblies</span></span>](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3)  
 [<span data-ttu-id="e7e9b-122">연습: 관리되는 어셈블리의 형식 포함</span><span class="sxs-lookup"><span data-stu-id="e7e9b-122">Walkthrough: Embedding Types from Managed Assemblies</span></span>](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [<span data-ttu-id="e7e9b-123">/link(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="e7e9b-123">/link (C# Compiler Options)</span></span>](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md)  
 [<span data-ttu-id="e7e9b-124">/link(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7e9b-124">/link (Visual Basic)</span></span>](~/docs/visual-basic/reference/command-line-compiler/link.md)
