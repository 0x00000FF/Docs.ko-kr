---
title: . 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: a092c1a916e3dc4bf6d96660c532540945e57554
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520710"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="8ff52-103">.</span><span class="sxs-lookup"><span data-stu-id="8ff52-103">.</span></span> <span data-ttu-id="8ff52-104">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8ff52-104">Operator (C# Reference)</span></span>
<span data-ttu-id="8ff52-105">점 연산자(`.`)는 멤버 액세스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ff52-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="8ff52-106">점 연산자는 형식 또는 네임스페이스의 멤버를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff52-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="8ff52-107">예를 들어 점 연산자는 .NET Framework 클래스 라이브러리 내의 특정 메서드에 액세스하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ff52-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>  
  
 [!code-csharp[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]  
  
 <span data-ttu-id="8ff52-108">예를 들어 다음 클래스를 예로 들어 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ff52-108">For example, consider the following class:</span></span>  
  
 [!code-csharp[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]  
  
 [!code-csharp[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]  
  
 <span data-ttu-id="8ff52-109">`s` 변수에는 두 개의 멤버 `a`와 `b`가 있으며, 액세스하려면 점 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff52-109">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>  
  
 [!code-csharp[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]  
  
 <span data-ttu-id="8ff52-110">예를 들어 점은 속하는 네임스페이스 또는 인터페이스를 지정하는 이름인 정규화된 이름을 형성하는 데에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ff52-110">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>  
  
 [!code-csharp[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]  
  
 <span data-ttu-id="8ff52-111">using 지시문을 사용하면 일부 이름 한정이 선택 사항이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ff52-111">The using directive makes some name qualification optional:</span></span>  
  
 [!code-csharp[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]  
  
 <span data-ttu-id="8ff52-112">하지만 식별자가 모호한 경우 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff52-112">But when an identifier is ambiguous, it must be qualified:</span></span>  
  
 [!code-csharp[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8ff52-113">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8ff52-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8ff52-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ff52-114">See Also</span></span>

- [<span data-ttu-id="8ff52-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8ff52-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="8ff52-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8ff52-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="8ff52-117">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="8ff52-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
