---
title: '방법: LINQ를 사용하여 저장 프로시저 호출(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: 50a4dff90dc1ce02869978f1da147e530cefc3e1
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43779827"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="75778-102">방법: LINQ를 사용하여 저장 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75778-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="75778-103">언어 통합 쿼리 (LINQ) 쉽게 데이터베이스 개체와 같은 저장 프로시저를 포함 하 여 데이터베이스 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75778-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="75778-104">다음 예제에는 SQL Server 데이터베이스에서 저장된 프로시저를 호출 하는 응용 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="75778-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="75778-105">샘플은 데이터베이스에 두 개의 다른 저장된 프로시저를 호출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="75778-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="75778-106">각 프로시저의 쿼리 결과 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="75778-107">하나의 프로시저는 입력된 매개 변수를 사용 하 고 다른 프로시저 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75778-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="75778-108">이 항목의 예제는 Northwind 샘플 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="75778-109">개발 컴퓨터에이 데이터베이스가 없는 경우에 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75778-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="75778-110">자세한 내용은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="75778-111">데이터베이스에 대 한 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="75778-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="75778-112">Visual Studio에서 엽니다 **서버 탐색기**/**데이터베이스 탐색기** 를 클릭 하 여 **서버 탐색기**/**데이터베이스 탐색기** 에 **보기** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="75778-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="75778-113">마우스 오른쪽 단추로 클릭 **데이터 연결** 에 **서버 탐색기**/**데이터베이스 탐색기** 을 클릭 한 다음 **연결 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="75778-114">Northwind 샘플 데이터베이스에 올바른 연결을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="75778-115">LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="75778-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="75778-116">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="75778-117">Visual basic **Windows Forms 응용 프로그램** 프로젝트 유형으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="75778-118">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="75778-119">선택 된 **LINQ to SQL 클래스** 항목 템플릿.</span><span class="sxs-lookup"><span data-stu-id="75778-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="75778-120">파일 이름을 `northwind.dbml`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="75778-121">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-121">Click **Add**.</span></span> <span data-ttu-id="75778-122">개체 관계형 디자이너 (O/R 디자이너) northwind.dbml 파일이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="75778-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="75778-123">저장된 프로시저를 O/R 디자이너에 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="75778-123">To add stored procedures to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="75778-124">**서버 탐색기**/**데이터베이스 탐색기**, Northwind 데이터베이스에 연결을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="75778-125">확장 된 **Stored Procedures** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="75778-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="75778-126">O/R 디자이너를 닫은 경우 이전에 추가한 northwind.dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75778-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="75778-127">클릭 합니다 **연도별 판매량** 저장 프로시저를 디자이너의 오른쪽 창으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="75778-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="75778-128">클릭 합니다 **Ten Most Expensive Products** 저장된 프로시저 디자이너의 오른쪽 창으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="75778-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3.  <span data-ttu-id="75778-129">변경 내용을 저장 하 고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="75778-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="75778-130">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="75778-131">저장된 프로시저의 결과 표시 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="75778-131">To add code to display the results of the stored procedures</span></span>  
  
1.  <span data-ttu-id="75778-132">**도구 상자**를 끌어를 <xref:System.Windows.Forms.DataGridView> Form1 프로젝트에 대 한 기본 Windows Form 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="75778-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="75778-133">코드를 추가 하는 Form1을 두 번 클릭 해당 `Load` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="75778-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3.  <span data-ttu-id="75778-134">디자이너의 추가 저장된 프로시저를 O/R 디자이너에 추가 하는 경우는 <xref:System.Data.Linq.DataContext> 프로젝트에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="75778-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="75778-135">이 개체는 해당 프로시저에 액세스 해야 하는 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="75778-136"><xref:System.Data.Linq.DataContext> .dbml 파일의 이름에 따라 프로젝트에 대해 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="75778-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="75778-137">이 프로젝트에는 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext`합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="75778-138">인스턴스를 만들 수는 <xref:System.Data.Linq.DataContext> O/R 디자이너에서 지정 된 저장된 프로시저 메서드 코드에서 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="75778-139">바인딩할 합니다 <xref:System.Windows.Forms.DataGridView> 개체를 호출 하 여 즉시 실행 하도록 쿼리를 강제 적용 해야 할 수 있습니다는 <xref:System.Linq.Enumerable.ToList%2A> 메서드 저장된 프로시저의 결과를 합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="75778-140">다음 코드를 추가 합니다 `Load` 이벤트에서 데이터에 대해 메서드로 노출할 프로시저 중 하나를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]  
    [!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]  
  
4.  <span data-ttu-id="75778-141">F5 키를 눌러 프로젝트를 실행 하 고 결과 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="75778-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75778-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75778-142">See Also</span></span>  
 [<span data-ttu-id="75778-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="75778-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="75778-144">쿼리</span><span class="sxs-lookup"><span data-stu-id="75778-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="75778-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="75778-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="75778-146">DataContext 메서드(O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="75778-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="75778-147">방법: 저장 프로시저를 할당하여 업데이트, 삽입 및 삭제 수행(O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="75778-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](https://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
