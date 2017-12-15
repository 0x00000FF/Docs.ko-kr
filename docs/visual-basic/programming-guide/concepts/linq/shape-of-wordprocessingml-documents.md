---
title: "(Visual Basic) WordprocessingML 문서의 모양"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dfb446b-5a07-4c00-9ab3-a74ba734ff3a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5809e8148e7ac426b876ad11948878ee0bfcd016
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2017
---
# <a name="shape-of-wordprocessingml-documents-visual-basic"></a><span data-ttu-id="835b5-102">(Visual Basic) WordprocessingML 문서의 모양</span><span class="sxs-lookup"><span data-stu-id="835b5-102">Shape of WordprocessingML Documents (Visual Basic)</span></span>
<span data-ttu-id="835b5-103">이 항목에서는 WordprocessingML 문서의 XML 모양에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-103">This topic introduces the XML shape of a WordprocessingML document.</span></span>  
  
## <a name="microsoft-office-formats"></a><span data-ttu-id="835b5-104">Microsoft Office 형식</span><span class="sxs-lookup"><span data-stu-id="835b5-104">Microsoft Office Formats</span></span>  
 <span data-ttu-id="835b5-105">2007 Microsoft Office system의 기본 파일 형식은 Office Open XML(일반적으로 Open XML이라고 함)입니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-105">The native file format for the 2007 Microsoft Office system is Office Open XML (commonly called Open XML).</span></span> <span data-ttu-id="835b5-106">Open XML은 Ecma 표준이며 현재 ISO-IEC 표준 과정을 거치고 있는 XML 기반 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-106">Open XML is an XML-based format that an Ecma standard and is currently going through the ISO-IEC standards process.</span></span> <span data-ttu-id="835b5-107">Open XML에 있는 워드 프로세서 파일의 마크업 언어를 WordprocessingML이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-107">The markup language for word processing files within Open XML is called WordprocessingML.</span></span> <span data-ttu-id="835b5-108">이 자습서에서는 WordprocessingML 소스 파일을 예제의 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-108">This tutorial uses WordprocessingML source files as input for the examples.</span></span>  
  
 <span data-ttu-id="835b5-109">Microsoft Office 2003을 사용 하는 경우에 Word, Excel 및 PowerPoint 2007 파일 형식용에 대 한 Microsoft Office 호환 기능 팩을 설치한 경우 Office Open XML 형식에서 문서를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-109">If you are using Microsoft Office 2003, you can save documents in the Office Open XML format if you have installed the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="the-shape-of-wordprocessingml-documents"></a><span data-ttu-id="835b5-110">WordprocessingML 문서의 모양</span><span class="sxs-lookup"><span data-stu-id="835b5-110">The Shape of WordprocessingML Documents</span></span>  
 <span data-ttu-id="835b5-111">먼저 WordprocessingML 문서의 모양을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-111">The first thing to understand is the shape of WordprocessingML documents.</span></span> <span data-ttu-id="835b5-112">WordprocessingML 문서에는 문서의 단락이 포함된 `w:body`라는 본문 요소가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-112">A WordprocessingML document contains a body element (named `w:body`) that contains the paragraphs of the document.</span></span> <span data-ttu-id="835b5-113">각 단락에는 `w:r`이라는 텍스트 실행이 하나 이상 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-113">Each paragraph contains one or more text runs (named `w:r`).</span></span> <span data-ttu-id="835b5-114">각 텍스트 실행에는 `w:t`라는 텍스트가 하나 이상 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-114">Each text run contains one or more text pieces (named `w:t`).</span></span>  
  
 <span data-ttu-id="835b5-115">다음은 매우 간단한 WordprocessingML 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-115">The following is a very simple WordprocessingML document:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<w:document  
xmlns:ve="http://schemas.openxmlformats.org/markup-compatibility/2006"  
xmlns:o="urn:schemas-microsoft-com:office:office"  
xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"  
xmlns:m="http://schemas.openxmlformats.org/officeDocument/2006/math"  
xmlns:v="urn:schemas-microsoft-com:vml"  
xmlns:wp="http://schemas.openxmlformats.org/drawingml/2006/wordprocessingDrawing"  
xmlns:w10="urn:schemas-microsoft-com:office:word"  
xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
xmlns:wne="http://schemas.microsoft.com/office/word/2006/wordml">  
  <w:body>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is a paragraph.</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is another paragraph.</w:t>  
      </w:r>  
    </w:p>  
  </w:body>  
</w:document>  
```  
  
 <span data-ttu-id="835b5-116">이 문서에는 두 단락이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-116">This document contains two paragraphs.</span></span> <span data-ttu-id="835b5-117">두 단락에는 모두 단일 텍스트 실행이 포함되어 있고 각 텍스트 실행에는 단일 텍스트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-117">They both contain a single text run, and each text run contains a single text piece.</span></span>  
  
 <span data-ttu-id="835b5-118">XML 형식으로 WordprocessingML 문서의 내용을 보는 가장 쉬운 방법은 Microsoft Word를 사용하여 문서를 만들어 저장한 후 XML을 콘솔에 출력하는 다음 프로그램을 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-118">The easiest way to see the contents of a WordprocessingML document in XML form is to create one using Microsoft Word, save it, and then run the following program that prints the XML to the console.</span></span>  
  
 <span data-ttu-id="835b5-119">이 예제에서는 WindowsBase 어셈블리의 클래스를 사용하고</span><span class="sxs-lookup"><span data-stu-id="835b5-119">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="835b5-120"><xref:System.IO.Packaging?displayProperty=nameWithType> 네임스페이스의 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-120">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    Sub Main()  
        Dim documentRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
  
        Using wdPackage As Package = _  
          Package.Open("SampleDoc.docx", _  
                       FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = wdPackage _  
                .GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri( _  
                            New Uri("/", UriKind.Relative), _  
                            docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                ' Get the officeDocument part from the package.  
                ' Load the XML in the part into an XDocument instance.  
                Dim xDoc As XDocument = _  
                    XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
                Console.WriteLine(xDoc.Root)  
            End If  
        End Using  
    End Sub  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="835b5-121">외부 리소스</span><span class="sxs-lookup"><span data-stu-id="835b5-121">External Resources</span></span>  
 [<span data-ttu-id="835b5-122">Office(2007) Open XML 파일 형식 소개</span><span class="sxs-lookup"><span data-stu-id="835b5-122">Introducing the Office (2007) Open XML File Formats</span></span>](http://go.microsoft.com/fwlink/?LinkId=98093)  
  
 [<span data-ttu-id="835b5-123">WordprocessingML의 개요</span><span class="sxs-lookup"><span data-stu-id="835b5-123">Overview of WordprocessingML</span></span>](http://go.microsoft.com/fwlink/?LinkId=98094)  
  
 [<span data-ttu-id="835b5-124">Office 2003: XML 참조 스키마 다운로드 페이지</span><span class="sxs-lookup"><span data-stu-id="835b5-124">Office 2003: XML Reference Schemas Download page</span></span>](http://go.microsoft.com/fwlink/?LinkId=98095)  
  
## <a name="see-also"></a><span data-ttu-id="835b5-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="835b5-125">See Also</span></span>  
 [<span data-ttu-id="835b5-126">자습서: WordprocessingML 문서 (Visual Basic)에서 내용 조작</span><span class="sxs-lookup"><span data-stu-id="835b5-126">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
