---
title: 로드 메서드
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: 82f840ab7dd26a4888ebf024d696f2c70701eb18
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607234"
---
# <a name="the-load-method"></a>로드 메서드
<xref:System.Data.DataTable.Load%2A> 메서드를 사용하여 데이터 소스의 행과 함께 <xref:System.Data.DataTable>을 로드할 수 있습니다. 이 가장 간단한 형태로 단일 매개 변수를 허용 하는 오버 로드 된 메서드를 **DataReader**합니다. 이 형식으로 로드 하는 기능만 합니다 **DataTable** 행. 선택적으로 지정할 수 있습니다는 **LoadOption** 매개 변수 데이터 추가 하는 방법을 제어 하는 **DataTable**합니다.  
  
 합니다 **LoadOption** 매개 변수는 경우에 특히 유용 여기서 합니다 **DataTable** 이미 데이터 행이 포함 된, 데이터 원본에서 어떻게 들어오는 데이터 설명 하므로 데이터를 사용 하 여 결합 됩니다 이미 표에 합니다. 예를 들어 **PreserveCurrentValues** (기본값)를 지정 하는로 표시 된 행의 경우에서 **Added** 에 **DataTable**, **원래** 값 이나 각 열은 데이터 원본에서 일치 하는 행의 내용으로 설정 됩니다. **현재** 값은 행이 추가 하는 경우 할당 된 값을 유지 및 **RowState** 행의로 설정 됩니다 **Changed**합니다.  
  
 다음 표에서는 <xref:System.Data.LoadOption> 열거형 값에 대해 간략하게 설명합니다.  
  
|LoadOption 값|설명|  
|----------------------|-----------------|  
|**OverwriteRow**|들어오는 행을가 같으면 **PrimaryKey** 에 이미 행 값을 **DataTable**의 **원래** 및 **현재** 각 값 열 들어오는 행의 값으로 바뀝니다. 및 **RowState** 속성이 **Unchanged**합니다.<br /><br /> 에 이미 존재 하지 않는 데이터 원본에서 행을 **DataTable** 와 함께 추가 되는 **RowState** 값 **Unchanged**.<br /><br /> 이 옵션에는 실제로 내용을 새로 고칩니다 합니다 **DataTable** 데이터 소스의 내용과 일치 하도록 합니다.|  
|**PreserveCurrentValues (기본값)**|들어오는 행을가 같으면 **PrimaryKey** 에 이미 행 값을 **DataTable**의 **원래** 들어오는 행 및 합니다 내용의값이설정**현재** 값 변경 되지 않습니다.<br /><br /> 경우는 **RowState** 는 **Added** 또는 **Modified**로 설정 됩니다 **Modified**합니다.<br /><br /> 경우는 **RowState** 되었습니다 **Deleted**, 상태로 유지 됩니다 **삭제**합니다.<br /><br /> 에 이미 존재 하지 않는 데이터 원본에서 행을 **DataTable** 추가 되 면 및 **RowState** 로 설정 되어 **Unchanged**합니다.|  
|**UpdateCurrentValues**|들어오는 행을가 같으면 **PrimaryKey** 에 이미 행 값을 **DataTable**의 **현재** 값으로 복사 됩니다는 **원래**값 및 **현재** 들어오는 행의 내용에 값이 설정 됩니다.<br /><br /> 경우는 **RowState** 에 **DataTable** 되었습니다 **Added**, **RowState** 유지 됩니다 **Added**. 행으로 표시 된 **Modified** 또는 **Deleted**, **RowState** 는 **수정**합니다.<br /><br /> 에 이미 존재 하지 않는 데이터 원본에서 행을 **DataTable** 추가 되 면 및 **RowState** 로 설정 되어 **Added**합니다.|  
  
 다음 샘플에서는 합니다 **부하** 에 직원 생일 목록을 표시 하는 메서드는 **Northwind** 데이터베이스입니다.  
  
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
  
## <a name="see-also"></a>참고자료

- [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
