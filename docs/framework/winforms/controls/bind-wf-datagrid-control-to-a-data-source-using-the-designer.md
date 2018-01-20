---
title: "방법: 디자이너를 사용하여 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3913ffe046bb55e31d8be223061af61371a47418
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a><span data-ttu-id="6b7da-102">방법: 디자이너를 사용하여 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="6b7da-102">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="6b7da-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="6b7da-104">자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b7da-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="6b7da-105">Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤 특별히 설계 된 데이터 원본에서 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="6b7da-106">설정 하 여 디자인 타임에 컨트롤을 바인딩하는 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 및 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성을 호출 하 여 런타임 시는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="6b7da-106">You bind the control at design time by setting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties, or at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="6b7da-107">다양 한 데이터 원본에서에서 데이터를 표시할 수 있지만 가장 일반적인 소스는 데이터 집합 및 데이터 보기.</span><span class="sxs-lookup"><span data-stu-id="6b7da-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
 <span data-ttu-id="6b7da-108">디자인 타임에 데이터 소스를 사용할 수 있는 경우-예: 폼 데이터 집합 또는 데이터 보기의 인스턴스를 포함 하는 경우-디자인 타임에 눈금 데이터 소스에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-108">If the data source is available at design time—for example, if the form contains an instance of a dataset or a data view—you can bind the grid to the data source at design time.</span></span> <span data-ttu-id="6b7da-109">다음 표에서 데이터 모양을 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-109">You can then preview what the data will look like in the grid.</span></span>  
  
 <span data-ttu-id="6b7da-110">또한 런타임 시 표를 프로그래밍 방식으로 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-110">You can also bind the grid programmatically, at run time.</span></span> <span data-ttu-id="6b7da-111">런타임에 발생 하는 정보에 따라 데이터 소스를 설정 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-111">This is useful when you want to set a data source based on information you get at run time.</span></span> <span data-ttu-id="6b7da-112">예를 들어 응용 프로그램 사용자를 보려면 테이블의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-112">For example, the application might let the user specify the name of a table to view.</span></span> <span data-ttu-id="6b7da-113">디자인 타임에 데이터 원본이 존재 하지 않는 경우에도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-113">It is also necessary in situations where the data source does not exist at design time.</span></span> <span data-ttu-id="6b7da-114">배열, 컬렉션, 형식화 되지 않은 데이터 집합 및 데이터 판독기와 같은 데이터 원본 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-114">This includes data sources such as arrays, collections, untyped datasets, and data readers.</span></span>  
  
 <span data-ttu-id="6b7da-115">다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.DataGrid> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-115">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="6b7da-116">이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-116">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="6b7da-117">[!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> 내에 **도구 상자** 기본적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-117">In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="6b7da-118">추가 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 도구 상자에 항목 추가](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0)합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-118">For information about adding it, see [How to: Add Items to the Toolbox](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).</span></span> <span data-ttu-id="6b7da-119">또한에 [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]를 사용할 수 있습니다는 **데이터 소스** 디자인 타임 데이터 바인딩에 대 한 창.</span><span class="sxs-lookup"><span data-stu-id="6b7da-119">Additionally in [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], you can use the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="6b7da-120">자세한 내용은 참조 [Visual Studio에서 데이터에 컨트롤 바인딩](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-120">For more information see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b7da-121">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-121">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6b7da-122">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-122">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6b7da-123">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b7da-123">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a><span data-ttu-id="6b7da-124">DataGrid 컨트롤을 디자이너에서 단일 테이블에 데이터 바인딩을 위해</span><span class="sxs-lookup"><span data-stu-id="6b7da-124">To data-bind the DataGrid control to a single table in the designer</span></span>  
  
1.  <span data-ttu-id="6b7da-125">컨트롤의 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성을 바인딩할 데이터 항목을 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-125">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2.  <span data-ttu-id="6b7da-126">이면 데이터 원본이 데이터 집합 설정의 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성을 바인딩할 테이블의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-126">If the data source is a dataset, set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the table to bind to.</span></span>  
  
3.  <span data-ttu-id="6b7da-127">이면 데이터 원본이 데이터 집합 또는 데이터 집합 테이블을 기반으로 데이터 뷰를 폼에 데이터 집합을 채우는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-127">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="6b7da-128">사용할 올바른 코드는 데이터 집합 데이터를 가져오는 위치에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-128">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="6b7da-129">일반적으로 호출 하는 데이터베이스에서 직접 데이터 집합을 채우는 경우는 `Fill` 메서드 라는 데이터 집합을 채우는 다음 코드 예제와 같이 데이터 어댑터의 `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="6b7da-129">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following code example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  <span data-ttu-id="6b7da-130">(선택 사항) 해당 테이블 스타일과 열 스타일을 표에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-130">(Optional) Add the appropriate table styles and column styles to the grid.</span></span>  
  
     <span data-ttu-id="6b7da-131">테이블, 테이블 스타일이 없는 경우 나타납니다 하지만 최소한의 서식으로 및 표시 하는 모든 열을 갖는 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-131">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a><span data-ttu-id="6b7da-132">DataGrid 컨트롤을 디자이너에서 데이터 집합에서 여러 테이블에 데이터 바인딩을 위해</span><span class="sxs-lookup"><span data-stu-id="6b7da-132">To data-bind the DataGrid control to multiple tables in a dataset in the designer</span></span>  
  
1.  <span data-ttu-id="6b7da-133">컨트롤의 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성을 바인딩할 데이터 항목을 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-133">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2.  <span data-ttu-id="6b7da-134">데이터 집합이 포함 된 관련된 테이블 (즉, 경우 relation 개체 포함)로 설정 된 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성을 부모 테이블의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-134">If the dataset contains related tables (that is, if it contains a relation object), set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the parent table.</span></span>  
  
3.  <span data-ttu-id="6b7da-135">데이터 집합을 채우는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7da-135">Write code to fill the dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b7da-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b7da-136">See Also</span></span>  
 [<span data-ttu-id="6b7da-137">DataGrid 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="6b7da-137">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [<span data-ttu-id="6b7da-138">방법: Windows Forms DataGrid 컨트롤에 테이블 및 열 추가</span><span class="sxs-lookup"><span data-stu-id="6b7da-138">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [<span data-ttu-id="6b7da-139">DataGrid 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6b7da-139">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="6b7da-140">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="6b7da-140">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="6b7da-141">Visual Studio에서 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="6b7da-141">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)
