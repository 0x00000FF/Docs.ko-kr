---
title: LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: b0660312f540a69911905edd08541ed70cf39bb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174318"
---
# <a name="linq-to-sql"></a><span data-ttu-id="2d2f1-102">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2d2f1-102">LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="2d2f1-103">는 .NET Framework 버전 3.5의 구성 요소로 관계형 데이터를 개체로 관리하기 위한 런타임 인프라를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-103">is a component of .NET Framework version 3.5 that provides a run-time infrastructure for managing relational data as objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d2f1-104">관계형 데이터는 테이블 간에 서로 관계된 공통 열이 있는 이차원 테이블(*관계* 또는 *플랫 파일*)의 컬렉션으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-104">Relational data appears as a collection of two-dimensional tables (*relations* or *flat files*), where common columns relate tables to each other.</span></span> <span data-ttu-id="2d2f1-105">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 효율적으로 사용하려면 관계형 데이터베이스의 기본 원리에 대해 조금은 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-105">To use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] effectively, you must have some familiarity with the underlying principles of relational databases.</span></span>  
  
 <span data-ttu-id="2d2f1-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 관계형 데이터베이스의 데이터 모델은 개발자의 프로그래밍 언어로 표현되는 개체 모델에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the data model of a relational database is mapped to an object model expressed in the programming language of the developer.</span></span> <span data-ttu-id="2d2f1-107">애플리케이션을 실행하면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 개체 모델의 SQL 언어 통합 쿼리를 변환하여 실행을 위해 데이터베이스로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-107">When the application runs, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates into SQL the language-integrated queries in the object model and sends them to the database for execution.</span></span> <span data-ttu-id="2d2f1-108">데이터베이스에서 결과를 반환하면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 해당 결과를 사용자의 프로그래밍 언어로 작업할 수 있는 개체로 다시 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-108">When the database returns the results, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates them back to objects that you can work with in your own programming language.</span></span>  
  
 <span data-ttu-id="2d2f1-109">Visual Studio를 사용하는 개발자는 일반적으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 많은 기능을 구현하기 위한 사용자 인터페이스를 제공하는 개체 관계형 디자이너를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-109">Developers using Visual Studio typically use the Object Relational Designer, which provides a user interface for implementing many of the features of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 <span data-ttu-id="2d2f1-110">이 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 릴리스에 포함된 설명서에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 애플리케이션을 빌드하는 데 필요한 기본 빌드 블록, 프로세스 및 기술에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-110">The documentation that is included with this release of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] describes the basic building blocks, processes, and techniques you need for building [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="2d2f1-111">또한 Microsoft 문서 문서에서 특정 문제를 검색할 수 있으며 [LINQ 포럼에](https://social.msdn.microsoft.com/forums/home?forum=linqtosql)참여하여 전문가와 보다 복잡한 주제에 대해 자세히 논의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-111">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="2d2f1-112">마지막으로 [LINQ 에서 SQL로: 관계형 데이터에 대한 .NET](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10)) [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 언어 통합 쿼리 는 Visual Basic 및 C# 코드 예제와 함께 기술 세부 정보를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-112">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10)) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d2f1-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2d2f1-113">In This Section</span></span>  
 [<span data-ttu-id="2d2f1-114">시작</span><span class="sxs-lookup"><span data-stu-id="2d2f1-114">Getting Started</span></span>](getting-started.md)  
 <span data-ttu-id="2d2f1-115">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 방법에 대한 정보와 함께 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대한 간략한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-115">Provides a condensed overview of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] along with information about how to get started using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="2d2f1-116">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="2d2f1-116">Programming Guide</span></span>](programming-guide.md)  
 <span data-ttu-id="2d2f1-117">매핑, 쿼리, 업데이트, 디버깅 및 유사한 작업에 대한 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-117">Provides steps for mapping, querying, updating, debugging, and similar tasks.</span></span>  
  
 [<span data-ttu-id="2d2f1-118">참조</span><span class="sxs-lookup"><span data-stu-id="2d2f1-118">Reference</span></span>](reference.md)  
 <span data-ttu-id="2d2f1-119">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 일부 측면에 대한 참조 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-119">Provides reference information about several aspects of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="2d2f1-120">항목에는 SQL-CLR 형식 매핑, 표준 쿼리 연산자 변환 등이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-120">Topics include SQL-CLR Type Mapping, Standard Query Operator Translation, and more.</span></span>  
  
 [<span data-ttu-id="2d2f1-121">샘플</span><span class="sxs-lookup"><span data-stu-id="2d2f1-121">Samples</span></span>](samples.md)  
 <span data-ttu-id="2d2f1-122">시각적 기본 및 C# 샘플에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-122">Provides links to Visual Basic and C# samples.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2d2f1-123">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="2d2f1-123">Related Sections</span></span>  
 <span data-ttu-id="2d2f1-124">[언어 통합 쿼리(LINQ) - C #](../../../../../csharp/programming-guide/concepts/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="2d2f1-124">[Language-Integrated Query (LINQ) - C#](../../../../../csharp/programming-guide/concepts/linq/index.md)</span></span>\
 <span data-ttu-id="2d2f1-125">C#에서 LINQ 기술에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-125">Provides overviews of LINQ technologies in C#.</span></span>

 [<span data-ttu-id="2d2f1-126">LINQ(Language-Integrated Query) - Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2d2f1-126">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="2d2f1-127">시각적 기본에서 LINQ 기술에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-127">Provides overviews of LINQ technologies in Visual Basic.</span></span>
  
 [<span data-ttu-id="2d2f1-128">LINQ</span><span class="sxs-lookup"><span data-stu-id="2d2f1-128">LINQ</span></span>](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="2d2f1-129">시각적 기본 사용자를 위한 LINQ 기술에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-129">Describes LINQ technologies for Visual Basic users.</span></span>  
  
 [<span data-ttu-id="2d2f1-130">LINQ 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2d2f1-130">LINQ and ADO.NET</span></span>](../../linq-and-ado-net.md)  
 <span data-ttu-id="2d2f1-131">ADO.NET 포털에 대한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-131">Links to the ADO.NET portal.</span></span>  
  
 <span data-ttu-id="2d2f1-132">[LINQ to SQL 연습](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2d2f1-132">[LINQ to SQL Walkthroughs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))</span></span>  
 <span data-ttu-id="2d2f1-133">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대한 연습을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-133">Lists walkthroughs available for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="2d2f1-134">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="2d2f1-134">Downloading Sample Databases</span></span>](downloading-sample-databases.md)  
 <span data-ttu-id="2d2f1-135">설명서에 사용되는 샘플 데이터베이스를 다운로드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-135">Describes how to download sample databases used in the documentation.</span></span>  
  
 <span data-ttu-id="2d2f1-136">[LinqDataSource 웹 서버 제어 개요](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2d2f1-136">[LinqDataSource Web Server Control Overview](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))</span></span>  
 <span data-ttu-id="2d2f1-137">컨트롤이 <xref:System.Web.UI.WebControls.LinqDataSource> ASP.NET 데이터 원본 제어 아키텍처를 통해 웹 개발자에게 언어 통합 쿼리(LINQ)를 노출하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f1-137">Describes how the <xref:System.Web.UI.WebControls.LinqDataSource> control exposes Language-Integrated Query (LINQ) to Web developers through the ASP.NET data-source control architecture.</span></span>
