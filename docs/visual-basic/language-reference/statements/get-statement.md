---
title: Get 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
ms.openlocfilehash: 245d2cc36abde76a8f8bd73bae5d7ede183d4d03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638031"
---
# <a name="get-statement"></a><span data-ttu-id="8589d-102">Get 문</span><span class="sxs-lookup"><span data-stu-id="8589d-102">Get Statement</span></span>
<span data-ttu-id="8589d-103">선언 된 `Get` 속성 프로시저는 속성의 값을 검색 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-103">Declares a `Get` property procedure used to retrieve the value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8589d-104">구문</span><span class="sxs-lookup"><span data-stu-id="8589d-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a><span data-ttu-id="8589d-105">요소</span><span class="sxs-lookup"><span data-stu-id="8589d-105">Parts</span></span>  
  
|<span data-ttu-id="8589d-106">용어</span><span class="sxs-lookup"><span data-stu-id="8589d-106">Term</span></span>|<span data-ttu-id="8589d-107">정의</span><span class="sxs-lookup"><span data-stu-id="8589d-107">Definition</span></span>|  
|---|---|  
|`attributelist`|<span data-ttu-id="8589d-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-108">Optional.</span></span> <span data-ttu-id="8589d-109">참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-109">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>|  
|`accessmodifier`|<span data-ttu-id="8589d-110">옵션 중 하나에 `Get` 및 `Set` 이 속성에는 문.</span><span class="sxs-lookup"><span data-stu-id="8589d-110">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="8589d-111">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-111">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="8589d-112">-   [보호](../../../visual-basic/language-reference/modifiers/protected.md)</span><span class="sxs-lookup"><span data-stu-id="8589d-112">-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)</span></span><br /><span data-ttu-id="8589d-113">-   [friend](../../../visual-basic/language-reference/modifiers/friend.md)</span><span class="sxs-lookup"><span data-stu-id="8589d-113">-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)</span></span><br /><span data-ttu-id="8589d-114">-   [개인](../../../visual-basic/language-reference/modifiers/private.md)</span><span class="sxs-lookup"><span data-stu-id="8589d-114">-   [Private](../../../visual-basic/language-reference/modifiers/private.md)</span></span><br />-   `Protected Friend`<br /><br /> <span data-ttu-id="8589d-115">[Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8589d-115">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`statements`|<span data-ttu-id="8589d-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-116">Optional.</span></span> <span data-ttu-id="8589d-117">될 때 실행 되는 하나 이상의 문을 `Get` 속성 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-117">One or more statements that run when the `Get` property procedure is called.</span></span>|  
|`End Get`|<span data-ttu-id="8589d-118">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8589d-118">Required.</span></span> <span data-ttu-id="8589d-119">정의 종료 합니다 `Get` 속성 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-119">Terminates the definition of the `Get` property procedure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8589d-120">설명</span><span class="sxs-lookup"><span data-stu-id="8589d-120">Remarks</span></span>  
 <span data-ttu-id="8589d-121">모든 속성에 있어야 합니다는 `Get` 속성 프로시저 속성 표시 되어 있지 않으면 `WriteOnly`합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-121">Every property must have a `Get` property procedure unless the property is marked `WriteOnly`.</span></span> <span data-ttu-id="8589d-122">`Get` 프로시저는 속성의 현재 값을 반환 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-122">The `Get` procedure is used to return the current value of the property.</span></span>  
  
 <span data-ttu-id="8589d-123">Visual Basic로 속성을 자동으로 호출 `Get` 식을 속성의 값을 요청 하는 경우 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-123">Visual Basic automatically calls a property's `Get` procedure when an expression requests the property's value.</span></span>  
  
 <span data-ttu-id="8589d-124">속성 선언의 본문에만 속성의 포함 될 수 있습니다 `Get` 하 고 `Set` 프로시저 간의 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md) 및 `End Property` 문.</span><span class="sxs-lookup"><span data-stu-id="8589d-124">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="8589d-125">이러한 프로시저 이외의 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-125">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="8589d-126">특히,이 속성의 현재 값을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-126">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="8589d-127">다른 속성 프로시저에서 액세스할 수 없으므로 속성 프로시저 중 어디에 저장 하는 경우에 외부 속성을이 값을 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-127">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="8589d-128">에 값을 저장 하는 일반적인 방법입니다를 [개인](../../../visual-basic/language-reference/modifiers/private.md) 속성과 동일한 수준에서 선언 된 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-128">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="8589d-129">정의 해야 합니다는 `Get` 적용 되는 속성 내의 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-129">You must define a `Get` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="8589d-130">합니다 `Get` 프로시저는 기본적으로 포함 하는 해당 속성의 액세스 수준을 사용 하지 않는 경우 `accessmodifier` 에 `Get` 문.</span><span class="sxs-lookup"><span data-stu-id="8589d-130">The `Get` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Get` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="8589d-131">규칙</span><span class="sxs-lookup"><span data-stu-id="8589d-131">Rules</span></span>  
  
- <span data-ttu-id="8589d-132">**혼합 된 액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="8589d-132">**Mixed Access Levels.**</span></span> <span data-ttu-id="8589d-133">서로 다른 액세스 수준에 대 한 필요에 따라 지정할 수는 읽기 / 쓰기 속성을 정의 하는 경우는 `Get` 또는 `Set` 절차, 하지만 둘 다.</span><span class="sxs-lookup"><span data-stu-id="8589d-133">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="8589d-134">이 작업을 수행 하는 경우 프로시저 액세스 수준 속성의 액세스 수준 보다 더 제한적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-134">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="8589d-135">예를 들어, 속성 선언 되 면 `Friend`를 선언할 수 있습니다 합니다 `Get` 프로시저 `Private`, 아닌 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-135">For example, if the property is declared `Friend`, you can declare the `Get` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="8589d-136">정의 하는 경우는 `ReadOnly` 속성을 `Get` 프로시저 전체 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-136">If you are defining a `ReadOnly` property, the `Get` procedure represents the entire property.</span></span> <span data-ttu-id="8589d-137">선언할 수 없습니다는 서로 다른 액세스 수준 `Get`이므로 속성에 대 한 두 가지 액세스 수준이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-137">You cannot declare a different access level for `Get`, because that would set two access levels for the property.</span></span>  
  
- <span data-ttu-id="8589d-138">**형식을 반환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8589d-138">**Return Type.**</span></span> <span data-ttu-id="8589d-139">합니다 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md) 반환 하는 값의 데이터 형식을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-139">The [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) can declare the data type of the value it returns.</span></span> <span data-ttu-id="8589d-140">`Get` 프로시저는 데이터 형식을 자동으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-140">The `Get` procedure automatically returns that data type.</span></span> <span data-ttu-id="8589d-141">모든 데이터 형식 또는 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-141">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="8589d-142">경우는 `Property` 문을 지정 하지 않습니다 `returntype`, 프로시저에서 반환 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-142">If the `Property` statement does not specify `returntype`, the procedure returns `Object`.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="8589d-143">동작</span><span class="sxs-lookup"><span data-stu-id="8589d-143">Behavior</span></span>  
  
- <span data-ttu-id="8589d-144">**프로시저에서 반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="8589d-144">**Returning from a Procedure.**</span></span> <span data-ttu-id="8589d-145">경우는 `Get` 프로시저가 호출 코드에 반환 되 면 속성 값을 요청 하는 문에서 계속 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-145">When the `Get` procedure returns to the calling code, execution continues within the statement that requested the property value.</span></span>  
  
     <span data-ttu-id="8589d-146">`Get` 속성 프로시저 중 하나를 사용 하 여 값을 반환할 수는 [Return 문이](../../../visual-basic/language-reference/statements/return-statement.md) 속성 이름에 반환 값을 할당 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-146">`Get` property procedures can return a value using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or by assigning the return value to the property name.</span></span> <span data-ttu-id="8589d-147">자세한 내용은 "반환 값"를 참조 하세요 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-147">For more information, see "Return Value" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
     <span data-ttu-id="8589d-148">합니다 `Exit Property` 및 `Return` 문은 속성 프로시저를 즉시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-148">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="8589d-149">임의 개수의 `Exit Property` 하 고 `Return` 문을 프로시저에서 아무 곳 이나 나타날 수 있으며 함께 사용할 수 있습니다 `Exit Property` 및 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="8589d-149">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
- <span data-ttu-id="8589d-150">**값을 반환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8589d-150">**Return Value.**</span></span> <span data-ttu-id="8589d-151">값을 반환 하는 `Get` 프로시저, 속성 이름에 값을 할당 하거나 포함을 [Return 문이](../../../visual-basic/language-reference/statements/return-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-151">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span> <span data-ttu-id="8589d-152">합니다 `Return` 문을 동시에 할당 된 `Get` 프로시저 반환 값 및 절차를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-152">The `Return` statement simultaneously assigns the `Get` procedure return value and exits the procedure.</span></span>  
  
     <span data-ttu-id="8589d-153">사용 하는 경우 `Exit Property` 속성 이름에 값을 할당 하지 않고는 `Get` 프로시저가 속성의 데이터 형식에 대 한 기본값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-153">If you use `Exit Property` without assigning a value to the property name, the `Get` procedure returns the default value for the property's data type.</span></span> <span data-ttu-id="8589d-154">자세한 내용은 "반환 값"를 참조 하세요 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-154">For more information, see "Return Value" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
     <span data-ttu-id="8589d-155">다음 예제에서는 두 가지 방법으로 읽기 전용 속성을 보여 줍니다 `quoteForTheDay` 전용 변수에 저장 된 값을 반환할 수 있습니다 `quoteValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-155">The following example illustrates two ways the read-only property `quoteForTheDay` can return the value held in the private variable `quoteValue`.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="8589d-156">예제</span><span class="sxs-lookup"><span data-stu-id="8589d-156">Example</span></span>  
 <span data-ttu-id="8589d-157">다음 예제에서는 `Get` 문을 속성의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8589d-157">The following example uses the `Get` statement to return the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="8589d-158">참고자료</span><span class="sxs-lookup"><span data-stu-id="8589d-158">See also</span></span>

- [<span data-ttu-id="8589d-159">Set 문</span><span class="sxs-lookup"><span data-stu-id="8589d-159">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="8589d-160">Property 문</span><span class="sxs-lookup"><span data-stu-id="8589d-160">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="8589d-161">Exit 문</span><span class="sxs-lookup"><span data-stu-id="8589d-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="8589d-162">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="8589d-162">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="8589d-163">연습: 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="8589d-163">Walkthrough: Defining Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
