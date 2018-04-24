---
title: 메모리 내 XML 데이터 처리
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
caps.latest.revision: 2
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1c451e4015e37c118f475ec1e7c099566e28767f
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="processing-xml-data-in-memory"></a><span data-ttu-id="8c1b3-102">메모리 내 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="8c1b3-102">Processing XML Data In-Memory</span></span>
<span data-ttu-id="8c1b3-103">Microsoft .NET Framework에는 XML 데이터를 처리할 수 있는 세 가지 모델 즉, <xref:System.Xml.XmlDocument> 클래스, <xref:System.Xml.XPath.XPathDocument> 클래스 및 [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c1b3-103">The Microsoft .NET Framework includes three models for processing XML data: the <xref:System.Xml.XmlDocument> class, the <xref:System.Xml.XPath.XPathDocument> class, and [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span>  
  
 <span data-ttu-id="8c1b3-104"><xref:System.Xml.XmlDocument> 클래스는 W3C DOM(문서 개체 모델) Level 1 Core 및 DOM Level 2 Core 권장 사항을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8c1b3-104">The <xref:System.Xml.XmlDocument> class implements the W3C document object model (DOM) level 1 core and the core DOM level 2 recommendations.</span></span> <span data-ttu-id="8c1b3-105">DOM은 XML 문서의 메모리 내(캐시) 트리 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="8c1b3-105">The DOM is an in-memory (cache) tree representation of an XML document.</span></span> <span data-ttu-id="8c1b3-106"><xref:System.Xml.XmlDocument> 및 관련 클래스를 사용하여 XML 문서를 생성하고, 데이터를 로드 및 액세스하여 수정하며 변경 내용을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c1b3-106">With the <xref:System.Xml.XmlDocument> and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
 <span data-ttu-id="8c1b3-107"><xref:System.Xml.XPath.XPathDocument> 클래스는 XPath 데이터 모델을 기반으로 하는 읽기 전용 메모리 내 데이터 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="8c1b3-107">The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory data store that is based on the XPath data model.</span></span> <span data-ttu-id="8c1b3-108"><xref:System.Xml.XPath.XPathNavigator> 클래스에서는 읽기 전용 <xref:System.Xml.XPath.XPathDocument> 클래스와 <xref:System.Xml.XmlDocument> 클래스에 포함된 XML 문서에 대해 커서 모델을 사용하는 몇 가지 편집 옵션 및 탐색 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8c1b3-108">The <xref:System.Xml.XPath.XPathNavigator> class offers several editing options and navigation capabilities using a cursor model over XML documents contained in the read-only <xref:System.Xml.XPath.XPathDocument> class as well as the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="8c1b3-109">[LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)은 XML 데이터를 처리하기 위한 .NET Framework 버전 3.5의 새 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="8c1b3-109">[LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) is the new model in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="8c1b3-110">즉, [LINQ(Language-Integrated Query)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)를 활용하는 메모리 내 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="8c1b3-110">It is an in-memory model that leverages [LINQ (Language-Integrated Query)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span></span> <span data-ttu-id="8c1b3-111">LINQ는 C# 및 Visual Basic의 언어 구문을 확장하여 새 쿼리 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8c1b3-111">LINQ extends the language syntax of C# and Visual Basic to provide new query capabilities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c1b3-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="8c1b3-112">In This Section</span></span>  
 [<span data-ttu-id="8c1b3-113">DOM 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="8c1b3-113">Process XML Data Using the DOM Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 <span data-ttu-id="8c1b3-114"><xref:System.Xml.XmlDocument> 및 관련 클래스를 사용하여 XML 데이터를 처리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c1b3-114">Discusses using the <xref:System.Xml.XmlDocument>, and its related classes to process XML data.</span></span>  
  
 [<span data-ttu-id="8c1b3-115">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="8c1b3-115">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="8c1b3-116"><xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> 및 <xref:System.Xml.XPath.XPathNavigator> 클래스를 사용하여 XML 데이터를 처리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c1b3-116">Discusses using the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument>, and <xref:System.Xml.XPath.XPathNavigator> classes to process XML data.</span></span>  
  
 [<span data-ttu-id="8c1b3-117">LINQ to XML을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="8c1b3-117">Process XML Data Using LINQ to XML</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 <span data-ttu-id="8c1b3-118">LINQ to XML의 간단한 개요 및 LINQ to XML 문서에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8c1b3-118">Provides a brief overview of LINQ to XML and provides links to the LINQ to XML documentation.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8c1b3-119">관련 단원</span><span class="sxs-lookup"><span data-stu-id="8c1b3-119">Related Sections</span></span>  
 [<span data-ttu-id="8c1b3-120">XML 문서 및 데이터</span><span class="sxs-lookup"><span data-stu-id="8c1b3-120">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)
