---
title: C# 전처리기 지시문
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: 1c0a97cabce347be0bc9367f3d090a1fc699db19
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43422003"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="57425-102">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="57425-102">C# preprocessor directives</span></span>
<span data-ttu-id="57425-103">이 단원에서는 다음 C# 전처리기 지시문에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="57425-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="57425-104">#if</span><span class="sxs-lookup"><span data-stu-id="57425-104">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
- [<span data-ttu-id="57425-105">#else</span><span class="sxs-lookup"><span data-stu-id="57425-105">#else</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md)
- [<span data-ttu-id="57425-106">#elif</span><span class="sxs-lookup"><span data-stu-id="57425-106">#elif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)
- [<span data-ttu-id="57425-107">#endif</span><span class="sxs-lookup"><span data-stu-id="57425-107">#endif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)
- [<span data-ttu-id="57425-108">#define</span><span class="sxs-lookup"><span data-stu-id="57425-108">#define</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)
- [<span data-ttu-id="57425-109">#undef</span><span class="sxs-lookup"><span data-stu-id="57425-109">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)
- [<span data-ttu-id="57425-110">#warning</span><span class="sxs-lookup"><span data-stu-id="57425-110">#warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)
- [<span data-ttu-id="57425-111">#error</span><span class="sxs-lookup"><span data-stu-id="57425-111">#error</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)
- [<span data-ttu-id="57425-112">#line</span><span class="sxs-lookup"><span data-stu-id="57425-112">#line</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-line.md)
- [<span data-ttu-id="57425-113">#region</span><span class="sxs-lookup"><span data-stu-id="57425-113">#region</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-region.md)
- [<span data-ttu-id="57425-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="57425-114">#endregion</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)
- [<span data-ttu-id="57425-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="57425-115">#pragma</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma.md)
- [<span data-ttu-id="57425-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="57425-116">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)
- [<span data-ttu-id="57425-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="57425-117">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)

<span data-ttu-id="57425-118">자세한 내용과 예제는 각 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57425-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="57425-119">컴파일러에는 별도의 전처리기가 없지만, 이 단원에 설명된 지시문은 전처리기가 있는 것처럼 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="57425-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="57425-120">지시문은 조건부 컴파일에서 지원하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="57425-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="57425-121">C 및 C++ 지시문과 달리, 매크로를 만들기 위해 이러한 지시문을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57425-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="57425-122">전처리기 지시문은 한 줄에서 유일한 명령이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57425-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="57425-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57425-123">See also</span></span>

- [<span data-ttu-id="57425-124">C# 참조</span><span class="sxs-lookup"><span data-stu-id="57425-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="57425-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="57425-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
