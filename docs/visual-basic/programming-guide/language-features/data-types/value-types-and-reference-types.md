---
title: Value Types and Reference Types
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: f25caec43b7118b7b64db1b14516b0c5ea80f4f6
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504885"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="9b7b3-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="9b7b3-102">Value Types and Reference Types</span></span>
<span data-ttu-id="9b7b3-103">두 가지 종류의 Visual Basic의 형식: 형식 및 값 형식을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-103">There are two kinds of types in Visual Basic: reference types and value types.</span></span> <span data-ttu-id="9b7b3-104">참조 형식의 변수에는 데이터(개체)에 대한 참조가 저장되며, 값 형식의 변수에는 해당 데이터가 직접 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="9b7b3-105">참조 형식에서는 두 가지 변수가 같은 개체를 참조할 수 있으므로 한 변수에 대한 작업이 다른 변수에서 참조하는 개체에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="9b7b3-106">값 형식에서는 각 변수에 데이터의 자체 복사본 및 작업으로 다른 변수를 하나에 대 한 불가능 (의 경우를 제외 하 고는 [ByRef 매개 변수 한정자](../../../language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="9b7b3-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of the [ByRef modifier on parameters](../../../language-reference/modifiers/byref.md)).</span></span>
  
## <a name="value-types"></a><span data-ttu-id="9b7b3-107">값 형식</span><span class="sxs-lookup"><span data-stu-id="9b7b3-107">Value Types</span></span>  
 <span data-ttu-id="9b7b3-108">데이터 형식은 *값 형식* 자신의 메모리 할당 데이터 보유 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-108">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="9b7b3-109">값 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-109">Value types include the following:</span></span>  
  
- <span data-ttu-id="9b7b3-110">모든 숫자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9b7b3-110">All numeric data types</span></span>  
  
- <span data-ttu-id="9b7b3-111">`Boolean`, `Char`및 `Date`</span><span class="sxs-lookup"><span data-stu-id="9b7b3-111">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="9b7b3-112">해당 멤버 참조 형식인 경우에 모든 구조</span><span class="sxs-lookup"><span data-stu-id="9b7b3-112">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="9b7b3-113">해당 기본 형식이 항상 이므로 열거형 `SByte`, `Short`를 `Integer`, `Long`를 `Byte`를 `UShort`, `UInteger`, 또는 `ULong`</span><span class="sxs-lookup"><span data-stu-id="9b7b3-113">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="9b7b3-114">모든 구조체가 값 형식이 참조 형식 멤버를 포함 하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-114">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="9b7b3-115">이 따라서가에 대 한 값과 같은 형식이 `Char` 고 `Integer` .net 구조체에서 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-115">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="9b7b3-116">예를 들어, 예약 된 키워드를 사용 하 여 값 형식을 선언할 수 있습니다 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-116">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="9b7b3-117">사용할 수도 있습니다는 `New` 값 형식을 초기화 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-117">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="9b7b3-118">형식 매개 변수를 사용 하는 생성자가 하는 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-118">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="9b7b3-119">이 예로 <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> 새 빌드는 생성자 `Decimal` 에서 제공 된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-119">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="9b7b3-120">참조 형식</span><span class="sxs-lookup"><span data-stu-id="9b7b3-120">Reference Types</span></span>  
 <span data-ttu-id="9b7b3-121">A *유형을 참조* 해당 데이터에 대 한 참조를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-121">A *reference type* stores a reference to its data.</span></span> <span data-ttu-id="9b7b3-122">참조 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-122">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="9b7b3-123">모든 배열의 해당 요소 값 형식인 경우에</span><span class="sxs-lookup"><span data-stu-id="9b7b3-123">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="9b7b3-124">클래스 형식 <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="9b7b3-124">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="9b7b3-125">대리자</span><span class="sxs-lookup"><span data-stu-id="9b7b3-125">Delegates</span></span>  
  
 <span data-ttu-id="9b7b3-126">클래스는 *유형을 참조*합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-126">A class is a *reference type*.</span></span> <span data-ttu-id="9b7b3-127">모든 배열은 참조 형식 인지, 해당 멤버 값 형식인 경우에 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="9b7b3-128">모든 참조 형식을 나타내므로 기본.NET Framework 클래스를 사용 해야 합니다 [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md) 초기화할 때 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="9b7b3-129">다음 문은 배열을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="9b7b3-130">형식 없는 요소</span><span class="sxs-lookup"><span data-stu-id="9b7b3-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="9b7b3-131">그 중 하나에서 선언 된 요소에 대 한 데이터 형식으로 지정할 수 없으므로 다음 프로그래밍 요소 형식으로 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="9b7b3-132">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="9b7b3-132">Namespaces</span></span>  
  
- <span data-ttu-id="9b7b3-133">모듈</span><span class="sxs-lookup"><span data-stu-id="9b7b3-133">Modules</span></span>  
  
- <span data-ttu-id="9b7b3-134">이벤트</span><span class="sxs-lookup"><span data-stu-id="9b7b3-134">Events</span></span>  
  
- <span data-ttu-id="9b7b3-135">속성 및 절차</span><span class="sxs-lookup"><span data-stu-id="9b7b3-135">Properties and procedures</span></span>  
  
- <span data-ttu-id="9b7b3-136">변수, 상수 및 필드</span><span class="sxs-lookup"><span data-stu-id="9b7b3-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="9b7b3-137">개체 데이터 형식 사용</span><span class="sxs-lookup"><span data-stu-id="9b7b3-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="9b7b3-138">참조 형식 또는 값 형식 변수에 할당할 수 있습니다는 `Object` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="9b7b3-139">`Object` 변수 항상 데이터를 데이터 자체에 대 한 참조를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-139">An `Object` variable always holds a reference to the data, never the data itself.</span></span> <span data-ttu-id="9b7b3-140">그러나 값 형식을 할당 하는 경우는 `Object` 변수인 것 처럼 동작 자체 데이터를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="9b7b3-141">자세한 내용은 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="9b7b3-142">여부를 확인할 수 있습니다는 `Object` 변수 역할을 하는 참조 형식 또는 값 형식을 전달 하 여는 <xref:Microsoft.VisualBasic.Information.IsReference%2A> 에서 메서드는 <xref:Microsoft.VisualBasic.Information> 의 클래스는 <xref:Microsoft.VisualBasic?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="9b7b3-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> 반환 `True` 경우의 콘텐츠는 `Object` 변수에 참조 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b3-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b7b3-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="9b7b3-144">See also</span></span>

- [<span data-ttu-id="9b7b3-145">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="9b7b3-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="9b7b3-146">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="9b7b3-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="9b7b3-147">Structure 문</span><span class="sxs-lookup"><span data-stu-id="9b7b3-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="9b7b3-148">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="9b7b3-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="9b7b3-149">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9b7b3-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="9b7b3-150">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9b7b3-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
