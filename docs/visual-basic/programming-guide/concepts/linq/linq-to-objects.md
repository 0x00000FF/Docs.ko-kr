---
title: LINQ to Objects(Visual Basic)
ms.date: 07/20/2015
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
ms.openlocfilehash: c1e2e8fbaaf984fec69322a459fc7c55890965ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59326881"
---
# <a name="linq-to-objects-visual-basic"></a><span data-ttu-id="b49e9-102">LINQ to Objects(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b49e9-102">LINQ to Objects (Visual Basic)</span></span>
<span data-ttu-id="b49e9-103">“LINQ to Objects”라는 용어는 중간 LINQ 공급자 또는 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md), [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md) 등의 API를 사용하지 않고 모든 <xref:System.Collections.IEnumerable> 또는 <xref:System.Collections.Generic.IEnumerable%601> 컬렉션에 대해 LINQ 쿼리를 직접 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-103">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) or [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span></span> <span data-ttu-id="b49e9-104">LINQ를 사용하면 <xref:System.Collections.Generic.List%601>, <xref:System.Array>, <xref:System.Collections.Generic.Dictionary%602> 등의 모든 열거 가능 컬렉션을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-104">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="b49e9-105">컬렉션은 사용자가 정의할 수도 있고 .NET Framework API에서 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-105">The collection may be user-defined or may be returned by a .NET Framework API.</span></span>  
  
 <span data-ttu-id="b49e9-106">기본적으로 LINQ to Objects는 새로운 컬렉션 방식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-106">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="b49e9-107">이전에는 컬렉션에서 데이터를 검색하는 방법을 지정하는 복잡한 `For Each` 루프를 작성해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-107">In the old way, you had to write complex `For Each` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="b49e9-108">그러나 LINQ 방식에서는 검색할 항목을 설명하는 선언적 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-108">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="b49e9-109">또한 LINQ 쿼리는 기존의 `For Each` 루프에 비해 세 가지 주요 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-109">In addition, LINQ queries offer three main advantages over traditional `For Each` loops:</span></span>  
  
1. <span data-ttu-id="b49e9-110">보다 간결하며 쉽게 읽을 수 있습니다(특히 여러 조건을 필터링하는 경우).</span><span class="sxs-lookup"><span data-stu-id="b49e9-110">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
2. <span data-ttu-id="b49e9-111">최소한의 애플리케이션 코드로도 강력한 필터링, 순서 지정 및 그룹화 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-111">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
3. <span data-ttu-id="b49e9-112">거의 또는 전혀 수정하지 않고도 다른 데이터 소스에 이식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-112">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="b49e9-113">일반적으로는 데이터에 대해 수행하려는 작업이 복잡할수록 기존의 반복 기술 대신 LINQ를 사용하면 더 큰 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-113">In general, the more complex the operation you want to perform on the data, the more benefit you will realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="b49e9-114">이 섹션에서는 몇 가지 예제를 통해 LINQ 방식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-114">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="b49e9-115">여기서 설명하는 방식 외에도 다양한 방식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-115">It is not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b49e9-116">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="b49e9-116">In This Section</span></span>  
 [<span data-ttu-id="b49e9-117">LINQ 및 문자열 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b49e9-117">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 <span data-ttu-id="b49e9-118">LINQ를 사용하여 문자열 및 문자열 컬렉션을 쿼리하고 변환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-118">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="b49e9-119">또한 이러한 원칙을 설명하는 항목의 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-119">Also includes links to topics that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="b49e9-120">LINQ 및 리플렉션 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b49e9-120">LINQ and Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-reflection.md)  
 <span data-ttu-id="b49e9-121">LINQ에서 리플렉션을 사용하는 방식을 보여 주는 샘플 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-121">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="b49e9-122">LINQ 및 파일 디렉터리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b49e9-122">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)  
 <span data-ttu-id="b49e9-123">LINQ를 사용하여 파일 시스템을 조작하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-123">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="b49e9-124">또한 이러한 개념을 설명하는 항목의 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-124">Also includes links to topics that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="b49e9-125">방법: LINQ (Visual Basic)를 사용 하 여 ArrayList 쿼리</span><span class="sxs-lookup"><span data-stu-id="b49e9-125">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="b49e9-126">C#에서 ArrayList를 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-126">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="b49e9-127">방법: LINQ 쿼리 (Visual Basic)에 대 한 사용자 지정 메서드 추가</span><span class="sxs-lookup"><span data-stu-id="b49e9-127">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="b49e9-128"><xref:System.Collections.Generic.IEnumerable%601> 인터페이스에 확장 메서드를 추가하여 LINQ 쿼리에 대해 사용할 수 있는 메서드 집합 확장 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-128">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="b49e9-129">LINQ(Language-Integrated Query)(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b49e9-129">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="b49e9-130">LINQ 관련 설명과 쿼리를 수행하는 코드 예제를 제공하는 항목의 링크가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49e9-130">Provides links to topics that explain LINQ and provide examples of code that perform queries.</span></span>
