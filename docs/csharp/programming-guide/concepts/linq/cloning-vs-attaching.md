---
title: "복제와 연결(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 357c5efa-7b73-4f14-aa67-6bebdba4e7ea
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e58e9538c319c20f9e820ff1de1fb6f973a18bdc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="cloning-vs-attaching-c"></a><span data-ttu-id="3c1fe-102">복제와 연결(C#)</span><span class="sxs-lookup"><span data-stu-id="3c1fe-102">Cloning vs. Attaching (C#)</span></span>
<span data-ttu-id="3c1fe-103"><xref:System.Xml.Linq.XNode>(<xref:System.Xml.Linq.XElement> 포함) 또는 <xref:System.Xml.Linq.XAttribute> 개체를 새 트리에 추가할 때 새 내용에 부모가 없으면 개체가 XML 트리에 추가되기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1fe-103">When adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects to a new tree, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="3c1fe-104">새 내용에 이미 부모가 있고 다른 XML 트리의 일부이면 새 내용이 복제되고</span><span class="sxs-lookup"><span data-stu-id="3c1fe-104">If the new content already is parented, and is part of another XML tree, the new content is cloned.</span></span> <span data-ttu-id="3c1fe-105">새로 복제된 내용이 XML 트리에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c1fe-105">The newly cloned content is then attached to the XML tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c1fe-106">예제</span><span class="sxs-lookup"><span data-stu-id="3c1fe-106">Example</span></span>  
 <span data-ttu-id="3c1fe-107">다음 코드에서는 부모가 있는 요소를 트리에 추가할 때의 동작과 부모가 없는 요소를 트리에 추가할 때의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c1fe-107">The following code demonstrates the behavior when you add a parented element to a tree, and when you add an element with no parent to a tree.</span></span>  
  
```csharp  
// Create a tree with a child element.  
XElement xmlTree1 = new XElement("Root",  
    new XElement("Child1", 1)  
);  
  
// Create an element that is not parented.  
XElement child2 = new XElement("Child2", 2);  
  
// Create a tree and add Child1 and Child2 to it.  
XElement xmlTree2 = new XElement("Root",  
    xmlTree1.Element("Child1"),  
    child2  
);  
  
// Compare Child1 identity.  
Console.WriteLine("Child1 was {0}",  
    xmlTree1.Element("Child1") == xmlTree2.Element("Child1") ?  
    "attached" : "cloned");  
  
// Compare Child2 identity.  
Console.WriteLine("Child2 was {0}",  
    child2 == xmlTree2.Element("Child2") ?  
    "attached" : "cloned");  
```  
  
 <span data-ttu-id="3c1fe-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1fe-108">This example produces the following output:</span></span>  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c1fe-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c1fe-109">See Also</span></span>  
 [<span data-ttu-id="3c1fe-110">XML 트리 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="3c1fe-110">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
