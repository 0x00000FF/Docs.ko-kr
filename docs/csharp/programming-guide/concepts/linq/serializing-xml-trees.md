---
title: XML 트리 serialize(C#)
ms.date: 07/20/2015
ms.assetid: b3937e54-4ce9-4236-ac96-14e7972aa594
ms.openlocfilehash: 8f372a05bd69b801085cba9d9a3b11ae01841a2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33338353"
---
# <a name="serializing-xml-trees-c"></a><span data-ttu-id="16755-102">XML 트리 serialize(C#)</span><span class="sxs-lookup"><span data-stu-id="16755-102">Serializing XML Trees (C#)</span></span>
<span data-ttu-id="16755-103">XML 트리를 serialize하는 것은 XML 트리에서 XML을 생성하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="16755-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="16755-104">파일, <xref:System.IO.TextWriter> 클래스의 구체적 구현 또는 <xref:System.Xml.XmlWriter>의 구체적 구현으로 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16755-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="16755-105">serialization의 다양한 측면을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16755-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="16755-106">예를 들어, serialize된 XML을 들여쓸지 여부와 XML 선언을 쓸지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16755-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16755-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="16755-107">In This Section</span></span>  
  
|<span data-ttu-id="16755-108">항목</span><span class="sxs-lookup"><span data-stu-id="16755-108">Topic</span></span>|<span data-ttu-id="16755-109">설명</span><span class="sxs-lookup"><span data-stu-id="16755-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="16755-110">serialize할 때 공백 유지</span><span class="sxs-lookup"><span data-stu-id="16755-110">Preserving White Space While Serializing</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="16755-111">XML 트리를 serialize할 때 공백 동작을 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16755-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="16755-112">XML 선언으로 serialize(C#)</span><span class="sxs-lookup"><span data-stu-id="16755-112">Serializing with an XML Declaration (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="16755-113">XML 선언이 포함된 XML 트리를 serialize하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16755-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="16755-114">Files, TextWriters 및 XmlWriters로 serialization</span><span class="sxs-lookup"><span data-stu-id="16755-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="16755-115">문서를 <xref:System.IO.File>, <xref:System.IO.TextWriter> 또는 <xref:System.Xml.XmlWriter>로 serialize하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16755-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="16755-116">XmlReader로 serialize(XSLT 호출)(C#)</span><span class="sxs-lookup"><span data-stu-id="16755-116">Serializing to an XmlReader (Invoking XSLT) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="16755-117">다른 모듈에서 XML 트리의 내용을 읽을 수 있도록 하는 <xref:System.Xml.XmlReader>를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16755-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16755-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16755-118">See Also</span></span>  
 [<span data-ttu-id="16755-119">프로그래밍 가이드(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="16755-119">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
