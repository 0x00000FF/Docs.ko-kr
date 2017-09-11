---
title: "단락 및 해당 스타일 (Visual Basic) 검색 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: d9ed2238-d38e-4ad4-b88b-db7859df9bde
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d21ea826c8263ff391d4174ad1a7ebb173bb54d9
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="retrieving-the-paragraphs-and-their-styles-visual-basic"></a><span data-ttu-id="a4aad-102">단락 및 해당 스타일 (Visual Basic) 검색</span><span class="sxs-lookup"><span data-stu-id="a4aad-102">Retrieving the Paragraphs and Their Styles (Visual Basic)</span></span>
<span data-ttu-id="a4aad-103">이 예제에서는 WordprocessingML 문서에서 단락 노드를 검색하는 쿼리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-103">In this example, we write a query that retrieves the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="a4aad-104">또한 각 단락의 스타일도 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-104">It also identifies the style of each paragraph.</span></span>  
  
 <span data-ttu-id="a4aad-105">이전 예제에서 쿼리를 기반으로이 쿼리 [(Visual Basic)의 기본 단락 스타일 찾기](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md), 스타일의 목록에서 기본 스타일을 검색 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-105">This query builds on the query in the previous example, [Finding the Default Paragraph Style (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md), which retrieves the default style from the list of styles.</span></span> <span data-ttu-id="a4aad-106">이 정보는 쿼리에서 스타일이 명시적으로 설정되지 않은 단락의 스타일을 식별할 수 있도록 하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-106">This information is required so that the query can identify the style of paragraphs that do not have a style explicitly set.</span></span> <span data-ttu-id="a4aad-107">단락 스타일은 `w:pPr` 요소를 통해 설정되며 단락이 이 요소를 포함하지 않으면 기본 스타일로 서식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-107">Paragraph styles are set through the `w:pPr` element; if a paragraph does not contain this element, it is formatted with the default style.</span></span>  
  
 <span data-ttu-id="a4aad-108">이 항목에서는 몇 가지 쿼리 부분의 의미에 대해 설명한 다음 작동하는 전체 예제의 일부로 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-108">This topic explains the significance of some pieces of the query, then shows the query as part of a complete, working example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4aad-109">예제</span><span class="sxs-lookup"><span data-stu-id="a4aad-109">Example</span></span>  
 <span data-ttu-id="a4aad-110">문서의 모든 단락과 단락 스타일을 검색하는 쿼리의 소스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-110">The source of the query to retrieve all the paragraphs in a document and their styles is as follows:</span></span>  
  
```vb  
xDoc.Root.<w:body>...<w:p>  
```  
  
 <span data-ttu-id="a4aad-111">이 식은 이전 예제에서 쿼리의 원본 비슷합니다 [(Visual Basic)의 기본 단락 스타일 찾기](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-111">This expression is similar to the source of the query in the previous example, [Finding the Default Paragraph Style (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md).</span></span> <span data-ttu-id="a4aad-112">주요 차이점은 사용 한다는 것은 <xref:System.Xml.Linq.XContainer.Descendants%2A>축 대신는 <xref:System.Xml.Linq.XContainer.Elements%2A>축.</xref:System.Xml.Linq.XContainer.Elements%2A> </xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="a4aad-112">The main difference is that it uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis instead of the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span> <span data-ttu-id="a4aad-113">쿼리에서 사용 된 <xref:System.Xml.Linq.XContainer.Descendants%2A>축 단락은 본문 요소의 직계 자식 문서의 섹션이 포함 된 때문에 되지 것입니다; 대신, 단락을 두 가지 수준 아래로 계층 구조에서.</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="a4aad-113">The query uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis because in documents that have sections, the paragraphs will not be the direct children of the body element; rather, the paragraphs will be two levels down in the hierarchy.</span></span> <span data-ttu-id="a4aad-114">사용 하 여는 <xref:System.Xml.Linq.XContainer.Descendants%2A>축에는 코드에 대 한 작업 문서에서 섹션을 사용 하는 여부.</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="a4aad-114">By using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis, the code will work of whether or not the document uses sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4aad-115">예제</span><span class="sxs-lookup"><span data-stu-id="a4aad-115">Example</span></span>  
 <span data-ttu-id="a4aad-116">쿼리에서는 `Let` 절을 사용하여 스타일 노드가 포함된 요소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-116">The query uses a `Let` clause to determine the element that contains the style node.</span></span> <span data-ttu-id="a4aad-117">요소가 없으면 `styleNode`가 `Nothing`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-117">If there is no element, then `styleNode` is set to `Nothing`:</span></span>  
  
```vb  
Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault()  
```  
  
 <span data-ttu-id="a4aad-118">`Let` 절 먼저 사용 하 여는 <xref:System.Xml.Linq.XContainer.Elements%2A>축 이라는 모든 요소를 찾은 `pPr`를 사용 하 여는 <xref:System.Xml.Linq.Extensions.Elements%2A>확장 메서드 라는 모든 자식 요소를 `pStyle`, 마지막으로 사용 하 여는 <xref:System.Linq.Enumerable.FirstOrDefault%2A>표준 쿼리 연산자를 단일 컬렉션으로 변환 합니다.</xref:System.Linq.Enumerable.FirstOrDefault%2A> </xref:System.Xml.Linq.Extensions.Elements%2A> </xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="a4aad-118">The `Let` clause first uses the <xref:System.Xml.Linq.XContainer.Elements%2A> axis to find all elements named `pPr`, then uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method to find all child elements named `pStyle`, and finally uses the <xref:System.Linq.Enumerable.FirstOrDefault%2A> standard query operator to convert the collection to a singleton.</span></span> <span data-ttu-id="a4aad-119">컬렉션이 비어 있으면 `styleNode`가 `Nothing`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-119">If the collection is empty, `styleNode` is set to `Nothing`.</span></span> <span data-ttu-id="a4aad-120">이 방법은 `pStyle` 하위 노드를 찾을 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-120">This is a useful idiom to look for the `pStyle` descendant node.</span></span> <span data-ttu-id="a4aad-121">`pPr` 자식 노드가 없으면 코드에서 예외를 throw하지 않고, 대신 `styleNode`가 `Nothing`로 설정됩니다. 이는 이 `Let` 절의 원하는 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-121">Note that if the `pPr` child node does not exist, the code does nor fail by throwing an exception; instead, `styleNode` is set to `Nothing`, which is the desired behavior of this `Let` clause.</span></span>  
  
 <span data-ttu-id="a4aad-122">쿼리에서는 두 멤버 `StyleName` 및 `ParagraphNode`가 있는 익명 형식의 컬렉션을 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-122">The query projects a collection of an anonymous type with two members, `StyleName` and `ParagraphNode`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4aad-123">예제</span><span class="sxs-lookup"><span data-stu-id="a4aad-123">Example</span></span>  
 <span data-ttu-id="a4aad-124">이 예제에서는 WordprocessingML 문서를 처리하여 WordprocessingML 문서에서 단락 노드를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-124">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="a4aad-125">또한 각 단락의 스타일도 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-125">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="a4aad-126">이 예제는 이 자습서의 이전 예제를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-126">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="a4aad-127">새 쿼리는 아래에 있는 코드의 주석에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-127">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="a4aad-128">이 예제에 대 한 소스 문서를 만들기 위한 지침을 찾을 수 있습니다 [원본 Office Open XML 문서 (Visual Basic)를 만드는](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-128">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="a4aad-129">이 예제에서는 WindowsBase 어셈블리의 클래스를 사용하고</span><span class="sxs-lookup"><span data-stu-id="a4aad-129">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="a4aad-130">형식을 사용는 <xref:System.IO.Packaging?displayProperty=fullName>네임 스페이스.</xref:System.IO.Packaging?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a4aad-130">It uses types in the <xref:System.IO.Packaging?displayProperty=fullName> namespace.</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, ByVal defaultStyle As String) As String  
        If (styleNode Is Nothing) Then  
            Return defaultStyle  
        Else  
            Return styleNode.@w:val  
        End If  
    End Function  
  
    Sub Main()  
        Dim fileName = "SampleDoc.docx"  
  
        Dim documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Dim stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
        Dim wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                '  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                '  Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If (styleRelation IsNot Nothing) Then  
                    Dim styleUri As Uri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    '  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        Dim defaultStyle As String = _  
            ( _  
                From style In styleDoc.Root.<w:style> _  
                Where style.@w:type = "paragraph" And _  
                      style.@w:default = "1" _  
                Select style _  
            ).First().@w:styleId  
  
        ' Following is the new query that finds all paragraphs in the  
        ' document and their styles.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault() _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        For Each p In paragraphs  
            Console.WriteLine("StyleName:{0}", p.StyleName)  
        Next  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="a4aad-131">이 예제는 다음에 설명 된 문서에 적용 하면 출력을 생성 [원본 Office Open XML 문서 (Visual Basic)를 만드는](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-131">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
```  
StyleName:Heading1  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
```  
  
## <a name="next-steps"></a><span data-ttu-id="a4aad-132">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a4aad-132">Next Steps</span></span>  
 <span data-ttu-id="a4aad-133">다음 항목에서 [(Visual Basic) 단락의 텍스트 검색](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), 단락의 텍스트를 검색 하는 쿼리를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4aad-133">In the next topic, [Retrieving the Text of the Paragraphs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), you'll create a query to retrieve the text of paragraphs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4aad-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4aad-134">See Also</span></span>  
 [<span data-ttu-id="a4aad-135">자습서: WordprocessingML 문서 (Visual Basic)에서 내용 조작</span><span class="sxs-lookup"><span data-stu-id="a4aad-135">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
