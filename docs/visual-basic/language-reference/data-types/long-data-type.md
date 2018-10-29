---
title: Long 데이터 형식(Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: 040306b49bbf6b0f30556309457510ca873d8a74
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197225"
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="989cf-102">Long 데이터 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="989cf-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="989cf-103">포함 까지의 부호 있는 64 비트 (8 바이트) 정수 값-9223372036854775808에서 9223372036854775807 (9.2... E + 18).</span><span class="sxs-lookup"><span data-stu-id="989cf-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="989cf-104">설명</span><span class="sxs-lookup"><span data-stu-id="989cf-104">Remarks</span></span>

 <span data-ttu-id="989cf-105">사용 된 `Long` 데이터 형식에 맞게 너무 큰 정수를 포함 하는 `Integer` 데이터 형식.</span><span class="sxs-lookup"><span data-stu-id="989cf-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>  
  
 <span data-ttu-id="989cf-106">`Long`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="989cf-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="989cf-107">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="989cf-107">Literal assignments</span></span> 

<span data-ttu-id="989cf-108">선언 하 고 초기화할 수 있습니다는 `Long` 변수 (Visual Basic 2017부터) 이진 리터럴을 또는 10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="989cf-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="989cf-109">정수 리터럴이 `Long` 범위를 벗어나는 경우(즉 <xref:System.Int64.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Int64.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="989cf-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="989cf-110">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 4,294,967,296과 같은 정수가 `Long` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="989cf-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>
  
[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]  

> [!NOTE]
> <span data-ttu-id="989cf-111">접두사를 사용할 `&h` 또는 `&H` 16 진수 리터럴, 접두사를 나타내는 `&b` 또는 `&B` 이진 리터럴 및 접두사를 나타내는 `&o` 또는 `&O` 8 진수 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="989cf-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="989cf-112">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="989cf-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="989cf-113">Visual Basic 2017부터 사용할 수도 있습니다 밑줄 문자 `_`, 가독성 향상을 위해 숫자 구분 기호를 다음 예제와 같이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="989cf-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="989cf-114">Visual Basic 15.5부터 사용할 수도 있습니다는 밑줄 문자 (`_`) 접두사 및 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 합니다.</span><span class="sxs-lookup"><span data-stu-id="989cf-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="989cf-115">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="989cf-115">For example:</span></span>

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="989cf-116">숫자 리터럴을 포함할 수도 있습니다는 `L` [문자를 입력](../../programming-guide\language-features\data-types/type-characters.md) 나타내기 위해는 `Long` 다음 예제와 같이 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="989cf-116">Numeric literals can also include the `L` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a><span data-ttu-id="989cf-117">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="989cf-117">Programming tips</span></span>

-   <span data-ttu-id="989cf-118">**Interop 고려 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="989cf-118">**Interop Considerations.**</span></span> <span data-ttu-id="989cf-119">예제에서는 자동화 개체나 COM 개체에 대 한.NET Framework 용으로 작성 되지 구성 요소와 상호 작용 하는 경우에 유의 해야 `Long` 다른 환경에서 다른 데이터 너비 (32 비트)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989cf-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="989cf-120">이러한 구성 요소는 32 비트 인수를 전달 하는 경우로 선언 `Integer` 대신 `Long` 새 Visual Basic 코드에서.</span><span class="sxs-lookup"><span data-stu-id="989cf-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="989cf-121">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="989cf-121">**Widening.**</span></span> <span data-ttu-id="989cf-122">합니다 `Long` 데이터 형식으로 확장 되는지를 `Decimal`를 `Single`, 또는 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="989cf-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="989cf-123">이는 `Long` 오류 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType>를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="989cf-123">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="989cf-124">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="989cf-124">**Type Characters.**</span></span> <span data-ttu-id="989cf-125">리터럴 형식 문자 `L`를 리터럴에 추가하면 `Long` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="989cf-125">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="989cf-126">식별자 형식 문자 `&`를 식별자에 추가하면 `Long`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="989cf-126">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>  
  
-   <span data-ttu-id="989cf-127">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="989cf-127">**Framework Type.**</span></span> <span data-ttu-id="989cf-128">.NET Framework에서 해당하는 형식은 <xref:System.Int64?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="989cf-128">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>  

## <a name="see-also"></a><span data-ttu-id="989cf-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="989cf-129">See also</span></span>

<span data-ttu-id="989cf-130"><xref:System.Int64>
[데이터 형식](../../../visual-basic/language-reference/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="989cf-130"><xref:System.Int64>
[Data Types](../../../visual-basic/language-reference/data-types/index.md) </span></span>  
<span data-ttu-id="989cf-131">[정수 데이터 형식](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="989cf-131">[Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span></span>  
<span data-ttu-id="989cf-132">[Short 데이터 형식](../../../visual-basic/language-reference/data-types/short-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="989cf-132">[Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md) </span></span>  
<span data-ttu-id="989cf-133">[형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="989cf-133">[Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="989cf-134">[변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span><span class="sxs-lookup"><span data-stu-id="989cf-134">[Conversion Summary](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span></span>  
[<span data-ttu-id="989cf-135">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="989cf-135">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
