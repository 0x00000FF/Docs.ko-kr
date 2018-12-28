---
title: 소스 줄, 파일 및 경로 식별자
description: 기본 제공을 사용 하는 방법을 알아봅니다 F# 식별자 값 원본에 액세스할 수 있도록 하는 줄 번호, 디렉터리 및 코드에서 파일 이름입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 4b145fe1fe20e3d7f868558e33bab26204fb0125
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2018
ms.locfileid: "53656013"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="3d6de-103">소스 줄, 파일 및 경로 식별자</span><span class="sxs-lookup"><span data-stu-id="3d6de-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="3d6de-104">식별자 `__LINE__`, `__SOURCE_DIRECTORY__` 고 `__SOURCE_FILE__` 소스 줄 번호, 디렉터리 및 파일 이름을 코드에 액세스할 수 있는 기본 제공 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6de-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="3d6de-105">구문</span><span class="sxs-lookup"><span data-stu-id="3d6de-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="3d6de-106">설명</span><span class="sxs-lookup"><span data-stu-id="3d6de-106">Remarks</span></span>

<span data-ttu-id="3d6de-107">이러한 각 값 형식이 `string`합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6de-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="3d6de-108">다음 표에서 사용할 수 있는 소스 줄, 파일 및 경로 식별자 F#입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6de-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="3d6de-109">이러한 식별자는 전처리기 매크로; 없습니다. 이러한 값은 컴파일러에서 인식 되는 기본 제공 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6de-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="3d6de-110">미리 정의 된 식별자</span><span class="sxs-lookup"><span data-stu-id="3d6de-110">Predefined identifier</span></span>|<span data-ttu-id="3d6de-111">설명</span><span class="sxs-lookup"><span data-stu-id="3d6de-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="3d6de-112">현재 줄 번호를로 고려 `#line` 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6de-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="3d6de-113">원본 디렉터리의 전체 경로 평가 고려 `#line` 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6de-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="3d6de-114">현재 소스 파일 이름과 경로 평가 고려 `#line` 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6de-114">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|

<span data-ttu-id="3d6de-115">에 대 한 자세한 내용은 합니다 `#line` 지시문을 참조 하십시오 [컴파일러 지시문](compiler-directives.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6de-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="3d6de-116">예제</span><span class="sxs-lookup"><span data-stu-id="3d6de-116">Example</span></span>

<span data-ttu-id="3d6de-117">다음 코드 예제에서는 이러한 값을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d6de-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="3d6de-118">출력:</span><span class="sxs-lookup"><span data-stu-id="3d6de-118">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="3d6de-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d6de-119">See also</span></span>

- [<span data-ttu-id="3d6de-120">컴파일러 지시문</span><span class="sxs-lookup"><span data-stu-id="3d6de-120">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="3d6de-121">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="3d6de-121">F# Language Reference</span></span>](index.md)
