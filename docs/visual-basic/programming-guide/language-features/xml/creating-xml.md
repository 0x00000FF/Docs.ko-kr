---
title: "Visual Basic에서 XML 만들기"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 95ab82f2a8ae11b04e3887d5a179931c47346155
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="9baa1-102">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="9baa1-102">Creating XML in Visual Basic</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="9baa1-103">사용할 수 있습니다 *XML 리터럴을* 코드에서 직접 합니다.</span><span class="sxs-lookup"><span data-stu-id="9baa1-103"> enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="9baa1-104">XML 리터럴 구문을 나타내는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체는 XML 1.0 구문을 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="9baa1-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="9baa1-105">이렇게 하면 더 쉽게 코드에 최종 XML 구조가 동일 하기 때문에 XML 요소, 문서 및 조각을 프로그래밍 방식으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9baa1-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9baa1-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="9baa1-106">In This Section</span></span>  
  
|<span data-ttu-id="9baa1-107">용어</span><span class="sxs-lookup"><span data-stu-id="9baa1-107">Term</span></span>|<span data-ttu-id="9baa1-108">정의</span><span class="sxs-lookup"><span data-stu-id="9baa1-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="9baa1-109">XML 리터럴 개요</span><span class="sxs-lookup"><span data-stu-id="9baa1-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="9baa1-110">XML 리터럴 및 관계를 소개 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="9baa1-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="9baa1-111">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="9baa1-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="9baa1-112">XML 리터럴의 포함된 식을 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9baa1-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="9baa1-113">방법: XML 리터럴 만들기</span><span class="sxs-lookup"><span data-stu-id="9baa1-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="9baa1-114">XML 리터럴을 사용 하 여 코드에서 XML 요소를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9baa1-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="9baa1-115">XML 리터럴의 공백</span><span class="sxs-lookup"><span data-stu-id="9baa1-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="9baa1-116">설명 방법을 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] XML 리터럴의 공백을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9baa1-116">Describes how [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="9baa1-117">XML 리터럴 및 XML 1.0 사양</span><span class="sxs-lookup"><span data-stu-id="9baa1-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="9baa1-118">설명 방법에서 XML 리터럴 구문을 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] XML 1.0 사양에 연결 됨.</span><span class="sxs-lookup"><span data-stu-id="9baa1-118">Describes how the XML literal syntax in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="9baa1-119">방법: XML 리터럴에 식 포함</span><span class="sxs-lookup"><span data-stu-id="9baa1-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="9baa1-120">XML 리터럴의 포함 된 식을 사용 하 여 실행된 시간에 콘텐츠를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9baa1-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="9baa1-121">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="9baa1-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="9baa1-122">XML 요소 및 특성 이름을 지정 하는 것에 대 한 지침을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9baa1-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9baa1-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9baa1-123">See Also</span></span>  
 [<span data-ttu-id="9baa1-124">XML</span><span class="sxs-lookup"><span data-stu-id="9baa1-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
