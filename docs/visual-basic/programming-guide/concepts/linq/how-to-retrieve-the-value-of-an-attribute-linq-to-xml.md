---
title: '방법: 특성 값 검색(LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: 6593639dcdc234ddda808cfdb5e85ebe1a771b62
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80248949"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="3c0c1-102">방법: 특성 값(LINQ에서 XML까지)(시각적 기본)을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0c1-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="3c0c1-103">이 항목에서는 특성의 값을 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c0c1-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="3c0c1-104">두 가지 주요 방법이 있습니다. <xref:System.Xml.Linq.XAttribute>를 원하는 형식으로 캐스팅할 수 있습니다. 그러면 명시적 변환 연산자가 요소나 특성의 내용을 지정된 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0c1-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="3c0c1-105">또는 <xref:System.Xml.Linq.XAttribute.Value%2A> 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0c1-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="3c0c1-106">그러나 일반적으로 캐스팅이 더 나은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0c1-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="3c0c1-107">nullable 값 형식에 특성을 캐스팅하는 경우 존재할 수도 있거나 존재하지 않을 수도 있는 특성값을 검색할 때 코드를 작성하는 것이 더 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0c1-107">If you cast the attribute to a nullable value type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="3c0c1-108">이 기술의 예는 [요소의 값 검색(LINQ에서 XML까지)(시각적 기본)을 참조합니다.](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="3c0c1-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c0c1-109">예제</span><span class="sxs-lookup"><span data-stu-id="3c0c1-109">Example</span></span>  
 <span data-ttu-id="3c0c1-110">Visual Basic에서는 통합 특성 속성을 사용하여 특성의 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0c1-110">In Visual Basic, you can use the integrated attribute property to retrieve the value of an attribute.</span></span>  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="3c0c1-111">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0c1-111">This example produces the following output:</span></span>  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="3c0c1-112">예제</span><span class="sxs-lookup"><span data-stu-id="3c0c1-112">Example</span></span>  
 <span data-ttu-id="3c0c1-113">Visual Basic에서는 통합 특성 속성을 사용하여 특성의 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0c1-113">In Visual Basic, you can use the integrated attribute property to set the value of an attribute.</span></span> <span data-ttu-id="3c0c1-114">또한 통합 특성 속성을 사용하여 존재하지 않는 특성의 값을 설정하는 경우 특성이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3c0c1-114">Further, if you use the integrated attribute property to set the value of an attribute that does not exist, the attribute will be created.</span></span>  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="3c0c1-115">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0c1-115">This example produces the following output:</span></span>  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a><span data-ttu-id="3c0c1-116">예제</span><span class="sxs-lookup"><span data-stu-id="3c0c1-116">Example</span></span>  
 <span data-ttu-id="3c0c1-117">다음 예제에서는 특성이 네임스페이스에 있는 경우 특성의 값을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c0c1-117">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="3c0c1-118">자세한 내용은 [네임스페이스 개요(LINQ에서 XML까지)(시각적 기본)를](namespaces-overview-linq-to-xml.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c0c1-118">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root aw:Attr="abcde"/>  
        Dim str As String = root.@aw:Attr  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="3c0c1-119">이 예에서 생성되는 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0c1-119">This example produces the following output:</span></span>  
  
```console  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c0c1-120">참조</span><span class="sxs-lookup"><span data-stu-id="3c0c1-120">See also</span></span>

- [<span data-ttu-id="3c0c1-121">LINQ to XML 축(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c0c1-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
