---
title: '방법: 속성 (Visual Basic) 값 입력'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: ee2449ff905bfdacaeeee4cc244db1ce50e00104
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824311"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="794d4-102">방법: 속성 (Visual Basic) 값 입력</span><span class="sxs-lookup"><span data-stu-id="794d4-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="794d4-103">대입문의 왼쪽에 속성 이름을 입력 하 여 속성에 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="794d4-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="794d4-104">속성의 `Set` 프로시저에서 값을 저장 하지만 명시적으로 호출 하지 해당 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="794d4-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="794d4-105">변수를 사용할 때 처럼 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="794d4-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="794d4-106">Visual Basic에서는 속성의 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="794d4-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="794d4-107">속성에 값을 저장 하려면</span><span class="sxs-lookup"><span data-stu-id="794d4-107">To store a value in a property</span></span>  
  
1.  <span data-ttu-id="794d4-108">대입문의 왼쪽에 속성 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="794d4-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="794d4-109">다음 예제에서는 Visual Basic의 값을 설정 `TimeOfDay` 암시적으로 호출 정오에 속성 해당 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="794d4-109">The following example sets the value of the Visual Basic `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2.  <span data-ttu-id="794d4-110">속성 인수를 사용 하는 경우에 속성 이름을 괄호로 묶어 인수 목록에 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="794d4-110">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="794d4-111">인수가 없는 경우에 필요에 따라 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794d4-111">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="794d4-112">쉼표로 구분 하 여 괄호 안에 인수 목록의 인수를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="794d4-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="794d4-113">속성은 해당 매개 변수 정의 동일한 순서로 인수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="794d4-113">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4.  <span data-ttu-id="794d4-114">대입문의 오른쪽에 생성 된 값을 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="794d4-114">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="794d4-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="794d4-115">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [<span data-ttu-id="794d4-116">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="794d4-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="794d4-117">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="794d4-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="794d4-118">Property 문</span><span class="sxs-lookup"><span data-stu-id="794d4-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="794d4-119">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="794d4-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="794d4-120">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="794d4-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="794d4-121">방법: 액세스 수준이 혼합된 된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="794d4-121">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="794d4-122">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="794d4-122">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="794d4-123">방법: 선언 및 Visual Basic의 기본 속성을 호출</span><span class="sxs-lookup"><span data-stu-id="794d4-123">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="794d4-124">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="794d4-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
