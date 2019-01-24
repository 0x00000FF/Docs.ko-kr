---
title: Static(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 1205d620fb5b6ec6af14cdeb7c6d78439f9e6b97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627631"
---
# <a name="static-visual-basic"></a><span data-ttu-id="d211c-102">Static(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d211c-102">Static (Visual Basic)</span></span>
<span data-ttu-id="d211c-103">계속 존재 하 고 선언 된 프로시저가 종료 된 후 최신 값을 보유 하는 하나 이상의 선언 된 지역 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-103">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d211c-104">설명</span><span class="sxs-lookup"><span data-stu-id="d211c-104">Remarks</span></span>  
 <span data-ttu-id="d211c-105">일반적으로 프로시저에서 지역 변수 소멸 프로시저를 중지 하는 즉시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-105">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="d211c-106">정적 변수는 계속 존재 하 고 최신 값을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-106">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="d211c-107">프로시저를 호출 하는 코드 다음에 변수가 다시 초기화 되지 않습니다 및에 할당 되는 최신 값을 계속 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-107">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="d211c-108">정적 변수 계속에 정의 된 클래스 또는 모듈의 수명 동안 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-108">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d211c-109">규칙</span><span class="sxs-lookup"><span data-stu-id="d211c-109">Rules</span></span>  
  
-   <span data-ttu-id="d211c-110">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="d211c-110">**Declaration Context.**</span></span> <span data-ttu-id="d211c-111">사용할 수 있습니다 `Static` 로컬 변수 에서만.</span><span class="sxs-lookup"><span data-stu-id="d211c-111">You can use `Static` only on local variables.</span></span> <span data-ttu-id="d211c-112">즉, 선언 컨텍스트는 `Static` 변수는 프로시저 또는 프로시저에서 블록 이어야 합니다 하 고 소스 파일, 네임 스페이스, 클래스, 구조체 또는 모듈 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-112">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="d211c-113">사용할 수 없습니다 `Static` 구조 프로시저 내에서.</span><span class="sxs-lookup"><span data-stu-id="d211c-113">You cannot use `Static` inside a structure procedure.</span></span>  
  
-   <span data-ttu-id="d211c-114">데이터 형식의 `Static` 로컬 변수를 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-114">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="d211c-115">자세한 내용은 [로컬 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-115">For more information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
-   <span data-ttu-id="d211c-116">**결합 된 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="d211c-116">**Combined Modifiers.**</span></span> <span data-ttu-id="d211c-117">지정할 수 없습니다 `Static` 와 함께 `ReadOnly`를 `Shadows`, 또는 `Shared` 같은 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-117">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="d211c-118">동작</span><span class="sxs-lookup"><span data-stu-id="d211c-118">Behavior</span></span>  
 <span data-ttu-id="d211c-119">정적 변수를 선언 하는 경우는 `Shared` 절차, 정적 변수 복사본 하나만 전체 응용 프로그램에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-119">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="d211c-120">호출을 `Shared` 클래스를 사용 하 여 프로시저 이름, 클래스의 인스턴스를 가리키는 변수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-120">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="d211c-121">되지 않는 프로시저에서 정적 변수를 선언 하는 경우 `Shared`만 변수의 복사본 하나를 클래스의 각 인스턴스에 대해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-121">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="d211c-122">클래스의 특정 인스턴스를 가리키는 변수를 사용 하는 비공유 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-122">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d211c-123">예제</span><span class="sxs-lookup"><span data-stu-id="d211c-123">Example</span></span>  
 <span data-ttu-id="d211c-124">다음 예에서는 `Static`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-124">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](../../../visual-basic/language-reference/codesnippet/VisualBasic/static_1.vb)]  
  
 <span data-ttu-id="d211c-125">합니다 `Static` 변수 `totalSales` 한 번만 0으로 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-125">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="d211c-126">입력할 때마다 `updateSales`, `totalSales` 아직 최신 값에 대 한 계산입니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-126">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="d211c-127">`Static` 한정자는이 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d211c-127">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="d211c-128">Dim 문</span><span class="sxs-lookup"><span data-stu-id="d211c-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d211c-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="d211c-129">See also</span></span>
- [<span data-ttu-id="d211c-130">Shadows</span><span class="sxs-lookup"><span data-stu-id="d211c-130">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="d211c-131">공유</span><span class="sxs-lookup"><span data-stu-id="d211c-131">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="d211c-132">Visual Basic의 수명</span><span class="sxs-lookup"><span data-stu-id="d211c-132">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="d211c-133">변수 선언</span><span class="sxs-lookup"><span data-stu-id="d211c-133">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="d211c-134">구조체</span><span class="sxs-lookup"><span data-stu-id="d211c-134">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="d211c-135">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="d211c-135">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="d211c-136">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="d211c-136">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
