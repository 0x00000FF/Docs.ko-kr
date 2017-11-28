---
title: "방법: 특성을 사용하여 C-C++ 공용 구조체 만들기(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 450fb922079ca6737b8db7754f25435b9c3b884b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a><span data-ttu-id="c988e-102">방법: 특성을 사용하여 C/C++ 공용 구조체 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="c988e-102">How to: Create a C/C++ Union by Using Attributes (C#)</span></span>
<span data-ttu-id="c988e-103">특성을 사용하면 메모리에서 구조체가 레이아웃되는 방식을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c988e-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="c988e-104">예를 들어 `StructLayout(LayoutKind.Explicit)` 및 `FieldOffset` 특성을 사용하여 C/C++에서 공용 구조체로 알려진 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c988e-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c988e-105">예제</span><span class="sxs-lookup"><span data-stu-id="c988e-105">Example</span></span>  
 <span data-ttu-id="c988e-106">이 코드 세그먼트에서 `TestUnion`의 모든 필드는 메모리의 같은 위치에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c988e-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestUnion  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public byte b;  
       }  
```  
  
## <a name="example"></a><span data-ttu-id="c988e-107">예제</span><span class="sxs-lookup"><span data-stu-id="c988e-107">Example</span></span>  
 <span data-ttu-id="c988e-108">다음은 명시적으로 설정된 다른 위치에서 필드가 시작하는 또 다른 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="c988e-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestExplicit  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public long lg;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i1;  
  
           [System.Runtime.InteropServices.FieldOffset(4)]  
           public int i2;  
  
           [System.Runtime.InteropServices.FieldOffset(8)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(12)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(14)]  
           public byte b;  
       }  
```  
  
 <span data-ttu-id="c988e-109">두 개의 정수 필드 `i1` 및 `i2`는 `lg`와 동일한 메모리 위치를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="c988e-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="c988e-110">구조체 레이아웃에 대한 이러한 종류의 제어는 플랫폼 호출을 사용할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c988e-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c988e-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c988e-111">See Also</span></span>  
 <xref:System.Reflection>  
 <xref:System.Attribute>  
 [<span data-ttu-id="c988e-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c988e-112">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c988e-113">특성</span><span class="sxs-lookup"><span data-stu-id="c988e-113">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)  
 [<span data-ttu-id="c988e-114">리플렉션(C#)</span><span class="sxs-lookup"><span data-stu-id="c988e-114">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="c988e-115">특성(C#)</span><span class="sxs-lookup"><span data-stu-id="c988e-115">Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="c988e-116">사용자 지정 특성 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="c988e-116">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="c988e-117">리플렉션을 사용하여 특성 액세스(C#)</span><span class="sxs-lookup"><span data-stu-id="c988e-117">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
