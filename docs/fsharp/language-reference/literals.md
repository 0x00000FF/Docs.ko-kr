---
title: 리터럴(F#)
description: 'F # 프로그래밍 언어의 리터럴 형식에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: e6d34acd928edce8447c793105b08085ab0757b9
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087627"
---
# <a name="literals"></a><span data-ttu-id="e95a5-103">리터럴</span><span class="sxs-lookup"><span data-stu-id="e95a5-103">Literals</span></span>

> [!NOTE]
<span data-ttu-id="e95a5-104">이 문서의 API 참조 링크 하면 MSDN (당분간).</span><span class="sxs-lookup"><span data-stu-id="e95a5-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="e95a5-105">이 항목에서는 F #의 리터럴 형식을 지정 하는 방법을 보여 주는 테이블을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e95a5-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="e95a5-106">리터럴 형식</span><span class="sxs-lookup"><span data-stu-id="e95a5-106">Literal Types</span></span>

<span data-ttu-id="e95a5-107">다음 표에서 F #의 리터럴 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e95a5-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="e95a5-108">16 진수 표기법으로 숫자를 나타내는 문자; 대/소문자 구분 하지 않습니다. 문자 형식을 식별 하는 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e95a5-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="e95a5-109">형식</span><span class="sxs-lookup"><span data-stu-id="e95a5-109">Type</span></span>|<span data-ttu-id="e95a5-110">설명</span><span class="sxs-lookup"><span data-stu-id="e95a5-110">Description</span></span>|<span data-ttu-id="e95a5-111">접미사 또는 접두사</span><span class="sxs-lookup"><span data-stu-id="e95a5-111">Suffix or prefix</span></span>|<span data-ttu-id="e95a5-112">예제</span><span class="sxs-lookup"><span data-stu-id="e95a5-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="e95a5-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="e95a5-113">sbyte</span></span>|<span data-ttu-id="e95a5-114">부호 있는 8 비트 정수</span><span class="sxs-lookup"><span data-stu-id="e95a5-114">signed 8-bit integer</span></span>|<span data-ttu-id="e95a5-115">y</span><span class="sxs-lookup"><span data-stu-id="e95a5-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="e95a5-116">byte</span><span class="sxs-lookup"><span data-stu-id="e95a5-116">byte</span></span>|<span data-ttu-id="e95a5-117">부호 없는 8 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="e95a5-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="e95a5-118">uy</span><span class="sxs-lookup"><span data-stu-id="e95a5-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="e95a5-119">int16</span><span class="sxs-lookup"><span data-stu-id="e95a5-119">int16</span></span>|<span data-ttu-id="e95a5-120">부호 있는 16 비트 정수</span><span class="sxs-lookup"><span data-stu-id="e95a5-120">signed 16-bit integer</span></span>|<span data-ttu-id="e95a5-121">s</span><span class="sxs-lookup"><span data-stu-id="e95a5-121">s</span></span>|`86s`|
|<span data-ttu-id="e95a5-122">uint16</span><span class="sxs-lookup"><span data-stu-id="e95a5-122">uint16</span></span>|<span data-ttu-id="e95a5-123">부호 없는 16 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="e95a5-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="e95a5-124">us</span><span class="sxs-lookup"><span data-stu-id="e95a5-124">us</span></span>|`86us`|
|<span data-ttu-id="e95a5-125">int</span><span class="sxs-lookup"><span data-stu-id="e95a5-125">int</span></span><br /><br /><span data-ttu-id="e95a5-126">int32</span><span class="sxs-lookup"><span data-stu-id="e95a5-126">int32</span></span>|<span data-ttu-id="e95a5-127">부호 있는 32 비트 정수</span><span class="sxs-lookup"><span data-stu-id="e95a5-127">signed 32-bit integer</span></span>|<span data-ttu-id="e95a5-128">l 또는 없음</span><span class="sxs-lookup"><span data-stu-id="e95a5-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="e95a5-129">uint</span><span class="sxs-lookup"><span data-stu-id="e95a5-129">uint</span></span><br /><br /><span data-ttu-id="e95a5-130">uint32</span><span class="sxs-lookup"><span data-stu-id="e95a5-130">uint32</span></span>|<span data-ttu-id="e95a5-131">부호 없는 32 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="e95a5-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="e95a5-132">u 또는 ul</span><span class="sxs-lookup"><span data-stu-id="e95a5-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="e95a5-133">unativeint</span><span class="sxs-lookup"><span data-stu-id="e95a5-133">unativeint</span></span>|<span data-ttu-id="e95a5-134">부호 없는 자연 수는 네이티브 포인터</span><span class="sxs-lookup"><span data-stu-id="e95a5-134">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="e95a5-135">취소</span><span class="sxs-lookup"><span data-stu-id="e95a5-135">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="e95a5-136">int64</span><span class="sxs-lookup"><span data-stu-id="e95a5-136">int64</span></span>|<span data-ttu-id="e95a5-137">부호 있는 64 비트 정수</span><span class="sxs-lookup"><span data-stu-id="e95a5-137">signed 64-bit integer</span></span>|<span data-ttu-id="e95a5-138">L</span><span class="sxs-lookup"><span data-stu-id="e95a5-138">L</span></span>|`86L`|
|<span data-ttu-id="e95a5-139">uint64</span><span class="sxs-lookup"><span data-stu-id="e95a5-139">uint64</span></span>|<span data-ttu-id="e95a5-140">부호 없는 64 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="e95a5-140">unsigned 64-bit natural number</span></span>|<span data-ttu-id="e95a5-141">UL</span><span class="sxs-lookup"><span data-stu-id="e95a5-141">UL</span></span>|`86UL`|
|<span data-ttu-id="e95a5-142">단일 float32</span><span class="sxs-lookup"><span data-stu-id="e95a5-142">single, float32</span></span>|<span data-ttu-id="e95a5-143">32 비트 부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="e95a5-143">32-bit floating point number</span></span>|<span data-ttu-id="e95a5-144">F 또는 f</span><span class="sxs-lookup"><span data-stu-id="e95a5-144">F or f</span></span>|<span data-ttu-id="e95a5-145">`4.14F` 또는 `4.14f`</span><span class="sxs-lookup"><span data-stu-id="e95a5-145">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="e95a5-146">lf</span><span class="sxs-lookup"><span data-stu-id="e95a5-146">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="e95a5-147">float; double</span><span class="sxs-lookup"><span data-stu-id="e95a5-147">float; double</span></span>|<span data-ttu-id="e95a5-148">64 비트 부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="e95a5-148">64-bit floating point number</span></span>|<span data-ttu-id="e95a5-149">없음</span><span class="sxs-lookup"><span data-stu-id="e95a5-149">none</span></span>|<span data-ttu-id="e95a5-150">`4.14`, `2.3E+32` 또는 `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="e95a5-150">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="e95a5-151">LF</span><span class="sxs-lookup"><span data-stu-id="e95a5-151">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="e95a5-152">bigint</span><span class="sxs-lookup"><span data-stu-id="e95a5-152">bigint</span></span>|<span data-ttu-id="e95a5-153">64 비트 표현으로 제한 되지 않는 정수</span><span class="sxs-lookup"><span data-stu-id="e95a5-153">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="e95a5-154">I</span><span class="sxs-lookup"><span data-stu-id="e95a5-154">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="e95a5-155">decimal</span><span class="sxs-lookup"><span data-stu-id="e95a5-155">decimal</span></span>|<span data-ttu-id="e95a5-156">고정된 소수점 또는 유리수로 표현 되는 소수</span><span class="sxs-lookup"><span data-stu-id="e95a5-156">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="e95a5-157">M 또는 m</span><span class="sxs-lookup"><span data-stu-id="e95a5-157">M or m</span></span>|<span data-ttu-id="e95a5-158">`0.7833M` 또는 `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="e95a5-158">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="e95a5-159">Char</span><span class="sxs-lookup"><span data-stu-id="e95a5-159">Char</span></span>|<span data-ttu-id="e95a5-160">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="e95a5-160">Unicode character</span></span>|<span data-ttu-id="e95a5-161">없음</span><span class="sxs-lookup"><span data-stu-id="e95a5-161">none</span></span>|`'a'`|
|<span data-ttu-id="e95a5-162">문자열</span><span class="sxs-lookup"><span data-stu-id="e95a5-162">String</span></span>|<span data-ttu-id="e95a5-163">유니코드 문자열</span><span class="sxs-lookup"><span data-stu-id="e95a5-163">Unicode string</span></span>|<span data-ttu-id="e95a5-164">없음</span><span class="sxs-lookup"><span data-stu-id="e95a5-164">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="e95a5-165">또는</span><span class="sxs-lookup"><span data-stu-id="e95a5-165">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="e95a5-166">또는</span><span class="sxs-lookup"><span data-stu-id="e95a5-166">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="e95a5-167">또는</span><span class="sxs-lookup"><span data-stu-id="e95a5-167">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="e95a5-168">참고 항목 [문자열](Strings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e95a5-168">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="e95a5-169">byte</span><span class="sxs-lookup"><span data-stu-id="e95a5-169">byte</span></span>|<span data-ttu-id="e95a5-170">ASCII 문자</span><span class="sxs-lookup"><span data-stu-id="e95a5-170">ASCII character</span></span>|<span data-ttu-id="e95a5-171">B</span><span class="sxs-lookup"><span data-stu-id="e95a5-171">B</span></span>|`'a'B`|
|<span data-ttu-id="e95a5-172">byte[]</span><span class="sxs-lookup"><span data-stu-id="e95a5-172">byte[]</span></span>|<span data-ttu-id="e95a5-173">ASCII 문자열</span><span class="sxs-lookup"><span data-stu-id="e95a5-173">ASCII string</span></span>|<span data-ttu-id="e95a5-174">B</span><span class="sxs-lookup"><span data-stu-id="e95a5-174">B</span></span>|`"text"B`|
|<span data-ttu-id="e95a5-175">String 또는 byte]</span><span class="sxs-lookup"><span data-stu-id="e95a5-175">String or byte[]</span></span>|<span data-ttu-id="e95a5-176">축 자 문자열</span><span class="sxs-lookup"><span data-stu-id="e95a5-176">verbatim string</span></span>|<span data-ttu-id="e95a5-177">@ 접두사</span><span class="sxs-lookup"><span data-stu-id="e95a5-177">@ prefix</span></span>|<span data-ttu-id="e95a5-178">`@"\\server\share"` (유니코드)</span><span class="sxs-lookup"><span data-stu-id="e95a5-178">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="e95a5-179">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="e95a5-179">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="e95a5-180">설명</span><span class="sxs-lookup"><span data-stu-id="e95a5-180">Remarks</span></span>

<span data-ttu-id="e95a5-181">유니코드 문자열에는 명시적 인코딩을 사용 하 여 지정할 수 있는 포함 될 수 있습니다 `\u` 뒤에 16 비트 16 진수 코드 또는 UTF-32 인코딩을 사용 하 여 지정할 수 있는 `\U` 뒤에 유니코드를 나타내는 32 비트 16 진수 코드 서로게이트 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="e95a5-181">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="e95a5-182">F # 3.1부터 사용할 수는 `+` 문자열 리터럴을 결합 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e95a5-182">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="e95a5-183">비트 이용할 수 있습니다 또는 (`|||`) 열거형 플래그를 결합 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="e95a5-183">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="e95a5-184">예를 들어, 다음 코드는 F # 3.1에서 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="e95a5-184">For example, the following code is legal in F# 3.1:</span></span>

```fsharp
[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

<span data-ttu-id="e95a5-185">다른 비트 연산자의 사용이 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e95a5-185">The use of other bitwise operators isn't allowed.</span></span>

## <a name="named-literals"></a><span data-ttu-id="e95a5-186">명명 된 리터럴</span><span class="sxs-lookup"><span data-stu-id="e95a5-186">Named Literals</span></span>

<span data-ttu-id="e95a5-187">값은 상수를 사용 하 여 표시할 수 있습니다 합니다 [리터럴](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e95a5-187">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="e95a5-188">이 특성에 적용 하면 값을 상수로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="e95a5-188">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="e95a5-189">패턴 일치 식에서에서 소문자로 시작 하는 식별자는 항상 바인딩을 위한 변수로 처리 됩니다 것이 아니라 리터럴로 하므로 일반적으로 사용 해야 문자가 대문자 리터럴을 정의할 때.</span><span class="sxs-lookup"><span data-stu-id="e95a5-189">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="e95a5-190">다른 밑에 있는 정수</span><span class="sxs-lookup"><span data-stu-id="e95a5-190">Integers In Other Bases</span></span>

<span data-ttu-id="e95a5-191">부호 있는 32 비트 정수의 16 진수, 8 진수 또는 이진 사용 하 여 지정할 수도 있습니다는 `0x`, `0o` 또는 `0b` 각각 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="e95a5-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="e95a5-192">숫자 리터럴의 밑줄</span><span class="sxs-lookup"><span data-stu-id="e95a5-192">Underscores in Numeric Literals</span></span>

<span data-ttu-id="e95a5-193">F # 4.1 부터는을 구분할 수 있습니다 자리 밑줄 문자 (`_`).</span><span class="sxs-lookup"><span data-stu-id="e95a5-193">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="e95a5-194">참고자료</span><span class="sxs-lookup"><span data-stu-id="e95a5-194">See also</span></span>

- [<span data-ttu-id="e95a5-195">Core.LiteralAttribute 클래스</span><span class="sxs-lookup"><span data-stu-id="e95a5-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
