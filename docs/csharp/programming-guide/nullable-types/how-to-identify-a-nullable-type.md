---
title: '방법: nullable 형식 식별(C# 프로그래밍 가이드)'
description: 형식이 nullable 형식이거나 인스턴스가 nullable 형식인지 여부를 확인하는 방법 알아보기
ms.date: 08/06/2018
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: bb7ab2b8c13c2b8b4b6cd60e7959a391cd7e75c1
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2018
ms.locfileid: "42754958"
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a><span data-ttu-id="19ddc-103">방법: nullable 형식 식별(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="19ddc-103">How to: Identify a nullable type (C# Programming Guide)</span></span>

<span data-ttu-id="19ddc-104">다음 코드 예제에서는 <xref:System.Type?displayProperty=nameWithType> 인스턴스가 nullable 형식을 나타내는지 여부를 확인하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="19ddc-104">The following example shows how to determine whether a <xref:System.Type?displayProperty=nameWithType> instance represents a nullable type:</span></span>

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

<span data-ttu-id="19ddc-105">예제에서 보여주는 것과 같이 [typeof](../../language-reference/keywords/typeof.md) 연산자를 사용하여 <xref:System.Type?displayProperty=nameWithType> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="19ddc-105">As the example shows, you use the [typeof](../../language-reference/keywords/typeof.md) operator to create a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
<span data-ttu-id="19ddc-106">인스턴스가 있는지 nullable 형식인지 여부를 확인하려는 경우 위의 코드로 테스트되도록 <xref:System.Type> 인스턴스를 가져오는 데 <xref:System.Object.GetType%2A?displayProperty=nameWithType> 메서드를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="19ddc-106">If you want to determine whether an instance is of a nullable type, don't use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method to get a <xref:System.Type> instance to be tested with the preceding code.</span></span> <span data-ttu-id="19ddc-107">nullable 형식의 인스턴스에서 <xref:System.Object.GetType%2A?displayProperty=nameWithType> 메서드를 호출하는 경우 인스턴스는 <xref:System.Object>로 [boxing](using-nullable-types.md#boxing-and-unboxing)됩니다.</span><span class="sxs-lookup"><span data-stu-id="19ddc-107">When you call the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method on an instance of a nullable type, the instance is [boxed](using-nullable-types.md#boxing-and-unboxing) to <xref:System.Object>.</span></span> <span data-ttu-id="19ddc-108">nullable 형식의 Null이 아닌 인스턴스의 boxing은 기본 형식 값의 boxing과 동일하며, <xref:System.Object.GetType%2A>는 nullable 형식의 기본 형식을 나타내는 <xref:System.Type> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="19ddc-108">As boxing of a non-null instance of a nullable type is equivalent to boxing of a value of the underlying type, <xref:System.Object.GetType%2A> returns a <xref:System.Type> object that represents the underlying type of a nullable type:</span></span>

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

<span data-ttu-id="19ddc-109">인스턴스가 nullable 형식인지 여부를 확인하는 데 [is](../../language-reference/keywords/is.md) 연산자를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="19ddc-109">Don't use the [is](../../language-reference/keywords/is.md) operator to determine whether an instance is of a nullable type.</span></span> <span data-ttu-id="19ddc-110">다음 예제에서 보여주는 것과 같이 nullable 형식의 인스턴스 형식과 `is` 연산자를 사용하는 해당 기본 형식을 구분할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19ddc-110">As the following example shows, you cannot distinguish types of instances of a nullable type and its underlying type with using the `is` operator:</span></span>

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

<span data-ttu-id="19ddc-111">다음 예제에서 제공된 코드를 사용하여 인스턴스가 nullable 형식인지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19ddc-111">You can use the code presented in the following example to determine whether an instance is of a nullable type:</span></span>

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]
  
## <a name="see-also"></a><span data-ttu-id="19ddc-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19ddc-112">See also</span></span>

[<span data-ttu-id="19ddc-113">Nullable 형식</span><span class="sxs-lookup"><span data-stu-id="19ddc-113">Nullable types</span></span>](index.md)  
[<span data-ttu-id="19ddc-114">nullable 형식 사용</span><span class="sxs-lookup"><span data-stu-id="19ddc-114">Using nullable types</span></span>](using-nullable-types.md)  
<xref:System.Nullable.GetUnderlyingType%2A>  
