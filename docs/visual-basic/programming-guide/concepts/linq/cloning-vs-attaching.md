---
title: 복제와 연결 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 3c3bd105-c9d3-49bd-875b-27ab4e8bc7a3
ms.openlocfilehash: 59ffedfdbb2820683f1e6cc232154688f5c29fc8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832296"
---
# <a name="cloning-vs-attaching-visual-basic"></a><span data-ttu-id="3fd1f-102">복제와 연결 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3fd1f-102">Cloning vs. Attaching (Visual Basic)</span></span>
<span data-ttu-id="3fd1f-103"><xref:System.Xml.Linq.XNode>(<xref:System.Xml.Linq.XElement> 포함) 또는 <xref:System.Xml.Linq.XAttribute> 개체를 새 트리에 추가할 때 새 내용에 부모가 없으면 개체가 XML 트리에 추가되기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-103">When adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects to a new tree, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="3fd1f-104">새 내용에 이미 부모가 있고 다른 XML 트리의 일부이면 새 내용이 복제되고</span><span class="sxs-lookup"><span data-stu-id="3fd1f-104">If the new content already is parented, and is part of another XML tree, the new content is cloned.</span></span> <span data-ttu-id="3fd1f-105">새로 복제된 내용이 XML 트리에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-105">The newly cloned content is then attached to the XML tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fd1f-106">예제</span><span class="sxs-lookup"><span data-stu-id="3fd1f-106">Example</span></span>  
 <span data-ttu-id="3fd1f-107">다음 코드에서는 부모가 있는 요소를 트리에 추가할 때의 동작과 부모가 없는 요소를 트리에 추가할 때의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-107">The following code demonstrates the behavior when you add a parented element to a tree, and when you add an element with no parent to a tree.</span></span>  
  
```vb  
' Create a tree with a child element.  
Dim xmlTree1 As XElement = _  
    <Root>  
        <Child1>1</Child1>  
    </Root>  
  
' Create an element that is not parented.  
Dim child2 As XElement = <Child2>2</Child2>  
  
' Create a tree and add Child1 and Child2 to it.  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child1>(0) %>  
        <%= child2 %>  
    </Root>  
  
' Compare Child1 identity.  
Console.WriteLine("Child1 was {0}", _  
    IIf(xmlTree1.Element("Child1") Is xmlTree2.Element("Child1"), _  
    "attached", "cloned"))  
  
' Compare Child2 identity.  
Console.WriteLine("Child2 was {0}", _  
    IIf(child2 Is xmlTree2.Element("Child2"), _  
    "attached", "cloned"))  
```  
  
 <span data-ttu-id="3fd1f-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-108">This example produces the following output:</span></span>  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="3fd1f-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="3fd1f-109">See also</span></span>

- [<span data-ttu-id="3fd1f-110">XML 트리 만들기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3fd1f-110">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
