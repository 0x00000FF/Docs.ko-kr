---
title: "기본 단락 스타일 찾기(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: be102177-8ab0-444a-b671-7023e555ffdb
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e2664620127e6e3ed9f723a7c23012905be3781b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="finding-the-default-paragraph-style-c"></a><span data-ttu-id="cb81d-102">기본 단락 스타일 찾기(C#)</span><span class="sxs-lookup"><span data-stu-id="cb81d-102">Finding the Default Paragraph Style (C#)</span></span>
<span data-ttu-id="cb81d-103">WordprocessingML 문서에서 정보 조작 자습서의 첫 번째 작업은 문서에 있는 단락의 기본 스타일을 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cb81d-103">The first task in the Manipulating Information in a WordprocessingML Document tutorial is to find the default style of paragraphs in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb81d-104">예제</span><span class="sxs-lookup"><span data-stu-id="cb81d-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cb81d-105">설명</span><span class="sxs-lookup"><span data-stu-id="cb81d-105">Description</span></span>  
 <span data-ttu-id="cb81d-106">다음 예제에서는 Office Open XML WordprocessingML 문서를 열고 패키지의 문서 및 스타일 부분을 찾은 다음 기본 스타일 이름을 찾는 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb81d-106">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="cb81d-107">Office Open XML 문서 패키지와 패키지를 구성하는 부분에 대한 자세한 내용은 [Office Open XML WordprocessingML 문서 정보(C#)](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb81d-107">For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (C#)](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span></span>  
  
 <span data-ttu-id="cb81d-108">쿼리에서는 값이 "paragraph"인 `w:style` 특성과 값이 "1"인 `w:type` 특성을 가진 `w:default`이라는 노드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cb81d-108">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="cb81d-109">이러한 특성을 가진 XML 노드는 하나뿐이기 때문에 쿼리에서는 <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> 연산자를 사용하여 컬렉션을 singleton으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="cb81d-109">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="cb81d-110">그런 다음 이름이 `w:styleId`인 특성의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cb81d-110">It then gets the value of the attribute with the name `w:styleId`.</span></span>  
  
 <span data-ttu-id="cb81d-111">이 예제에서는 WindowsBase 어셈블리의 클래스를 사용하고</span><span class="sxs-lookup"><span data-stu-id="cb81d-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="cb81d-112"><xref:System.IO.Packaging?displayProperty=nameWithType> 네임스페이스의 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb81d-112">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cb81d-113">코드</span><span class="sxs-lookup"><span data-stu-id="cb81d-113">Code</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship =  
      wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative),  
          docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation =  
          documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
        }  
    }  
}  
  
// The following query finds all the paragraphs that have the default style.  
string defaultStyle =   
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
Console.WriteLine("The default style is: {0}", defaultStyle);  
```  
  
### <a name="comments"></a><span data-ttu-id="cb81d-114">설명</span><span class="sxs-lookup"><span data-stu-id="cb81d-114">Comments</span></span>  
 <span data-ttu-id="cb81d-115">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cb81d-115">This example produces the following output:</span></span>  
  
```  
The default style is: Normal  
```  
  
## <a name="next-steps"></a><span data-ttu-id="cb81d-116">다음 단계</span><span class="sxs-lookup"><span data-stu-id="cb81d-116">Next Steps</span></span>  
 <span data-ttu-id="cb81d-117">다음 예제에서는 문서의 모든 단락과 단락의 스타일을 찾는 유사한 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cb81d-117">In the next example, you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>  
  
-   [<span data-ttu-id="cb81d-118">단락 및 해당 스타일 검색(C#)</span><span class="sxs-lookup"><span data-stu-id="cb81d-118">Retrieving the Paragraphs and Their Styles (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)  
  
## <a name="see-also"></a><span data-ttu-id="cb81d-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb81d-119">See Also</span></span>  
 [<span data-ttu-id="cb81d-120">자습서: WordprocessingML 문서에서 내용 조작</span><span class="sxs-lookup"><span data-stu-id="cb81d-120">Tutorial: Manipulating Content in a WordprocessingML Document</span></span>](http://msdn.microsoft.com/library/2696355e-4f83-4eaf-91b2-baa721f42fb4)
