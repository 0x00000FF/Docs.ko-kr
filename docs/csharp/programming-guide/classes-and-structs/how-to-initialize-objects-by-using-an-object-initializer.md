---
title: '방법: 개체 이니셜라이저를 사용하여 개체 초기화(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 1f5f068cd8dc3787eb8cb2cd72cc30e9ea159390
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33320910"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="eec5c-102">방법: 개체 이니셜라이저를 사용하여 개체 초기화(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="eec5c-102">How to: Initialize Objects by Using an Object Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="eec5c-103">개체 이니셜라이저를 사용하여 형식에 대한 생성자를 명시적으로 호출하지 않고 선언적 방식으로 형식 개체를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eec5c-103">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
 <span data-ttu-id="eec5c-104">다음 예제에서는 명명된 개체와 함께 개체 이니셜라이저를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eec5c-104">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="eec5c-105">컴파일러는 먼저 기본 인스턴스 생성자에 액세스한 다음 멤버 초기화를 처리하여 개체 이니셜라이저를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="eec5c-105">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="eec5c-106">따라서 클래스에서 기본 생성자가 `private`로 선언된 경우 공용 액세스가 필요한 개체 이니셜라이저는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="eec5c-106">Therefore, if the default constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>  
  
 <span data-ttu-id="eec5c-107">무명 형식을 정의하는 경우 개체 이니셜라이저를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eec5c-107">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="eec5c-108">자세한 내용은 [방법: 쿼리에서 요소 속성의 하위 집합 반환](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eec5c-108">For more information, see [How to: Return Subsets of Element Properties in a Query](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eec5c-109">예</span><span class="sxs-lookup"><span data-stu-id="eec5c-109">Example</span></span>  
 <span data-ttu-id="eec5c-110">다음 예제에서는 개체 이니셜라이저를 사용하여 새 `StudentName` 형식을 초기화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eec5c-110">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="eec5c-111">예</span><span class="sxs-lookup"><span data-stu-id="eec5c-111">Example</span></span>  
 <span data-ttu-id="eec5c-112">다음 예제에서는 컬렉션 이니셜라이저를 사용하여 `StudentName` 형식 컬렉션을 초기화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eec5c-112">The following example shows how to initialize a collection of `StudentName` types by using a collection initializer.</span></span> <span data-ttu-id="eec5c-113">컬렉션 이니셜라이저는 일련의 쉼표로 구분된 개체 이니셜라이저입니다.</span><span class="sxs-lookup"><span data-stu-id="eec5c-113">Note that a collection initializer is a series of comma-separated object initializers.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eec5c-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="eec5c-114">Compiling the Code</span></span>  
 <span data-ttu-id="eec5c-115">이 코드를 실행하려면 클래스를 복사하여 Visual Studio에서 만든 Visual C# 콘솔 응용 프로그램 프로젝트에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="eec5c-115">To run this code, copy and paste the class into a Visual C# console application project that has been created in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eec5c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eec5c-116">See Also</span></span>  
 [<span data-ttu-id="eec5c-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="eec5c-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="eec5c-118">개체 이니셜라이저 및 컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="eec5c-118">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
