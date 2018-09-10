---
title: '[] 연산자(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 19283a795f8cfc444dfcb186dcecc0ea86eb27fd
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500454"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f6619-102">[] 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f6619-102">[] Operator (C# Reference)</span></span>
<span data-ttu-id="f6619-103">대괄호(`[]`)는 배열, 인덱서 및 특성에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6619-103">Square brackets (`[]`) are used for arrays, indexers, and attributes.</span></span> <span data-ttu-id="f6619-104">포인터에 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6619-104">They can also be used with pointers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6619-105">설명</span><span class="sxs-lookup"><span data-stu-id="f6619-105">Remarks</span></span>  
 <span data-ttu-id="f6619-106">배열 형식은 뒤에 `[]`가 오는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f6619-106">An array type is a type followed by `[]`:</span></span>  
  
 [!code-csharp[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]  
  
 <span data-ttu-id="f6619-107">배열의 요소에 액세스하려면 원하는 요소의 인덱스를 대괄호로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="f6619-107">To access an element of an array, the index of the desired element is enclosed in brackets:</span></span>  
  
 [!code-csharp[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]  
  
 <span data-ttu-id="f6619-108">배열 인덱스가 범위를 벗어나면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6619-108">An exception is thrown if an array index is out of range.</span></span>  
  
 <span data-ttu-id="f6619-109">배열 인덱싱 연산자를 오버로드할 수는 없습니다. 그러나 형식에서 하나 이상의 매개 변수를 사용하는 인덱서를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6619-109">The array indexing operator cannot be overloaded; however, types can define indexers that take one or more parameters.</span></span> <span data-ttu-id="f6619-110">인덱서 매개 변수는 배열 인덱스와 마찬가지로 대괄호에 묶여 있지만 인덱서 매개 변수는 정수여야 하는 배열 인덱스와 달리 임의 형식으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6619-110">Indexer parameters are enclosed in square brackets, just like array indexes, but indexer parameters can be declared to be of any type, unlike array indexes, which must be integral.</span></span>  
  
 <span data-ttu-id="f6619-111">예를 들어 .NET Framework에서는 임의 형식의 키와 값을 연결하는 `Hashtable` 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f6619-111">For example, the .NET Framework defines a `Hashtable` type that associates keys and values of arbitrary type:</span></span>  
  
 [!code-csharp[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]  
  
 <span data-ttu-id="f6619-112">대괄호는 [특성](../../../csharp/programming-guide/concepts/attributes/index.md)을 지정하는 데에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6619-112">Square brackets are also used to specify [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md):</span></span>  
  
 [!code-csharp[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]  
  
 <span data-ttu-id="f6619-113">대괄호를 사용하여 포인터를 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6619-113">You can use square brackets to index off a pointer:</span></span>  
  
 [!code-csharp[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]  
  
 <span data-ttu-id="f6619-114">범위 검사는 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6619-114">No bounds checking is performed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f6619-115">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f6619-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f6619-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6619-116">See Also</span></span>

- [<span data-ttu-id="f6619-117">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f6619-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="f6619-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f6619-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f6619-119">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="f6619-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="f6619-120">배열</span><span class="sxs-lookup"><span data-stu-id="f6619-120">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
- [<span data-ttu-id="f6619-121">인덱서</span><span class="sxs-lookup"><span data-stu-id="f6619-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
- [<span data-ttu-id="f6619-122">unsafe</span><span class="sxs-lookup"><span data-stu-id="f6619-122">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="f6619-123">fixed 문</span><span class="sxs-lookup"><span data-stu-id="f6619-123">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
