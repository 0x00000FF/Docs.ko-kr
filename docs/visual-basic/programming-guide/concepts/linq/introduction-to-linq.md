---
title: LINQ (Visual Basic) 소개
ms.date: 07/20/2015
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
ms.openlocfilehash: 2900cade8bc4166cccb62baf4381cb926cdff5f8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58822325"
---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="665eb-102">LINQ (Visual Basic) 소개</span><span class="sxs-lookup"><span data-stu-id="665eb-102">Introduction to LINQ (Visual Basic)</span></span>
<span data-ttu-id="665eb-103">LINQ(Language-Integrated Query)는 개체 환경과 데이터 환경 간의 간격을 연결하는 .NET Framework 버전 3.5에서 도입된 혁신입니다.</span><span class="sxs-lookup"><span data-stu-id="665eb-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="665eb-104">일반적으로 데이터에 대한 쿼리는 컴파일 시간의 형식 검사나 IntelliSense 지원 없이 간단한 문자열로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="665eb-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="665eb-105">또한 데이터 원본의 각 유형에 대해 다른 쿼리 언어를 배워야 합니다. SQL 데이터베이스, XML 문서, 다양한 웹 서비스 등.</span><span class="sxs-lookup"><span data-stu-id="665eb-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="665eb-106">LINQ 사용 하면를 *쿼리* Visual Basic의 고급 언어 구문이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="665eb-106">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="665eb-107">언어 키워드 및 친숙한 연산자를 사용하여 강력한 형식의 개체 컬렉션에 대해 쿼리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="665eb-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="665eb-108">SQL Server 데이터베이스, XML 문서, ADO.NET 데이터 집합 및 지 원하는 개체의 컬렉션에 대 한 Visual Basic의 LINQ 쿼리를 작성할 수 있습니다 <xref:System.Collections.IEnumerable> 또는 제네릭 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="665eb-108">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="665eb-109">LINQ는 많은 웹 서비스 및 기타 데이터베이스 구현을 위해 타사에서도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="665eb-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="665eb-110">LINQ 쿼리는 새 프로젝트에서 사용하거나 기존 프로젝트에서 LINQ가 아닌 쿼리와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="665eb-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="665eb-111">프로젝트가 .NET Framework 3.5 이상을 대상으로 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="665eb-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="665eb-112">다음 그림에서는 Visual Studio에서 전체 형식 검사 및 IntelliSense를 지원하는 C#과 Visual Basic을 사용하여 SQL Server 데이터베이스에 대해 부분적으로 완성된 LINQ 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="665eb-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 ![해당 shwos Intellisense 사용한 LINQ 쿼리를 다이어그램입니다.](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a><span data-ttu-id="665eb-114">다음 단계</span><span class="sxs-lookup"><span data-stu-id="665eb-114">Next Steps</span></span>  
 <span data-ttu-id="665eb-115">시작 섹션에서 몇 가지 기본 개념을 파악 하 여 시작에 LINQ에 대 한 자세한 내용을 알아보려면 [Getting Started with Visual Basic의 LINQ](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), 다음에 LINQ 기술에 대 한 설명서를 읽어보세요 관련:</span><span class="sxs-lookup"><span data-stu-id="665eb-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
-   <span data-ttu-id="665eb-116">SQL Server 데이터베이스: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="665eb-116">SQL Server databases: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span></span>  
  
-   <span data-ttu-id="665eb-117">XML 문서: [LINQ to XML(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="665eb-117">XML documents: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="665eb-118">ADO.NET 데이터 세트: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="665eb-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
-   <span data-ttu-id="665eb-119">.NET 컬렉션, 파일, 문자열 등: [LINQ to Objects(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="665eb-119">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="665eb-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="665eb-120">See also</span></span>

- [<span data-ttu-id="665eb-121">LINQ(Language-Integrated Query)(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="665eb-121">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
