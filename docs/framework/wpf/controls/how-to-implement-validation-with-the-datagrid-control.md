---
title: '방법: DataGrid 컨트롤을 사용하여 유효성 검사 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
ms.openlocfilehash: 00d09c62aae67e3438816409c95ccf96050b3206
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770879"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a><span data-ttu-id="ad9e0-102">방법: DataGrid 컨트롤을 사용하여 유효성 검사 구현</span><span class="sxs-lookup"><span data-stu-id="ad9e0-102">How to: Implement Validation with the DataGrid Control</span></span>
<span data-ttu-id="ad9e0-103"><xref:System.Windows.Controls.DataGrid> 컨트롤을 사용 하면 셀 및 행 수준에서 유효성 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-103">The <xref:System.Windows.Controls.DataGrid> control enables you to perform validation at both the cell and row level.</span></span> <span data-ttu-id="ad9e0-104">셀 수준 유효성 검사를 사용 하 여 사용자는 값을 업데이트 하는 경우 바인딩된 데이터 개체의 개별 속성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-104">With cell-level validation, you validate individual properties of a bound data object when a user updates a value.</span></span> <span data-ttu-id="ad9e0-105">행 수준 유효성 검사를 사용 하 여 행에 변경 내용을 커밋할 때 전체 데이터 개체에 유효성 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-105">With row-level validation, you validate entire data objects when a user commits changes to a row.</span></span> <span data-ttu-id="ad9e0-106">유효성 검사 오류에 대 한 사용자 지정된 시각적 피드백을 제공 하거나 기본 시각적 피드백을 사용할 수도 있습니다는 <xref:System.Windows.Controls.DataGrid> 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-106">You can also provide customized visual feedback for validation errors, or use the default visual feedback that the <xref:System.Windows.Controls.DataGrid> control provides.</span></span>  
  
 <span data-ttu-id="ad9e0-107">다음 절차 유효성 검사 규칙을 적용 하는 방법에 설명 <xref:System.Windows.Controls.DataGrid> 바인딩 및 시각적 피드백을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-107">The following procedures describe how to apply validation rules to <xref:System.Windows.Controls.DataGrid> bindings and customize the visual feedback.</span></span>  
  
### <a name="to-validate-individual-cell-values"></a><span data-ttu-id="ad9e0-108">개별 셀 값의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ad9e0-108">To validate individual cell values</span></span>  
  
- <span data-ttu-id="ad9e0-109">열을 사용 하 여 사용 되는 바인딩에 대해 하나 이상의 유효성 검사 규칙을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-109">Specify one or more validation rules on the binding used with a column.</span></span> <span data-ttu-id="ad9e0-110">에 설명 된 대로이 간단한 컨트롤의 데이터 유효성 검사 비슷합니다 [데이터 바인딩 개요](../data/data-binding-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-110">This is similar to validating data in simple controls, as described in [Data Binding Overview](../data/data-binding-overview.md).</span></span>  
  
     <span data-ttu-id="ad9e0-111">다음 예제와 <xref:System.Windows.Controls.DataGrid> 비즈니스 개체의 다른 속성에 바인딩된 열 4 개를 사용 하 여 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-111">The following example shows a <xref:System.Windows.Controls.DataGrid> control with four columns bound to different properties of a business object.</span></span> <span data-ttu-id="ad9e0-112">세 개의 열을 지정 합니다 <xref:System.Windows.Controls.ExceptionValidationRule> 설정 하 여는 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-112">Three of the columns specify the <xref:System.Windows.Controls.ExceptionValidationRule> by setting the <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> property to `true`.</span></span>  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     <span data-ttu-id="ad9e0-113">사용자가 잘못 된 값 (예: 정수가 아닌 과정 ID 열에서)을 입력 셀 주위에 빨간색 테두리가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-113">When a user enters an invalid value (such as a non-integer in the Course ID column), a red border appears around the cell.</span></span> <span data-ttu-id="ad9e0-114">다음 절차에 설명 된 대로이 기본 유효성 검사 의견을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-114">You can change this default validation feedback as described in the following procedure.</span></span>  
  
### <a name="to-customize-cell-validation-feedback"></a><span data-ttu-id="ad9e0-115">셀 유효성 검사 피드백을 사용자 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="ad9e0-115">To customize cell validation feedback</span></span>  
  
- <span data-ttu-id="ad9e0-116">열 설정 <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> 열 편집 컨트롤에 대 한 스타일 속성 적절 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-116">Set the column's <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> property to a style appropriate for the column's editing control.</span></span> <span data-ttu-id="ad9e0-117">편집 컨트롤을 런타임에 생성 되므로 사용할 수 없습니다는 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> 간단한 컨트롤과 마찬가지로 속성을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-117">Because the editing controls are created at run time, you cannot use the <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> attached property like you would with simple controls.</span></span>  
  
     <span data-ttu-id="ad9e0-118">다음 예에서는 유효성 검사 규칙을 사용 하 여 세 개의 열을 기준으로 공유 하는 오류 스타일을 추가 하 여 앞의 예제를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-118">The following example updates the previous example by adding an error style shared by the three columns with validation rules.</span></span> <span data-ttu-id="ad9e0-119">사용자가 잘못 된 값을 입력 스타일 셀 배경색을 변경 하 고 도구 설명을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-119">When a user enters an invalid value, the style changes the cell background color and adds a ToolTip.</span></span> <span data-ttu-id="ad9e0-120">유효성 검사 오류가 있는지 여부를 확인 하는 트리거 사용을 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-120">Note the use of a trigger to determine whether there is a validation error.</span></span> <span data-ttu-id="ad9e0-121">현재 셀에 대 한 전용된 오류 템플릿이 있기 때문에 이것이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-121">This is required because there is currently no dedicated error template for cells.</span></span>  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     <span data-ttu-id="ad9e0-122">대체 하 여 보다 광범위 한 사용자 지정을 구현할 수 있습니다는 <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> 열을 기준으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-122">You can implement more extensive customization by replacing the <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> used by the column.</span></span>  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a><span data-ttu-id="ad9e0-123">단일 행에 여러 값의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ad9e0-123">To validate multiple values in a single row</span></span>  
  
1. <span data-ttu-id="ad9e0-124">구현 된 <xref:System.Windows.Controls.ValidationRule> 바인딩된 데이터 개체의 여러 속성을 확인 하는 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-124">Implement a <xref:System.Windows.Controls.ValidationRule> subclass that checks multiple properties of the bound data object.</span></span> <span data-ttu-id="ad9e0-125">사용자 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드 구현으로 캐스팅 합니다 `value` 매개 변수 값을를 <xref:System.Windows.Data.BindingGroup> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-125">In your <xref:System.Windows.Controls.ValidationRule.Validate%2A> method implementation, cast the `value` parameter value to a <xref:System.Windows.Data.BindingGroup> instance.</span></span> <span data-ttu-id="ad9e0-126">통해 데이터 개체에 액세스할 수 있습니다는 <xref:System.Windows.Data.BindingGroup.Items%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-126">You can then access the data object through the <xref:System.Windows.Data.BindingGroup.Items%2A> property.</span></span>  
  
     <span data-ttu-id="ad9e0-127">다음 예제에서는이 유효성 검사이 프로세스를 여부를 `StartDate` 속성 값을 `Course` 개체가 이전의 해당 `EndDate` 속성 값.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-127">The following example demonstrates this process to validate whether the `StartDate` property value for a `Course` object is earlier than its `EndDate` property value.</span></span>  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. <span data-ttu-id="ad9e0-128">유효성 검사 규칙을 추가 합니다 <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-128">Add the validation rule to the <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> collection.</span></span> <span data-ttu-id="ad9e0-129"><xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> 속성에 대 한 직접 액세스를 제공 합니다 <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> 의 속성을 <xref:System.Windows.Data.BindingGroup> 컨트롤에서 사용 하는 모든 바인딩이 그룹화 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-129">The <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> property provides direct access to the <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> property of a <xref:System.Windows.Data.BindingGroup> instance that groups all the bindings used by the control.</span></span>  
  
     <span data-ttu-id="ad9e0-130">다음 예제에서는 <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> XAML의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-130">The following example sets the <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> property in XAML.</span></span> <span data-ttu-id="ad9e0-131">합니다 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 속성이 <xref:System.Windows.Controls.ValidationStep.UpdatedValue> 바인딩된 데이터 개체를 업데이트 한 후에 유효성 검사가 수행 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-131">The <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> property is set to <xref:System.Windows.Controls.ValidationStep.UpdatedValue> so that the validation occurs only after the bound data object is updated.</span></span>  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     <span data-ttu-id="ad9e0-132">사용자 종료 날짜는 시작 날짜 보다 이전 인지를 지정 하는 경우 빨간색 느낌표 (!) 행 머리글에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-132">When a user specifies an end date that is earlier than the start date, a red exclamation mark (!) appears in the row header.</span></span> <span data-ttu-id="ad9e0-133">다음 절차에 설명 된 대로이 기본 유효성 검사 의견을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-133">You can change this default validation feedback as described in the following procedure.</span></span>  
  
### <a name="to-customize-row-validation-feedback"></a><span data-ttu-id="ad9e0-134">행 유효성 검사 피드백을 사용자 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="ad9e0-134">To customize row validation feedback</span></span>  
  
- <span data-ttu-id="ad9e0-135"><xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-135">Set the <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="ad9e0-136">이 속성을 사용 하면 개인에 대 한 행 유효성 검사 피드백을 사용자 지정할 수 있습니다 <xref:System.Windows.Controls.DataGrid> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-136">This property enables you to customize row validation feedback for individual <xref:System.Windows.Controls.DataGrid> controls.</span></span> <span data-ttu-id="ad9e0-137">암시적 행 스타일을 설정 하 여 여러 컨트롤에 영향을 줄 수도 있습니다는 <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-137">You can also affect multiple controls by using an implicit row style to set the <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     <span data-ttu-id="ad9e0-138">다음 예제에서는 기본 행 유효성 검사 의견을 더 잘 보이도록 표시기를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-138">The following example replaces the default row validation feedback with a more visible indicator.</span></span> <span data-ttu-id="ad9e0-139">사용자가 잘못 된 값을 입력 하는 경우 행 머리글에 흰색 느낌표가 있는 빨간색 원이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-139">When a user enters an invalid value, a red circle with a white exclamation mark appears in the row header.</span></span> <span data-ttu-id="ad9e0-140">이 행 및 셀 모두 유효성 검사 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-140">This occurs for both row and cell validation errors.</span></span> <span data-ttu-id="ad9e0-141">관련된 된 오류 메시지는 도구 설명에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-141">The associated error message is displayed in a ToolTip.</span></span>  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a><span data-ttu-id="ad9e0-142">예제</span><span class="sxs-lookup"><span data-stu-id="ad9e0-142">Example</span></span>  
 <span data-ttu-id="ad9e0-143">다음 예에서는 셀 및 행 유효성 검사의 전체 데모를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-143">The following example provides a complete demonstration for cell and row validation.</span></span> <span data-ttu-id="ad9e0-144">합니다 `Course` 클래스를 구현 하는 샘플 데이터 개체를 제공 합니다. <xref:System.ComponentModel.IEditableObject> 트랜잭션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-144">The `Course` class provides a sample data object that implements <xref:System.ComponentModel.IEditableObject> to support transactions.</span></span> <span data-ttu-id="ad9e0-145">합니다 <xref:System.Windows.Controls.DataGrid> 컨트롤이와 상호 작용 <xref:System.ComponentModel.IEditableObject> 사용자가 ESC 키를 눌러 변경 내용이 되돌릴 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-145">The <xref:System.Windows.Controls.DataGrid> control interacts with <xref:System.ComponentModel.IEditableObject> to enable users to revert changes by pressing ESC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad9e0-146">Visual Basic의 경우 MainWindow.xaml의 첫 번째 줄을 사용 하는 경우 대체 `x:Class="DataGridValidation.MainWindow"` 사용 하 여 `x:Class="MainWindow"`입니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-146">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridValidation.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
 <span data-ttu-id="ad9e0-147">유효성 검사를 테스트 하려면 다음을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-147">To test the validation, try the following:</span></span>  
  
- <span data-ttu-id="ad9e0-148">강좌 ID 열에는 정수가 아닌 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-148">In the Course ID column, enter a non-integer value.</span></span>  
  
- <span data-ttu-id="ad9e0-149">종료 날짜 열에는 시작 날짜 보다 이전 날짜를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-149">In the End Date column, enter a date that is earlier than the Start Date.</span></span>  
  
- <span data-ttu-id="ad9e0-150">과정 ID, 시작 날짜 또는 종료 날짜의 값을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-150">Delete the value in Course ID, Start Date, or End Date.</span></span>  
  
- <span data-ttu-id="ad9e0-151">잘못 된 셀 값을 실행 취소, 다시 셀에에서 커서를 놓고 및 ESC 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-151">To undo an invalid cell value, put the cursor back in the cell and press the ESC key.</span></span>  
  
- <span data-ttu-id="ad9e0-152">현재 셀이 편집 모드일 때 전체 행에 대 한 변경 내용을 실행 취소 하려면 ESC 키를 두 번 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-152">To undo changes for an entire row when the current cell is in edit mode, press the ESC key twice.</span></span>  
  
- <span data-ttu-id="ad9e0-153">유효성 검사 오류가 발생 하면 관련된 된 오류 메시지를 보려면 행 머리글의 표시기 위로 마우스 포인터를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9e0-153">When a validation error occurs, move your mouse pointer over the indicator in the row header to see the associated error message.</span></span>  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="ad9e0-154">참고자료</span><span class="sxs-lookup"><span data-stu-id="ad9e0-154">See also</span></span>

- <xref:System.Windows.Controls.DataGrid>
- [<span data-ttu-id="ad9e0-155">DataGrid</span><span class="sxs-lookup"><span data-stu-id="ad9e0-155">DataGrid</span></span>](datagrid.md)
- [<span data-ttu-id="ad9e0-156">데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="ad9e0-156">Data Binding</span></span>](../data/data-binding-wpf.md)
- [<span data-ttu-id="ad9e0-157">바인딩 유효성 검사 구현</span><span class="sxs-lookup"><span data-stu-id="ad9e0-157">Implement Binding Validation</span></span>](../data/how-to-implement-binding-validation.md)
- [<span data-ttu-id="ad9e0-158">사용자 지정 개체의 유효성 검사 논리 구현</span><span class="sxs-lookup"><span data-stu-id="ad9e0-158">Implement Validation Logic on Custom Objects</span></span>](../data/how-to-implement-validation-logic-on-custom-objects.md)
