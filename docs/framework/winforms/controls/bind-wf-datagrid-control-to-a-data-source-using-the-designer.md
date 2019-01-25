---
title: '방법: 디자이너를 사용 하 여 데이터 원본에 Windows Forms DataGrid 컨트롤 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
ms.openlocfilehash: 414c989d258ca4b7a9097afa2b7f2407505fb629
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687585"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a><span data-ttu-id="284d1-102">방법: 디자이너를 사용 하 여 데이터 원본에 Windows Forms DataGrid 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="284d1-102">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>

> [!NOTE]
>  <span data-ttu-id="284d1-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="284d1-104">자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="284d1-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="284d1-105">Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤 데이터 소스에서 정보를 표시 하도록 특별히 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="284d1-106">설정 하 여 디자인 타임에 컨트롤을 바인딩하는 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 및 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성을 호출 하 여 런타임 시는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="284d1-106">You bind the control at design time by setting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties, or at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="284d1-107">다양 한 데이터 원본에서에서 데이터를 표시할 수 있지만 가장 일반적인 소스는 데이터 집합 및 데이터 뷰입니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
 <span data-ttu-id="284d1-108">디자인 타임에 데이터 소스를 사용할 수 있는 경우, 예를 들어 데이터 집합 또는 데이터 보기의 인스턴스를 포함 하는 폼-디자인 타임에 데이터 원본에 모눈을 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-108">If the data source is available at design time—for example, if the form contains an instance of a dataset or a data view—you can bind the grid to the data source at design time.</span></span> <span data-ttu-id="284d1-109">다음 표의 데이터 모양을 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-109">You can then preview what the data will look like in the grid.</span></span>  
  
 <span data-ttu-id="284d1-110">또한 런타임 시 그리드를 프로그래밍 방식으로 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-110">You can also bind the grid programmatically, at run time.</span></span> <span data-ttu-id="284d1-111">런타임 시 얻게 되는 정보를 기반으로 데이터 소스를 설정 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-111">This is useful when you want to set a data source based on information you get at run time.</span></span> <span data-ttu-id="284d1-112">예를 들어, 응용 프로그램 보기 테이블의 이름을 지정 하는 사용자를 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-112">For example, the application might let the user specify the name of a table to view.</span></span> <span data-ttu-id="284d1-113">디자인 타임에 데이터 원본 없는 상황에서 필요한 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-113">It is also necessary in situations where the data source does not exist at design time.</span></span> <span data-ttu-id="284d1-114">이 배열, 컬렉션, 형식화 되지 않은 데이터 집합 및 데이터 판독기와 같은 데이터 원본이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-114">This includes data sources such as arrays, collections, untyped datasets, and data readers.</span></span>  
  
 <span data-ttu-id="284d1-115">다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGrid> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-115">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="284d1-116">이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows 응용 프로그램 프로젝트를 만듭니다](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) 고 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-116">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="284d1-117">Visual Studio 2005에는 <xref:System.Windows.Forms.DataGrid> 컨트롤에 없는 경우는 **도구 상자** 기본적으로.</span><span class="sxs-lookup"><span data-stu-id="284d1-117">In Visual Studio 2005, the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="284d1-118">추가 하는 방법에 대 한 내용은 [방법: 도구 상자 항목 추가](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0)합니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-118">For information about adding it, see [How to: Add Items to the Toolbox](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).</span></span> <span data-ttu-id="284d1-119">또한 Visual Studio 2005에서 사용할 수는 **데이터 원본** 디자인 타임 데이터 바인딩에 대 한 창.</span><span class="sxs-lookup"><span data-stu-id="284d1-119">Additionally in Visual Studio 2005, you can use the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="284d1-120">자세한 내용은 참조 [Visual Studio에서 데이터에 컨트롤 바인딩](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-120">For more information see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="284d1-121">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-121">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="284d1-122">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-122">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="284d1-123">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="284d1-123">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a><span data-ttu-id="284d1-124">DataGrid 컨트롤을 디자이너에서 단일 테이블에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="284d1-124">To data-bind the DataGrid control to a single table in the designer</span></span>  
  
1.  <span data-ttu-id="284d1-125">컨트롤의 설정 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성에 바인딩할 데이터 항목을 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-125">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2.  <span data-ttu-id="284d1-126">이면 데이터 원본이 데이터 집합을 설정 합니다 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성을 바인딩할 테이블의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-126">If the data source is a dataset, set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the table to bind to.</span></span>  
  
3.  <span data-ttu-id="284d1-127">데이터 원본이 데이터 집합 또는 데이터 집합 테이블을 기반으로 데이터 뷰를 폼에 데이터 집합을 채우는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-127">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="284d1-128">사용할 정확한 코드를 데이터 집합 데이터를 가져오는 위치에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-128">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="284d1-129">일반적으로 호출 하는 데이터베이스에서 직접 데이터 집합을 채우는 경우 합니다 `Fill` 이라는 데이터 집합을 채우는 다음 코드 예제와 같이 데이터 어댑터를 메서드의 `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="284d1-129">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following code example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  <span data-ttu-id="284d1-130">(선택 사항) 그리드로 해당 테이블 스타일과 열 스타일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-130">(Optional) Add the appropriate table styles and column styles to the grid.</span></span>  
  
     <span data-ttu-id="284d1-131">테이블 표시는 테이블 스타일이 없는 경우 최소한의 서식 지정 및 표시 하는 모든 열을 사용 하 여 있지만.</span><span class="sxs-lookup"><span data-stu-id="284d1-131">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a><span data-ttu-id="284d1-132">DataGrid 컨트롤을 디자이너에서 데이터 집합의 여러 테이블에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="284d1-132">To data-bind the DataGrid control to multiple tables in a dataset in the designer</span></span>  
  
1.  <span data-ttu-id="284d1-133">컨트롤의 설정 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성에 바인딩할 데이터 항목을 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-133">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2.  <span data-ttu-id="284d1-134">데이터 집합이 포함 된 관련된 테이블 (즉, 경우 관계를 포함)로 설정 합니다 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성을 부모 테이블의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-134">If the dataset contains related tables (that is, if it contains a relation object), set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the parent table.</span></span>  
  
3.  <span data-ttu-id="284d1-135">데이터 집합을 채우는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="284d1-135">Write code to fill the dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="284d1-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="284d1-136">See also</span></span>
- [<span data-ttu-id="284d1-137">DataGrid 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="284d1-137">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="284d1-138">방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가</span><span class="sxs-lookup"><span data-stu-id="284d1-138">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="284d1-139">DataGrid 컨트롤</span><span class="sxs-lookup"><span data-stu-id="284d1-139">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
- [<span data-ttu-id="284d1-140">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="284d1-140">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)
- [<span data-ttu-id="284d1-141">Visual Studio에서 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="284d1-141">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)
