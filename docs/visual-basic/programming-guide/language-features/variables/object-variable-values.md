---
title: 개체 변수 값(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: c17c5f85952596f0a080ca473e8f792740e66b8f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840395"
---
# <a name="object-variable-values-visual-basic"></a><span data-ttu-id="4c84c-102">개체 변수 값(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c84c-102">Object Variable Values (Visual Basic)</span></span>
<span data-ttu-id="4c84c-103">변수를 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) 모든 형식의 데이터를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c84c-103">A variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) can refer to data of any type.</span></span> <span data-ttu-id="4c84c-104">에 저장 되는 값을 `Object` 변수는 특정 위치에 보관 메모리 변수 자체는 데이터에 대 한 포인터를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c84c-104">The value you store in an `Object` variable is kept elsewhere in memory, while the variable itself holds a pointer to the data.</span></span>  
  
## <a name="object-classifier-functions"></a><span data-ttu-id="4c84c-105">분류자 함수 개체</span><span class="sxs-lookup"><span data-stu-id="4c84c-105">Object Classifier Functions</span></span>  
 <span data-ttu-id="4c84c-106">항목에 대 한 정보를 반환 하는 함수를 제공 하는 Visual Basic을 `Object` 변수가 참조 하는 다음 표에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c84c-106">Visual Basic supplies functions that return information about what an `Object` variable refers to, as shown in the following table.</span></span>  
  
|<span data-ttu-id="4c84c-107">함수</span><span class="sxs-lookup"><span data-stu-id="4c84c-107">Function</span></span>|<span data-ttu-id="4c84c-108">개체 변수가 참조 하는 경우 True를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c84c-108">Returns True if the Object variable refers to</span></span>|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|<span data-ttu-id="4c84c-109">단일 값이 아닌 값의 배열</span><span class="sxs-lookup"><span data-stu-id="4c84c-109">An array of values, rather than a single value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|<span data-ttu-id="4c84c-110">A [날짜 데이터 형식](../../../../visual-basic/language-reference/data-types/date-data-type.md) 값 또는 날짜 및 시간 값으로 해석 될 수 있는 문자열</span><span class="sxs-lookup"><span data-stu-id="4c84c-110">A [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) value, or a string that can be interpreted as a date and time value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|<span data-ttu-id="4c84c-111">형식의 개체 <xref:System.DBNull>, 누락 되었거나 존재 하지 않는 데이터를 나타내는</span><span class="sxs-lookup"><span data-stu-id="4c84c-111">An object of type <xref:System.DBNull>, which represents missing or nonexistent data</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|<span data-ttu-id="4c84c-112">파생 되는 예외 개체 <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="4c84c-112">An exception object, which derives from <xref:System.Exception></span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|<span data-ttu-id="4c84c-113">[Nothing](../../../../visual-basic/language-reference/nothing.md)에 개체가 없는 변수에 현재 할당 되어, 즉</span><span class="sxs-lookup"><span data-stu-id="4c84c-113">[Nothing](../../../../visual-basic/language-reference/nothing.md), that is, no object is currently assigned to the variable</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|<span data-ttu-id="4c84c-114">숫자 또는 숫자로 해석 될 수 있는 문자열</span><span class="sxs-lookup"><span data-stu-id="4c84c-114">A number, or a string that can be interpreted as a number</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|<span data-ttu-id="4c84c-115">참조 형식 (예: 문자열, 배열, 대리자 또는 클래스 형식)</span><span class="sxs-lookup"><span data-stu-id="4c84c-115">A reference type (such as a string, array, delegate, or class type)</span></span>|  
  
 <span data-ttu-id="4c84c-116">작업 또는 프로시저에 잘못 된 값을 제출 하지 않으려면 이러한 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c84c-116">You can use these functions to avoid submitting an invalid value to an operation or a procedure.</span></span>  
  
## <a name="typeof-operator"></a><span data-ttu-id="4c84c-117">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="4c84c-117">TypeOf Operator</span></span>  
 <span data-ttu-id="4c84c-118">사용할 수도 있습니다는 [TypeOf 연산자](../../../../visual-basic/language-reference/operators/typeof-operator.md) 개체 변수를 특정 데이터 형식이 현재 참조 하는지 여부를 확인 하려면.</span><span class="sxs-lookup"><span data-stu-id="4c84c-118">You can also use the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to determine whether an object variable currently refers to a specific data type.</span></span> <span data-ttu-id="4c84c-119">`TypeOf`... `Is` 식이 `True` 피연산자의 런타임 형식에서 파생 되거나 지정 된 형식을 구현 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="4c84c-119">The `TypeOf`...`Is` expression evaluates to `True` if the run-time type of the operand is derived from or implements the specified type.</span></span>  
  
 <span data-ttu-id="4c84c-120">다음 예제에서는 `TypeOf` 개체 변수 값 및 참조 형식을 참조 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c84c-120">The following example uses `TypeOf` on object variables referring to value and reference types.</span></span>  
  
```  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 <span data-ttu-id="4c84c-121">앞의 예제는 다음 줄을 작성 합니다 **디버그** 창:</span><span class="sxs-lookup"><span data-stu-id="4c84c-121">The preceding example writes the following lines to the **Debug** window:</span></span>  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 <span data-ttu-id="4c84c-122">개체 변수 `num` 데이터 형식 가리킵니다 `Integer`, 및 `frm` 클래스의 개체를 참조 <xref:System.Windows.Forms.Form>합니다.</span><span class="sxs-lookup"><span data-stu-id="4c84c-122">The object variable `num` refers to data of type `Integer`, and `frm` refers to an object of class <xref:System.Windows.Forms.Form>.</span></span>  
  
## <a name="object-arrays"></a><span data-ttu-id="4c84c-123">개체 배열</span><span class="sxs-lookup"><span data-stu-id="4c84c-123">Object Arrays</span></span>  
 <span data-ttu-id="4c84c-124">선언 하 고 배열을 사용 하 여 `Object` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4c84c-124">You can declare and use an array of `Object` variables.</span></span> <span data-ttu-id="4c84c-125">다양 한 데이터 형식 및 개체 클래스를 처리 해야 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c84c-125">This is useful when you need to handle a variety of data types and object classes.</span></span> <span data-ttu-id="4c84c-126">배열의 모든 요소에는 동일한 선언 된 데이터 형식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c84c-126">All the elements in an array must have the same declared data type.</span></span> <span data-ttu-id="4c84c-127">이 데이터 형식으로 선언 `Object` 개체를 저장 하 고 클래스 인스턴스의 배열에 다른 데이터 형식과 함께 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c84c-127">Declaring this data type as `Object` allows you to store objects and class instances alongside other data types in the array.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c84c-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="4c84c-128">See also</span></span>

- [<span data-ttu-id="4c84c-129">개체 변수</span><span class="sxs-lookup"><span data-stu-id="4c84c-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="4c84c-130">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="4c84c-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="4c84c-131">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="4c84c-131">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="4c84c-132">방법: 개체의 현재 인스턴스 참조</span><span class="sxs-lookup"><span data-stu-id="4c84c-132">How to: Refer to the Current Instance of an Object</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="4c84c-133">방법: 개체 변수가 참조 하는 형식 확인</span><span class="sxs-lookup"><span data-stu-id="4c84c-133">How to: Determine What Type an Object Variable Refers To</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)
- [<span data-ttu-id="4c84c-134">방법: 두 개체가 관련이 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c84c-134">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="4c84c-135">방법: 두 개체가 동일한 지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c84c-135">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
- [<span data-ttu-id="4c84c-136">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4c84c-136">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
