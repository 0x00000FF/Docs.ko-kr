---
title: (Visual Basic) XML의 순수 함수 변환
ms.date: 07/20/2015
ms.assetid: 5e19b74a-7773-4b58-b110-953ffd364c55
ms.openlocfilehash: 48149faba1c41583ab4e50c539d52e4caf90592a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766456"
---
# <a name="pure-functional-transformations-of-xml-visual-basic"></a><span data-ttu-id="7d5bf-102">(Visual Basic) XML의 순수 함수 변환</span><span class="sxs-lookup"><span data-stu-id="7d5bf-102">Pure Functional Transformations of XML (Visual Basic)</span></span>
<span data-ttu-id="7d5bf-103">이 단원에서는 XML의 함수 변환 자습서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5bf-103">This section provides a functional transformation tutorial for XML.</span></span> <span data-ttu-id="7d5bf-104">이 자습서에는 함수 변환을 사용하기 위해 이해해야 하는 주요 개념과 언어 구문에 대한 설명과 함수 변환을 사용하여 XML 문서를 조작하는 예제가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d5bf-104">This includes explanations of the main concepts and language constructs that you must understand to use functional transformations, and examples of using functional transformations to manipulate an XML document.</span></span> <span data-ttu-id="7d5bf-105">이 자습서에서 LINQ to XML 코드 예제를 제공하지만 모든 기본 개념은 다른 LINQ 기술에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d5bf-105">Although this tutorial provides LINQ to XML code examples, all of the underlying concepts also apply to other LINQ technologies.</span></span>  
  
 <span data-ttu-id="7d5bf-106">[자습서: (Visual Basic) WordprocessingML 문서에서 내용 조작](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) 자습서에서는 이전에 각 빌드를 일련의 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5bf-106">The [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial provides a series of examples, each building on the previous one.</span></span> <span data-ttu-id="7d5bf-107">이러한 예제에서는 XML을 조작하기 위한 순수 함수 변환 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d5bf-107">These examples demonstrate the pure functional transformational approach to manipulating XML.</span></span>  
  
 <span data-ttu-id="7d5bf-108">이 자습서에는 Visual Basic의 알고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5bf-108">This tutorial assumes a working knowledge of Visual Basic.</span></span> <span data-ttu-id="7d5bf-109">언어 구문의 자세한 의미는 이 자습서에 나와 있지 않지만 해당 언어 설명서에 대한 링크가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d5bf-109">Detailed semantics of the language constructs are not provided in this tutorial, but links are provided to the language documentation as appropriate.</span></span>  
  
 <span data-ttu-id="7d5bf-110">이 자습서의 대상 사용자는 기본 컴퓨터 과학 개념과 XML 네임스페이스를 비롯한 XML에 대한 실무 지식도 있다고 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d5bf-110">A working knowledge of basic computer science concepts and XML, including XML namespaces, is also assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7d5bf-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="7d5bf-111">In This Section</span></span>  
  
|<span data-ttu-id="7d5bf-112">항목</span><span class="sxs-lookup"><span data-stu-id="7d5bf-112">Topic</span></span>|<span data-ttu-id="7d5bf-113">설명</span><span class="sxs-lookup"><span data-stu-id="7d5bf-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7d5bf-114">순수 함수 변환 (Visual Basic) 소개</span><span class="sxs-lookup"><span data-stu-id="7d5bf-114">Introduction to Pure Functional Transformations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)|<span data-ttu-id="7d5bf-115">함수 변환에 대해 설명하고 관련 용어를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5bf-115">Describes functional transformations and defines the relevant terminology.</span></span>|  
|[<span data-ttu-id="7d5bf-116">자습서: 지연 된 실행 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d5bf-116">Tutorial: Deferred Execution (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)|<span data-ttu-id="7d5bf-117">지연 계산과 지연된 실행에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5bf-117">Describes lazy evaluation and deferred execution in detail.</span></span>|  
|[<span data-ttu-id="7d5bf-118">자습서: (Visual Basic) WordprocessingML 문서에서 내용 조작</span><span class="sxs-lookup"><span data-stu-id="7d5bf-118">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)|<span data-ttu-id="7d5bf-119">함수 변환을 보여 주는 자습서입니다.</span><span class="sxs-lookup"><span data-stu-id="7d5bf-119">A tutorial that demonstrates a functional transformation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d5bf-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="7d5bf-120">See also</span></span>

- [<span data-ttu-id="7d5bf-121">XML 트리 쿼리 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d5bf-121">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
