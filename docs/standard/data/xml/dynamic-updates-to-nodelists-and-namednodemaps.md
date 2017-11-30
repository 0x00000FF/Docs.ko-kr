---
title: "NodeList 및 NamedNodeMap에 대한 동적 업데이트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 459d746ff278ac4affa0318c1fad0aeb6a73e560
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a><span data-ttu-id="bca25-102">NodeList 및 NamedNodeMap에 대한 동적 업데이트</span><span class="sxs-lookup"><span data-stu-id="bca25-102">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>
<span data-ttu-id="bca25-103">때문에 **XmlNodeList** 및 **XmlNamedNodeMap** XML 문서를 메모리에 로드 하 고 수정 하 고 아직 노드 집합을 포함 하는 World Wide Web Consortium (W3C) 상태 이러한 개체 하는 동적으로 해야 하는 노드 집합을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bca25-103">Because the **XmlNodeList** and the **XmlNamedNodeMap** contain a set of nodes, yet the XML document is loaded into memory and is being modified, the World Wide Web Consortium (W3C) states that these objects that contain sets of nodes need to be dynamic.</span></span> <span data-ttu-id="bca25-104">즉, 원본으로 사용하는 문서가 변경되면 이러한 두 개체의 데이터도 변경되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bca25-104">That is, if the underlying document changes, then the data in these two objects should change also.</span></span> <span data-ttu-id="bca25-105">따라서 있는 경우는 **XmlNodeList** (예를 들어 요소 X), 특정 요소의 모든 자식 요소를 포함 하는 다음 X 요소 아래의 문서에 Q 요소 라는 추가 요소를 추가 합니다. **XmlNodeList** 도 새 Q 해당 컬렉션에 추가 된 요소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bca25-105">Therefore, if you have an **XmlNodeList** that contains all the child elements of a particular element (for example, element X), then you add an additional element, element Q, to the document under element X. The **XmlNodeList** should also have that new element Q added to its collection.</span></span> <span data-ttu-id="bca25-106">그 반대의 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="bca25-106">The same is true in reverse.</span></span> <span data-ttu-id="bca25-107">에 노드가 추가 되는 **XmlNodeList**, 사용 하는 문서 역시 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bca25-107">If a node is added to the **XmlNodeList**, the underlying document is updated as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bca25-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bca25-108">See Also</span></span>  
 [<span data-ttu-id="bca25-109">XML 문서 개체 모델 (DOM)</span><span class="sxs-lookup"><span data-stu-id="bca25-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
