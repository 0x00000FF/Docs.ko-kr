---
title: partial 형식(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 365d00d2c53d3efe1cd4330bdd3ec48740a49c53
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2018
ms.locfileid: "46586582"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="68678-102">partial 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="68678-102">partial type (C# Reference)</span></span>

<span data-ttu-id="68678-103">부분 형식(Partial Type) 정의를 사용하면 클래스, 구조체 또는 인터페이스의 정의를 여러 파일로 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68678-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>

<span data-ttu-id="68678-104">*File1.cs*:</span><span class="sxs-lookup"><span data-stu-id="68678-104">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="68678-105">*File2.cs*에서 선언은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68678-105">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="68678-106">설명</span><span class="sxs-lookup"><span data-stu-id="68678-106">Remarks</span></span>

<span data-ttu-id="68678-107">클래스, 구조체 또는 인터페이스 형식을 여러 파일에 분할하면 대형 프로젝트 또는 [Windows Forms 디자이너](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)에서 제공하는 것과 같은 자동으로 생성된 코드로 작업할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68678-107">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="68678-108">부분 형식(Partial Type)에는 [부분 메서드(Partial Method)](partial-method.md)가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68678-108">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="68678-109">자세한 내용은 참조 [Partial 클래스 및 메서드](../../programming-guide/classes-and-structs/partial-classes-and-methods.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="68678-109">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="68678-110">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="68678-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="68678-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68678-111">See also</span></span>

- [<span data-ttu-id="68678-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="68678-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="68678-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="68678-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="68678-114">한정자</span><span class="sxs-lookup"><span data-stu-id="68678-114">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="68678-115">제네릭 소개</span><span class="sxs-lookup"><span data-stu-id="68678-115">Introduction to Generics</span></span>](../../programming-guide/generics/introduction-to-generics.md)