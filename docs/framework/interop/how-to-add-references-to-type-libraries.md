---
title: '방법: 형식 라이브러리에 참조 추가'
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71c2a6b183890aa9625dcffbef59d14c27ebe754
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219402"
---
# <a name="how-to-add-references-to-type-libraries"></a><span data-ttu-id="e0916-102">방법: 형식 라이브러리에 참조 추가</span><span class="sxs-lookup"><span data-stu-id="e0916-102">How to: Add References to Type Libraries</span></span>
<span data-ttu-id="e0916-103">Visual Studio에서는 형식 라이브러리에 참조를 추가하면 메타데이터가 포함된 interop 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e0916-103">Visual Studio generates an interop assembly containing metadata when you add a reference to a type library.</span></span> <span data-ttu-id="e0916-104">주 interop 어셈블리를 사용할 수 있는 경우 Visual Studio는 새 interop 어셈블리를 생성하기 전에 기존 어셈블리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0916-104">If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a><span data-ttu-id="e0916-105">Visual Studio에서 형식 라이브러리에 대한 참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="e0916-105">To add a reference to a type library in Visual Studio</span></span>  
  
1.  <span data-ttu-id="e0916-106">Windows Setup.exe 파일이 자동으로 설치를 수행하는 경우가 아니라면 컴퓨터에 COM DLL 또는 EXE 파일을 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="e0916-106">Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.</span></span>  
  
2.  <span data-ttu-id="e0916-107">**프로젝트**, **참조 추가**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0916-107">Choose **Project**, **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="e0916-108">참조 관리자에서 **COM**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0916-108">In the Reference Manager, choose **COM**.</span></span>  
  
4.  <span data-ttu-id="e0916-109">목록에서 형식 라이브러리를 선택하거나 .tlb 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e0916-109">Select the type library from the list, or browse for the .tlb file.</span></span>  
  
5.  <span data-ttu-id="e0916-110">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0916-110">Choose **OK**.</span></span>  
  
6.  <span data-ttu-id="e0916-111">솔루션 탐색기에서 방금 추가한 참조에 대한 바로 가기 메뉴를 열고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0916-111">In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.</span></span>  
  
7.  <span data-ttu-id="e0916-112">**속성** 창에서 **Interop 형식 포함** 속성이 **True**로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e0916-112">In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**.</span></span> <span data-ttu-id="e0916-113">이 경우 Visual Studio가 COM 형식에 대한 형식 정보를 실행 파일에 포함하므로 앱과 함께 주 interop 어셈블리를 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0916-113">This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0916-114">메뉴 및 대화 상자 옵션은 사용 중인 Visual Studio 버전에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0916-114">The menu and dialog box options may vary depending on the version of Visual Studio you're using.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a><span data-ttu-id="e0916-115">명령줄 컴파일용으로 형식 라이브러리에 대한 참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="e0916-115">To add a reference to a type library for command-line compilation</span></span>  
  
1.  <span data-ttu-id="e0916-116">[방법: 형식 라이브러리에서 Interop 어셈블리 생성](how-to-generate-interop-assemblies-from-type-libraries.md)의 설명에 따라 interop 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e0916-116">Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
2.  <span data-ttu-id="e0916-117">interop 어셈블리 이름을 포함한 [/link(C# 컴파일러 옵션)](../../csharp/language-reference/compiler-options/link-compiler-option.md) 또는 [/link(Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) 컴파일러 옵션을 사용하여 COM 형식에 대한 형식 정보를 실행 파일에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e0916-117">Use the [/link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler option with the interop assembly name to embed type information for COM types in your executables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0916-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0916-118">See also</span></span>
- [<span data-ttu-id="e0916-119">형식 라이브러리를 어셈블리로 가져오기</span><span class="sxs-lookup"><span data-stu-id="e0916-119">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="e0916-120">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="e0916-120">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="e0916-121">연습: Visual Studio에서 Microsoft Office 어셈블리의 형식 정보 포함(C#)</span><span class="sxs-lookup"><span data-stu-id="e0916-121">Walkthrough: Embedding Type Information from Microsoft Office Assemblies in Visual Studio (C#)</span></span>](../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-type-information-from-microsoft-office-assemblies.md)
- [<span data-ttu-id="e0916-122">연습: Visual Studio에서 Microsoft Office 어셈블리의 형식 정보 포함(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0916-122">Walkthrough: Embedding Type Information from Microsoft Office Assemblies in Visual Studio (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-vs.md)
- [<span data-ttu-id="e0916-123">연습: Visual Studio에서 관리형 어셈블리의 형식 포함(C#)</span><span class="sxs-lookup"><span data-stu-id="e0916-123">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>](/docs/csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md) 
- [<span data-ttu-id="e0916-124">연습: Visual Studio에서 관리형 어셈블리의 형식 포함(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0916-124">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>](/docs/visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)
- [<span data-ttu-id="e0916-125">/link(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="e0916-125">/link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="e0916-126">/link(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0916-126">/link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
