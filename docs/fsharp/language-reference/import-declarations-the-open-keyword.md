---
title: "가져오기 선언: open 키워드(F#)"
description: "해당 요소를 정규화 된 이름을 사용 하지 않고 참조할 수 F # 가져오기 선언 및 모듈 또는 네임 스페이스 지정 방법에 대해 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1e98e48c-52e9-4314-8954-85d5583125f0
ms.openlocfilehash: a6d79bed3dd202657d06956edf9499a9b21a5f03
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="6f82b-104">가져오기 선언:는 `open` 키워드</span><span class="sxs-lookup"><span data-stu-id="6f82b-104">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
<span data-ttu-id="6f82b-105">이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-105">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="6f82b-106">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-106">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="6f82b-107">*가져오기 선언* 모듈이 나 네임 스페이스 정규화 된 이름을 사용 하지 않고 참조할 수 있는 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-107">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>


## <a name="syntax"></a><span data-ttu-id="6f82b-108">구문</span><span class="sxs-lookup"><span data-stu-id="6f82b-108">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="6f82b-109">설명</span><span class="sxs-lookup"><span data-stu-id="6f82b-109">Remarks</span></span>
<span data-ttu-id="6f82b-110">정규화 된 네임 스페이스 또는 모듈 경로 사용 하 여 코드를 참조 될 때마다 작성 읽고 유지 관리 하는 코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-110">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="6f82b-111">대신 사용할 수는 `open` 키워드에 대 한 자주 네임 스페이스 및 모듈을 사용 하 여 해당 모듈 또는 네임 스페이스의 멤버를 참조할 때 정규화 된 이름 대신 이름의 약식 형태를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-111">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="6f82b-112">이 키워드는 비슷합니다는 `using` C# 키워드 `using namespace` Visual c + +에서 및 `Imports` Visual Basic의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-112">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="6f82b-113">동일한 프로젝트에서 또는 참조 되는 프로젝트 또는 어셈블리에서 모듈 또는 제공 된 네임 스페이스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-113">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="6f82b-114">없는 경우에 프로젝트에 대 한 참조를 추가 하거나 사용할 수 있습니다는 `-reference` 명령`-`명령줄 옵션 (또는 그 축약형 `-r`).</span><span class="sxs-lookup"><span data-stu-id="6f82b-114">If it is not, you can add a reference to the project, or use the `-reference` command`-`line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="6f82b-115">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f82b-115">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="6f82b-116">가져오기 선언을 사용 하면 이름을 바깥쪽 네임 스페이스, 모듈 또는 파일의 끝까지 선언 뒤에 오는 코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-116">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="6f82b-117">가져오기 선언이 여러 개를 사용 하면 별도 줄에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-117">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="6f82b-118">다음 코드의 사용을 보여 줍니다.는 `open` 코드를 단순화 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-118">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="6f82b-119">F # 컴파일러 같은 이름을 여러 개 열려 모듈 또는 네임 스페이스에서 발생 하는 경우 모호성으로 인해 발생 하는 경우에 오류 또는 경고 생성 하지 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-119">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="6f82b-120">모호성이 발생 하면 F #에서는 더 최근에 열었던 모듈 또는 네임 스페이스를 기본 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-120">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="6f82b-121">예를 들어, 다음 코드에서에서 `empty` 의미 `Seq.empty`경우라도, `empty` 둘 다에 `List` 및 `Seq` 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-121">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="6f82b-122">따라서 때는 주의 해야 모듈 또는 네임 스페이스와 같은 열 `List` 또는 `Seq` 동일한 이름을 가진; 대신 정규화 된 이름 사용을 고려 하는 멤버를 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-122">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="6f82b-123">코드는 가져오기 선언의 순서에 종속 된 경우를 피해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-123">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>


## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="6f82b-124">기본적으로 열려 있는 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="6f82b-124">Namespaces That Are Open by Default</span></span>
<span data-ttu-id="6f82b-125">일부 네임 스페이스를 열 때 암시적으로 명시적 가져오기 선언이 필요 없이 F # 코드에서 매우 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-125">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="6f82b-126">다음 표에서 기본적으로 열려 있는 네임 스페이스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-126">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="6f82b-127">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="6f82b-127">Namespace</span></span>|<span data-ttu-id="6f82b-128">설명</span><span class="sxs-lookup"><span data-stu-id="6f82b-128">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="6f82b-129">와 같은 기본 제공 형식에 대 한 F # 형식 정의 기본 들어 `int` 및 `float`합니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-129">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="6f82b-130">와 같은 기본 산술 연산을 포함 `+` 및 `*`합니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-130">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="6f82b-131">변경 불가능 컬렉션 클래스와 같은 포함 `List` 및 `Array`합니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-131">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="6f82b-132">지연 계산 등 비동기 워크플로 제어 구문에 대 한 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-132">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="6f82b-133">서식이 지정 된 io와 같은 함수를 포함 된 `printf` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-133">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="6f82b-134">AutoOpen 특성</span><span class="sxs-lookup"><span data-stu-id="6f82b-134">AutoOpen Attribute</span></span>
<span data-ttu-id="6f82b-135">적용할 수는 `AutoOpen` 어셈블리를 참조할 때 네임 스페이스 또는 모듈을 자동으로 열리게 하려면 특성을 어셈블리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-135">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="6f82b-136">적용할 수 있습니다는 `AutoOpen` 부모 모듈 또는 네임 스페이스를 열 때 해당 모듈을 자동으로 열도록 모듈에 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-136">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="6f82b-137">자세한 내용은 참조 [Core.AutoOpenAttribute 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-137">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>


## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="6f82b-138">RequireQualifiedAccess 특성</span><span class="sxs-lookup"><span data-stu-id="6f82b-138">RequireQualifiedAccess Attribute</span></span>
<span data-ttu-id="6f82b-139">일부 모듈, 레코드 또는 공용 구조체 형식을 지정할 수는 `RequireQualifiedAccess` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-139">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="6f82b-140">이러한 모듈, 레코드 또는 공용 구조체의 요소를 참조 하는 경우 가져오기 선언 포함 하는지 여부에 관계 없이 정규화 된 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-140">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="6f82b-141">에 전략적으로이 특성을 사용 하는 경우 일반적으로 정의 하는 형식 이름이 사용 되는, 이름이 충돌 하지 않도록 하 고 있으므로 코드 복원 성도 뛰어납니다. 라이브러리의 변화에 따라 도움말입니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-141">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="6f82b-142">자세한 내용은 참조 [Core.RequireQualifiedAccessAttribute 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f82b-142">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>


## <a name="see-also"></a><span data-ttu-id="6f82b-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f82b-143">See Also</span></span>
[<span data-ttu-id="6f82b-144"># 언어 참조</span><span class="sxs-lookup"><span data-stu-id="6f82b-144"># Language Reference</span></span>](index.md)

[<span data-ttu-id="6f82b-145">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="6f82b-145">Namespaces</span></span>](namespaces.md)

[<span data-ttu-id="6f82b-146">모듈</span><span class="sxs-lookup"><span data-stu-id="6f82b-146">Modules</span></span>](modules.md)

