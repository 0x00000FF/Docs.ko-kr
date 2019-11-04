---
title: '방법: COM Interop 프로그래밍에서 인덱싱된 속성 사용 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: 0d4e85646a1e7f8c4ee9a73fbf7bf5a01b10b14b
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423215"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="b59a7-102">방법: COM Interop 프로그래밍에서 인덱싱된 속성 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b59a7-102">How to: Use Indexed Properties in COM Interop Programming (C# Programming Guide)</span></span>
<span data-ttu-id="b59a7-103">*인덱싱된 속성*은 매개 변수가 있는 COM 속성이 C# 프로그래밍에서 사용되는 방식을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-103">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="b59a7-104">인덱싱된 속성은 Visual C#의 다른 기능(예: [명명된 인수 및 선택적 인수](../classes-and-structs/named-and-optional-arguments.md)), 새 형식([dynamic](../../language-reference/builtin-types/reference-types.md)), [포함된 형식 정보](../../../standard/assembly/embed-types-visual-studio.md)와 함께 작동하여 Microsoft Office 프로그래밍을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-104">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../language-reference/builtin-types/reference-types.md)), and [embedded type information](../../../standard/assembly/embed-types-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="b59a7-105">이전 버전의 C#에서는 `get` 메서드에 매개 변수가 없고 `set` 메서드에 하나의 값 매개 변수가 있는 경우에만 메서드를 속성으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-105">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="b59a7-106">그러나 모든 COM 속성이 이러한 제한을 충족하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-106">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="b59a7-107">예를 들어 Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> 속성에는 범위 이름에 대한 매개 변수가 필요한 `get` 접근자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-107">For example, the Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="b59a7-108">이전에는 `Range` 속성에 직접 액세스할 수 없었기 때문에 다음 예제와 같이 `get_Range` 메서드를 대신 사용해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-108">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 <span data-ttu-id="b59a7-109">인덱싱된 속성을 사용하면 대신 다음과 같이 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-109">Indexed properties enable you to write the following instead:</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
> <span data-ttu-id="b59a7-110">또한 앞의 예제에서는 [선택적 인수](../classes-and-structs/named-and-optional-arguments.md) 기능을 사용하므로 `Type.Missing`을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-110">The previous example also uses the [optional arguments](../classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="b59a7-111">마찬가지로, C# 3.0 이하에서 <xref:Microsoft.Office.Interop.Excel.Range> 개체의 `Value` 속성 값을 설정하려면 두 개의 인수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-111">Similarly to set the value of the `Value` property of a <xref:Microsoft.Office.Interop.Excel.Range> object in C# 3.0 and earlier, two arguments are required.</span></span> <span data-ttu-id="b59a7-112">하나는 범위 값의 형식을 지정하는 선택적 매개 변수의 인수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-112">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="b59a7-113">다른 하나는 `Value` 속성의 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-113">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="b59a7-114">다음 예제에서는 이러한 기법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-114">The following examples illustrate these techniques.</span></span> <span data-ttu-id="b59a7-115">둘 다 A1 셀의 값을 `Name`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-115">Both set the value of the A1 cell to `Name`.</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 <span data-ttu-id="b59a7-116">인덱싱된 속성을 사용하면 대신 다음 코드와 같이 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-116">Indexed properties enable you to write the following code instead.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 <span data-ttu-id="b59a7-117">인덱싱된 속성을 직접 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-117">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="b59a7-118">이 기능은 기존 인덱싱된 속성의 사용만을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-118">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b59a7-119">예</span><span class="sxs-lookup"><span data-stu-id="b59a7-119">Example</span></span>  
 <span data-ttu-id="b59a7-120">다음 코드에서는 전체 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b59a7-120">The following code shows a complete example.</span></span> <span data-ttu-id="b59a7-121">Office API에 액세스하는 프로젝트를 설정하는 방법에 대한 자세한 내용은 [방법: Visual C# 기능을 사용하여 Office Interop 개체에 액세스](./how-to-access-office-onterop-objects.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b59a7-121">For more information about how to set up a project that accesses the Office API, see [How to: Access Office Interop Objects by Using Visual C# Features](./how-to-access-office-onterop-objects.md).</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="b59a7-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b59a7-122">See also</span></span>

- [<span data-ttu-id="b59a7-123">명명된 인수 및 선택적 인수</span><span class="sxs-lookup"><span data-stu-id="b59a7-123">Named and Optional Arguments</span></span>](../classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="b59a7-124">dynamic</span><span class="sxs-lookup"><span data-stu-id="b59a7-124">dynamic</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="b59a7-125">dynamic 형식 사용</span><span class="sxs-lookup"><span data-stu-id="b59a7-125">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="b59a7-126">방법: Office 프로그래밍에서 명명된 인수 및 선택적 인수 사용</span><span class="sxs-lookup"><span data-stu-id="b59a7-126">How to: Use Named and Optional Arguments in Office Programming</span></span>](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="b59a7-127">방법: Visual C# 기능을 사용하여 Office Interop 개체에 액세스</span><span class="sxs-lookup"><span data-stu-id="b59a7-127">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](./how-to-access-office-onterop-objects.md)
- [<span data-ttu-id="b59a7-128">연습: Office 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b59a7-128">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
