---
title: LINQ to XML 주석3
ms.date: 07/20/2015
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
ms.openlocfilehash: 753fc656d78f2cefde98a8cbfb48713c7a107f77
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676721"
---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="4e2ec-102">LINQ to XML 주석</span><span class="sxs-lookup"><span data-stu-id="4e2ec-102">LINQ to XML Annotations</span></span>
<span data-ttu-id="4e2ec-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서 주석을 사용하여 임의의 형식에 대한 임의의 개체를 XML 트리의 XML 구성 요소와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e2ec-103">Annotations in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>  
  
 <span data-ttu-id="4e2ec-104"><xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XAttribute>와 같은 XML 구성 요소에 주석을 추가하려면 <xref:System.Xml.Linq.XObject.AddAnnotation%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4e2ec-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="4e2ec-105">형식별로 주석을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e2ec-105">You retrieve annotations by type.</span></span>  
  
 <span data-ttu-id="4e2ec-106">주석은 XML infoset의 일부가 아니므로 serialize되거나 deserialize되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e2ec-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4e2ec-107">메서드</span><span class="sxs-lookup"><span data-stu-id="4e2ec-107">Methods</span></span>  
 <span data-ttu-id="4e2ec-108">주석 작업을 할 때 다음 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e2ec-108">You can use the following methods when working with annotations:</span></span>  
  
|<span data-ttu-id="4e2ec-109">메서드</span><span class="sxs-lookup"><span data-stu-id="4e2ec-109">Method</span></span>|<span data-ttu-id="4e2ec-110">설명</span><span class="sxs-lookup"><span data-stu-id="4e2ec-110">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="4e2ec-111"><xref:System.Xml.Linq.XObject>의 주석 목록에 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4e2ec-111">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="4e2ec-112">지정된 형식의 첫 번째 주석 개체를 <xref:System.Xml.Linq.XObject>에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4e2ec-112">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="4e2ec-113"><xref:System.Xml.Linq.XObject>에 대한 지정된 형식의 주석 컬렉션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4e2ec-113">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="4e2ec-114">지정된 형식의 주석을 <xref:System.Xml.Linq.XObject>에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4e2ec-114">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e2ec-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e2ec-115">See also</span></span>

- [<span data-ttu-id="4e2ec-116">고급 LINQ to XML 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="4e2ec-116">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
