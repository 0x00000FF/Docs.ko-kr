---
title: '방법: 데이터에 Windows Forms ComboBox 또는 ListBox 컨트롤 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], binding to controls
- list boxes [Windows Forms], data binding
- ComboBox control [Windows Forms], data binding
- data binding [Windows Forms], combo boxes
- ListBox control [Windows Forms], data binding
- combo boxes [Windows Forms], data binding
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
ms.openlocfilehash: 949b63f435289d486f445bad01d0bc6cc33e6f08
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197193"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>방법: 데이터에 Windows Forms ComboBox 또는 ListBox 컨트롤 바인딩
바인딩할 수 있습니다 합니다 <xref:System.Windows.Forms.ComboBox> 고 <xref:System.Windows.Forms.ListBox> 데이터베이스의 데이터를 검색 하는 등의 작업을 수행 하는 데이터를 새 데이터를 입력 하거나 기존 데이터를 편집 합니다.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>ComboBox 또는 ListBox 컨트롤을 바인딩하려면  
  
1.  설정 된 `DataSource` 속성을 데이터 원본 개체입니다. 가능한 데이터 소스를 <xref:System.Windows.Forms.BindingSource> 데이터, 데이터 테이블, 데이터 뷰, 데이터 집합에 바인딩된 데이터 보기 관리자, 배열 또는 구현 하는 클래스는 <xref:System.Collections.IList> 인터페이스입니다. 자세한 내용은 [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md)합니다.  
  
2.  테이블에 바인딩하는 경우에 설정 된 `DisplayMember` 속성을 데이터 원본에 있는 열의 이름입니다.  
  
     \- 또는 -  
  
     바인딩하는 경우는 <xref:System.Collections.IList>, 멤버 표시 목록에서 형식의 공용 속성을 설정 합니다.  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
    ```  
  
    > [!NOTE]
    >  구현 하지 않는 데이터 소스에 바인딩한 경우는 <xref:System.ComponentModel.IBindingList> 인터페이스를 <xref:System.Collections.ArrayList>, 바인딩된 컨트롤의 데이터는 데이터 원본 업데이트 될 때 업데이트 되지 것입니다. 예를 들어 있는 경우 콤보 상자에 바인딩된를 <xref:System.Collections.ArrayList> 데이터에 추가 됩니다는 <xref:System.Collections.ArrayList>, 이러한 새 항목 콤보 상자에 표시 되지 것입니다. 그러나 콤보 상자를 호출 하 여 업데이트를 강제로 지정할 수 있습니다는 <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> 하 고 <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> 의 인스턴스에 대 한 메서드는 <xref:System.Windows.Forms.BindingContext> 컨트롤이 바인딩되는 클래스입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Windows Forms 데이터 바인딩](../windows-forms-data-binding.md)
- [데이터 바인딩 및 Windows Forms](../data-binding-and-windows-forms.md)
- [옵션 목록 표시에 사용하는 Windows Forms 컨트롤](windows-forms-controls-used-to-list-options.md)
