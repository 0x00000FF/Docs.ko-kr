---
title: '방법: Windows Forms DataGridView 컨트롤에서 동작 및 모양을 확장하여 셀과 열 사용자 지정'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell customization
- columns [Windows Forms], customizing in DataGridView control
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 9b7dc7b6-5ce6-4566-9949-902f74f17a81
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e48c5d451b4eece1bd88916e33f6a61d646b7fa
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-customize-cells-and-columns-in-the-windows-forms-datagridview-control-by-extending-their-behavior-and-appearance"></a>방법: Windows Forms DataGridView 컨트롤에서 동작 및 모양을 확장하여 셀과 열 사용자 지정
<xref:System.Windows.Forms.DataGridView> 컨트롤은 속성, 이벤트 및 도우미 클래스를 통해 모양과 동작을 사용자 지정하는 다양한 방법을 제공합니다. 경우에 따라 해당 셀에 대해 이러한 기능으로 충족할 수 없는 요구 사항이 있을 수 있습니다. 고유한 사용자 지정 <xref:System.Windows.Forms.DataGridViewCell> 클래스를 만들어 확장 기능을 제공할 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridViewCell> 기본 클래스 또는 파생 클래스 중 하나에서 파생시켜 사용자 지정 <xref:System.Windows.Forms.DataGridViewCell> 클래스를 만듭니다. 모든 유형의 열에 모든 유형의 셀을 표시할 수 있지만 일반적으로 셀 형식을 표시하기 위한 사용자 지정 <xref:System.Windows.Forms.DataGridViewColumn> 클래스도 만듭니다. 열 클래스는 <xref:System.Windows.Forms.DataGridViewColumn> 또는 파생 형식 중 하나에서 파생됩니다.  
  
 다음 코드 예제에서는 마우스가 셀 경계로 들어오고 나갈 때 이를 감지하는 `DataGridViewRolloverCell`이라는 사용자 지정 셀 클래스를 만듭니다. 마우스가 셀 범위 내에 있는 동안 삽입 사각형이 그려집니다. 이 새로운 형식은 <xref:System.Windows.Forms.DataGridViewTextBoxCell>에서 파생되며 다른 모든 측면에서 기본 클래스처럼 동작합니다. 도우미 열 클래스는 `DataGridViewRolloverColumn`이라고 합니다.  
  
 이러한 클래스를 사용하려면 <xref:System.Windows.Forms.DataGridView> 컨트롤이 포함된 폼을 만들고 하나 이상의 `DataGridViewRolloverColumn` 개체를 <xref:System.Windows.Forms.DataGridView.Columns%2A> 컬렉션에 추가한 다음 값이 포함된 행으로 컨트롤을 채웁니다.  
  
> [!NOTE]
>  빈 행을 추가하는 경우에는 이 예제가 제대로 작동하지 않습니다. 예를 들어 <xref:System.Windows.Forms.DataGridView.RowCount%2A> 속성을 설정하여 컨트롤에 행을 추가할 때 빈 행이 만들어집니다. 이러한 경우에 추가된 행이 자동으로 공유되기 때문이며, 이는 개별 셀을 클릭하여 연결된 행이 공유되지 않도록 할 때까지 `DataGridViewRolloverCell` 개체가 인스턴스화되지 않음을 의미합니다.  
  
 이 형식의 셀 사용자 지정에는 공유되지 않는 행이 필요하므로 큰 데이터 집합에 사용하기에 적합하지 않습니다. 행 공유에 대 한 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 크기 조정에 대 한 유용한](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridViewCell> 또는 <xref:System.Windows.Forms.DataGridViewColumn>에서 파생시키고 파생 클래스에 새 속성을 추가하는 경우 복제 작업 중 새 속성을 복사하도록 `Clone` 메서드를 재정의해야 합니다. 또한 기본 클래스의 속성이 새로운 셀 또는 열에 복사되도록 기본 클래스의 `Clone` 메서드를 호출해야 합니다.  
  
### <a name="to-customize-cells-and-columns-in-the-datagridview-control"></a>DataGridView 컨트롤에서 셀과 열을 사용자 지정하려면  
  
1.  <xref:System.Windows.Forms.DataGridViewTextBoxCell> 형식에서 `DataGridViewRolloverCell`이라는 새로운 셀 클래스를 파생시킵니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#201)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#201)]  
    [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#202](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#202)]
    [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#202](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#202)]  
  
2.  <xref:System.Windows.Forms.DataGridViewTextBoxCell.Paint%2A> 클래스에서 `DataGridViewRolloverCell` 메서드를 재정의합니다. 재정의에서 먼저 호스트된 텍스트 상자 기능을 처리하는 기본 클래스 구현을 호출합니다. 그런 다음 컨트롤의 <xref:System.Windows.Forms.Control.PointToClient%2A> 메서드를 사용하여 커서 위치(화면 좌표)를 <xref:System.Windows.Forms.DataGridView> 클라이언트 영역 좌표로 변환합니다. 마우스 좌표가 셀 범위에 속하는 경우 삽입 사각형을 그립니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#210](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#210)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#210](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#210)]  
  
3.  `DataGridViewRolloverCell` 클래스의 <xref:System.Windows.Forms.DataGridViewCell.OnMouseEnter%2A> 및 <xref:System.Windows.Forms.DataGridViewCell.OnMouseLeave%2A> 메서드를 재정의하여 마우스 포인터가 들어가거나 나올 때 셀이 자동으로 그려지도록 강제합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#220)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#220)]  
  
4.  <xref:System.Windows.Forms.DataGridViewColumn> 형식에서 `DataGridViewRolloverCellColumn`이라는 새 클래스를 파생시킵니다. 생성자에서 해당 <xref:System.Windows.Forms.DataGridViewColumn.CellTemplate%2A> 속성에 새 `DataGridViewRolloverCell` 개체를 할당합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#300)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#300)]  
  
## <a name="example"></a>예제  
 전체 코드 예제에는 사용자 지정 셀 형식의 동작을 보여 주는 작은 테스트 폼이 포함되어 있습니다.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#000)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Windows.Forms 및 System.Drawing 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [DataGridView 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)
