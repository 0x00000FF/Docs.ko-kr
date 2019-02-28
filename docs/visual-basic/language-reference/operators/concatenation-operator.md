---
title: '&amp; 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: 2237da5d64ada6817d3a9a88b04b76f573bd76c0
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976514"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="9e753-102">&amp; 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e753-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="9e753-103">두 식의 문자열 연결을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e753-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e753-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e753-104">Syntax</span></span>  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="9e753-105">요소</span><span class="sxs-lookup"><span data-stu-id="9e753-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="9e753-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="9e753-106">Required.</span></span> <span data-ttu-id="9e753-107">모든 `String` 또는 `Object` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9e753-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="9e753-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="9e753-108">Required.</span></span> <span data-ttu-id="9e753-109">데이터 형식으로 확대 되는 식을 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e753-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="9e753-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="9e753-110">Required.</span></span> <span data-ttu-id="9e753-111">데이터 형식으로 확대 되는 식을 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e753-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e753-112">설명</span><span class="sxs-lookup"><span data-stu-id="9e753-112">Remarks</span></span>  
 <span data-ttu-id="9e753-113">데이터 형식이 `expression1` 또는 `expression2` 아닙니다 `String` 로 확대 변환 하지만 `String`, 변환할 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e753-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="9e753-114">하는 경우 데이터 형식 중 하나는 변환할 `String`, 컴파일러는 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e753-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="9e753-115">데이터 형식이 `result` 는 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e753-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="9e753-116">하나 또는 둘 다 식으로 계산 되 면 [아무](../../../visual-basic/language-reference/nothing.md) 의 값 또는 <xref:System.DBNull.Value?displayProperty=nameWithType>의 값을 사용 하 여 문자열로 처리 되는 ""입니다.</span><span class="sxs-lookup"><span data-stu-id="9e753-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e753-117">합니다 `&` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우.</span><span class="sxs-lookup"><span data-stu-id="9e753-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9e753-118">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e753-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9e753-119">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e753-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e753-120">앰퍼샌드 (&) 문자로 사용할 수도 있습니다 형식으로 변수를 식별 하려면 `Long`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e753-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="9e753-121">자세한 내용은 [형식 문자](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e753-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e753-122">예제</span><span class="sxs-lookup"><span data-stu-id="9e753-122">Example</span></span>  
 <span data-ttu-id="9e753-123">이 예제에서는 `&` 문자열을 연결 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="9e753-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="9e753-124">결과 두 문자열 피연산자의 연결을 나타내는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9e753-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9e753-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="9e753-125">See also</span></span>
- [<span data-ttu-id="9e753-126">&= 연산자</span><span class="sxs-lookup"><span data-stu-id="9e753-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="9e753-127">연결 연산자</span><span class="sxs-lookup"><span data-stu-id="9e753-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="9e753-128">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="9e753-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9e753-129">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="9e753-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="9e753-130">Visual Basic의 연결 연산자</span><span class="sxs-lookup"><span data-stu-id="9e753-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
