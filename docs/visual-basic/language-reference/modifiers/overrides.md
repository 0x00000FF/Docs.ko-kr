---
title: Overrides(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 7fff91d993743574d13030aa3d5cc1e462e76838
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751032"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="36536-102">Overrides(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36536-102">Overrides (Visual Basic)</span></span>

<span data-ttu-id="36536-103">속성 또는 프로시저가 기본 클래스에서 상속된 이름이 같은 속성 또는 프로시저를 재정의하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="36536-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>

## <a name="rules"></a><span data-ttu-id="36536-104">규칙</span><span class="sxs-lookup"><span data-stu-id="36536-104">Rules</span></span>

- <span data-ttu-id="36536-105">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="36536-105">**Declaration Context.**</span></span> <span data-ttu-id="36536-106">속성 또는 프로시저 선언문에서만 `Overrides`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36536-106">You can use `Overrides` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="36536-107">**결합 된 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="36536-107">**Combined Modifiers.**</span></span> <span data-ttu-id="36536-108">동일한 선언에서 `Shadows` 또는 `Shared`와 함께 `Overrides`를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36536-108">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="36536-109">재정의 요소는 암시적으로 재정의할 수 있으므로 `Overridable`과 `Overrides`를 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36536-109">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>

- <span data-ttu-id="36536-110">**일치 하는 서명입니다.**</span><span class="sxs-lookup"><span data-stu-id="36536-110">**Matching Signatures.**</span></span> <span data-ttu-id="36536-111">이 선언의 서명은 정확히 일치 해야 합니다 *서명* 속성 또는 프로시저를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="36536-111">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="36536-112">즉, 매개 변수 목록에 동일한 데이터 형식의 매개 변수가 동일한 개수 및 순서로 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36536-112">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>

  <span data-ttu-id="36536-113">서명 외에도 재정의 선언이 다음과 정확히 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36536-113">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>

  - <span data-ttu-id="36536-114">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="36536-114">The access level</span></span>

  - <span data-ttu-id="36536-115">반환 형식(있는 경우)</span><span class="sxs-lookup"><span data-stu-id="36536-115">The return type, if any</span></span>

- <span data-ttu-id="36536-116">**제네릭 서명입니다.**</span><span class="sxs-lookup"><span data-stu-id="36536-116">**Generic Signatures.**</span></span> <span data-ttu-id="36536-117">제네릭 프로시저의 경우 서명에 형식 매개 변수 개수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="36536-117">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="36536-118">따라서 해당 측면에서도 재정의 선언이 기본 클래스 버전과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36536-118">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>

- <span data-ttu-id="36536-119">**추가 일치.**</span><span class="sxs-lookup"><span data-stu-id="36536-119">**Additional Matching.**</span></span> <span data-ttu-id="36536-120">기본 클래스 버전과의 서명 일치 외에도 이 선언은 다음 측면에서 기본 클래스 버전과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36536-120">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>

  - <span data-ttu-id="36536-121">액세스 수준 한정자 (같은 [공용](../../../visual-basic/language-reference/modifiers/public.md))</span><span class="sxs-lookup"><span data-stu-id="36536-121">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>

  - <span data-ttu-id="36536-122">각 매개 변수의 전달 메커니즘 ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) 하거나 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="36536-122">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>

  - <span data-ttu-id="36536-123">제네릭 프로시저의 각 형식 매개 변수에 대한 제약 조건 목록</span><span class="sxs-lookup"><span data-stu-id="36536-123">Constraint lists on each type parameter of a generic procedure</span></span>

- <span data-ttu-id="36536-124">**숨기기와 재정의 합니다.**</span><span class="sxs-lookup"><span data-stu-id="36536-124">**Shadowing and Overriding.**</span></span> <span data-ttu-id="36536-125">숨김과 재정의는 둘 다 상속된 요소를 다시 정의하지만 두 방법에는 중요한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36536-125">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="36536-126">자세한 내용은 [Visual Basic의 숨김 기능](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="36536-126">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>

<span data-ttu-id="36536-127">`Overrides`를 사용하는 경우 라이브러리 API가 보다 쉽게 C#으로 작업할 수 있도록 컴파일러에서 암시적으로 `Overloads`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="36536-127">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="36536-128">`Overrides` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36536-128">The `Overrides` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="36536-129">Function 문</span><span class="sxs-lookup"><span data-stu-id="36536-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="36536-130">Property 문</span><span class="sxs-lookup"><span data-stu-id="36536-130">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="36536-131">Sub 문</span><span class="sxs-lookup"><span data-stu-id="36536-131">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="36536-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="36536-132">See also</span></span>

- [<span data-ttu-id="36536-133">MustOverride</span><span class="sxs-lookup"><span data-stu-id="36536-133">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="36536-134">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="36536-134">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="36536-135">재정의 가능</span><span class="sxs-lookup"><span data-stu-id="36536-135">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="36536-136">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="36536-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="36536-137">Visual Basic의 숨김 기능</span><span class="sxs-lookup"><span data-stu-id="36536-137">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="36536-138">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="36536-138">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="36536-139">형식 목록</span><span class="sxs-lookup"><span data-stu-id="36536-139">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
