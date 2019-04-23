---
title: 로드 메서드
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: 82f840ab7dd26a4888ebf024d696f2c70701eb18
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173292"
---
# <a name="the-load-method"></a><span data-ttu-id="5a699-102">로드 메서드</span><span class="sxs-lookup"><span data-stu-id="5a699-102">The Load Method</span></span>
<span data-ttu-id="5a699-103"><xref:System.Data.DataTable.Load%2A> 메서드를 사용하여 데이터 소스의 행과 함께 <xref:System.Data.DataTable>을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="5a699-104">이 가장 간단한 형태로 단일 매개 변수를 허용 하는 오버 로드 된 메서드를 **DataReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="5a699-105">이 형식으로 로드 하는 기능만 합니다 **DataTable** 행.</span><span class="sxs-lookup"><span data-stu-id="5a699-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="5a699-106">선택적으로 지정할 수 있습니다는 **LoadOption** 매개 변수 데이터 추가 하는 방법을 제어 하는 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="5a699-107">합니다 **LoadOption** 매개 변수는 경우에 특히 유용 여기서 합니다 **DataTable** 이미 데이터 행이 포함 된, 데이터 원본에서 어떻게 들어오는 데이터 설명 하므로 데이터를 사용 하 여 결합 됩니다 이미 표에 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="5a699-108">예를 들어 **PreserveCurrentValues** (기본값)를 지정 하는로 표시 된 행의 경우에서 **Added** 에 **DataTable**, **원래** 값 이나 각 열은 데이터 원본에서 일치 하는 행의 내용으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="5a699-109">**현재** 값은 행이 추가 하는 경우 할당 된 값을 유지 및 **RowState** 행의로 설정 됩니다 **Changed**합니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="5a699-110">다음 표에서는 <xref:System.Data.LoadOption> 열거형 값에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="5a699-111">LoadOption 값</span><span class="sxs-lookup"><span data-stu-id="5a699-111">LoadOption value</span></span>|<span data-ttu-id="5a699-112">설명</span><span class="sxs-lookup"><span data-stu-id="5a699-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="5a699-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="5a699-113">**OverwriteRow**</span></span>|<span data-ttu-id="5a699-114">들어오는 행을가 같으면 **PrimaryKey** 에 이미 행 값을 **DataTable**의 **원래** 및 **현재** 각 값 열 들어오는 행의 값으로 바뀝니다. 및 **RowState** 속성이 **Unchanged**합니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="5a699-115">에 이미 존재 하지 않는 데이터 원본에서 행을 **DataTable** 와 함께 추가 되는 **RowState** 값 **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="5a699-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="5a699-116">이 옵션에는 실제로 내용을 새로 고칩니다 합니다 **DataTable** 데이터 소스의 내용과 일치 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="5a699-117">**PreserveCurrentValues (기본값)**</span><span class="sxs-lookup"><span data-stu-id="5a699-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="5a699-118">들어오는 행을가 같으면 **PrimaryKey** 에 이미 행 값을 **DataTable**의 **원래** 들어오는 행 및 합니다 내용의값이설정**현재** 값 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="5a699-119">경우는 **RowState** 는 **Added** 또는 **Modified**로 설정 됩니다 **Modified**합니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="5a699-120">경우는 **RowState** 되었습니다 **Deleted**, 상태로 유지 됩니다 **삭제**합니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="5a699-121">에 이미 존재 하지 않는 데이터 원본에서 행을 **DataTable** 추가 되 면 및 **RowState** 로 설정 되어 **Unchanged**합니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="5a699-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="5a699-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="5a699-123">들어오는 행을가 같으면 **PrimaryKey** 에 이미 행 값을 **DataTable**의 **현재** 값으로 복사 됩니다는 **원래**값 및 **현재** 들어오는 행의 내용에 값이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="5a699-124">경우는 **RowState** 에 **DataTable** 되었습니다 **Added**, **RowState** 유지 됩니다 **Added**.</span><span class="sxs-lookup"><span data-stu-id="5a699-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="5a699-125">행으로 표시 된 **Modified** 또는 **Deleted**, **RowState** 는 **수정**합니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="5a699-126">에 이미 존재 하지 않는 데이터 원본에서 행을 **DataTable** 추가 되 면 및 **RowState** 로 설정 되어 **Added**합니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="5a699-127">다음 샘플에서는 합니다 **부하** 에 직원 생일 목록을 표시 하는 메서드는 **Northwind** 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5a699-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
```vb  
Private Sub LoadBirthdays(ByVal connectionString As String)  
    ' Assumes that connectionString is a valid connection string  
    ' to the Northwind database on SQL Server.  
    Dim queryString As String = _  
    "SELECT LastName, FirstName, BirthDate " & _  
      " FROM dbo.Employees " & _  
      "ORDER BY BirthDate, LastName, FirstName"  
  
    ' Open and fill a DataSet.   
    Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
        queryString, connectionString)  
    Dim employees As New DataSet  
    adapter.Fill(employees, "Employees")  
  
    ' Create a SqlDataReader for use with the Load Method.  
    Dim reader As DataTableReader = employees.GetDataReader()  
  
    ' Create an instance of DataTable and assign the first  
    ' DataTable in the DataSet.Tables collection to it.  
    Dim dataTableEmp As DataTable = employees.Tables(0)  
  
    ' Fill the DataTable with data by calling Load and  
    ' passing the SqlDataReader.  
    dataTableEmp.Load(reader, LoadOption.OverwriteRow)  
  
    ' Loop through the rows collection and display the values  
    ' in the console window.  
    Dim employeeRow As DataRow  
    For Each employeeRow In dataTableEmp.Rows  
        Console.WriteLine("{0:MM\\dd\\yyyy}" & ControlChars.Tab & _  
          "{1}, {2}", _  
          employeeRow("BirthDate"), _  
          employeeRow("LastName"), _  
          employeeRow("FirstName"))  
    Next employeeRow  
  
    ' Keep the window opened to view the contents.  
    Console.ReadLine()  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a699-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="5a699-128">See also</span></span>

- [<span data-ttu-id="5a699-129">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="5a699-129">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="5a699-130">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="5a699-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
