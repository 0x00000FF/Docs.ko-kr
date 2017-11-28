---
title: "방법: 복사 생성자 작성(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f15d8fabc49cbff5515b78a7d2fb6f9e49d0704e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="da4eb-102">방법: 복사 생성자 작성(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="da4eb-102">How to: Write a Copy Constructor (C# Programming Guide)</span></span>
<span data-ttu-id="da4eb-103">C#에서는 개체에 대한 복사 생성자를 제공하지 않지만 직접 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da4eb-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da4eb-104">예제</span><span class="sxs-lookup"><span data-stu-id="da4eb-104">Example</span></span>  
 <span data-ttu-id="da4eb-105">다음 예제에서 `Person`[클래스](../../../csharp/language-reference/keywords/class.md)는 `Person` 인스턴스를 해당 인수로 사용하는 복사 생성자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="da4eb-105">In the following example, the `Person`[class](../../../csharp/language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="da4eb-106">인수의 속성 값이 `Person`의 새 인스턴스 속성에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="da4eb-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="da4eb-107">코드에는 복사하려는 인스턴스의 `Name` 및 `Age` 속성을 클래스의 인스턴스 생성자에 보내는 대체 복사 생성자가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da4eb-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="da4eb-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da4eb-108">See Also</span></span>  
 <xref:System.ICloneable>  
 [<span data-ttu-id="da4eb-109">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="da4eb-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="da4eb-110">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="da4eb-110">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="da4eb-111">생성자</span><span class="sxs-lookup"><span data-stu-id="da4eb-111">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [<span data-ttu-id="da4eb-112">종료자</span><span class="sxs-lookup"><span data-stu-id="da4eb-112">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
