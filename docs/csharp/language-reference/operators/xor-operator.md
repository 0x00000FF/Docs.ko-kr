---
title: "^ 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4ccd32ea8abd8ca3252380083eafecad2b572ed7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="68a72-102">^ 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="68a72-102">^ Operator (C# Reference)</span></span>
<span data-ttu-id="68a72-103">이항 `^` 연산자는 정수 형식 및 `bool`에 대해 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a72-103">Binary `^` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="68a72-104">정수 형식의 경우 `^` 연산자는 해당 피연산자의 배타적 비트 OR 연산자를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="68a72-104">For integral types, `^` computes the bitwise exclusive-OR of its operands.</span></span> <span data-ttu-id="68a72-105">`bool` 피연산자의 경우 `^` 연산자는 피연산자의 배타적 논리 OR 연산을 계산합니다. 즉 피연산자 중 정확히 하나가 `true`일 경우에만 결과가 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="68a72-105">For `bool` operands, `^` computes the logical exclusive-or of its operands; that is, the result is `true` if and only if exactly one of its operands is `true`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68a72-106">설명</span><span class="sxs-lookup"><span data-stu-id="68a72-106">Remarks</span></span>  
 <span data-ttu-id="68a72-107">사용자 정의 형식은 `^` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="68a72-107">User-defined types can overload the `^` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="68a72-108">정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a72-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68a72-109">예제</span><span class="sxs-lookup"><span data-stu-id="68a72-109">Example</span></span>  
 [!code-csharp[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]  
  
 <span data-ttu-id="68a72-110">이전 예제에서의 `0xf8 ^ 0x3f` 계산은 16진수 값 F8 및 3F에 해당하는 다음 두 이진 값에 대하여 배타적 비트 OR 연산을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="68a72-110">The computation of `0xf8 ^ 0x3f` in the previous example performs a bitwise exclusive-OR of the following two binary values, which correspond to the hexadecimal values F8 and 3F:</span></span>  
  
 `1111 1000`  
  
 `0011 1111`  
  
 <span data-ttu-id="68a72-111">배타적 OR 연산 결과는 `1100 0111`이며 16진수로 나타내면 C7입니다.</span><span class="sxs-lookup"><span data-stu-id="68a72-111">The result of the exclusive-OR is `1100 0111`, which is C7 in hexadecimal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a72-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68a72-112">See Also</span></span>  
 [<span data-ttu-id="68a72-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="68a72-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="68a72-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="68a72-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="68a72-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="68a72-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
