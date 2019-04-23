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
ms.openlocfilehash: b869898a20008343b6c6cbe4bc7e399fc86fb232
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306055"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="5c490-102">방법: 데이터에 Windows Forms ComboBox 또는 ListBox 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="5c490-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="5c490-103">바인딩할 수 있습니다 합니다 <xref:System.Windows.Forms.ComboBox> 고 <xref:System.Windows.Forms.ListBox> 데이터베이스의 데이터를 검색 하는 등의 작업을 수행 하는 데이터를 새 데이터를 입력 하거나 기존 데이터를 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c490-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="5c490-104">ComboBox 또는 ListBox 컨트롤을 바인딩하려면</span><span class="sxs-lookup"><span data-stu-id="5c490-104">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="5c490-105">설정 된 `DataSource` 속성을 데이터 원본 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5c490-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="5c490-106">가능한 데이터 소스를 <xref:System.Windows.Forms.BindingSource> 데이터, 데이터 테이블, 데이터 뷰, 데이터 집합에 바인딩된 데이터 보기 관리자, 배열 또는 구현 하는 클래스는 <xref:System.Collections.IList> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5c490-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="5c490-107">자세한 내용은 [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5c490-107">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="5c490-108">테이블에 바인딩하는 경우에 설정 된 `DisplayMember` 속성을 데이터 원본에 있는 열의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5c490-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="5c490-109">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="5c490-109">\- or -</span></span>  
  
     <span data-ttu-id="5c490-110">바인딩하는 경우는 <xref:System.Collections.IList>, 멤버 표시 목록에서 형식의 공용 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c490-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    >  <span data-ttu-id="5c490-111">구현 하지 않는 데이터 소스에 바인딩한 경우는 <xref:System.ComponentModel.IBindingList> 인터페이스를 <xref:System.Collections.ArrayList>, 바인딩된 컨트롤의 데이터는 데이터 원본 업데이트 될 때 업데이트 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5c490-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="5c490-112">예를 들어 있는 경우 콤보 상자에 바인딩된를 <xref:System.Collections.ArrayList> 데이터에 추가 됩니다는 <xref:System.Collections.ArrayList>, 이러한 새 항목 콤보 상자에 표시 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5c490-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="5c490-113">그러나 콤보 상자를 호출 하 여 업데이트를 강제로 지정할 수 있습니다는 <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> 하 고 <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> 의 인스턴스에 대 한 메서드는 <xref:System.Windows.Forms.BindingContext> 컨트롤이 바인딩되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5c490-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c490-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="5c490-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="5c490-115">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="5c490-115">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="5c490-116">데이터 바인딩 및 Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c490-116">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="5c490-117">옵션 목록 표시에 사용된 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5c490-117">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
