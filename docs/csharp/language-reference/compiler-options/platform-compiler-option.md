---
title: "-platform(C# 컴파일러 옵션)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /platform
dev_langs:
- CSharp
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
caps.latest.revision: 46
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 44d4cadbc45eb141ecb7a83345d2a7a834ce5299
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="platform-c-compiler-options"></a><span data-ttu-id="9fcd6-102">/platform(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="9fcd6-102">/platform (C# Compiler Options)</span></span>
<span data-ttu-id="9fcd6-103">어셈블리를 실행할 수 있는 CLR(공용 언어 런타임) 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-103">Specifies which version of the common language runtime (CLR) can run the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fcd6-104">구문</span><span class="sxs-lookup"><span data-stu-id="9fcd6-104">Syntax</span></span>  
  
```console  
/platform:string  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9fcd6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9fcd6-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="9fcd6-106">anycpu(기본값), anycpu32bitpreferred, ARM, x64, x86 또는 Itanium입니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-106">anycpu (default), anycpu32bitpreferred, ARM, x64, x86, or Itanium.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fcd6-107">설명</span><span class="sxs-lookup"><span data-stu-id="9fcd6-107">Remarks</span></span>  
  
-   <span data-ttu-id="9fcd6-108">**anycpu**(기본값)는 어셈블리를 모든 플랫폼에서 실행되도록 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-108">**anycpu** (default) compiles your assembly to run on any platform.</span></span> <span data-ttu-id="9fcd6-109">응용 프로그램은 가능할 때마다 64비트로 실행되고 해당 모드를 사용할 수 있을 때만 32비트로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-109">Your application runs as a 64-bit process whenever possible and falls back to 32-bit when only that mode is available.</span></span>  
  
-   <span data-ttu-id="9fcd6-110">**anycpu32bitpreferred**는 어셈블리를 모든 플랫폼에서 실행되도록 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-110">**anycpu32bitpreferred** compiles your assembly to run on any platform.</span></span> <span data-ttu-id="9fcd6-111">응용 프로그램은 64비트와 32비트 응용 프로그램을 모두 지원하는 시스템에서 32비트로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-111">Your application runs in 32-bit mode on systems that support both 64-bit and 32-bit applications.</span></span> <span data-ttu-id="9fcd6-112">.NET Framework 4.5를 대상으로 하는 프로젝트에 대해서만 이 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-112">You can specify this option only for projects that target the .NET Framework 4.5.</span></span>  
  
-   <span data-ttu-id="9fcd6-113">**ARM**은 ARM(고급 RISC 컴퓨터) 프로세서가 있는 컴퓨터에서 실행할 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-113">**ARM** compiles your assembly to run on a computer that has an Advanced RISC Machine (ARM) processor.</span></span>  
  
-   <span data-ttu-id="9fcd6-114">**x64**를 지정하면 AMD64 또는 EM64T 명령 집합을 지원하는 컴퓨터에서 64비트 공용 언어 런타임에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-114">**x64** compiles your assembly to be run by the 64-bit common language runtime on a computer that supports the AMD64 or EM64T instruction set.</span></span>  
  
-   <span data-ttu-id="9fcd6-115">**x86**은 32비트, x86 호환 공용 언어 런타임에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-115">**x86** compiles your assembly to be run by the 32-bit, x86-compatible common language runtime.</span></span>  
  
-   <span data-ttu-id="9fcd6-116">**Itanium**은 Itanium 프로세서 탑재 컴퓨터에서 64비트 공용 언어 런타임에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-116">**Itanium** compiles your assembly to be run by the 64-bit common language runtime on a computer with an Itanium processor.</span></span>  
  
 <span data-ttu-id="9fcd6-117">64비트 Windows 운영 체제:</span><span class="sxs-lookup"><span data-stu-id="9fcd6-117">On a 64-bit Windows operating system:</span></span>  
  
-   <span data-ttu-id="9fcd6-118">**/platform:x86**으로 컴파일된 어셈블리는 WOW64에서 실행되는 32비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-118">Assemblies compiled with **/platform:x86** execute on the 32-bit CLR running under WOW64.</span></span>  
  
-   <span data-ttu-id="9fcd6-119">**/platform:anycpu**로 컴파일된 DLL은 이 DLL이 로드된 프로세스와 동일한 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-119">A DLL compiled with the **/platform:anycpu** executes on the same CLR as the process into which it is loaded.</span></span>  
  
-   <span data-ttu-id="9fcd6-120">**/platform:anycpu**로 컴파일된 실행 파일은 64비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-120">Executables that are compiled with the **/platform:anycpu** execute on the 64-bit CLR.</span></span>  
  
-   <span data-ttu-id="9fcd6-121">**/platform:anycpu32bitpreferred**로 컴파일된 실행 파일은 32비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-121">Executables compiled with **/platform:anycpu32bitpreferred** execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="9fcd6-122">**anycpu32bitpreferred** 설정은 실행 파일(.EXE)에 대해서만 유효하고 .NET Framework 4.5를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-122">The **anycpu32bitpreferred** setting is valid only for executable (.EXE) files, and it requires the .NET Framework 4.5.</span></span>  
  
 <span data-ttu-id="9fcd6-123">Windows 64비트 운영 체제에서 실행할 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [64비트 응용 프로그램](https://msdn.microsoft.com/library/ms241064)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-123">For more information about developing an application to run on a Windows 64-bit operating system, see [64-bit Applications](https://msdn.microsoft.com/library/ms241064).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="9fcd6-124">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9fcd6-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="9fcd6-125">프로젝트의 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-125">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="9fcd6-126">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-126">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="9fcd6-127">.NET Framework 4.5를 대상으로 하는 프로젝트에 대해 **플랫폼 대상** 속성을 수정하고 **32비트 선호** 확인란을 선택하거나 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-127">Modify the **Platform target** property and, for projects that target the .NET Framework 4.5, select or clear the **Prefer 32-bit** check box.</span></span>  
  
 <span data-ttu-id="9fcd6-128">**/platform**은 Visual C# Express의 개발 환경에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-128">**Note /platform** is not available in the development environment in Visual C# Express.</span></span>  
  
 <span data-ttu-id="9fcd6-129">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-129">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fcd6-130">예제</span><span class="sxs-lookup"><span data-stu-id="9fcd6-130">Example</span></span>  
 <span data-ttu-id="9fcd6-131">다음 예제에서는 **/platform** 옵션을 사용하여 응용 프로그램이 64비트 Windows 운영 체제의 64비트 CLR에서만 실행되도록 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-131">The following example shows how to use the **/platform** option to specify that the application should be run by the 64-bit CLR on a 64-bit Windows operating system.</span></span>  
  
```console  
csc /platform:anycpu filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="9fcd6-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9fcd6-132">See Also</span></span>  
 <span data-ttu-id="9fcd6-133">[C# 컴파일러 옵션](index.md) </span><span class="sxs-lookup"><span data-stu-id="9fcd6-133">[C# Compiler Options](index.md) </span></span>  
 [<span data-ttu-id="9fcd6-134">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="9fcd6-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

