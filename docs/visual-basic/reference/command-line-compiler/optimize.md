---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: e8daf4a49123623b6470bc3c6281869f1b9b3d0f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005375"
---
# <a name="-optimize"></a><span data-ttu-id="eb4d2-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="eb4d2-102">-optimize</span></span>
<span data-ttu-id="eb4d2-103">컴파일러 최적화를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb4d2-104">구문</span><span class="sxs-lookup"><span data-stu-id="eb4d2-104">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="eb4d2-105">인수</span><span class="sxs-lookup"><span data-stu-id="eb4d2-105">Arguments</span></span>  
  
|<span data-ttu-id="eb4d2-106">용어</span><span class="sxs-lookup"><span data-stu-id="eb4d2-106">Term</span></span>|<span data-ttu-id="eb4d2-107">정의</span><span class="sxs-lookup"><span data-stu-id="eb4d2-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="eb4d2-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="eb4d2-108">`+` &#124; `-`</span></span>|<span data-ttu-id="eb4d2-109">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="eb4d2-109">Optional.</span></span> <span data-ttu-id="eb4d2-110">@No__t-0 옵션은 컴파일러 최적화를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="eb4d2-111">@No__t-0 옵션은 최적화를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="eb4d2-112">최적화는 기본적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb4d2-113">설명</span><span class="sxs-lookup"><span data-stu-id="eb4d2-113">Remarks</span></span>  
 <span data-ttu-id="eb4d2-114">컴파일러 최적화를 통해 더 작지만 빠르고 효율적인 출력 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="eb4d2-115">그러나 최적화를 수행 하면 출력 파일에서 코드가 재배치 되기 때문에 `-optimize+`을 사용 하면 디버깅이 어려워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="eb4d2-116">어셈블리에 대해 `-target:module`으로 생성 된 모든 모듈은 어셈블리와 동일한 `-optimize` 설정을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="eb4d2-117">자세한 내용은 [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-117">For more information, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="eb4d2-118">@No__t-0 및 `-debug` 옵션을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="eb4d2-119">Visual Studio 통합 개발 환경에서을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="eb4d2-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="eb4d2-120">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="eb4d2-121">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="eb4d2-122">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="eb4d2-123">3.  **고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="eb4d2-124">4.  **최적화 사용** 확인란을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eb4d2-125">예제</span><span class="sxs-lookup"><span data-stu-id="eb4d2-125">Example</span></span>  
 <span data-ttu-id="eb4d2-126">다음 코드는-0 @no__t 컴파일하고 컴파일러 최적화를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="eb4d2-127">참조</span><span class="sxs-lookup"><span data-stu-id="eb4d2-127">See also</span></span>

- [<span data-ttu-id="eb4d2-128">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="eb4d2-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="eb4d2-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb4d2-129">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="eb4d2-130">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="eb4d2-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="eb4d2-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb4d2-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
