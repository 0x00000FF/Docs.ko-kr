---
title: 인터페이스의 인덱서 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: 4ac51589ed1680f8484fde797c045d15beed3af9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712119"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="d1d2f-102">인터페이스의 인덱서(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="d1d2f-102">Indexers in Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="d1d2f-103">[interface](../../language-reference/keywords/interface.md)에 인덱서를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d2f-103">Indexers can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="d1d2f-104">인터페이스 인덱서 접근자와 [class](../../language-reference/keywords/class.md) 인덱서 접근자 간에는 다음과 같은 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d2f-104">Accessors of interface indexers differ from the accessors of [class](../../language-reference/keywords/class.md) indexers in the following ways:</span></span>  
  
- <span data-ttu-id="d1d2f-105">인터페이스 접근자는 한정자를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d2f-105">Interface accessors do not use modifiers.</span></span>  
  
- <span data-ttu-id="d1d2f-106">인터페이스 접근자에는 본문이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d2f-106">An interface accessor does not have a body.</span></span>  
  
 <span data-ttu-id="d1d2f-107">따라서 접근자의 목적은 인덱서가 읽기/쓰기인지, 읽기 전용인지, 쓰기 전용인지를 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d2f-107">Thus, the purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span>  
  
 <span data-ttu-id="d1d2f-108">다음은 인터페이스 인덱서 접근자의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d2f-108">The following is an example of an interface indexer accessor:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#3)]  
  
 <span data-ttu-id="d1d2f-109">인덱서의 시그니처는 동일한 인터페이스에 선언된 다른 모든 인덱서의 시그니처와 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d2f-109">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1d2f-110">예제</span><span class="sxs-lookup"><span data-stu-id="d1d2f-110">Example</span></span>  
 <span data-ttu-id="d1d2f-111">다음 예제에서는 인터페이스 인덱서를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1d2f-111">The following example shows how to implement interface indexers.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#4)]  
  
 <span data-ttu-id="d1d2f-112">앞의 예제에서는 인터페이스 멤버의 정규화된 이름을 사용하여 명시적 인터페이스 멤버 구현을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d2f-112">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="d1d2f-113">예:</span><span class="sxs-lookup"><span data-stu-id="d1d2f-113">For example:</span></span>  
  
```csharp  
string ISomeInterface.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="d1d2f-114">그러나 정규화된 이름은 클래스가 동일한 인덱서 시그니처로 둘 이상의 인터페이스를 구현할 때 모호성을 피하기 위해서만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d2f-114">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="d1d2f-115">예를 들어 `Employee` 클래스가 두 인터페이스 `ICitizen` 및 `IEmployee`를 구현하고 두 인터페이스의 인덱서 시그니처가 같으면 명시적 인터페이스 멤버 구현이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d2f-115">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="d1d2f-116">즉, 다음과 같은 인덱서 선언이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d2f-116">That is, the following indexer declaration:</span></span>  
  
```csharp  
string IEmployee.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="d1d2f-117">이 선언은 `IEmployee` 인터페이스의 인덱서를 구현합니다. 또한 다음과 같은 선언이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d2f-117">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>  
  
```csharp  
string ICitizen.this[int index]
{   
}   
```  
  
 <span data-ttu-id="d1d2f-118">이 선언은 `ICitizen` 인터페이스의 인덱서를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d2f-118">implements the indexer on the `ICitizen` interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1d2f-119">참조</span><span class="sxs-lookup"><span data-stu-id="d1d2f-119">See also</span></span>

- [<span data-ttu-id="d1d2f-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d1d2f-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d1d2f-121">인덱서</span><span class="sxs-lookup"><span data-stu-id="d1d2f-121">Indexers</span></span>](./index.md)
- [<span data-ttu-id="d1d2f-122">속성</span><span class="sxs-lookup"><span data-stu-id="d1d2f-122">Properties</span></span>](../classes-and-structs/properties.md)
- [<span data-ttu-id="d1d2f-123">인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1d2f-123">Interfaces</span></span>](../interfaces/index.md)
