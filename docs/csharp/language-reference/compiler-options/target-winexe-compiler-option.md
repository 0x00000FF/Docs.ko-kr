---
title: -target:winexe(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 3c16bf8aed0d281b2b5a3f9c6ae06f343b1eff7c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307315"
---
# <a name="-targetwinexe-c-compiler-options"></a><span data-ttu-id="30a33-102">-target:winexe(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="30a33-102">-target:winexe (C# Compiler Options)</span></span>
<span data-ttu-id="30a33-103">**-target:winexe** 옵션을 사용하면 컴파일러가 Windows 프로그램 실행 파일(EXE)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="30a33-103">The **-target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30a33-104">구문</span><span class="sxs-lookup"><span data-stu-id="30a33-104">Syntax</span></span>  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="30a33-105">주의</span><span class="sxs-lookup"><span data-stu-id="30a33-105">Remarks</span></span>  
 <span data-ttu-id="30a33-106">실행 파일은 .exe 확장명으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="30a33-106">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="30a33-107">Windows 프로그램은 .NET Framework 라이브러리나 Windows API를 통해 사용자 인터페이스를 제공하는 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="30a33-107">A Windows program is one that provides a user interface from either the .NET Framework library or with the Windows APIs.</span></span>  
  
 <span data-ttu-id="30a33-108">[-target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md)를 사용하여 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="30a33-108">Use [-target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="30a33-109">[-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) 옵션을 사용하여 지정하지 않으면 [Main](../../../csharp/programming-guide/main-and-command-args/index.md) 메서드가 포함된 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30a33-109">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="30a33-110">명령줄에서 지정된 경우, 다음 **-out** 또는 [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) 옵션까지의 모든 파일이 Windows 프로그램을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30a33-110">When specified at the command line, all files until the next **-out** or [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="30a33-111">.exe 파일로 컴파일되는 소스 코드 파일에 **Main** 메서드가 하나만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30a33-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="30a33-112">[-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) 옵션을 사용하면 코드에 **Main** 메서드를 포함하는 클래스가 둘 이상 있는 경우 **Main** 메서드를 포함하는 클래스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30a33-112">The [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="30a33-113">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="30a33-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="30a33-114">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="30a33-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="30a33-115">**애플리케이션** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="30a33-115">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="30a33-116">**출력 형식** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="30a33-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="30a33-117">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30a33-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30a33-118">예제</span><span class="sxs-lookup"><span data-stu-id="30a33-118">Example</span></span>  
 <span data-ttu-id="30a33-119">`in.cs`를 Windows 프로그램으로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="30a33-119">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="30a33-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30a33-120">See also</span></span>

- [<span data-ttu-id="30a33-121">-target(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="30a33-121">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [<span data-ttu-id="30a33-122">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="30a33-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
