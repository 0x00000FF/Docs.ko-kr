---
title: '방법: LINQ 쿼리 결과를 특정 형식으로 반환(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 720660153cb357c11168ab45ebf8343559faf82a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393248"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="f7789-102">방법: LINQ 쿼리 결과를 특정 형식으로 반환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7789-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="f7789-103">언어 통합 쿼리 (LINQ)를 사용 하면 쉽게 데이터베이스 정보에 액세스 하 고 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="f7789-104">LINQ 쿼리는 기본적으로 익명 형식으로 개체의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="f7789-105">쿼리를 사용 하 여 특정 형식의 목록을 반환 하도록 지정할 수도 있습니다는 `Select` 절.</span><span class="sxs-lookup"><span data-stu-id="f7789-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="f7789-106">다음 예제에서는 특정 명명 된 형식으로 결과 프로젝트 및 SQL Server 데이터베이스에 대 한 쿼리를 수행 하는 새 응용 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="f7789-107">자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) 하 고 [Select 절](../../../../visual-basic/language-reference/queries/select-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-107">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="f7789-108">이 항목의 예제는 Northwind 샘플 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="f7789-109">개발 컴퓨터에이 데이터베이스가 없는 경우에 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="f7789-110">자세한 내용은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="f7789-111">데이터베이스에 대 한 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="f7789-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="f7789-112">Visual Studio에서 엽니다 **서버 탐색기**/**데이터베이스 탐색기** 를 클릭 하 여 **서버 탐색기**/**데이터베이스 탐색기** 에 **보기** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="f7789-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="f7789-113">마우스 오른쪽 단추로 클릭 **데이터 연결** 에 **서버 탐색기**/**데이터베이스 탐색기** 을 클릭 한 다음 **연결 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="f7789-114">Northwind 샘플 데이터베이스에 올바른 연결을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="f7789-115">LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="f7789-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="f7789-116">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="f7789-117">Visual basic **Windows Forms 응용 프로그램** 프로젝트 유형으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="f7789-118">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="f7789-119">선택 된 **LINQ to SQL 클래스** 항목 템플릿.</span><span class="sxs-lookup"><span data-stu-id="f7789-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="f7789-120">파일 이름을 `northwind.dbml`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="f7789-121">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-121">Click **Add**.</span></span> <span data-ttu-id="f7789-122">개체 관계형 디자이너 (O/R 디자이너) northwind.dbml 파일이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="f7789-123">O/R 디자이너를 쿼리 하는 테이블을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="f7789-123">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="f7789-124">**서버 탐색기**/**데이터베이스 탐색기**, Northwind 데이터베이스에 연결을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="f7789-125">확장 된 **테이블** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="f7789-126">O/R 디자이너를 닫은 경우 이전에 추가한 northwind.dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="f7789-127">Customers 테이블을 클릭 하 고 디자이너의 왼쪽된 창에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="f7789-128">디자이너를 새로 만들고 `Customer` 프로젝트에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="f7789-129">쿼리 결과를 프로젝션 할 수 있습니다는 `Customer` 형식 또는 사용자가 만든 형식으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="f7789-130">이 샘플 이후 절차에서 새 형식을 만들고 쿼리 결과 해당 형식으로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3.  <span data-ttu-id="f7789-131">변경 내용을 저장 하 고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="f7789-132">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="f7789-133">데이터베이스를 쿼리하고 결과 표시 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="f7789-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="f7789-134">**도구 상자**를 끌어를 <xref:System.Windows.Forms.DataGridView> Form1 프로젝트에 대 한 기본 Windows Form 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="f7789-135">Form1 클래스를 수정 하는 Form1을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3.  <span data-ttu-id="f7789-136">후 합니다 `End Class` Form1 클래스의 문을 만들려면 다음 코드를 추가 `CustomerInfo` 이 샘플에 대 한 쿼리 결과 보관 하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_1.vb)]  
  
4.  <span data-ttu-id="f7789-137">O/R 디자이너에 테이블을 추가한 경우 디자이너 추가 <xref:System.Data.Linq.DataContext> 프로젝트에는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="f7789-138">이 개체는 해당 테이블에 액세스 하 고 개별 개체 및 각 테이블에 대 한 컬렉션에 액세스할 수 있어야 하는 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="f7789-139"><xref:System.Data.Linq.DataContext> .dbml 파일의 이름에 따라 프로젝트에 대해 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="f7789-140">이 프로젝트에는 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext`합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="f7789-141">인스턴스를 만들 수는 <xref:System.Data.Linq.DataContext> 코드와 쿼리가에서 O/R 디자이너에서 지정 된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="f7789-142">에 `Load` Form1 클래스의 이벤트 데이터 컨텍스트 속성으로 노출 되는 테이블을 쿼리하려면 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="f7789-143">합니다 `Select` 쿼리 절에 새 만들어집니다 `CustomerInfo` 쿼리 결과의 각 항목에 대 한 익명 형식 대신 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_2.vb)]  
  
5.  <span data-ttu-id="f7789-144">F5 키를 눌러 프로젝트를 실행 하 고 결과 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7789-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7789-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7789-145">See Also</span></span>  
 [<span data-ttu-id="f7789-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="f7789-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="f7789-147">쿼리</span><span class="sxs-lookup"><span data-stu-id="f7789-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="f7789-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f7789-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="f7789-149">DataContext 메서드(O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="f7789-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
