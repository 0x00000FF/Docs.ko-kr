---
title: "XML 트리에서 요소, 특성 및 노드 수정3"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: da3b31456bc86b547c5174143620f464dc42f35b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="728af-102">XML 트리에서 요소, 특성 및 노드 수정</span><span class="sxs-lookup"><span data-stu-id="728af-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="728af-103">다음 표에는 요소, 해당 요소의 자식 요소 또는 특성을 수정하는 데 사용할 수 있는 메서드와 속성이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="728af-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="728af-104">다음 메서드는 <xref:System.Xml.Linq.XElement>를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="728af-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="728af-105">메서드</span><span class="sxs-lookup"><span data-stu-id="728af-105">Method</span></span>|<span data-ttu-id="728af-106">설명</span><span class="sxs-lookup"><span data-stu-id="728af-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="728af-107">요소를 구문 분석된 XML로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="728af-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="728af-108">요소의 모든 내용(자식 노드와 특성)을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="728af-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="728af-109">요소의 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="728af-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="728af-110">요소의 모든 내용(자식 노드와 특성)을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="728af-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="728af-111">요소의 특성을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="728af-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="728af-112">특성의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="728af-112">Sets the value of an attribute.</span></span> <span data-ttu-id="728af-113">특성이 없으면 특성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="728af-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="728af-114">값이 `null`로 설정되어 있으면 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="728af-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="728af-115">자식 요소의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="728af-115">Sets the value of a child element.</span></span> <span data-ttu-id="728af-116">요소가 없으면 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="728af-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="728af-117">값이 `null`로 설정되어 있으면 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="728af-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="728af-118">요소의 내용(자식 노드)을 지정된 텍스트로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="728af-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="728af-119">요소의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="728af-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="728af-120">다음 메서드는 <xref:System.Xml.Linq.XAttribute>를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="728af-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="728af-121">메서드</span><span class="sxs-lookup"><span data-stu-id="728af-121">Method</span></span>|<span data-ttu-id="728af-122">설명</span><span class="sxs-lookup"><span data-stu-id="728af-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="728af-123">특성의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="728af-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="728af-124">특성의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="728af-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="728af-125">다음 메서드는 <xref:System.Xml.Linq.XNode>(<xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 포함)를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="728af-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="728af-126">메서드</span><span class="sxs-lookup"><span data-stu-id="728af-126">Method</span></span>|<span data-ttu-id="728af-127">설명</span><span class="sxs-lookup"><span data-stu-id="728af-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="728af-128">노드를 새 내용으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="728af-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="728af-129">다음 메서드는 <xref:System.Xml.Linq.XContainer>(<xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument>)를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="728af-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="728af-130">메서드</span><span class="sxs-lookup"><span data-stu-id="728af-130">Method</span></span>|<span data-ttu-id="728af-131">설명</span><span class="sxs-lookup"><span data-stu-id="728af-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="728af-132">자식 노드를 새 내용으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="728af-132">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="728af-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="728af-133">See Also</span></span>  
 [<span data-ttu-id="728af-134">XML 트리 수정(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="728af-134">Modifying XML Trees (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
