---
title: Short 데이터 형식(Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: d4dab1a72d1e240bc428b2c6b83a722584e35ecc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971797"
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="95b51-102">Short 데이터 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95b51-102">Short data type (Visual Basic)</span></span>
<span data-ttu-id="95b51-103">부호 있는 16 비트 (2 바이트) 정수 값 범위에 있는-32,768부터 32,767 까지의 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95b51-104">설명</span><span class="sxs-lookup"><span data-stu-id="95b51-104">Remarks</span></span>  
 <span data-ttu-id="95b51-105">사용 된 `Short` 의 전체 데이터 너비를 필요 하지 않은 정수 값을 포함 하는 데이터 형식 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="95b51-106">일부 경우에 공용 언어 런타임 팩 수에 `Short` 변수 밀접 하 게 함께 및 메모리 사용량을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="95b51-107">`Short`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="95b51-108">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="95b51-108">Literal assignments</span></span>

<span data-ttu-id="95b51-109">선언 하 고 초기화할 수 있습니다는 `Short` 변수 (Visual Basic 2017부터) 이진 리터럴을 또는 10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="95b51-110">정수 리터럴이 `Short` 범위를 벗어나는 경우(즉 <xref:System.Int16.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Int16.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="95b51-111">다음 예제에서는 10 진수, 16 진수 표현 된 1,034와 같은 정수가 및 이진 리터럴로의 암시적으로 변환 됩니다 [정수](integer-data-type.md) 에 `Short` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="95b51-112">접두사를 사용할 `&h` 또는 `&H` 16 진수 리터럴, 접두사를 나타내는 `&b` 또는 `&B` 이진 리터럴 및 접두사를 나타내는 `&o` 또는 `&O` 8 진수 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="95b51-113">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="95b51-114">Visual Basic 2017부터 사용할 수도 있습니다 밑줄 문자 `_`, 가독성 향상을 위해 숫자 구분 기호를 다음 예제와 같이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="95b51-115">Visual Basic 15.5부터 사용할 수도 있습니다는 밑줄 문자 (`_`) 접두사 및 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="95b51-116">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="95b51-116">For example:</span></span>

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="95b51-117">숫자 리터럴을 포함할 수도 있습니다는 `S` [문자를 입력](../../programming-guide/language-features/data-types/type-characters.md) 나타내기 위해는 `Short` 다음 예제와 같이 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-117">Numeric literals can also include the `S` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a><span data-ttu-id="95b51-118">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="95b51-118">Programming tips</span></span>

- <span data-ttu-id="95b51-119">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="95b51-119">**Widening.**</span></span> <span data-ttu-id="95b51-120">`Short` 데이터 형식으로 확장 되는지를 `Integer`를 `Long`, `Decimal`를 `Single`, 또는 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-120">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="95b51-121">이는 `Short` 오류 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType>를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-121">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="95b51-122">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="95b51-122">**Type Characters.**</span></span> <span data-ttu-id="95b51-123">리터럴 형식 문자 `S`를 리터럴에 추가하면 `Short` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-123">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="95b51-124">`Short` 에 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-124">`Short` has no identifier type character.</span></span>  
  
- <span data-ttu-id="95b51-125">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="95b51-125">**Framework Type.**</span></span> <span data-ttu-id="95b51-126">.NET Framework에서 해당하는 형식은 <xref:System.Int16?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="95b51-126">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95b51-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="95b51-127">See also</span></span>

- <xref:System.Int16?displayProperty=nameWithType>
- [<span data-ttu-id="95b51-128">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="95b51-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="95b51-129">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="95b51-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="95b51-130">변환 요약</span><span class="sxs-lookup"><span data-stu-id="95b51-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="95b51-131">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="95b51-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="95b51-132">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="95b51-132">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="95b51-133">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="95b51-133">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
