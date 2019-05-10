---
title: (Visual Basic)의 기본 단락 스타일 찾기
ms.date: 07/20/2015
ms.assetid: 9d094a4a-ec8c-41b0-b7ab-a3deb2a01d45
ms.openlocfilehash: f874033b9a070b951d27f37aae36f738ab1fd222
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64618372"
---
# <a name="finding-the-default-paragraph-style-visual-basic"></a><span data-ttu-id="b7f47-102">(Visual Basic)의 기본 단락 스타일 찾기</span><span class="sxs-lookup"><span data-stu-id="b7f47-102">Finding the Default Paragraph Style (Visual Basic)</span></span>
<span data-ttu-id="b7f47-103">WordprocessingML 문서에서 정보 조작 자습서의 첫 번째 작업은 문서에 있는 단락의 기본 스타일을 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b7f47-103">The first task in the Manipulating Information in a WordprocessingML Document tutorial is to find the default style of paragraphs in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7f47-104">예제</span><span class="sxs-lookup"><span data-stu-id="b7f47-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b7f47-105">설명</span><span class="sxs-lookup"><span data-stu-id="b7f47-105">Description</span></span>  
 <span data-ttu-id="b7f47-106">다음 예제에서는 Office Open XML WordprocessingML 문서를 열고 패키지의 문서 및 스타일 부분을 찾은 다음 기본 스타일 이름을 찾는 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f47-106">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="b7f47-107">Office Open XML 문서 패키지 및 구성 하는 부분에 대 한 정보를 참조 하세요 [세부 정보의 Office Open XML WordprocessingML 문서 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f47-107">For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span></span>  
  
 <span data-ttu-id="b7f47-108">쿼리에서는 값이 "paragraph"인 `w:style` 특성과 값이 "1"인 `w:type` 특성을 가진 `w:default`이라는 노드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f47-108">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="b7f47-109">이러한 특성을 가진 XML 노드는 하나뿐이기 때문에 쿼리에서는 <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> 연산자를 사용하여 컬렉션을 singleton으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f47-109">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="b7f47-110">그런 다음 이름이 `w:styleId`인 특성의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b7f47-110">It then gets the value of the attribute with the name `w:styleId`.</span></span>  
  
 <span data-ttu-id="b7f47-111">이 예제에서는 WindowsBase 어셈블리의 클래스를 사용하고</span><span class="sxs-lookup"><span data-stu-id="b7f47-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="b7f47-112"><xref:System.IO.Packaging?displayProperty=nameWithType> 네임스페이스의 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f47-112">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b7f47-113">코드</span><span class="sxs-lookup"><span data-stu-id="b7f47-113">Code</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
  
    Sub Main()  
  
        Const fileName As String = "SampleDoc.docx"  
  
        Const documentRelationshipType As String = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Const stylesRelationshipType As String = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = _  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If docPackageRelationship IsNot Nothing Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _  
                  docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                ' Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                ' Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = _  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If styleRelation IsNot Nothing Then  
                    Dim styleUri As Uri = _  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    ' Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        ' The following query finds all the paragraphs that have the default style.  
        Dim defParas As IEnumerable(Of XElement) = _  
            From style In styleDoc.Root.<w:style> _  
            Where style.@w:type.Equals("paragraph") And _  
                   style.@w:default.Equals("1") _  
            Select style  
        ' Then find the style of the first.  
        Dim defaultStyle As String = defParas.First().@w:styleId  
  
        Console.WriteLine("The default style is: " & defaultStyle)  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="b7f47-114">설명</span><span class="sxs-lookup"><span data-stu-id="b7f47-114">Comments</span></span>  
 <span data-ttu-id="b7f47-115">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f47-115">This example produces the following output:</span></span>  
  
```  
The default style is: Normal  
```  
  
## <a name="next-steps"></a><span data-ttu-id="b7f47-116">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b7f47-116">Next Steps</span></span>  
 <span data-ttu-id="b7f47-117">다음 예제에서는 문서의 모든 단락과 단락의 스타일을 찾는 유사한 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b7f47-117">In the next example, you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>  
  
- [<span data-ttu-id="b7f47-118">단락 및 해당 스타일 (Visual Basic) 검색</span><span class="sxs-lookup"><span data-stu-id="b7f47-118">Retrieving the Paragraphs and Their Styles (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)  
  
## <a name="see-also"></a><span data-ttu-id="b7f47-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="b7f47-119">See also</span></span>

- [<span data-ttu-id="b7f47-120">자습서: (Visual Basic) WordprocessingML 문서에서 내용 조작</span><span class="sxs-lookup"><span data-stu-id="b7f47-120">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
