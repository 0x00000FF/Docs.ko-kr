---
title: 자동으로 구현된 속성 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 6768926c782b23dd495b338125d62b7833b0d9e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554519"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="7072a-102">자동으로 구현된 속성(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="7072a-102">Auto-Implemented Properties (C# Programming Guide)</span></span>
<span data-ttu-id="7072a-103">C# 3.0 이상에서는 속성 접근자에 추가적인 논리가 필요하지 않을 경우 자동 구현 속성을 통해 속성 선언이 더 간결해집니다.</span><span class="sxs-lookup"><span data-stu-id="7072a-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="7072a-104">이를 통해 클라이언트 코드에서 개체를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7072a-104">They also enable client code to create objects.</span></span> <span data-ttu-id="7072a-105">다음 예제와 같이 속성을 선언할 때 컴파일러는 속성의 `get` 및 `set` 접근자를 통해서만 액세스할 수 있는 전용 익명 지원 필드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7072a-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7072a-106">예제</span><span class="sxs-lookup"><span data-stu-id="7072a-106">Example</span></span>  
 <span data-ttu-id="7072a-107">다음 예제에서는 일부 자동 구현 속성이 있는 간단한 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7072a-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/auto-implemented-properties_1.cs)]  
  
 <span data-ttu-id="7072a-108">C# 6 이상 버전에서는 필드와 유사하게 자동 구현 속성을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7072a-108">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 <span data-ttu-id="7072a-109">앞의 예제에 표시된 클래스는 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7072a-109">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="7072a-110">클라이언트 코드에서는 개체가 만들어진 후 개체의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7072a-110">Client code can change the values in objects after they are created.</span></span> <span data-ttu-id="7072a-111">데이터 및 중요 동작(메서드)을 포함하는 복잡한 클래스에는 공용 속성을 포함해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7072a-111">In complex classes that contain significant behavior (methods) as well as data, it is often necessary to have public properties.</span></span> <span data-ttu-id="7072a-112">그러나 값 집합(데이터)만 캡슐화하고 동작이 적거나 없는 작은 클래스나 구조체의 경우 set 접근자를 [private](../../../csharp/language-reference/keywords/private.md)로 선언하거나(소비자에 대한 변경 불가능) get 접근자만 선언하여(생성자를 제외한 모든 위치에서 변경 불가능) 개체를 변경 불가능으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7072a-112">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../../csharp/language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="7072a-113">자세한 내용은 [방법: 자동으로 구현된 속성을 사용하여 간단한 클래스 구현](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md)</span><span class="sxs-lookup"><span data-stu-id="7072a-113">For more information, see [How to: Implement a Lightweight Class with Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7072a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7072a-114">See also</span></span>

- [<span data-ttu-id="7072a-115">속성</span><span class="sxs-lookup"><span data-stu-id="7072a-115">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [<span data-ttu-id="7072a-116">한정자</span><span class="sxs-lookup"><span data-stu-id="7072a-116">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
