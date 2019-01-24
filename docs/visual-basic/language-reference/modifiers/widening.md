---
title: Widening(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: 3b9d1ec15c6c2000fb0842abe25848f853cdf986
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703712"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="39784-102">Widening(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39784-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="39784-103">나타내는 변환 연산자 (`CType`) 클래스 또는 구조체를 원래 클래스 또는 구조체의 모든 가능한 값을 보유할 수 있는 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="39784-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="39784-104">확대 키워드를 사용 하 여 변환</span><span class="sxs-lookup"><span data-stu-id="39784-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="39784-105">변환 절차 지정 해야 합니다 `Public Shared` 외에 `Widening`합니다.</span><span class="sxs-lookup"><span data-stu-id="39784-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="39784-106">확대 변환 런타임에 항상 실패 하 고 데이터가 손실 되지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="39784-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="39784-107">예로 `Single` 하 `Double`, `Char` 에 `String`, 파생 형식과 해당 기본 형식에 합니다.</span><span class="sxs-lookup"><span data-stu-id="39784-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="39784-108">이 마지막은 확대 변환 파생된 형식은 기본 형식의 모든 멤버를 포함 되어 있으므로 기본 형식의 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="39784-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="39784-109">사용 하는 코드를 사용할 필요가 없습니다 `CType` 확대 변환에 대 한 경우에 `Option Strict` 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="39784-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="39784-110">`Widening` 키워드는이 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39784-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="39784-111">Operator 문</span><span class="sxs-lookup"><span data-stu-id="39784-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 <span data-ttu-id="39784-112">예를 들어 확대 변환과 축소 변환 연산자의 정의 참조 [방법: 변환 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="39784-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39784-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="39784-113">See also</span></span>
- [<span data-ttu-id="39784-114">Operator 문</span><span class="sxs-lookup"><span data-stu-id="39784-114">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="39784-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="39784-115">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="39784-116">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="39784-116">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="39784-117">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="39784-117">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="39784-118">CType 함수</span><span class="sxs-lookup"><span data-stu-id="39784-118">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="39784-119">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="39784-119">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="39784-120">방법: 변환 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="39784-120">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
