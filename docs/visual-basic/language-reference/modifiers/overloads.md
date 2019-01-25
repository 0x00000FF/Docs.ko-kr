---
title: Overloads(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
ms.openlocfilehash: b20dbf20c580d08553ae22f6a62ee33a7354db74
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624917"
---
# <a name="overloads-visual-basic"></a><span data-ttu-id="37bfd-102">Overloads(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37bfd-102">Overloads (Visual Basic)</span></span>
<span data-ttu-id="37bfd-103">속성 또는 프로시저에서 하나 이상의 기존 속성 또는 프로시저를 같은 이름으로 다시 선언할 수 있도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-103">Specifies that a property or procedure redeclares one or more existing properties or procedures with the same name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37bfd-104">설명</span><span class="sxs-lookup"><span data-stu-id="37bfd-104">Remarks</span></span>  
 <span data-ttu-id="37bfd-105">*오버 로드* 는 같은 범위에서 지정된 된 속성 또는 프로시저 이름에 대 한 둘 이상의 정의 제공 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-105">*Overloading* is the practice of supplying more than one definition for a given property or procedure name in the same scope.</span></span> <span data-ttu-id="37bfd-106">속성 또는 다른 서명이 있는 프로시저를 다시 선언 이라고 *시그니처로 숨김*합니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-106">Redeclaring a property or procedure with a different signature is sometimes called *hiding by signature*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="37bfd-107">규칙</span><span class="sxs-lookup"><span data-stu-id="37bfd-107">Rules</span></span>  
  
-   <span data-ttu-id="37bfd-108">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="37bfd-108">**Declaration Context.**</span></span> <span data-ttu-id="37bfd-109">속성 또는 프로시저 선언문에서만 `Overloads`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-109">You can use `Overloads` only in a property or procedure declaration statement.</span></span>  
  
-   <span data-ttu-id="37bfd-110">**결합 된 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="37bfd-110">**Combined Modifiers.**</span></span> <span data-ttu-id="37bfd-111">지정할 수 없습니다 `Overloads` 와 함께 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md) 동일한 프로시저 선언에서.</span><span class="sxs-lookup"><span data-stu-id="37bfd-111">You cannot specify `Overloads` together with [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) in the same procedure declaration.</span></span>  
  
-   <span data-ttu-id="37bfd-112">**차이 필요.**</span><span class="sxs-lookup"><span data-stu-id="37bfd-112">**Required Differences.**</span></span> <span data-ttu-id="37bfd-113">합니다 *서명* 이 선언에서 달라 야 모든 속성 또는 오버 로드 하는 프로시저의 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-113">The *signature* in this declaration must be different from the signature of every property or procedure that it overloads.</span></span> <span data-ttu-id="37bfd-114">서명은 다음 항목과 함께 속성 또는 프로시저 이름으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-114">The signature comprises the property or procedure name together with the following:</span></span>  
  
    -   <span data-ttu-id="37bfd-115">매개 변수 수</span><span class="sxs-lookup"><span data-stu-id="37bfd-115">the number of parameters</span></span>  
  
    -   <span data-ttu-id="37bfd-116">매개 변수의 순서</span><span class="sxs-lookup"><span data-stu-id="37bfd-116">the order of the parameters</span></span>  
  
    -   <span data-ttu-id="37bfd-117">매개 변수의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="37bfd-117">the data types of the parameters</span></span>  
  
    -   <span data-ttu-id="37bfd-118">형식 매개 변수의 수(제네릭 프로시저의 경우)</span><span class="sxs-lookup"><span data-stu-id="37bfd-118">the number of type parameters (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="37bfd-119">반환 형식(변환 연산자 프로시저의 경우만)</span><span class="sxs-lookup"><span data-stu-id="37bfd-119">the return type (only for a conversion operator procedure)</span></span>  
  
     <span data-ttu-id="37bfd-120">모든 오버로드는 이름이 같아야 하지만 앞에서 설명한 하나 이상의 측면과 관련하여 각각은 다른 모든 오버로드와 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-120">All overloads must have the same name, but each must differ from all the others in one or more of the preceding respects.</span></span> <span data-ttu-id="37bfd-121">그러면 컴파일러가 코드에서 속성 또는 프로시저를 호출할 때 사용할 버전을 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-121">This allows the compiler to distinguish which version to use when code calls the property or procedure.</span></span>  
  
-   <span data-ttu-id="37bfd-122">**차이 허용 되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="37bfd-122">**Disallowed Differences.**</span></span> <span data-ttu-id="37bfd-123">다음 중 하나 이상은 서명의 일부가 아니므로 속성 또는 프로시저를 오버로드하기 위해 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-123">Changing one or more of the following is not valid for overloading a property or procedure, because they are not part of the signature:</span></span>  
  
    -   <span data-ttu-id="37bfd-124">값을 반환하는지 여부(프로시저의 경우)</span><span class="sxs-lookup"><span data-stu-id="37bfd-124">whether or not it returns a value (for a procedure)</span></span>  
  
    -   <span data-ttu-id="37bfd-125">반환 값의 데이터 형식(변환 연산자 제외)</span><span class="sxs-lookup"><span data-stu-id="37bfd-125">the data type of the return value (except for a conversion operator)</span></span>  
  
    -   <span data-ttu-id="37bfd-126">매개 변수 또는 형식 매개 변수의 이름</span><span class="sxs-lookup"><span data-stu-id="37bfd-126">the names of the parameters or type parameters</span></span>  
  
    -   <span data-ttu-id="37bfd-127">형식 매개 변수에 대한 제약 조건(제네릭 프로시저의 경우)</span><span class="sxs-lookup"><span data-stu-id="37bfd-127">the constraints on the type parameters (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="37bfd-128">매개 변수 한정자 키워드(예: `ByRef` 또는 `Optional`)</span><span class="sxs-lookup"><span data-stu-id="37bfd-128">parameter modifier keywords (such as `ByRef` or `Optional`)</span></span>  
  
    -   <span data-ttu-id="37bfd-129">속성 또는 프로시저 한정자 키워드(예: `Public` 또는 `Shared`)</span><span class="sxs-lookup"><span data-stu-id="37bfd-129">property or procedure modifier keywords (such as `Public` or `Shared`)</span></span>  
  
-   <span data-ttu-id="37bfd-130">**선택적 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="37bfd-130">**Optional Modifier.**</span></span> <span data-ttu-id="37bfd-131">동일한 클래스에서 오버로드된 속성 또는 프로시저를 여러 개 정의하려는 경우 `Overloads` 한정자를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-131">You do not have to use the `Overloads` modifier when you are defining multiple overloaded properties or procedures in the same class.</span></span> <span data-ttu-id="37bfd-132">그러나 선언 중 하나에서 `Overloads`를 사용하는 경우에는 모든 선언에서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-132">However, if you use `Overloads` in one of the declarations, you must use it in all of them.</span></span>  
  
-   <span data-ttu-id="37bfd-133">**섀도잉 및 오버 로드 합니다.**</span><span class="sxs-lookup"><span data-stu-id="37bfd-133">**Shadowing and Overloading.**</span></span> <span data-ttu-id="37bfd-134">`Overloads` 섀도 기존 멤버 또는 기본 클래스에서 오버 로드 된 멤버 집합에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-134">`Overloads` can also be used to shadow an existing member, or set of overloaded members, in a base class.</span></span> <span data-ttu-id="37bfd-135">이런 방식으로 `Overloads`를 사용하는 경우 기본 클래스 멤버와 동일한 이름 및 동일한 매개 변수 목록을 사용하여 속성 또는 메서드를 선언하고 `Shadows` 키워드는 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-135">When you use `Overloads` in this way, you declare the property or method with the same name and the same parameter list as the base class member, and you do not supply the `Shadows` keyword.</span></span>  
  
 <span data-ttu-id="37bfd-136">`Overrides`를 사용하는 경우 라이브러리 API가 보다 쉽게 C#으로 작업할 수 있도록 컴파일러에서 암시적으로 `Overloads`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-136">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>  
  
 <span data-ttu-id="37bfd-137">`Overloads` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-137">The `Overloads` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="37bfd-138">Function 문</span><span class="sxs-lookup"><span data-stu-id="37bfd-138">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="37bfd-139">Operator 문</span><span class="sxs-lookup"><span data-stu-id="37bfd-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="37bfd-140">Property 문</span><span class="sxs-lookup"><span data-stu-id="37bfd-140">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="37bfd-141">Sub 문</span><span class="sxs-lookup"><span data-stu-id="37bfd-141">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="37bfd-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="37bfd-142">See also</span></span>
- [<span data-ttu-id="37bfd-143">Shadows</span><span class="sxs-lookup"><span data-stu-id="37bfd-143">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="37bfd-144">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="37bfd-144">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="37bfd-145">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="37bfd-145">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="37bfd-146">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="37bfd-146">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="37bfd-147">방법: 변환 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="37bfd-147">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
