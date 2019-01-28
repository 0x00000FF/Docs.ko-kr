---
title: 사용자 지정 특성 만들기(C#)
ms.date: 07/20/2015
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
ms.openlocfilehash: 0277a88b7e5beda511f6490261a7009adcfed4ee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674637"
---
# <a name="creating-custom-attributes-c"></a><span data-ttu-id="0abe8-102">사용자 지정 특성 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="0abe8-102">Creating Custom Attributes (C#)</span></span>
<span data-ttu-id="0abe8-103">메타데이터에서 특성 정의를 빠르고 쉽게 식별할 수 있도록 하는 <xref:System.Attribute>에서 직접 또는 간접적으로 파생되는 특성 클래스를 정의하여 자체 사용자 지정 특성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0abe8-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="0abe8-104">형식을 작성한 프로그래머의 이름을 형식에 태그로 지정한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="0abe8-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="0abe8-105">사용자 지정 `Author` 특성 클래스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0abe8-105">You might define a custom `Author` attribute class:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct)  
]  
public class Author : System.Attribute  
{  
    private string name;  
    public double version;  
  
    public Author(string name)  
    {  
        this.name = name;  
        version = 1.0;  
    }  
}  
```  
  
 <span data-ttu-id="0abe8-106">클래스 이름은 특성의 이름인 `Author`입니다.</span><span class="sxs-lookup"><span data-stu-id="0abe8-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="0abe8-107">이 클래스는 `System.Attribute`에서 파생되므로 사용자 지정 특성 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0abe8-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="0abe8-108">생성자의 매개 변수는 사용자 지정 특성의 위치 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0abe8-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="0abe8-109">이 예제에서는 `name`이 위치 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0abe8-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="0abe8-110">모든 public 읽기-쓰기 필드 또는 속성은 명명된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0abe8-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="0abe8-111">이 경우에는 `version`이 유일한 명명된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0abe8-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="0abe8-112">클래스 및 `struct` 선언에서만 `Author` 특성을 유효하게 설정하려면 `AttributeUsage` 특성을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0abe8-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `struct` declarations.</span></span>  
  
 <span data-ttu-id="0abe8-113">이 새로운 특성은 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0abe8-113">You could use this new attribute as follows:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 <span data-ttu-id="0abe8-114">`AttributeUsage`에는 사용자 지정 특성을 한 번 또는 여러 번 사용하도록 설정하는 데 이용하는 명명된 매개 변수인 `AllowMultiple`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0abe8-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="0abe8-115">다음 코드 예제에서는 다중 사용 특성이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0abe8-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class Author : System.Attribute  
```  
  
 <span data-ttu-id="0abe8-116">다음 코드 예제에서는 같은 형식의 여러 특성이 한 클래스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0abe8-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0abe8-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0abe8-117">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="0abe8-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="0abe8-118">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="0abe8-119">사용자 지정 특성 작성</span><span class="sxs-lookup"><span data-stu-id="0abe8-119">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- [<span data-ttu-id="0abe8-120">리플렉션(C#)</span><span class="sxs-lookup"><span data-stu-id="0abe8-120">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)
- [<span data-ttu-id="0abe8-121">특성(C#)</span><span class="sxs-lookup"><span data-stu-id="0abe8-121">Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="0abe8-122">리플렉션을 사용하여 특성 액세스(C#)</span><span class="sxs-lookup"><span data-stu-id="0abe8-122">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
- [<span data-ttu-id="0abe8-123">AttributeUsage(C#)</span><span class="sxs-lookup"><span data-stu-id="0abe8-123">AttributeUsage (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md)
