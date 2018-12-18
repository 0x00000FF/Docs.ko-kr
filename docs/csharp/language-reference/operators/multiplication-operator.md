---
title: '* 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: 24ac4a99c48f1e8204b821bfbf5f7fbc0a2b2f1d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237352"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c9ba8-102">\* 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="c9ba8-102">\* Operator (C# Reference)</span></span>
<span data-ttu-id="c9ba8-103">곱하기 연산자(`*`)는 피연산자의 곱을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-103">The multiplication operator (`*`) computes the product of its operands.</span></span> <span data-ttu-id="c9ba8-104">모든 숫자 형식에는 곱하기 연산자가 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-104">All numeric types have predefined multiplication operators.</span></span>  

<span data-ttu-id="c9ba8-105">`*`는 역참조 연산자로 사용되어 포인터를 읽고 쓸 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-105">`*` also serves as the dereference operator, which allows reading and writing to a pointer.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c9ba8-106">설명</span><span class="sxs-lookup"><span data-stu-id="c9ba8-106">Remarks</span></span>  
 <span data-ttu-id="c9ba8-107">`*` 연산자는 포인터 형식의 선언과 포인터의 역참조에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="c9ba8-108">이 연산자는 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 키워드로 표시되었으며 [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) 컴파일러 옵션이 필요한 안전하지 않은 컨텍스트에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, and requiring the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="c9ba8-109">역참조 연산자를 간접 참조 연산자라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-109">The dereference operator is also known as the indirection operator.</span></span>  
  
 <span data-ttu-id="c9ba8-110">사용자 정의 형식으로 이항 `*` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="c9ba8-110">User-defined types can overload the binary `*` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="c9ba8-111">이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9ba8-112">예</span><span class="sxs-lookup"><span data-stu-id="c9ba8-112">Example</span></span>  
 [!code-csharp-interactive[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="c9ba8-113">예제</span><span class="sxs-lookup"><span data-stu-id="c9ba8-113">Example</span></span>  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c9ba8-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9ba8-114">See Also</span></span>

- [<span data-ttu-id="c9ba8-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="c9ba8-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="c9ba8-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c9ba8-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="c9ba8-117">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="c9ba8-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="c9ba8-118">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="c9ba8-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
