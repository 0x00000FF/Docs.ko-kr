---
title: Byte 데이터 형식(Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b106005ff07f55e05ae66dba94041cd8b5c24bb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43732146"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="ceca9-102">Byte 데이터 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ceca9-102">Byte data type (Visual Basic)</span></span>
<span data-ttu-id="ceca9-103">값 범위에 있는 0에서 255 까지의 부호 없는 8 비트 (1 바이트) 정수를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="ceca9-104">설명</span><span class="sxs-lookup"><span data-stu-id="ceca9-104">Remarks</span></span>

<span data-ttu-id="ceca9-105">사용 된 `Byte` 이진 데이터를 포함 하도록 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="ceca9-106">`Byte`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="ceca9-107">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="ceca9-107">Literal assignments</span></span>

<span data-ttu-id="ceca9-108">선언 하 고 초기화할 수 있습니다는 `Byte` 변수 (Visual Basic 2017부터) 이진 리터럴을 또는 10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="ceca9-109">정수 계열 리터럴을의 범위를 벗어난 경우는 `Byte` (경우 즉, 보다 작거나 <xref:System.Byte.MinValue?displayProperty=nameWithType> 보다 크거나 <xref:System.Byte.MaxValue?displayProperty=nameWithType>), 컴파일 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="ceca9-110">다음 예제에서는 10 진수, 16 진수 표현 된 201 및 이진 리터럴로의 암시적으로 변환 됩니다 [정수](integer-data-type.md) 에 `byte` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="ceca9-111">접두사를 사용할 `&h` 또는 `&H` 16 진수 리터럴, 접두사를 나타내는 `&b` 또는 `&B` 이진 리터럴 및 접두사를 나타내는 `&o` 또는 `&O` 8 진수 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="ceca9-112">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="ceca9-113">Visual Basic 2017부터 사용할 수도 있습니다 밑줄 문자 `_`, 가독성 향상을 위해 숫자 구분 기호를 다음 예제와 같이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="ceca9-114">Visual Basic 15.5부터 사용할 수도 있습니다는 밑줄 문자 (`_`) 접두사 및 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="ceca9-115">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="ceca9-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="ceca9-116">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="ceca9-116">Programming tips</span></span>

-   <span data-ttu-id="ceca9-117">**음수를 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="ceca9-117">**Negative Numbers.**</span></span> <span data-ttu-id="ceca9-118">때문에 `Byte` 부호 없는 형식에는 음수를 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="ceca9-119">단항 빼기를 사용 하는 경우 (`-`) 형식으로 계산 되는 식에 연산자 `Byte`, Visual Basic 변환 식이 `Short` 첫 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
-   <span data-ttu-id="ceca9-120">**형식 변환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ceca9-120">**Format Conversions.**</span></span> <span data-ttu-id="ceca9-121">Visual Basic을 읽거나 파일을 작성 하는 경우, Dll, 메서드 및 속성을 호출할 때 자동 데이터 형식 간에 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="ceca9-122">에 저장 된 이진 데이터 `Byte` 변수 및 배열 이러한 형식으로 변환 하는 동안 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="ceca9-123">사용 하지 않아야는 `String` 의 내용이 ANSI 및 유니코드 형식 간에 변환 하는 동안 손상 될 수 있으므로 이진 데이터에 대 한 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

-   <span data-ttu-id="ceca9-124">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ceca9-124">**Widening.**</span></span> <span data-ttu-id="ceca9-125">`Byte` 데이터 형식으로 확장 되는지를 `Short`, `UShort`, `Integer`, `UInteger`를 `Long`, `ULong`, `Decimal`, `Single`, 또는 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="ceca9-126">즉, 변환할 수 있습니다 `Byte` 발생 없이 이러한 형식 중 하나에 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="ceca9-127">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="ceca9-127">**Type Characters.**</span></span> <span data-ttu-id="ceca9-128">`Byte` 에 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-128">`Byte` has no literal type character or identifier type character.</span></span>

-   <span data-ttu-id="ceca9-129">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="ceca9-129">**Framework Type.**</span></span> <span data-ttu-id="ceca9-130">.NET Framework에서 해당하는 형식은 <xref:System.Byte?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="ceca9-131">예제</span><span class="sxs-lookup"><span data-stu-id="ceca9-131">Example</span></span>

 <span data-ttu-id="ceca9-132">다음 예에서 `b` 되는 `Byte` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="ceca9-133">문은 변수의 범위 및 비트 시프트 연산자의 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a><span data-ttu-id="ceca9-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ceca9-134">See Also</span></span>

 <xref:System.Byte?displayProperty=nameWithType>  
 [<span data-ttu-id="ceca9-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ceca9-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="ceca9-136">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="ceca9-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="ceca9-137">변환 요약</span><span class="sxs-lookup"><span data-stu-id="ceca9-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="ceca9-138">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="ceca9-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
