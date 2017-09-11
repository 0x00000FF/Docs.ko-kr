---
title: "제네릭 및 배열(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 46cea2733504e56aec5e65a4c9a8b655bc9431cf
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="0360f-102">제네릭 및 배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="0360f-102">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="0360f-103">C# 2.0 이상에서 하한이 0인 1차원 배열은 자동으로 <xref:System.Collections.Generic.IList%601>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0360f-103">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="0360f-104">이러한 특성으로 인해 동일한 코드를 사용하여 배열 및 기타 컬렉션 형식에서 반복할 수 있는 제네릭 메서드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0360f-104">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="0360f-105">이 기술은 주로 컬렉션에서 데이터를 읽는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0360f-105">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="0360f-106"><xref:System.Collections.Generic.IList%601> 인터페이스는 배열에서 요소를 추가하거나 제거하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0360f-106">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="0360f-107">이 컨텍스트의 배열에서 <xref:System.Collections.Generic.IList%601.RemoveAt%2A>과 같은 <xref:System.Collections.Generic.IList%601> 메서드를 호출하려는 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0360f-107">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="0360f-108">다음 코드 예제는 <xref:System.Collections.Generic.IList%601> 입력 매개 변수를 사용하는 단일 제네릭 메서드가 목록과 배열(여기에서는 정수 배열) 모두를 통해 반복하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0360f-108">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 <span data-ttu-id="0360f-109">[!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0360f-109">[!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0360f-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0360f-110">See Also</span></span>  
 <span data-ttu-id="0360f-111"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="0360f-111"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="0360f-112">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0360f-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0360f-113">[제네릭](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="0360f-113">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 <span data-ttu-id="0360f-114">[배열](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="0360f-114">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 [<span data-ttu-id="0360f-115">제네릭</span><span class="sxs-lookup"><span data-stu-id="0360f-115">Generics</span></span>](~/docs/standard/generics/index.md)

