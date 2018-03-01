---
title: "-optimize(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /optimize
helpviewer_keywords:
- /optimize compiler option [C#]
- -o compiler option [C#]
- optimize compiler option [C#]
- /o compiler option [C#]
- -optimize compiler option [C#]
- compiler optimization [C#]
- o compiler option [C#]
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2cf6919ee2d4f0a4031e18d46b9e5ebaf816b120
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="-optimize-c-compiler-options"></a><span data-ttu-id="1e169-102">-optimize(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="1e169-102">-optimize (C# Compiler Options)</span></span>
<span data-ttu-id="1e169-103">**-optimize** 옵션은 컴파일러에서 더 작지만 빠르고 효율적인 출력 파일을 만들기 위해 수행하는 최적화 기능을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e169-103">The **-optimize** option enables or disables optimizations performed by the compiler to make your output file smaller, faster, and more efficient.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e169-104">구문</span><span class="sxs-lookup"><span data-stu-id="1e169-104">Syntax</span></span>  
  
```console  
-optimize[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="1e169-105">설명</span><span class="sxs-lookup"><span data-stu-id="1e169-105">Remarks</span></span>  
 <span data-ttu-id="1e169-106">또한 **-optimize**는 런타임에 코드를 최적화하도록 공용 언어 런타임에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1e169-106">**-optimize** also tells the common language runtime to optimize code at runtime.</span></span>  
  
 <span data-ttu-id="1e169-107">최적화는 기본적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e169-107">By default, optimizations are disabled.</span></span> <span data-ttu-id="1e169-108">최적화를 사용하려면 **-optimize+**를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e169-108">Specify **-optimize+** to enable optimizations.</span></span>  
  
 <span data-ttu-id="1e169-109">어셈블리에서 사용할 모듈을 빌드하는 경우 어셈블리의 설정과 동일한 **-optimize** 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e169-109">When building a module to be used by an assembly, use the same **-optimize** settings as those of the assembly.</span></span>  
  
 <span data-ttu-id="1e169-110">**-o**는 **-optimize**의 약식 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="1e169-110">**-o** is the short form of **-optimize**.</span></span>  
  
 <span data-ttu-id="1e169-111">**-optimize** 및 [-debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) 옵션을 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e169-111">It is possible to combine the **-optimize** and [-debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) options.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="1e169-112">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1e169-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="1e169-113">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1e169-113">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="1e169-114">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1e169-114">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="1e169-115">**코드 최적화** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e169-115">Modify the **Optimize Code** property.</span></span>  
  
 <span data-ttu-id="1e169-116">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e169-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e169-117">예</span><span class="sxs-lookup"><span data-stu-id="1e169-117">Example</span></span>  
 <span data-ttu-id="1e169-118">`t2.cs`를 컴파일하고 컴파일러 최적화를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e169-118">Compile `t2.cs` and enable compiler optimizations:</span></span>  
  
```console  
csc t2.cs -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e169-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e169-119">See Also</span></span>  
 [<span data-ttu-id="1e169-120">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="1e169-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="1e169-121">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="1e169-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
