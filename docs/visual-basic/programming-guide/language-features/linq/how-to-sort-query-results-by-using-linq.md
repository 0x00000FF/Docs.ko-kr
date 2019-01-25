---
title: '방법: LINQ (Visual Basic)를 사용 하 여 쿼리 결과 정렬'
ms.date: 07/20/2015
helpviewer_keywords:
- sorting query results, multiple columns
- sorting data [Visual Basic]
- sorting data [LINQ in Visual Basic]
- sorting query results [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], sorting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 07a4584d-9fd8-4a1d-b7d9-ccf2efa5c84e
ms.openlocfilehash: 04e8f6eaa06577ac556dbed89088f6268aae81df
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672775"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="82263-102">방법: LINQ (Visual Basic)를 사용 하 여 쿼리 결과 정렬</span><span class="sxs-lookup"><span data-stu-id="82263-102">How to: Sort Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="82263-103">언어 통합 쿼리 (LINQ)를 사용 하면 쉽게 데이터베이스 정보에 액세스 하 고 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="82263-104">다음 예제를 사용 하 여 여러 필드를 기준으로 결과 정렬 및 SQL Server 데이터베이스에 대 한 쿼리를 수행 하는 새 응용 프로그램을 만드는 방법을 보여 줍니다는 `Order By` 절.</span><span class="sxs-lookup"><span data-stu-id="82263-104">The following example shows how to create a new application that performs queries against a SQL Server database and sorts the results by multiple fields by using the `Order By` clause.</span></span> <span data-ttu-id="82263-105">각 필드에 대 한 정렬 순서는 오름차순 또는 내림차순 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82263-105">The sort order for each field can be ascending order or descending order.</span></span> <span data-ttu-id="82263-106">자세한 내용은 [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-106">For more information, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="82263-107">이 항목의 예제는 Northwind 샘플 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="82263-108">개발 컴퓨터에이 데이터베이스가 없는 경우에 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82263-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="82263-109">자세한 내용은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="82263-110">데이터베이스에 대 한 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="82263-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="82263-111">Visual Studio에서 엽니다 **서버 탐색기**/**데이터베이스 탐색기** 를 클릭 하 여 **서버 탐색기**/**데이터베이스 탐색기** 에 **보기** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="82263-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="82263-112">마우스 오른쪽 단추로 클릭 **데이터 연결** 에 **서버 탐색기**/**데이터베이스 탐색기** 을 클릭 한 다음 **연결 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="82263-113">Northwind 샘플 데이터베이스에 올바른 연결을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="82263-114">LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="82263-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="82263-115">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="82263-116">Visual basic **Windows Forms 응용 프로그램** 프로젝트 유형으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="82263-117">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="82263-118">선택 된 **LINQ to SQL 클래스** 항목 템플릿.</span><span class="sxs-lookup"><span data-stu-id="82263-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="82263-119">파일 이름을 `northwind.dbml`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="82263-120">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-120">Click **Add**.</span></span> <span data-ttu-id="82263-121">개체 관계형 디자이너 (O/R 디자이너) northwind.dbml 파일이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="82263-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="82263-122">O/R 디자이너를 쿼리 하는 테이블을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="82263-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="82263-123">**서버 탐색기**/**데이터베이스 탐색기**, Northwind 데이터베이스에 연결을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="82263-124">**테이블** 폴더를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="82263-125">O/R 디자이너를 닫은 경우 이전에 추가한 northwind.dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82263-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="82263-126">Customers 테이블을 클릭 하 고 디자이너의 왼쪽된 창에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="82263-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="82263-127">Orders 테이블을 클릭 하 고 디자이너의 왼쪽된 창에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="82263-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="82263-128">디자이너를 새로 만듭니다 `Customer` 고 `Order` 프로젝트에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="82263-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="82263-129">디자이너 자동으로 테이블 간의 관계를 검색 및 확인 자식 관련된 개체에 대 한 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="82263-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="82263-130">예를 들어 IntelliSense는 표시 됩니다는 `Customer` 개체에는 `Orders` 해당 고객에 게 관련 된 모든 주문에 대 한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="82263-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="82263-131">변경 내용을 저장 하 고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="82263-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="82263-132">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="82263-133">데이터베이스를 쿼리하고 결과 표시 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="82263-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="82263-134">**도구 상자**를 끌어를 <xref:System.Windows.Forms.DataGridView> Form1 프로젝트에 대 한 기본 Windows Form 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="82263-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="82263-135">코드를 추가 하는 Form1을 두 번 클릭 합니다 `Load` 폼의 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="82263-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="82263-136">O/R 디자이너에 테이블을 추가한 경우 디자이너 추가 <xref:System.Data.Linq.DataContext> 프로젝트에는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="82263-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="82263-137">이 개체는 해당 테이블에 액세스 하 고 개별 개체 및 각 테이블에 대 한 컬렉션에 액세스할 수 있어야 하는 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="82263-138"><xref:System.Data.Linq.DataContext> .dbml 파일의 이름에 따라 프로젝트에 대해 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="82263-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="82263-139">이 프로젝트에는 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext`합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="82263-140">인스턴스를 만들 수는 <xref:System.Data.Linq.DataContext> 코드와 쿼리가에서 O/R 디자이너에서 지정 된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="82263-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="82263-141">다음 코드를 추가 합니다 `Load` 데이터 컨텍스트 속성으로 노출 되 고 결과 정렬 하는 테이블을 쿼리 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="82263-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context and sort the results.</span></span> <span data-ttu-id="82263-142">쿼리는 내림차순에서 고객 주문 수로 결과 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-142">The query sorts the results by the number of customer orders, in descending order.</span></span> <span data-ttu-id="82263-143">주문 수가 같아야 하는 고객은 오름차순 (기본값) 회사 이름별으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82263-143">Customers that have the same number of orders are ordered by company name in ascending order (the default).</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#10](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-sort-query-results-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="82263-144">F5 키를 눌러 프로젝트를 실행 하 고 결과 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="82263-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82263-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="82263-145">See also</span></span>
- [<span data-ttu-id="82263-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="82263-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="82263-147">쿼리</span><span class="sxs-lookup"><span data-stu-id="82263-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="82263-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="82263-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="82263-149">DataContext 메서드(O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="82263-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
