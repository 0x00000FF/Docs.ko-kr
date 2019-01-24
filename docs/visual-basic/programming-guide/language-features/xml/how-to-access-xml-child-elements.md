---
title: '방법: XML 자식 요소 액세스 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 92ecea2c2e6e117add37b30498f5fb34adfeac6e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626657"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="6c390-102">방법: XML 자식 요소 액세스 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c390-102">How to: Access XML Child Elements (Visual Basic)</span></span>
<span data-ttu-id="6c390-103">이 예제에서는 자식을 사용 하는 방법을 XML 요소에 지정 된 이름이 있는 모든 XML 자식 요소에 액세스 하려면 축 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c390-103">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="6c390-104">사용 하 여 특히 합니다 <xref:System.Xml.Linq.XElement.Value%2A> 속성을 하는 컬렉션의 첫 번째 요소의 값을 가져옵니다는 `name` 자식 축 속성에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c390-104">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="6c390-105">합니다 `name` 자식 축 속성 이라는 모든 자식 요소를 가져옵니다 `phone` 에 `contact` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6c390-105">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="6c390-106">또한이 예제에서는 합니다 `phone` 이라는 모든 자식 요소를 액세스 하는 자식 축 속성 `phone` 에 포함 된를 `contact` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6c390-106">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c390-107">예제</span><span class="sxs-lookup"><span data-stu-id="6c390-107">Example</span></span>  
 [!code-vb[VbXMLSamples#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-child-elements_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6c390-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="6c390-108">Compiling the Code</span></span>  
 <span data-ttu-id="6c390-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6c390-109">This example requires:</span></span>  
  
-   <span data-ttu-id="6c390-110"><xref:System.Xml.Linq> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="6c390-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c390-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="6c390-111">See also</span></span>
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6c390-112">XML Child 축 속성</span><span class="sxs-lookup"><span data-stu-id="6c390-112">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="6c390-113">XML 값 속성</span><span class="sxs-lookup"><span data-stu-id="6c390-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="6c390-114">Visual Basic에서 XML에 액세스</span><span class="sxs-lookup"><span data-stu-id="6c390-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="6c390-115">XML</span><span class="sxs-lookup"><span data-stu-id="6c390-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
