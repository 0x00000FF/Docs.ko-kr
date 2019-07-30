---
title: 배열
description: F# 프로그래밍 언어로 배열을 만들고 사용 하는 방법에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 142d2c8d9aa7247e1490867a7bb905e2e7fec41e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630047"
---
# <a name="arrays"></a><span data-ttu-id="6162c-103">배열</span><span class="sxs-lookup"><span data-stu-id="6162c-103">Arrays</span></span>

> [!NOTE]
> <span data-ttu-id="6162c-104">API 참조 링크를 통해 MSDN으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-104">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="6162c-105">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="6162c-106">배열은 동일한 형식의 연속 데이터 요소에 대 한 고정 크기의 변경 가능한 컬렉션으로, 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-106">Arrays are fixed-size, zero-based, mutable collections of consecutive data elements that are all of the same type.</span></span>

## <a name="creating-arrays"></a><span data-ttu-id="6162c-107">배열 만들기</span><span class="sxs-lookup"><span data-stu-id="6162c-107">Creating Arrays</span></span>

<span data-ttu-id="6162c-108">여러 가지 방법으로 배열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-108">You can create arrays in several ways.</span></span> <span data-ttu-id="6162c-109">다음 예제와 같이 및 `[|` `|]` 사이에 연속 값을 나열 하 고 세미콜론으로 구분 하 여 작은 배열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-109">You can create a small array by listing consecutive values between `[|` and `|]` and separated by semicolons, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet1.fs)]

<span data-ttu-id="6162c-110">각 요소를 별도의 줄에 배치할 수도 있습니다 .이 경우 세미콜론 구분 기호는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-110">You can also put each element on a separate line, in which case the semicolon separator is optional.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet2.fs)]

<span data-ttu-id="6162c-111">배열 요소의 형식은 사용 된 리터럴에서 유추 되며 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-111">The type of the array elements is inferred from the literals used and must be consistent.</span></span> <span data-ttu-id="6162c-112">다음 코드는 1.0가 float이 고 2와 3이 정수 이므로 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-112">The following code causes an error because 1.0 is a float and 2 and 3 are integers.</span></span>

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

<span data-ttu-id="6162c-113">시퀀스 식을 사용 하 여 배열을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-113">You can also use sequence expressions to create arrays.</span></span> <span data-ttu-id="6162c-114">다음은 1에서 10 사이의 정수 제곱 배열을 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-114">Following is an example that creates an array of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet3.fs)]

<span data-ttu-id="6162c-115">모든 요소가 0으로 초기화 되는 배열을 만들려면를 사용 `Array.zeroCreate`합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-115">To create an array in which all the elements are initialized to zero, use `Array.zeroCreate`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="accessing-elements"></a><span data-ttu-id="6162c-116">요소 액세스</span><span class="sxs-lookup"><span data-stu-id="6162c-116">Accessing Elements</span></span>

<span data-ttu-id="6162c-117">점 연산자 (`.`)와 대괄호 (`[` 및 `]`)를 사용 하 여 배열 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-117">You can access array elements by using a dot operator (`.`) and brackets (`[` and `]`).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet5.fs)]

<span data-ttu-id="6162c-118">배열 인덱스는 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-118">Array indexes start at 0.</span></span>

<span data-ttu-id="6162c-119">배열의 하위 범위를 지정 하는 데 사용할 수 있는 조각 표기법을 사용 하 여 배열 요소에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-119">You can also access array elements by using slice notation, which enables you to specify a subrange of the array.</span></span> <span data-ttu-id="6162c-120">조각 표기법의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-120">Examples of slice notation follow.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet51.fs)]

<span data-ttu-id="6162c-121">조각 표기법을 사용 하면 배열의 새 복사본이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-121">When slice notation is used, a new copy of the array is created.</span></span>

## <a name="array-types-and-modules"></a><span data-ttu-id="6162c-122">배열 형식 및 모듈</span><span class="sxs-lookup"><span data-stu-id="6162c-122">Array Types and Modules</span></span>

<span data-ttu-id="6162c-123">모든 F# 배열의 형식은 .NET Framework 형식 <xref:System.Array?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-123">The type of all F# arrays is the .NET Framework type <xref:System.Array?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6162c-124">따라서 F# 배열은에서 <xref:System.Array?displayProperty=nameWithType>사용할 수 있는 모든 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-124">Therefore, F# arrays support all the functionality available in <xref:System.Array?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="6162c-125">라이브러리 모듈 [`Microsoft.FSharp.Collections.Array`](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) 은 1 차원 배열에 대 한 작업을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-125">The library module [`Microsoft.FSharp.Collections.Array`](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) supports operations on one-dimensional arrays.</span></span> <span data-ttu-id="6162c-126">모듈 `Array2D`, `Array3D`및 에는각각2,3및4차원배열에대한작업을지원하는함수가포함되어있습니다.`Array4D`</span><span class="sxs-lookup"><span data-stu-id="6162c-126">The modules `Array2D`, `Array3D`, and `Array4D` contain functions that support operations on arrays of two, three, and four dimensions, respectively.</span></span> <span data-ttu-id="6162c-127">을 사용 <xref:System.Array?displayProperty=nameWithType>하 여 4 보다 큰 차수 배열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-127">You can create arrays of rank greater than four by using <xref:System.Array?displayProperty=nameWithType>.</span></span>

### <a name="simple-functions"></a><span data-ttu-id="6162c-128">간단한 함수</span><span class="sxs-lookup"><span data-stu-id="6162c-128">Simple Functions</span></span>

<span data-ttu-id="6162c-129">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc)요소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-129">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc) gets an element.</span></span> <span data-ttu-id="6162c-130">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f)배열의 길이를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-130">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f) gives the length of an array.</span></span> <span data-ttu-id="6162c-131">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790)요소를 지정 된 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-131">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="6162c-132">다음 코드 예제에서는 이러한 함수를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-132">The following code example illustrates the use of these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet9.fs)]

<span data-ttu-id="6162c-133">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-133">The output is as follows.</span></span>

```
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a><span data-ttu-id="6162c-134">배열을 만드는 함수</span><span class="sxs-lookup"><span data-stu-id="6162c-134">Functions That Create Arrays</span></span>

<span data-ttu-id="6162c-135">여러 함수는 기존 배열을 요구 하지 않고 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-135">Several functions create arrays without requiring an existing array.</span></span> <span data-ttu-id="6162c-136">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32)요소가 포함 되지 않은 새 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-136">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32) creates a new array that does not contain any elements.</span></span> <span data-ttu-id="6162c-137">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be)지정 된 크기의 배열을 만들고 모든 요소를 제공 된 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-137">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be) creates an array of a specified size and sets all the elements to provided values.</span></span> <span data-ttu-id="6162c-138">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665)지정 된 차원과 요소를 생성 하는 함수를 지정 하 여 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-138">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665) creates an array, given a dimension and a function to generate the elements.</span></span> <span data-ttu-id="6162c-139">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)모든 요소가 배열의 형식에 대해 0 값으로 초기화 되는 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-139">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2) creates an array in which all the elements are initialized to the zero value for the array's type.</span></span> <span data-ttu-id="6162c-140">다음 코드에서는 이러한 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-140">The following code demonstrates these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet91.fs)]

<span data-ttu-id="6162c-141">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-141">The output is as follows.</span></span>

```
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

<span data-ttu-id="6162c-142">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f)기존 배열에서 복사 된 요소를 포함 하는 새 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-142">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f) creates a new array that contains elements that are copied from an existing array.</span></span> <span data-ttu-id="6162c-143">복사본은 단순 복사본입니다. 즉, 요소 형식이 참조 형식이 면 참조만 복사 되 고 기본 개체는 복사 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-143">Note that the copy is a shallow copy, which means that if the element type is a reference type, only the reference is copied, not the underlying object.</span></span> <span data-ttu-id="6162c-144">다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-144">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet11.fs)]

<span data-ttu-id="6162c-145">위의 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-145">The output of the preceding code is as follows:</span></span>

```
[|Test1; Test2; |]
[|; Test2; |]
```

<span data-ttu-id="6162c-146">새 요소 `Test1` 를 만드는 작업은에서 `firstArray` 참조를 덮어쓰므로에서 여전히에 `secondArray`있는 빈 문자열에 대 한 원래 참조에는 영향을 주지 않기 때문에이 문자열은 첫 번째 배열에만 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-146">The string `Test1` appears only in the first array because the operation of creating a new element overwrites the reference in `firstArray` but does not affect the original reference to an empty string that is still present in `secondArray`.</span></span> <span data-ttu-id="6162c-147">형식에 `Test2` 대 `Insert` 한 작업이 두 배열에서 참조 되는 기본 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 개체에 영향을 주기 때문에 두 배열에 문자열이 모두 표시 됩니다. <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6162c-147">The string `Test2` appears in both arrays because the `Insert` operation on the <xref:System.Text.StringBuilder?displayProperty=nameWithType> type affects the underlying <xref:System.Text.StringBuilder?displayProperty=nameWithType> object, which is referenced in both arrays.</span></span>

<span data-ttu-id="6162c-148">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d)배열의 하위 범위에서 새 배열을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-148">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d) generates a new array from a subrange of an array.</span></span> <span data-ttu-id="6162c-149">시작 인덱스 및 길이를 제공 하 여 하위 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-149">You specify the subrange by providing the starting index and the length.</span></span> <span data-ttu-id="6162c-150">다음 코드는 `Array.sub`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-150">The following code demonstrates the use of `Array.sub`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet12.fs)]

<span data-ttu-id="6162c-151">출력은 하위 배열을 요소 5에서 시작 하 고 10 개의 요소를 포함 하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-151">The output shows that the subarray starts at element 5 and contains 10 elements.</span></span>

```
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```

<span data-ttu-id="6162c-152">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911)두 개의 기존 배열을 결합 하 여 새 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-152">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911) creates a new array by combining two existing arrays.</span></span>

<span data-ttu-id="6162c-153">다음 코드에서는 **배열. append**를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-153">The following code demonstrates **Array.append**.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet13.fs)]

<span data-ttu-id="6162c-154">위의 코드는 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-154">The output of the preceding code is as follows.</span></span>

```
[|1; 2; 3; 4; 5; 6|]
```

<span data-ttu-id="6162c-155">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09)새 배열에 포함할 배열의 요소를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-155">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09) selects elements of an array to include in a new array.</span></span> <span data-ttu-id="6162c-156">다음 코드에서는을 `Array.choose`보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-156">The following code demonstrates `Array.choose`.</span></span> <span data-ttu-id="6162c-157">배열의 요소 형식은 옵션 형식에서 반환 되는 값의 형식과 일치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-157">Note that the element type of the array does not have to match the type of the value returned in the option type.</span></span> <span data-ttu-id="6162c-158">이 예제에서 요소 형식은이 `int` 고 옵션은 다항식 `elem*elem - 1`함수의 결과인 부동 소수점 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-158">In this example, the element type is `int` and the option is the result of a polynomial function, `elem*elem - 1`, as a floating point number.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet14.fs)]

<span data-ttu-id="6162c-159">위의 코드는 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-159">The output of the preceding code is as follows.</span></span>

```
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

<span data-ttu-id="6162c-160">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a)기존 배열의 각 배열 요소에 대해 지정 된 함수를 실행 한 다음 함수에 의해 생성 된 요소를 수집 하 여 새 배열로 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-160">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a) runs a specified function on each array element of an existing array and then collects the elements generated by the function and combines them into a new array.</span></span> <span data-ttu-id="6162c-161">다음 코드에서는을 `Array.collect`보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-161">The following code demonstrates `Array.collect`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet15.fs)]

<span data-ttu-id="6162c-162">위의 코드는 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-162">The output of the preceding code is as follows.</span></span>

```
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

<span data-ttu-id="6162c-163">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302)배열의 시퀀스를 사용 하 여 단일 배열로 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-163">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302) takes a sequence of arrays and combines them into a single array.</span></span> <span data-ttu-id="6162c-164">다음 코드에서는을 `Array.concat`보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-164">The following code demonstrates `Array.concat`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet16.fs)]

<span data-ttu-id="6162c-165">위의 코드는 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-165">The output of the preceding code is as follows.</span></span>

```
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

<span data-ttu-id="6162c-166">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede)부울 조건 함수를 사용 하 고 조건이 true 인 입력 배열의 요소만 포함 하는 새 배열을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-166">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede) takes a Boolean condition function and generates a new array that contains only those elements from the input array for which the condition is true.</span></span> <span data-ttu-id="6162c-167">다음 코드에서는을 `Array.filter`보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-167">The following code demonstrates `Array.filter`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet17.fs)]

<span data-ttu-id="6162c-168">위의 코드는 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-168">The output of the preceding code is as follows.</span></span>

```
[|2; 4; 6; 8; 10|]
```

<span data-ttu-id="6162c-169">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709)기존 배열의 순서를 반대로 하 여 새 배열을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-169">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709) generates a new array by reversing the order of an existing array.</span></span> <span data-ttu-id="6162c-170">다음 코드에서는을 `Array.rev`보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-170">The following code demonstrates `Array.rev`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet18.fs)]

<span data-ttu-id="6162c-171">위의 코드는 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-171">The output of the preceding code is as follows.</span></span>

```
"Hello world!"
```

<span data-ttu-id="6162c-172">다음 예제와 같이 파이프라인 연산자 (`|>`)를 사용 하 여 배열을 변환 하는 배열 모듈의 함수를 쉽게 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-172">You can easily combine functions in the array module that transform arrays by using the pipeline operator (`|>`), as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet19.fs)]

<span data-ttu-id="6162c-173">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-173">The output is</span></span>

```
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a><span data-ttu-id="6162c-174">다차원 배열</span><span class="sxs-lookup"><span data-stu-id="6162c-174">Multidimensional Arrays</span></span>

<span data-ttu-id="6162c-175">다차원 배열을 만들 수 있지만 다차원 배열 리터럴을 작성 하기 위한 구문이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-175">A multidimensional array can be created, but there is no syntax for writing a multidimensional array literal.</span></span> <span data-ttu-id="6162c-176">연산자 [`array2D`](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) 를 사용 하 여 배열 요소의 시퀀스 시퀀스에서 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-176">Use the operator [`array2D`](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) to create an array from a sequence of sequences of array elements.</span></span> <span data-ttu-id="6162c-177">시퀀스는 배열 또는 목록 리터럴일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-177">The sequences can be array or list literals.</span></span> <span data-ttu-id="6162c-178">예를 들어 다음 코드는 2 차원 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-178">For example, the following code creates a two-dimensional array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet20.fs)]

<span data-ttu-id="6162c-179">또한 함수 [`Array2D.init`](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) 를 사용 하 여 두 차원의 배열을 초기화할 수 있으며, 3 개 차원 및 4 차원 배열에도 유사한 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-179">You can also use the function [`Array2D.init`](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) to initialize arrays of two dimensions, and similar functions are available for arrays of three and four dimensions.</span></span> <span data-ttu-id="6162c-180">이러한 함수는 요소를 만드는 데 사용 되는 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-180">These functions take a function that is used to create the elements.</span></span> <span data-ttu-id="6162c-181">함수를 지정 하는 대신 초기 값으로 설정 된 요소를 포함 하는 2 차원 배열을 만들려면 최대 4 차원 [`Array2D.create`](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) 배열에도 사용할 수 있는 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-181">To create a two-dimensional array that contains elements set to an initial value instead of specifying a function, use the [`Array2D.create`](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) function, which is also available for arrays up to four dimensions.</span></span> <span data-ttu-id="6162c-182">다음 코드 예제에서는 먼저 원하는 요소를 포함 하는 배열 배열을 만든 다음를 사용 `Array2D.init` 하 여 원하는 2 차원 배열을 생성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-182">The following code example first shows how to create an array of arrays that contain the desired elements, and then uses `Array2D.init` to generate the desired two-dimensional array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet21.fs)]

<span data-ttu-id="6162c-183">배열 인덱싱 및 조각화 구문은 차수가 4 인 배열에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-183">Array indexing and slicing syntax is supported for arrays up to rank 4.</span></span> <span data-ttu-id="6162c-184">여러 차원에서 인덱스를 지정 하는 경우 다음 코드 예제에 나와 있는 것 처럼 쉼표를 사용 하 여 인덱스를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-184">When you specify an index in multiple dimensions, you use commas to separate the indexes, as illustrated in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet22.fs)]

<span data-ttu-id="6162c-185">2 `<type>[,]` 차원 배열의 형식은 ( `int[,]`예:, `double[,]`)로 작성 되 고 3 차원 배열의 형식은로 작성 되며, 더 큰 차원의 배열에 대해서는로 `<type>[,,]`작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-185">The type of a two-dimensional array is written out as `<type>[,]` (for example, `int[,]`, `double[,]`), and the type of a three-dimensional array is written as `<type>[,,]`, and so on for arrays of higher dimensions.</span></span>

<span data-ttu-id="6162c-186">다차원 배열에는 1 차원 배열에 사용할 수 있는 함수의 하위 집합만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-186">Only a subset of the functions available for one-dimensional arrays is also available for multidimensional arrays.</span></span> <span data-ttu-id="6162c-187">자세한 내용은,, 및 [`Collections.Array Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d) [`Collections.Array2D Module`을참조](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d) [`Collections.Array3D Module`하십시오](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d) [`Collections.Array4D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="6162c-187">For more information, see [`Collections.Array Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [`Collections.Array2D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [`Collections.Array3D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d), and [`Collections.Array4D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).</span></span>

### <a name="array-slicing-and-multidimensional-arrays"></a><span data-ttu-id="6162c-188">배열 조각화 및 다차원 배열</span><span class="sxs-lookup"><span data-stu-id="6162c-188">Array Slicing and Multidimensional Arrays</span></span>

<span data-ttu-id="6162c-189">2 차원 배열 (행렬)에서 범위를 지정 하 고 와일드 카드 (`*`) 문자를 사용 하 여 하위 행렬을 추출 하 여 전체 행 또는 열을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-189">In a two-dimensional array (a matrix), you can extract a sub-matrix by specifying ranges and using a wildcard (`*`) character to specify whole rows or columns.</span></span>

```fsharp
// Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

<span data-ttu-id="6162c-190">3\.1의 F# 경우 다차원 배열을 같거나 낮은 차원의 subarrays으로 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-190">As of F# 3.1, you can decompose a multidimensional array into subarrays of the same or lower dimension.</span></span> <span data-ttu-id="6162c-191">예를 들어 단일 행 또는 열을 지정 하 여 행렬에서 벡터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-191">For example, you can obtain a vector from a matrix by specifying a single row or column.</span></span>

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

<span data-ttu-id="6162c-192">요소 액세스 연산자 및 오버 로드 `GetSlice` 된 메서드를 구현 하는 형식에 대해이 조각화 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-192">You can use this slicing syntax for types that implement the element access operators and overloaded `GetSlice` methods.</span></span> <span data-ttu-id="6162c-193">예를 들어 다음 코드는 F# 2d 배열을 래핑하고, 배열 인덱싱에 대 한 지원을 제공 하기 위해 항목 속성을 구현 하 고, 세 가지 버전의 `GetSlice`를 구현 하는 행렬 유형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-193">For example, the following code creates a Matrix type that wraps the F# 2D array, implements an Item property to provide support for array indexing, and implements three versions of `GetSlice`.</span></span> <span data-ttu-id="6162c-194">이 코드를 행렬 형식에 대 한 템플릿으로 사용할 수 있는 경우이 단원에서 설명 하는 모든 조각 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-194">If you can use this code as a template for your matrix types, you can use all the slicing operations that this section describes.</span></span>

```fsharp
type Matrix<'T>(N: int, M: int) =
    let internalArray = Array2D.zeroCreate<'T> N M

    member this.Item
        with get(a: int, b: int) = internalArray.[a, b]
        and set(a: int, b: int) (value:'T) = internalArray.[a, b] <- value

    member this.GetSlice(rowStart: int option, rowFinish : int option, colStart: int option, colFinish : int option) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[rowStart..rowFinish, colStart..colFinish]

    member this.GetSlice(row: int, colStart: int option, colFinish: int option) =
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[row, colStart..colFinish]

    member this.GetSlice(rowStart: int option, rowFinish: int option, col: int) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        internalArray.[rowStart..rowFinish, col]

module test =
    let generateTestMatrix x y =
        let matrix = new Matrix<float>(3, 3)
        for i in 0..2 do
            for j in 0..2 do
                matrix.[i, j] <- float(i) * x - float(j) * y
        matrix

    let test1 = generateTestMatrix 2.3 1.1
    let submatrix = test1.[0..1, 0..1]
    printfn "%A" submatrix

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn "%A" firstCol
```

### <a name="boolean-functions-on-arrays"></a><span data-ttu-id="6162c-195">배열의 부울 함수</span><span class="sxs-lookup"><span data-stu-id="6162c-195">Boolean Functions on Arrays</span></span>

<span data-ttu-id="6162c-196">각각 하나 [`Array.exists`](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) 또는 [`Array.exists2`](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) 두 배열의 함수 및 테스트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-196">The functions [`Array.exists`](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) and [`Array.exists2`](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) test elements in either one or two arrays, respectively.</span></span> <span data-ttu-id="6162c-197">이러한 함수는 테스트 함수를 사용 하 `true` 고 조건을 충족 하는 요소 또는에 대 한 `Array.exists2`요소 쌍이 있는 경우를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-197">These functions take a test function and return `true` if there is an element (or element pair for `Array.exists2`) that satisfies the condition.</span></span>

<span data-ttu-id="6162c-198">다음 코드에서는 `Array.exists` 및 `Array.exists2`를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-198">The following code demonstrates the use of `Array.exists` and `Array.exists2`.</span></span> <span data-ttu-id="6162c-199">이러한 예제에서는 인수 중 하나 (이 경우에는 함수 인수)만 적용 하 여 새 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-199">In these examples, new functions are created by applying only one of the arguments, in these cases, the function argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet23.fs)]

<span data-ttu-id="6162c-200">위의 코드는 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-200">The output of the preceding code is as follows.</span></span>

```
true
false
false
true
```

<span data-ttu-id="6162c-201">마찬가지로 함수 [`Array.forall`](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) 는 배열을 테스트 하 여 모든 요소가 부울 조건을 충족 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-201">Similarly, the function [`Array.forall`](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) tests an array to determine whether every element satisfies a Boolean condition.</span></span> <span data-ttu-id="6162c-202">동일한 길이의 [`Array.forall2`](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) 두 배열의 요소를 포함 하는 부울 함수를 사용 하 여 변형이 동일한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-202">The variation [`Array.forall2`](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) does the same thing by using a Boolean function that involves elements of two arrays of equal length.</span></span> <span data-ttu-id="6162c-203">다음 코드에서는 이러한 함수를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-203">The following code illustrates the use of these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet24.fs)]

<span data-ttu-id="6162c-204">이러한 예제에 대 한 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-204">The output for these examples is as follows.</span></span>

```
false
true
true
false
```

### <a name="searching-arrays"></a><span data-ttu-id="6162c-205">배열 검색</span><span class="sxs-lookup"><span data-stu-id="6162c-205">Searching Arrays</span></span>

<span data-ttu-id="6162c-206">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33)부울 함수를 사용 하 여 함수가 반환 `true`하는 첫 번째 요소를 반환 하거나 조건을 충족 하는 요소가 없는 경우을 <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-206">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33) takes a Boolean function and returns the first element for which the function returns `true`, or raises a <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> if no element that satisfies the condition is found.</span></span> <span data-ttu-id="6162c-207">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f)는 요소 `Array.find`자체 대신 요소의 인덱스를 반환 한다는 점을 제외 하 고와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-207">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) is like `Array.find`, except that it returns the index of the element instead of the element itself.</span></span>

<span data-ttu-id="6162c-208">다음 코드에서는 및 `Array.find` `Array.findIndex` 를 사용 하 여 완전 한 정사각형과 완전 한 큐브인 숫자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-208">The following code uses `Array.find` and `Array.findIndex` to locate a number that is both a perfect square and perfect cube.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet25.fs)]

<span data-ttu-id="6162c-209">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-209">The output is as follows.</span></span>

```
The first element that is both a square and a cube is 64 and its index is 62.
```

<span data-ttu-id="6162c-210">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9)는 결과가 `Array.find`옵션 형식 이라는 점을 제외 하 고는와 유사 하며, 요소 `None` 를 찾을 수 없는 경우를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-210">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9) is like `Array.find`, except that its result is an option type, and it returns `None` if no element is found.</span></span> <span data-ttu-id="6162c-211">`Array.tryFind`일치 하는 요소가 배열 `Array.find` 에 있는지 여부를 알 수 없는 경우 대신를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-211">`Array.tryFind` should be used instead of `Array.find` when you do not know whether a matching element is in the array.</span></span> <span data-ttu-id="6162c-212">마찬가지로 옵션 유형이 반환 [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) 값 이라는 점을 제외 하 고 [는와유사합니다.`Array.tryFindIndex`](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a)</span><span class="sxs-lookup"><span data-stu-id="6162c-212">Similarly, [`Array.tryFindIndex`](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) is like [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) except that the option type is the return value.</span></span> <span data-ttu-id="6162c-213">요소를 찾을 수 없는 경우 옵션 `None`은입니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-213">If no element is found, the option is `None`.</span></span>

<span data-ttu-id="6162c-214">다음 코드는 `Array.tryFind`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-214">The following code demonstrates the use of `Array.tryFind`.</span></span> <span data-ttu-id="6162c-215">이 코드는 이전 코드에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-215">This code depends on the previous code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet26.fs)]

<span data-ttu-id="6162c-216">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-216">The output is as follows.</span></span>

```
Found an element: 1
Found an element: 729
```

<span data-ttu-id="6162c-217">요소 [`Array.tryPick`](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) 를 찾을 뿐만 아니라 요소를 변환 해야 하는 경우에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-217">Use [`Array.tryPick`](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) when you need to transform an element in addition to finding it.</span></span> <span data-ttu-id="6162c-218">결과는 함수에서 변환 된 요소를 옵션 값으로 반환 하는 첫 번째 요소 이거나 `None` , 이러한 요소가 없는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-218">The result is the first element for which the function returns the transformed element as an option value, or `None` if no such element is found.</span></span>

<span data-ttu-id="6162c-219">다음 코드는 `Array.tryPick`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-219">The following code shows the use of `Array.tryPick`.</span></span> <span data-ttu-id="6162c-220">이 경우 람다 식 대신 코드를 단순화 하기 위해 몇 가지 로컬 도우미 함수가 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-220">In this case, instead of a lambda expression, several local helper functions are defined to simplify the code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet27.fs)]

<span data-ttu-id="6162c-221">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-221">The output is as follows.</span></span>

```
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
```

### <a name="performing-computations-on-arrays"></a><span data-ttu-id="6162c-222">배열에 대 한 계산 수행</span><span class="sxs-lookup"><span data-stu-id="6162c-222">Performing Computations on Arrays</span></span>

<span data-ttu-id="6162c-223">함수 [`Array.average`](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) 는 배열의 각 요소에 대 한 평균을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-223">The [`Array.average`](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) function returns the average of each element in an array.</span></span> <span data-ttu-id="6162c-224">정수로 정확히 나누기를 지 원하는 요소 형식으로 제한 됩니다. 여기에는 부동 소수점 형식이 포함 되지만 정수 계열 형식은 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-224">It is limited to element types that support exact division by an integer, which includes floating point types but not integral types.</span></span> <span data-ttu-id="6162c-225">함수 [`Array.averageBy`](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) 는 각 요소에 대해 함수를 호출한 결과의 평균을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-225">The [`Array.averageBy`](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) function returns the average of the results of calling a function on each element.</span></span> <span data-ttu-id="6162c-226">정수 계열 형식의 배열에 대해를 사용 `Array.averageBy` 하 고 함수에서 각 요소를 계산에 대 한 부동 소수점 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-226">For an array of integral type, you can use `Array.averageBy` and have the function convert each element to a floating point type for the computation.</span></span>

<span data-ttu-id="6162c-227">요소 [`Array.max`](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) 형식이 [`Array.min`](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) 지 원하는 경우 또는를 사용 하 여 maximum 또는 minimum 요소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-227">Use [`Array.max`](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) or [`Array.min`](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) to get the maximum or minimum element, if the element type supports it.</span></span> <span data-ttu-id="6162c-228">[`Array.maxBy`](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) 마찬가지로 및 [`Array.minBy`](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) 는 비교를 지 원하는 형식으로 변환 하는 등의 방법으로 함수를 먼저 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-228">Similarly, [`Array.maxBy`](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) and [`Array.minBy`](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) allow a function to be executed first, perhaps to transform to a type that supports comparison.</span></span>

<span data-ttu-id="6162c-229">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2)배열의 요소를 추가 하 고 [`Array.sumBy`](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) 각 요소에 대해 함수를 호출 하 고 결과를 함께 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-229">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2) adds the elements of an array, and [`Array.sumBy`](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) calls a function on each element and adds the results together.</span></span>

<span data-ttu-id="6162c-230">반환 값을 저장 하지 않고 배열의 각 요소에 대해 함수를 실행 하려면를 사용 [`Array.iter`](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516)합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-230">To execute a function on each element in an array without storing the return values, use [`Array.iter`](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516).</span></span> <span data-ttu-id="6162c-231">길이가 같은 두 배열이 포함 된 함수의 경우를 사용 [`Array.iter2`](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc)합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-231">For a function involving two arrays of equal length, use [`Array.iter2`](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc).</span></span> <span data-ttu-id="6162c-232">함수의 결과 배열을 유지 해야 하는 경우에는 한 번에 두 배열에 [`Array.map`](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) 대해 [`Array.map2`](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c)작동 하는 또는를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-232">If you also need to keep an array of the results of the function, use [`Array.map`](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) or [`Array.map2`](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), which operates on two arrays at a time.</span></span>

<span data-ttu-id="6162c-233">변형을 [`Array.iteri`](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) [`Array.mapi`](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) [`Array.mapi2`](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0)사용 하 여 요소의 인덱스를 계산에 포함 시킬 수 있습니다. 및의 경우에도 마찬가지입니다. [`Array.iteri2`](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405)</span><span class="sxs-lookup"><span data-stu-id="6162c-233">The variations [`Array.iteri`](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) and [`Array.iteri2`](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) allow the index of the element to be involved in the computation; the same is true for [`Array.mapi`](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) and [`Array.mapi2`](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).</span></span>

<span data-ttu-id="6162c-234">[`Array.fold`](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09) [,`Array.foldBack`](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [,`Array.reduceBack`](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), 및 [함수는배열의모든요소를포함하는를실행합니다`Array.scanBack`.](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) [`Array.reduce`](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d) [`Array.scan`](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0)</span><span class="sxs-lookup"><span data-stu-id="6162c-234">The functions [`Array.fold`](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [`Array.foldBack`](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [`Array.reduce`](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [`Array.reduceBack`](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [`Array.scan`](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0), and [`Array.scanBack`](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) execute algorithms that involve all the elements of an array.</span></span> <span data-ttu-id="6162c-235">마찬가지로, 변형이 [`Array.fold2`](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) [`Array.foldBack2`](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) 두 배열에 대해 계산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-235">Similarly, the variations [`Array.fold2`](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) and [`Array.foldBack2`](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) perform computations on two arrays.</span></span>

<span data-ttu-id="6162c-236">계산을 수행 하는 이러한 함수는 [목록 모듈](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)에 있는 동일한 이름의 함수에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-236">These functions for performing computations correspond to the functions of the same name in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span> <span data-ttu-id="6162c-237">사용 예제는 [목록](lists.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6162c-237">For usage examples, see [Lists](lists.md).</span></span>

### <a name="modifying-arrays"></a><span data-ttu-id="6162c-238">배열 수정</span><span class="sxs-lookup"><span data-stu-id="6162c-238">Modifying Arrays</span></span>

<span data-ttu-id="6162c-239">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790)요소를 지정 된 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-239">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="6162c-240">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2)배열의 요소 범위를 지정 된 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-240">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2) sets a range of elements in an array to a specified value.</span></span> <span data-ttu-id="6162c-241">다음 코드에서는의 `Array.fill`예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-241">The following code provides an example of `Array.fill`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet28.fs)]

<span data-ttu-id="6162c-242">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-242">The output is as follows.</span></span>

```
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

<span data-ttu-id="6162c-243">를 사용 [`Array.blit`](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) 하 여 한 배열의 하위 섹션을 다른 배열로 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-243">You can use [`Array.blit`](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) to copy a subsection of one array to another array.</span></span>

### <a name="converting-to-and-from-other-types"></a><span data-ttu-id="6162c-244">다른 형식으로 변환 또는 다른 형식에서 변환</span><span class="sxs-lookup"><span data-stu-id="6162c-244">Converting to and from Other Types</span></span>

<span data-ttu-id="6162c-245">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b)목록에서 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-245">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b) creates an array from a list.</span></span> <span data-ttu-id="6162c-246">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c)시퀀스에서 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-246">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c) creates an array from a sequence.</span></span> <span data-ttu-id="6162c-247">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786)및 [`Array.toSeq`](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) 는 배열 형식에서 이러한 다른 컬렉션 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-247">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786) and [`Array.toSeq`](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) convert to these other collection types from the array type.</span></span>

### <a name="sorting-arrays"></a><span data-ttu-id="6162c-248">배열 정렬</span><span class="sxs-lookup"><span data-stu-id="6162c-248">Sorting Arrays</span></span>

<span data-ttu-id="6162c-249">제네릭 [`Array.sort`](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) 비교 함수를 사용 하 여 배열을 정렬 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-249">Use [`Array.sort`](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) to sort an array by using the generic comparison function.</span></span> <span data-ttu-id="6162c-250">키 [`Array.sortBy`](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) 에 대 한 제네릭 비교 함수를 사용 하 여 정렬 하려면 *키*라고 하는 값을 생성 하는 함수를 지정 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-250">Use [`Array.sortBy`](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) to specify a function that generates a value, referred to as a *key*, to sort by using the generic comparison function on the key.</span></span> <span data-ttu-id="6162c-251">사용자 [`Array.sortWith`](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) 지정 비교 함수를 제공 하려는 경우를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-251">Use [`Array.sortWith`](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) if you want to provide a custom comparison function.</span></span> <span data-ttu-id="6162c-252">`Array.sort`, `Array.sortBy` 및`Array.sortWith` 는 모두 정렬 된 배열을 새 배열로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-252">`Array.sort`, `Array.sortBy`, and `Array.sortWith` all return the sorted array as a new array.</span></span> <span data-ttu-id="6162c-253">, [`Array.sortInPlace`](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0) [`Array.sortInPlaceBy`](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f)및 [변형은새배열을반환하는대신기존배열을수정합니다.`Array.sortInPlaceWith`](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b)</span><span class="sxs-lookup"><span data-stu-id="6162c-253">The variations [`Array.sortInPlace`](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [`Array.sortInPlaceBy`](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f), and [`Array.sortInPlaceWith`](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) modify the existing array instead of returning a new one.</span></span>

### <a name="arrays-and-tuples"></a><span data-ttu-id="6162c-254">배열 및 튜플</span><span class="sxs-lookup"><span data-stu-id="6162c-254">Arrays and Tuples</span></span>

<span data-ttu-id="6162c-255">함수 [`Array.zip`](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) [및`Array.unzip`](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) 는 튜플 쌍의 배열을 배열의 튜플로 변환 하 고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-255">The functions [`Array.zip`](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) and [`Array.unzip`](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) convert arrays of tuple pairs to tuples of arrays and vice versa.</span></span> <span data-ttu-id="6162c-256">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d)및 [`Array.unzip3`](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) 는 세 개의 요소로 된 튜플 또는 세 개의 배열로 된 튜플로 작업 한다는 점을 제외 하 고는 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-256">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d) and [`Array.unzip3`](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) are similar except that they work with tuples of three elements or tuples of three arrays.</span></span>

## <a name="parallel-computations-on-arrays"></a><span data-ttu-id="6162c-257">배열에 대 한 병렬 계산</span><span class="sxs-lookup"><span data-stu-id="6162c-257">Parallel Computations on Arrays</span></span>

<span data-ttu-id="6162c-258">모듈 [`Array.Parallel`](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) 에는 배열에 대 한 병렬 계산을 수행 하는 함수가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-258">The module [`Array.Parallel`](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) contains functions for performing parallel computations on arrays.</span></span> <span data-ttu-id="6162c-259">버전 4 이전 버전의 .NET Framework를 대상으로 하는 응용 프로그램에서는이 모듈을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6162c-259">This module is not available in applications that target versions of the .NET Framework prior to version 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="6162c-260">참고자료</span><span class="sxs-lookup"><span data-stu-id="6162c-260">See also</span></span>

- [<span data-ttu-id="6162c-261">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="6162c-261">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="6162c-262">F# 형식</span><span class="sxs-lookup"><span data-stu-id="6162c-262">F# Types</span></span>](fsharp-types.md)
