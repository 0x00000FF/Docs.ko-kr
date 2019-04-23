---
title: -target:exe(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /exe
helpviewer_keywords:
- target compiler options [C#], /target:exe
- /target compiler options [C#], /target:exe
- -target compiler options [C#], /target:exe
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
ms.openlocfilehash: 7d34a25fd614a209761714e1f4eff3042ca240c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331314"
---
# <a name="-targetexe-c-compiler-options"></a><span data-ttu-id="636a2-102">-target:exe(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="636a2-102">-target:exe (C# Compiler Options)</span></span>
<span data-ttu-id="636a2-103">**-target:exe** 옵션을 사용하면 컴파일러가 콘솔 애플리케이션 실행 파일(EXE)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="636a2-103">The **-target:exe** option causes the compiler to create an executable (EXE), console application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="636a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="636a2-104">Syntax</span></span>  
  
```console  
-target:exe  
```  
  
## <a name="remarks"></a><span data-ttu-id="636a2-105">주의</span><span class="sxs-lookup"><span data-stu-id="636a2-105">Remarks</span></span>  
 <span data-ttu-id="636a2-106">기본적으로 **-target:exe** 옵션이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="636a2-106">The **-target:exe** option is in effect by default.</span></span> <span data-ttu-id="636a2-107">실행 파일은 .exe 확장명으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="636a2-107">The executable file will be created with the .exe extension.</span></span>  
  
 <span data-ttu-id="636a2-108">[-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)를 사용하여 Windows 프로그램 실행 파일을 만드세요.</span><span class="sxs-lookup"><span data-stu-id="636a2-108">Use [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) to create a Windows program executable.</span></span>  
  
 <span data-ttu-id="636a2-109">[-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) 옵션을 사용하여 지정하지 않으면 출력 파일 이름은 [Main](../../../csharp/programming-guide/main-and-command-args/index.md) 메서드를 포함하는 입력 파일의 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="636a2-109">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="636a2-110">명령줄에서 지정된 경우, 다음 **-out** 또는 **-target:module** 옵션까지의 모든 파일이 .exe 파일을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="636a2-110">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .exe file</span></span>  
  
 <span data-ttu-id="636a2-111">.exe 파일로 컴파일되는 소스 코드 파일에 **Main** 메서드가 하나만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="636a2-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="636a2-112">[-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) 컴파일러 옵션을 사용하면 코드에 **Main** 메서드를 포함하는 클래스가 둘 이상 있는 경우 **Main** 메서드를 포함하는 클래스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="636a2-112">The [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) compiler option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="636a2-113">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="636a2-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="636a2-114">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="636a2-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="636a2-115">**애플리케이션** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="636a2-115">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="636a2-116">**출력 형식** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="636a2-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="636a2-117">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="636a2-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="636a2-118">예제</span><span class="sxs-lookup"><span data-stu-id="636a2-118">Example</span></span>  
 <span data-ttu-id="636a2-119">다음 명령줄은 각각 `in.cs`를 컴파일하고 `in.exe`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="636a2-119">Each of the following command lines will compile `in.cs`, creating `in.exe`:</span></span>  
  
```console  
csc -target:exe in.cs  
csc in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="636a2-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="636a2-120">See also</span></span>

- [<span data-ttu-id="636a2-121">-target(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="636a2-121">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [<span data-ttu-id="636a2-122">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="636a2-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
