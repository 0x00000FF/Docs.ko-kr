---
title: -target:library(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: 0bdf8d95004ca11e3d6b9b27568f7310a802a28b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542446"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="62db9-102">-target:library(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="62db9-102">-target:library (C# Compiler Options)</span></span>
<span data-ttu-id="62db9-103">**-target:library** 옵션을 사용하면 컴파일러가 실행 파일(EXE) 대신 DLL(동적 연결 라이브러리)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="62db9-103">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62db9-104">구문</span><span class="sxs-lookup"><span data-stu-id="62db9-104">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="62db9-105">주의</span><span class="sxs-lookup"><span data-stu-id="62db9-105">Remarks</span></span>  
 <span data-ttu-id="62db9-106">DLL은 .dll 확장명으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="62db9-106">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="62db9-107">[-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) 옵션을 사용하여 달리 지정되지 않은 경우 첫 번째 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="62db9-107">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="62db9-108">명령줄에서 지정된 경우, 다음 **-out** 또는 **-target: module** 옵션까지의 모든 파일이 .dll 파일을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="62db9-108">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="62db9-109">.dll 파일을 빌드하는 경우에는 [Main](../../../csharp/programming-guide/main-and-command-args/index.md) 메서드가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62db9-109">When building a .dll file, a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="62db9-110">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="62db9-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="62db9-111">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="62db9-111">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="62db9-112">**애플리케이션** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="62db9-112">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="62db9-113">**출력 형식** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="62db9-113">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="62db9-114">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62db9-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62db9-115">예제</span><span class="sxs-lookup"><span data-stu-id="62db9-115">Example</span></span>  
 <span data-ttu-id="62db9-116">`in.cs`를 컴파일하고 `in.dll`을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="62db9-116">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="62db9-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62db9-117">See also</span></span>

- [<span data-ttu-id="62db9-118">-target(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="62db9-118">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [<span data-ttu-id="62db9-119">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="62db9-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
