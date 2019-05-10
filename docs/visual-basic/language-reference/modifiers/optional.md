---
title: Optional(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: 40605d4843bfccf9d2819b3ec6f2ef65f9e9cf9a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661322"
---
# <a name="optional-visual-basic"></a><span data-ttu-id="dd7ec-102">Optional(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd7ec-102">Optional (Visual Basic)</span></span>
<span data-ttu-id="dd7ec-103">프로시저를 호출할 때 프로시저 인수를 생략할 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd7ec-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd7ec-104">설명</span><span class="sxs-lookup"><span data-stu-id="dd7ec-104">Remarks</span></span>  
 <span data-ttu-id="dd7ec-105">각 선택적 매개 변수에 상수 식 해당 매개 변수의 기본 값으로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd7ec-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="dd7ec-106">식이 계산 되는 경우 [Nothing](../../../visual-basic/language-reference/nothing.md), 값 데이터 형식의 기본 값 매개 변수의 기본값으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd7ec-106">If the expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>  
  
 <span data-ttu-id="dd7ec-107">선택적 매개 변수를 포함 하는 매개 변수 목록에서 오는 모든 매개 변수를 선택적 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd7ec-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>  
  
 <span data-ttu-id="dd7ec-108">`Optional` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd7ec-108">The `Optional` modifier can be used in these contexts:</span></span>  
  
- [<span data-ttu-id="dd7ec-109">Declare 문</span><span class="sxs-lookup"><span data-stu-id="dd7ec-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
- [<span data-ttu-id="dd7ec-110">Function 문</span><span class="sxs-lookup"><span data-stu-id="dd7ec-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
- [<span data-ttu-id="dd7ec-111">Property 문</span><span class="sxs-lookup"><span data-stu-id="dd7ec-111">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
- [<span data-ttu-id="dd7ec-112">Sub 문</span><span class="sxs-lookup"><span data-stu-id="dd7ec-112">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  <span data-ttu-id="dd7ec-113">선택적 매개 변수 없이 프로시저를 호출할 때에 위치 또는 이름으로 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd7ec-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="dd7ec-114">자세한 내용은 [위치 및 이름별 인수 전달](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd7ec-114">For more information, see [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd7ec-115">또한 오버 로드를 사용 하 여 선택적 매개 변수가 있는 프로시저를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd7ec-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="dd7ec-116">하나의 선택적 매개 변수를 사용 하는 경우에 두 가지 오버 로드 된 버전의 프로시저 매개 변수를 허용 하는 하나, 하나는 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd7ec-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="dd7ec-117">자세한 내용은 [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd7ec-117">For more information, see [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd7ec-118">예제</span><span class="sxs-lookup"><span data-stu-id="dd7ec-118">Example</span></span>  
 <span data-ttu-id="dd7ec-119">다음 예제에서는 선택적 매개 변수가 있는 프로시저를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd7ec-119">The following example defines a procedure that has an optional parameter.</span></span>  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a><span data-ttu-id="dd7ec-120">예제</span><span class="sxs-lookup"><span data-stu-id="dd7ec-120">Example</span></span>  
 <span data-ttu-id="dd7ec-121">다음 예제에서는 이름으로 전달 된 인수를 사용 하 여 프로시저 위치에서 전달 된 인수를 사용 하 여 호출 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd7ec-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="dd7ec-122">프로시저에 두 개의 선택적 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="dd7ec-122">The procedure has two optional parameters.</span></span>  
  
 [!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="dd7ec-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="dd7ec-123">See also</span></span>

- [<span data-ttu-id="dd7ec-124">매개 변수 목록</span><span class="sxs-lookup"><span data-stu-id="dd7ec-124">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)
- [<span data-ttu-id="dd7ec-125">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="dd7ec-125">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="dd7ec-126">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="dd7ec-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
