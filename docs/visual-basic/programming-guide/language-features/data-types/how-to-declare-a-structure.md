---
title: '방법: 선언 구조체 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: a52daddaa8701ccca9bd9b5b4a48535a6ffa19ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906713"
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="7f2c2-102">방법: 선언 구조체 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f2c2-102">How to: Declare a Structure (Visual Basic)</span></span>
<span data-ttu-id="7f2c2-103">먼저 사용 하 여 구조체 선언을 [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md)를 종료 하 고는 `End Structure` 문.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-103">You begin a structure declaration with the [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md), and you end it with the `End Structure` statement.</span></span> <span data-ttu-id="7f2c2-104">두 문 사이 선언 해야 하나 이상의 *요소*합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-104">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="7f2c2-105">모든 데이터 형식의 요소 수는 있지만 비공유 변수 또는 비공유, 비 사용자 정의 이벤트를 하나 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-105">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="7f2c2-106">구조체 선언에서는 구조 요소를 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="7f2c2-107">구조체 형식 이어야 하는 변수를 선언할 때 값을 할당 하는 요소 변수를 통해 액세스 하 여.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-107">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="7f2c2-108">구조체와 클래스 간의 차이점, 참조 [구조체와 클래스](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-108">For a discussion of the differences between structures and classes, see [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="7f2c2-109">데모용으로 직원의 이름과 내선 전화 번호, 급여를 추적 하려는 경우를 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-109">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="7f2c2-110">구조체를 사용 하면 단일 변수에서이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-110">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="7f2c2-111">구조체를 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="7f2c2-111">To declare a structure</span></span>  
  
1. <span data-ttu-id="7f2c2-112">시작 및 끝 문장 구조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-112">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="7f2c2-113">사용 하 여 구조 액세스 수준을 지정할 수 있습니다는 [공용](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), 또는 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 키워드 또는 있습니다 수 있도록 기본적으로 `Public`입니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-113">You can specify the access level of a structure using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2. <span data-ttu-id="7f2c2-114">구조체의 본문에 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-114">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="7f2c2-115">구조체에는 하나 이상의 요소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-115">A structure must have at least one element.</span></span> <span data-ttu-id="7f2c2-116">모든 요소를 선언 하 고에 대 한 액세스 수준을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-116">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="7f2c2-117">사용 하는 경우는 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 접근성 기본값으로 키워드 없이 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-117">If you use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
    ```  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     <span data-ttu-id="7f2c2-118">합니다 `salary` 앞의 예제에서 필드는 `Private`, 즉에 포함 하는 클래스 에서도 구조체 외부에서는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-118">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="7f2c2-119">그러나 합니다 `giveRaise` 절차는 `Public`이므로 구조 외부에서 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-119">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="7f2c2-120">마찬가지로, 발생 시킬 수 있습니다는 `salaryReviewTime` 구조 외부에서 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-120">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="7f2c2-121">변수 외에도 `Sub` 프로시저 및 이벤트에 상수를 정의할 수도 있습니다 `Function` 절차 및 구조에는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-121">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="7f2c2-122">에서는 하나 이상의 속성으로 지정할 수 있습니다 합니다 *속성의 기본값을*하나 이상의 인수를 사용 하는, 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-122">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="7f2c2-123">사용 하 여 이벤트를 처리할 수 있습니다는 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-123">You can handle an event with a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="7f2c2-124">자세한 내용은 [방법: 선언 및 Visual Basic의 기본 속성을 호출](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2c2-124">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f2c2-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="7f2c2-125">See also</span></span>

- [<span data-ttu-id="7f2c2-126">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7f2c2-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="7f2c2-127">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7f2c2-127">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="7f2c2-128">복합 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7f2c2-128">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="7f2c2-129">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="7f2c2-129">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="7f2c2-130">구조체</span><span class="sxs-lookup"><span data-stu-id="7f2c2-130">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="7f2c2-131">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7f2c2-131">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="7f2c2-132">구조체 변수</span><span class="sxs-lookup"><span data-stu-id="7f2c2-132">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="7f2c2-133">구조체 및 기타 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="7f2c2-133">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="7f2c2-134">구조체와 클래스</span><span class="sxs-lookup"><span data-stu-id="7f2c2-134">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="7f2c2-135">사용자 정의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7f2c2-135">User-Defined Data Type</span></span>](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
