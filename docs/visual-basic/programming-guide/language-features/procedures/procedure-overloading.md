---
title: 프로시저 오버로딩(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
ms.openlocfilehash: 4d90b81049197fbbf4a767b17399d3e9c80be0f7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975474"
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="93110-102">프로시저 오버로딩(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93110-102">Procedure Overloading (Visual Basic)</span></span>
<span data-ttu-id="93110-103">*오버 로드* 프로시저 이름은 같지만 다른 매개 변수 목록을 사용 하 여 여러 버전에서 정의 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="93110-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="93110-104">오버 로드의 용도 이름으로 구분할 필요 없이 프로시저의 밀접 한 관련이 있는 여러 버전을 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93110-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="93110-105">매개 변수 목록 변경 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="93110-105">You do this by varying the parameter list.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="93110-106">오버 로드 규칙</span><span class="sxs-lookup"><span data-stu-id="93110-106">Overloading Rules</span></span>  
 <span data-ttu-id="93110-107">프로시저를 오버 로드 하는 경우 다음 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93110-107">When you overload a procedure, the following rules apply:</span></span>  
  
-   <span data-ttu-id="93110-108">**이름이 같은**합니다.</span><span class="sxs-lookup"><span data-stu-id="93110-108">**Same Name**.</span></span> <span data-ttu-id="93110-109">각 오버 로드 된 버전에는 동일한 프로시저 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93110-109">Each overloaded version must use the same procedure name.</span></span>  
  
-   <span data-ttu-id="93110-110">**다른 서명을**합니다.</span><span class="sxs-lookup"><span data-stu-id="93110-110">**Different Signature**.</span></span> <span data-ttu-id="93110-111">각 오버 로드 된 버전의 다음 측면 중 하나 이상이 다른 모든 오버 로드 된 버전에서 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93110-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>  
  
    -   <span data-ttu-id="93110-112">매개 변수 개수</span><span class="sxs-lookup"><span data-stu-id="93110-112">Number of parameters</span></span>  
  
    -   <span data-ttu-id="93110-113">매개 변수의 순서</span><span class="sxs-lookup"><span data-stu-id="93110-113">Order of the parameters</span></span>  
  
    -   <span data-ttu-id="93110-114">매개 변수의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="93110-114">Data types of the parameters</span></span>  
  
    -   <span data-ttu-id="93110-115">형식 매개 변수 (제네릭 프로시저의 경우)의 수</span><span class="sxs-lookup"><span data-stu-id="93110-115">Number of type parameters (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="93110-116">반환 형식 (변환 연산자)에 해당</span><span class="sxs-lookup"><span data-stu-id="93110-116">Return type (only for a conversion operator)</span></span>  
  
     <span data-ttu-id="93110-117">프로시저 이름과 함께 이전 항목 이라고 합니다 *서명을* 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="93110-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="93110-118">오버 로드 된 프로시저를 호출 하면 컴파일러가 서명의 사용 하 여 호출 정의 올바르게 일치 하는지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="93110-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>  
  
-   <span data-ttu-id="93110-119">**서명의 일부가 아닌 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="93110-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="93110-120">시그니처를 변경 하지 않고 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93110-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="93110-121">특히, 다음 항목 중 하나 이상의 변경 하 여 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93110-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>  
  
    -   <span data-ttu-id="93110-122">프로시저 한정자 키워드와 같은 `Public`, `Shared`, 및 `Static`</span><span class="sxs-lookup"><span data-stu-id="93110-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>  
  
    -   <span data-ttu-id="93110-123">매개 변수 또는 형식 매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="93110-123">Parameter or type parameter names</span></span>  
  
    -   <span data-ttu-id="93110-124">형식 (제네릭 프로시저의 경우)에 대 한 매개 변수 제약 조건</span><span class="sxs-lookup"><span data-stu-id="93110-124">Type parameter constraints (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="93110-125">매개 변수 한정자 키워드와 같은 `ByRef` 및 `Optional`</span><span class="sxs-lookup"><span data-stu-id="93110-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>  
  
    -   <span data-ttu-id="93110-126">값을 반환 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="93110-126">Whether it returns a value</span></span>  
  
    -   <span data-ttu-id="93110-127">반환 값 (변환 연산자 제외)의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="93110-127">The data type of the return value (except for a conversion operator)</span></span>  
  
     <span data-ttu-id="93110-128">앞의 목록에 항목 서명의 일부가 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93110-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="93110-129">오버 로드 된 버전을 구분 하 고 사용할 수 없습니다, 있지만는 해당 서명이 올바르게 차별점 오버 로드 버전에서 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93110-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>  
  
-   <span data-ttu-id="93110-130">**런타임에 바인딩된 인수**합니다.</span><span class="sxs-lookup"><span data-stu-id="93110-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="93110-131">으로 적절 한 매개 변수를 선언 해야 오버 로드 된 버전을 런타임에 바인딩된 개체 변수를 전달 하려는 경우 <xref:System.Object>합니다.</span><span class="sxs-lookup"><span data-stu-id="93110-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>  
  
## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="93110-132">여러 버전의 프로시저</span><span class="sxs-lookup"><span data-stu-id="93110-132">Multiple Versions of a Procedure</span></span>  
 <span data-ttu-id="93110-133">작성 하는 가정 된 `Sub` 고객 계정 번호로 또는 이름으로 참조할 수 있게 되기를 원하는 고객의 잔액 하에 대 한 트랜잭션을 게시 하는 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="93110-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="93110-134">이 위해 서로 다른 두 정의할 수 있습니다 `Sub` 다음 예제와 같이 프로시저:</span><span class="sxs-lookup"><span data-stu-id="93110-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]  
  
### <a name="overloaded-versions"></a><span data-ttu-id="93110-135">오버 로드 된 버전</span><span class="sxs-lookup"><span data-stu-id="93110-135">Overloaded Versions</span></span>  
 <span data-ttu-id="93110-136">대신 단일 프로시저 이름을 오버 로드 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93110-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="93110-137">사용할 수는 [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드를 각 매개 변수 목록에 대 한 프로시저의 버전을 다음과 같이 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="93110-137">You can use the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
#### <a name="additional-overloads"></a><span data-ttu-id="93110-138">추가 오버 로드</span><span class="sxs-lookup"><span data-stu-id="93110-138">Additional Overloads</span></span>  
 <span data-ttu-id="93110-139">트랜잭션 시간을 허용 하려는 경우 `Decimal` 또는 `Single`, 추가로 오버 로드 하면 `post` 이 변형에 대 한 허용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="93110-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="93110-140">이 경우 앞의 예제에서 오버 로드 각각에 네 개 있는 `Sub` 프로시저 이름이 같지만 네 개의 서로 다른 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="93110-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>  
  
## <a name="advantages-of-overloading"></a><span data-ttu-id="93110-141">오버 로드의 장점</span><span class="sxs-lookup"><span data-stu-id="93110-141">Advantages of Overloading</span></span>  
 <span data-ttu-id="93110-142">프로시저 오버 로드의 장점은 호출의 유연한입니다.</span><span class="sxs-lookup"><span data-stu-id="93110-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="93110-143">사용 하는 `post` 앞의 예제에서 선언 된 프로시저 호출 코드로 고객 id를 가져올 수 있습니다를 `String` 또는 `Integer`, 다음 두 경우 모두 동일한 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="93110-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="93110-144">다음 예제는 이러한 과정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="93110-144">The following example illustrates this:</span></span>  
  
 [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
 [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a><span data-ttu-id="93110-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="93110-145">See also</span></span>
- [<span data-ttu-id="93110-146">절차</span><span class="sxs-lookup"><span data-stu-id="93110-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="93110-147">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="93110-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="93110-148">방법: 오버 로드 된 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="93110-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="93110-149">방법: 선택적 매개 변수를 사용 하는 프로시저 오버 로드</span><span class="sxs-lookup"><span data-stu-id="93110-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="93110-150">방법: 무한 개수의 매개 변수를 사용 하는 프로시저 오버 로드</span><span class="sxs-lookup"><span data-stu-id="93110-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="93110-151">프로시저를 오버로드할 때 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="93110-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="93110-152">오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="93110-152">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="93110-153">오버로드</span><span class="sxs-lookup"><span data-stu-id="93110-153">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="93110-154">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="93110-154">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
