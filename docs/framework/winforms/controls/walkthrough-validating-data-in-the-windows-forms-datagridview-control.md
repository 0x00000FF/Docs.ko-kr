---
title: "연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사"
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
helpviewer_keywords:
- validating data [Windows Forms], Windows Forms
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b460afb393c1b88b34281a8db1b61203e5c5962
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사
사용자에 게 데이터 입력 기능을 표시할 때 자주 폼에 입력 된 데이터의 유효성을 검사 해야 합니다. <xref:System.Windows.Forms.DataGridView> 클래스 데이터가 데이터 저장소에 커밋되기 전에 유효성 검사를 수행 하는 편리한 방법을 제공 합니다. 처리 하 여 데이터를 확인할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.CellValidating> 이벤트에 의해 발생 하는 <xref:System.Windows.Forms.DataGridView> 현재 셀이 변경 합니다.  
  
 이 연습에서는 행을 검색 합니다는 `Customers` Northwind 샘플 데이터베이스의 테이블을 표시 한 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 사용자가 셀을 편집 하는 경우는 `CompanyName` 열 벗어나려 고 할 셀을는 <xref:System.Windows.Forms.DataGridView.CellValidating> 이벤트 처리기에서는 새 회사 이름 문자열 인지 확인; 비어 있지 않은 경우 새 값이 빈 문자열을 검사 하 고 <xref:System.Windows.Forms.DataGridView> 사용자의 커서 수 없게 됩니다 비어 있지 않은 문자열이 입력 될 때까지 해당 셀에 유지 합니다.  
  
 단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md)합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind SQL Server 예제 데이터베이스에 있는 서버에 액세스 합니다.  
  
## <a name="creating-the-form"></a>폼 만들기  
  
#### <a name="to-validate-data-entered-in-a-datagridview"></a>DataGridView에 입력 된 데이터의 유효성을 검사 하려면  
  
1.  파생 되는 클래스를 만듭니다 <xref:System.Windows.Forms.Form> 포함 한 <xref:System.Windows.Forms.DataGridView> 제어 및 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.  
  
     다음 코드 예제에서는 기본 초기화를 제공 하 고 포함 된 `Main` 메서드.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]  
  
2.  폼의 클래스 정의 처리 하는 데이터베이스에 대 한 연결 정보에는 메서드를 구현 합니다.  
  
     사용 하 여이 코드 예제는 `GetData` 채워진 반환 하는 메서드 <xref:System.Data.DataTable> 개체입니다. 설정 하는 `connectionString` 변수를 사용 중인 데이터베이스에 대 한 적합 한 값입니다.  
  
    > [!IMPORTANT]
    >  암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다. Windows 인증을 라고도 통합된 보안을 사용 하는 데이터베이스에 대 한 액세스를 제어 하는 방법이 더 안전 합니다. 자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)를 참조하세요.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]  
  
3.  폼의에 대 한 처리기를 구현 <xref:System.Windows.Forms.Form.Load> 초기화 하는 이벤트는 <xref:System.Windows.Forms.DataGridView> 및 <xref:System.Windows.Forms.BindingSource> 데이터 바인딩을 가져오거나 설정 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]  
  
4.  구현에 대 한 처리기는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellValidating> 및 <xref:System.Windows.Forms.DataGridView.CellEndEdit> 이벤트입니다.  
  
     <xref:System.Windows.Forms.DataGridView.CellValidating> 결정할 수 있는 이벤트 처리기가 있는지 여부를에 있는 셀의 값은 `CompanyName` 열이 비어 있습니다. 셀 값 유효성 검사에 실패 하면 설정 된 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성은 <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> 클래스를 `true`합니다. 이 인해는 <xref:System.Windows.Forms.DataGridView> 커서 셀을 종료 하지 못하도록 방지 하기 위해 컨트롤입니다. 설정의 <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> 설명 문자열로 행에는 속성입니다. 오류 텍스트를 포함 하는 도구 설명에 오류 아이콘이 표시 됩니다. 에 <xref:System.Windows.Forms.DataGridView.CellEndEdit> 이벤트 처리기를 설정의 <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> 속성을 빈 문자열로 행에 있습니다. <xref:System.Windows.Forms.DataGridView.CellEndEdit> 셀 유효성 검사가 실패 없는 편집 모드를 종료 하는 경우에 이벤트가 발생 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
 이제 예상 대로 동작 되도록 폼을 테스트할 수 있습니다.  
  
#### <a name="to-test-the-form"></a>양식을 테스트 하려면  
  
-   응용 프로그램을 컴파일하고 실행합니다.  
  
     표시 됩니다는 <xref:System.Windows.Forms.DataGridView> 의 데이터로 채워진는 `Customers` 테이블입니다. 셀에 두 번 클릭은 `CompanyName` 열에서 값을 편집할 수 있습니다. 모든 문자를 삭제 하 고 셀을 종료 하려면 TAB 키 누르면는 <xref:System.Windows.Forms.DataGridView> 에서 종료할 수 없습니다. 셀에는 비어 있지 않은 문자열을 입력 하는 경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤 셀을 끝낼 수 있습니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 응용 프로그램에서는 기본적으로 이해는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기능입니다. 모양 및 동작을 사용자 지정할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 여러 가지 방법으로 제어 합니다.  
  
-   테두리 및 머리글 스타일을 변경 합니다. 자세한 내용은 참조 [하는 방법: 테두리 및 눈금선 스타일 Windows Forms DataGridView 컨트롤에서 변경](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)합니다.  
  
-   사용 하거나 사용자 입력을 제한 된 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 자세한 내용은 참조 [하는 방법: 행 추가 및 삭제 금지 Windows Forms DataGridView 컨트롤에서](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), 및 [하는 방법: 열을 읽기 전용 Windows Forms DataGridView 컨트롤에서](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)합니다.  
  
-   데이터베이스 관련 오류에 대 한 사용자 입력을 확인 합니다. 자세한 내용은 참조 [연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생 하는 오류 처리](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)합니다.  
  
-   가상 모드를 사용 하 여 매우 큰 데이터 집합을 처리 합니다. 자세한 내용은 참조 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)합니다.  
  
-   셀의 모양을 사용자 지정 합니다. 자세한 내용은 참조 [하는 방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) 및 [하는 방법: 글꼴 설정 및 Windows Forms DataGridView 컨트롤에서 색 스타일](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Windows Forms DataGridView 컨트롤의 데이터 입력](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [방법: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md)  
 [연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)
