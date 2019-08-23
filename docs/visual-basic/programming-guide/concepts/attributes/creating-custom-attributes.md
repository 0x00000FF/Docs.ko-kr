---
title: 사용자 지정 특성 만들기 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
ms.openlocfilehash: e4b55f92466fde47011937d08c946c9c75ca07b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966326"
---
# <a name="creating-custom-attributes-visual-basic"></a><span data-ttu-id="bf4c5-102">사용자 지정 특성 만들기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf4c5-102">Creating Custom Attributes (Visual Basic)</span></span>
<span data-ttu-id="bf4c5-103">메타데이터를 통해 특성의 정의를 빠르고 쉽게 식별할 수 있도록 해주는 <xref:System.Attribute>로부터 직접적으로 또는 간접적으로 상속한 특성 클래스를 정의하여 사용자 지정 특성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf4c5-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="bf4c5-104">형식을 작성한 프로그래머의 이름을 형식에 태그로 지정한다고 가정해봅시다.</span><span class="sxs-lookup"><span data-stu-id="bf4c5-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="bf4c5-105">사용자 지정 `Author` 특성 클래스를 아래와 같이 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf4c5-105">You might define a custom `Author` attribute class:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
        version = 1.0  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="bf4c5-106">클래스 이름은 특성의 이름인 `Author`입니다.</span><span class="sxs-lookup"><span data-stu-id="bf4c5-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="bf4c5-107">이 클래스는 `System.Attribute`를 상속하므로 사용자 지정 특성 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bf4c5-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="bf4c5-108">생성자의 매개 변수는 사용자 지정 특성의 위치 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bf4c5-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="bf4c5-109">이 예제에서는 `name`이 위치 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bf4c5-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="bf4c5-110">모든 public 읽기-쓰기 필드 또는 속성은 명명된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bf4c5-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="bf4c5-111">이 경우에는 `version`이 유일한 명명된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bf4c5-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="bf4c5-112">클래스 및 `Structure` 선언에서만 `Author` 특성을 유효하게 설정하려면 `AttributeUsage` 특성을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf4c5-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `Structure` declarations.</span></span>  
  
 <span data-ttu-id="bf4c5-113">이 새로운 특성은 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf4c5-113">You could use this new attribute as follows:</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 <span data-ttu-id="bf4c5-114">`AttributeUsage`에는 사용자 지정 특성을 한 번 또는 여러 번 사용하도록 설정하기 위해 사용하는 명명된 매개 변수인 `AllowMultiple`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf4c5-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="bf4c5-115">다음 코드 예제에서는 다중 사용 특성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf4c5-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```vb  
' multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
```  
  
 <span data-ttu-id="bf4c5-116">다음 코드 예제에서는 같은 형식의 여러 특성이 한 클래스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf4c5-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1),   
Author("R. Koch", Version:=1.2)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
    ' R. Koch's code goes here...  
End Class  
```  
  
> [!NOTE]
> <span data-ttu-id="bf4c5-117">특성 클래스에 속성이 포함되면 해당 속성은 읽기-쓰기여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf4c5-117">If your attribute class contains a property, that property must be read-write.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf4c5-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="bf4c5-118">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="bf4c5-119">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="bf4c5-119">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="bf4c5-120">사용자 지정 특성 작성</span><span class="sxs-lookup"><span data-stu-id="bf4c5-120">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- [<span data-ttu-id="bf4c5-121">리플렉션(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf4c5-121">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [<span data-ttu-id="bf4c5-122">특성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf4c5-122">Attributes (Visual Basic)</span></span>](../../../../visual-basic/language-reference/attributes.md)
- [<span data-ttu-id="bf4c5-123">리플렉션을 사용하여 특성 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf4c5-123">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
- [<span data-ttu-id="bf4c5-124">AttributeUsage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf4c5-124">AttributeUsage (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
