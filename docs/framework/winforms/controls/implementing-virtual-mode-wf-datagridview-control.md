---
title: '연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 7f6bf1703a6536f4d22b3a2fbe412579c59d39dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973773"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="34db1-102">연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현</span><span class="sxs-lookup"><span data-stu-id="34db1-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="34db1-103">매우 많은 양의의 표 형식 데이터를 표시 하려는 경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 설정할 수 있습니다 합니다 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성을 `true` 명시적으로 해당 데이터 저장소를 사용 하 여 컨트롤의 상호 작용을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="34db1-104">이렇게 하면이 상황에서 컨트롤의 성능을 미세 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="34db1-105"><xref:System.Windows.Forms.DataGridView> 컨트롤 사용자 지정 데이터 저장소와 상호 작용을 처리할 수 있는 몇 가지 이벤트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="34db1-106">이 연습에서는 이러한 이벤트 처리기를 구현 하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="34db1-107">이 항목의 코드 예제에서는 이해를 돕기 위해 매우 간단한 데이터 소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="34db1-108">프로덕션 설정에서 일반적으로 로드 하려는 캐시에 표시 하 고 처리 해야 하는 행만 <xref:System.Windows.Forms.DataGridView> 캐시 업데이트와 상호 작용 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="34db1-109">자세한 내용은 참조 하세요. [Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드 사용 하 여 가상 모드 구현](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span><span class="sxs-lookup"><span data-stu-id="34db1-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="34db1-110">이 항목의 코드를 단일 목록으로 복사하려면 [방법: Windows에서 가상 모드 구현 Forms DataGridView 컨트롤](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="34db1-111">폼 만들기</span><span class="sxs-lookup"><span data-stu-id="34db1-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="34db1-112">가상 모드 구현</span><span class="sxs-lookup"><span data-stu-id="34db1-112">To implement virtual mode</span></span>  
  
1. <span data-ttu-id="34db1-113">파생 되는 클래스를 만듭니다 <xref:System.Windows.Forms.Form> 개와 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="34db1-114">다음 코드는 몇 가지 기본 초기화를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="34db1-115">이후 단계에서 사용할 몇 가지 변수 선언, 제공을 `Main` 메서드를 클래스 생성자에서 간단한 폼 레이아웃을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. <span data-ttu-id="34db1-116">폼의 처리기를 구현 <xref:System.Windows.Forms.Form.Load> 초기화 하는 이벤트를 <xref:System.Windows.Forms.DataGridView> 제어 하 고 샘플 값을 사용 하 여 데이터 저장소를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. <span data-ttu-id="34db1-117">에 대 한 처리기를 구현 합니다 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 데이터 저장소에서 요청된 된 셀 값을 검색 하는 이벤트 또는 `Customer` 편집에서 현재 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="34db1-118">이 이벤트가 발생할 때마다는 <xref:System.Windows.Forms.DataGridView> 셀 그리기를 제어 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. <span data-ttu-id="34db1-119">에 대 한 처리기를 구현 합니다 <xref:System.Windows.Forms.DataGridView.CellValuePushed> 에서 편집된 셀 값을 저장 하는 이벤트를 `Customer` 편집된 된 행을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="34db1-120">이 이벤트는 사용자 커밋 셀 값이 변경 될 때마다 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. <span data-ttu-id="34db1-121">에 대 한 처리기를 구현 합니다 <xref:System.Windows.Forms.DataGridView.NewRowNeeded> 새로 만든 이벤트 `Customer` 새로 만든된 행을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="34db1-122">이 이벤트는 사용자가 새 레코드에 대 한 행을 입력할 때마다 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. <span data-ttu-id="34db1-123">에 대 한 처리기를 구현 합니다 <xref:System.Windows.Forms.DataGridView.RowValidated> 데이터 저장소로 새롭거나 수정 된 행을 저장 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="34db1-124">이 이벤트는 사용자는 현재 행이 변경 될 때마다 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. <span data-ttu-id="34db1-125">에 대 한 처리기를 구현 합니다 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 나타내는 이벤트 여부를 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> 사용자 행의 편집 모드에 두 번 또는 한 번 편집 모드 외부 ESC 키를 눌러 신호를 보낼 때 이벤트가 발생 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="34db1-126">기본적으로 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> 경우가 아니면 수정 된 현재 행에서 셀 있을 때 행의 버전을 변경 시 발생 합니다 <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> 속성이로 설정 되어 `true` 에 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 이벤트 처리기.</span><span class="sxs-lookup"><span data-stu-id="34db1-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="34db1-127">이 이벤트는 커밋 범위 런타임 시 결정 되는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. <span data-ttu-id="34db1-128">에 대 한 처리기를 구현 합니다 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> 의 값을 삭제 하는 이벤트를 `Customer` 현재 행을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="34db1-129">이 이벤트는 사용자 행의 편집 모드에 두 번 또는 한 번 편집 모드 외부 ESC 키를 눌러 신호를 보낼 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="34db1-130">경우 또는 현재 행에서 셀을 수정한 경우이 이벤트가 발생 하지 않습니다 값을 <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> 속성 설정한 `false` 에 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="34db1-131">처리기를 구현 합니다 <xref:System.Windows.Forms.DataGridView.UserDeletingRow> 기존를 삭제 하는 이벤트 `Customer` 데이터 저장소에서 개체는 저장 되지 않은 삭제 또는 `Customer` 새로 생성된 된 행을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="34db1-132">이 이벤트는 사용자 행 머리글을 클릭 하 고 DELETE 키를 눌러 행을 삭제 될 때마다 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="34db1-133">간단한 구현 `Customers` 이 코드 예제에서 사용 하는 데이터 항목을 나타내는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="34db1-134">애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="34db1-134">Testing the Application</span></span>  
 <span data-ttu-id="34db1-135">이제 예상 대로 작동 되도록 폼을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="34db1-136">폼을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="34db1-136">To test the form</span></span>  
  
- <span data-ttu-id="34db1-137">애플리케이션을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="34db1-138">표시 됩니다는 <xref:System.Windows.Forms.DataGridView> 컨트롤 세 고객 레코드를 사용 하 여 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="34db1-139">여러 행에 있는 셀의 값을 수정할 수 있으며 편집 모드에 두 번 및 한 번 전체 행을 원래 값으로 되돌리려면 편집 모드 외부 ESC 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="34db1-140">수정, 추가 또는 컨트롤에서 행을 삭제 하는 경우 `Customer` 데이터 저장소의 개체는 수정, 추가 또는 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="34db1-141">다음 단계</span><span class="sxs-lookup"><span data-stu-id="34db1-141">Next Steps</span></span>  
 <span data-ttu-id="34db1-142">이 응용 프로그램의 가상 모드 구현 하려면 처리 해야 하는 이벤트에 대 한 기본적인 이해를 제공 합니다 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="34db1-143">다양 한 방법으로에서이 기본 응용 프로그램을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-143">You can improve this basic application in a number of ways:</span></span>  
  
- <span data-ttu-id="34db1-144">외부 데이터베이스에서 값을 캐시 하는 데이터 저장소를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="34db1-145">캐시를 검색 하 고 클라이언트 컴퓨터에서 적은 양의 메모리를 사용 하는 동안 표시 하기 위해 필요한 것만 포함 되도록 필요에 따라 값을 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
- <span data-ttu-id="34db1-146">요구 사항에 따라 데이터 저장소의 성능을 미세 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="34db1-147">예를 들어, 다음 더 큰 캐시 크기를 사용 하 고 데이터베이스 쿼리의 수를 최소화 하 여 클라이언트 컴퓨터 메모리 제한 보다는 느린 네트워크 연결에 대 한 보정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="34db1-148">외부 데이터베이스에서 값을 캐시 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: Forms DataGridView 컨트롤의 Windows에서-Just-in-time 데이터 로드를 사용 하 여 가상 모드 구현](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="34db1-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34db1-149">참고자료</span><span class="sxs-lookup"><span data-stu-id="34db1-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="34db1-150">Windows Forms DataGridView 컨트롤의 성능 조정</span><span class="sxs-lookup"><span data-stu-id="34db1-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="34db1-151">Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="34db1-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="34db1-152">Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현</span><span class="sxs-lookup"><span data-stu-id="34db1-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="34db1-153">방법: Windows Forms DataGridView 컨트롤에서 가상 모드 구현</span><span class="sxs-lookup"><span data-stu-id="34db1-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
