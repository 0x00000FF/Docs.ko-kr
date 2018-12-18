---
title: '방법: 포인터 증가 및 감소 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: f28fc4f86e4ff01f90bfd49714f38eee7040f9d1
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242296"
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="52814-102">방법: 포인터 증가 및 감소(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="52814-102">How to: increment and decrement pointers (C# Programming Guide)</span></span>

<span data-ttu-id="52814-103">증가 및 감소 연산자인 `++` 및 `--`를 사용하여 `pointer-type*` 형식의 포인터에 대한 포인터 위치를 `sizeof(pointer-type)`만큼 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="52814-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by `sizeof(pointer-type)` for a pointer of the type `pointer-type*`.</span></span> <span data-ttu-id="52814-104">증가 및 감소 식은 다음 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="52814-104">The increment and decrement expressions take the following form:</span></span>  
  
```csharp
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="52814-105">`void*` 형식을 제외한 모든 형식의 포인터에 증가 및 감소 연산자를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52814-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="52814-106">`pointer-type*` 형식의 포인터에 증가 연산자를 적용할 경우 포인터 변수에 포함된 주소에 `sizeof(pointer-type)`를 더하는 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52814-106">The effect of applying the increment operator to a pointer of the type `pointer-type*` is to add `sizeof(pointer-type)` to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="52814-107">`pointer-type*` 형식의 포인터에 감소 연산자를 적용할 경우 포인터 변수에 포함된 주소에서 `sizeof(pointer-type)`를 빼는 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52814-107">The effect of applying the decrement operator to a pointer of the type `pointer-type*` is to subtract `sizeof(pointer-type)` from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="52814-108">연산이 포인터의 도메인을 오버플로하는 경우 예외가 생성되지 않고 결과는 구현에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="52814-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52814-109">예</span><span class="sxs-lookup"><span data-stu-id="52814-109">Example</span></span>  
 <span data-ttu-id="52814-110">이 예제에서는 포인터를 `int` 크기만큼 증가하여 배열을 단계별로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52814-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="52814-111">각 단계에서 주소와 배열 요소의 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="52814-111">With each step, you display the address and the content of the array element.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
<span data-ttu-id="52814-112">**Value:0 @ 주소:12860272**
**Value:1 @ 주소:12860276**
**Value:2 @ 주소:12860280**
**Value:3 @ 주소:12860284**
**Value:4 @ 주소:12860288**</span><span class="sxs-lookup"><span data-stu-id="52814-112">**Value:0 @ Address:12860272**
**Value:1 @ Address:12860276**
**Value:2 @ Address:12860280**
**Value:3 @ Address:12860284**
**Value:4 @ Address:12860288**</span></span>

## <a name="see-also"></a><span data-ttu-id="52814-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52814-113">See also</span></span>

- [<span data-ttu-id="52814-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="52814-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="52814-115">포인터 식</span><span class="sxs-lookup"><span data-stu-id="52814-115">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="52814-116">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="52814-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="52814-117">포인터 조작</span><span class="sxs-lookup"><span data-stu-id="52814-117">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [<span data-ttu-id="52814-118">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="52814-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="52814-119">유형</span><span class="sxs-lookup"><span data-stu-id="52814-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="52814-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="52814-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="52814-121">fixed 문</span><span class="sxs-lookup"><span data-stu-id="52814-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="52814-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="52814-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
- [<span data-ttu-id="52814-123">sizeof</span><span class="sxs-lookup"><span data-stu-id="52814-123">sizeof</span></span>](../../../csharp/language-reference/keywords/sizeof.md)
