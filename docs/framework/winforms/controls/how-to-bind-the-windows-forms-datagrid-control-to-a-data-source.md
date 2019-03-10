---
title: '방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
ms.openlocfilehash: 5da74abb107bc93bff496a35ecfc7a1233e5a76d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702960"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤 데이터 소스에서 정보를 표시 하도록 특별히 설계 되었습니다. 호출 하 여 런타임에 컨트롤을 바인딩하는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드. 다양 한 데이터 원본에서에서 데이터를 표시할 수 있지만 가장 일반적인 소스는 데이터 집합 및 데이터 뷰입니다.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>데이터 바인딩할 DataGrid 컨트롤을 프로그래밍 방식으로  
  
1.  데이터 집합을 채우는 코드를 작성 합니다.  
  
     데이터 원본이 데이터 집합 또는 데이터 집합 테이블을 기반으로 데이터 뷰를 폼에 데이터 집합을 채우는 코드를 추가 합니다.  
  
     사용할 정확한 코드를 데이터 집합 데이터를 가져오는 위치에 따라 달라 집니다. 일반적으로 호출 하는 데이터베이스에서 직접 데이터 집합을 채우는 경우 합니다 `Fill` 이라는 데이터 집합을 채우는 다음 예제와 같이 데이터 어댑터를 메서드의 `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     XML 웹 서비스에서 데이터 집합 가득 찰 경우 일반적으로 코드에 서비스의 인스턴스를 만들어야 하 고 데이터 집합을 반환 하는 해당 메서드 중 하나를 호출 합니다. 그런 다음 로컬 데이터 집합에 XML 웹 서비스에서 데이터 집합을 병합 합니다. 다음 예제에서는 XML 웹 서비스 호출의 인스턴스를 만들 수 있습니다 하는 방법을 보여 줍니다 `CategoriesService`, 호출 해당 `GetCategories` 메서드를 호출 하는 로컬 데이터 집합에 결과 데이터 집합을 병합 `DsCategories1`:  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =   
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2.  호출 된 <xref:System.Windows.Forms.DataGrid> 컨트롤의 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드, 데이터 원본 및 데이터 멤버를 전달 합니다. 데이터 멤버를 명시적으로 전달 해야 하는 경우 빈 문자열을 전달 합니다.  
  
    > [!NOTE]
    >  컨트롤의 표는 처음에 바인딩하는 경우 설정할 수 있습니다 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 고 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성입니다. 그러나 설정 된 후 이러한 속성을 재설정할 수 없습니다. 따라서 것이 좋습니다는 항상 사용 하 여 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드.  
  
     다음 예제에서는 프로그래밍 방식으로 바인딩하는 방법을 이라는 데이터 집합에서 Customers 테이블에 `DsCustomers1`:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     데이터 집합에만 테이블 Customers 테이블을 사용 하는 경우 그리드를 이러한 방식으로 또는 바인딩할 수 있습니다.  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3.  (선택 사항) 그리드로 해당 테이블 스타일과 열 스타일을 추가 합니다. 테이블 표시는 테이블 스타일이 없는 경우 최소한의 서식 지정 및 표시 하는 모든 열을 사용 하 여 있지만.  
  
## <a name="see-also"></a>참고자료
- [DataGrid 컨트롤 개요](datagrid-control-overview-windows-forms.md)
- [방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [DataGrid 컨트롤](datagrid-control-windows-forms.md)
- [Windows Forms 데이터 바인딩](../windows-forms-data-binding.md)
