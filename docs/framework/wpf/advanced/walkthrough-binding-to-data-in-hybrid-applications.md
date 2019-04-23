---
title: '연습: 하이브리드 애플리케이션에서 데이터에 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: f6fd1f2f5d0a729ee5610b81d4bfdca052a6e01e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300868"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a>연습: 하이브리드 애플리케이션에서 데이터에 바인딩
사용 하 여 기본 데이터에 대 한 액세스를 사용 하 여 사용자에 게 제공 하는 데 필수적입니다 데이터 소스 컨트롤에 바인딩 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 또는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다. 이 연습에서는 모두 포함 하는 하이브리드 응용 프로그램에서 데이터 바인딩을 사용 하는 방법을 보여 줍니다 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤입니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   프로젝트 만들기.  
  
-   데이터 템플릿 정의  
  
-   폼 레이아웃 지정  
  
-   데이터 바인딩 지정  
  
-   상호 운용성을 사용하여 데이터 표시  
  
-   프로젝트에 데이터 소스 추가  
  
-   데이터 소스에 바인딩  
  
 이 연습에 설명 된 작업의 전체 코드 목록은 참조 하세요 [하이브리드 응용 프로그램 샘플의 데이터 바인딩](https://go.microsoft.com/fwlink/?LinkID=159983)합니다.  
  
 작업을 완료하면 혼합 애플리케이션의 데이터 바인딩 기능을 이해하게 됩니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   Visual Studio.  
  
-   Microsoft SQL Server에서 실행 되는 Northwind 샘플 데이터베이스에 액세스 합니다.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
  
#### <a name="to-create-and-set-up-the-project"></a>프로젝트를 만들고 설정하려면  
  
1. 이라는 WPF 응용 프로그램 프로젝트를 만듭니다 `WPFWithWFAndDatabinding`합니다.  
  
2. 솔루션 탐색기에서 다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3. MainWindow.xaml을 엽니다는 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]합니다.  
  
4. 에 <xref:System.Windows.Window> 요소를 다음 추가 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 네임 스페이스 매핑.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. 기본 이름을 <xref:System.Windows.Controls.Grid> 요소 `mainGrid` 할당 하 여는 <xref:System.Windows.FrameworkElement.Name%2A> 속성입니다.  
  
     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]  
  
## <a name="defining-the-data-template"></a>데이터 템플릿 정의  
 고객의 마스터 목록에 표시 됩니다는 <xref:System.Windows.Controls.ListBox> 제어 합니다. 다음 코드 예제에서는 정의 <xref:System.Windows.DataTemplate> 개체인 `ListItemsTemplate` 의 시각적 트리를 제어 하는 <xref:System.Windows.Controls.ListBox> 제어 합니다. 이렇게 <xref:System.Windows.DataTemplate> 에 할당 되는 <xref:System.Windows.Controls.ListBox> 컨트롤의 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 속성.  
  
#### <a name="to-define-the-data-template"></a>데이터 템플릿을 정의하려면  
  
-   에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소의 선언 합니다.  
  
     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]  
  
## <a name="specifying-the-form-layout"></a>폼 레이아웃 지정  
 폼의 레이아웃은 세 개의 행과 세 개의 열이 있는 그리드로 정의됩니다. <xref:System.Windows.Controls.Label> Customers 테이블의 각 열을 식별 하는 컨트롤이 제공 됩니다.  
  
#### <a name="to-set-up-the-grid-layout"></a>그리드 레이아웃을 설정하려면  
  
-   에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소의 선언 합니다.  
  
     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]  
  
#### <a name="to-set-up-the-label-controls"></a>레이블 컨트롤을 설정하려면  
  
-   에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소의 선언 합니다.  
  
     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]  
  
## <a name="specifying-data-bindings"></a>데이터 바인딩 지정  
 고객의 마스터 목록에 표시 됩니다는 <xref:System.Windows.Controls.ListBox> 제어 합니다. 연결 된 `ListItemsTemplate` 바인딩하는 <xref:System.Windows.Controls.TextBlock> 컨트롤을 `ContactName` 데이터베이스에서 필드입니다.  
  
 몇 개에 각 고객 레코드의 세부 정보가 표시 됩니다 <xref:System.Windows.Controls.TextBox> 컨트롤입니다.  
  
#### <a name="to-specify-data-bindings"></a>데이터 바인딩을 지정하려면  
  
-   에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소의 선언 합니다.  
  
     합니다 <xref:System.Windows.Data.Binding> 바인딩합니다 클래스는 <xref:System.Windows.Controls.TextBox> 컨트롤을 데이터베이스에서 적절 한 필드입니다.  
  
     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]  
  
## <a name="displaying-data-by-using-interoperation"></a>상호 운용성을 사용하여 데이터 표시  
 에 선택한 고객과 해당 주문을 표시 되는 <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> 라는 컨트롤 `dataGridView1`합니다. `dataGridView1` 코드 숨김 파일에서 데이터 원본에 바인딩된 컨트롤입니다. A <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤의 부모인 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 제어 합니다.  
  
#### <a name="to-display-data-in-the-datagridview-control"></a>DataGridView 컨트롤에 데이터를 표시하려면  
  
-   에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소의 선언 합니다.  
  
     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]  
  
## <a name="adding-the-data-source-to-the-project"></a>프로젝트에 데이터 소스 추가  
 Visual Studio를 사용 하 여 프로젝트에 데이터 소스를 쉽게 추가할 수 있습니다. 이 절차에서는 강력한 형식의 데이터 집합을 프로젝트에 추가합니다. 선택한 각 테이블에 대한 테이블 어댑터 같은 여러 가지 다른 지원 클래스도 추가됩니다.  
  
#### <a name="to-add-the-data-source"></a>데이터 소스를 추가하려면  
  
1. **데이터** 메뉴에서 **새 데이터 소스 추가**합니다.  
  
2. 에 **데이터 소스 구성 마법사**, 데이터 집합을 사용 하 여 Northwind 데이터베이스에 대 한 연결을 만듭니다. 자세한 내용은 [방법: 데이터베이스의 데이터에에서 연결할](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))합니다.  
  
3. 메시지가 나타나면 합니다 **데이터 소스 구성 마법사**, 연결 문자열을 저장 `NorthwindConnectionString`합니다.  
  
4. 데이터베이스 개체를 선택 하 라는 메시지가 표시 됩니다, 선택는 `Customers` 하 고 `Orders` 테이블과 생성 된 데이터 집합 이름 `NorthwindDataSet`합니다.  
  
## <a name="binding-to-the-data-source"></a>데이터 소스에 바인딩  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> 구성 요소는 응용 프로그램의 데이터 원본에 대 한 일관 된 인터페이스를 제공 합니다. 데이터 소스에 바인딩은 코드 숨김 파일에서 구현됩니다.  
  
#### <a name="to-bind-to-the-data-source"></a>데이터 소스에 바인딩하려면  
  
1. MainWindow.xaml.vb 또는 MainWindow.xaml.cs라는 코드 숨김 파일을 엽니다.  
  
2. 다음 코드를 복사 합니다 `MainWindow` 클래스 정의 합니다.  
  
     이 코드는 선언 된 <xref:System.Windows.Forms.BindingSource> 구성 요소 및 데이터베이스에 연결 하는 연관 된 도우미 클래스입니다.  
  
     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. 다음 코드를 생성자에 복사합니다.

     이 코드를 만들고 초기화 된 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. MainWindow.xaml을 엽니다.

5. 디자인 뷰 또는 XAML 뷰에서 선택 된 <xref:System.Windows.Window> 요소입니다.

6. 속성 창에서 클릭 합니다 **이벤트** 탭 합니다.

7. 두 번 클릭 하 여 <xref:System.Windows.FrameworkElement.Loaded> 이벤트입니다.

8. 다음 코드를 복사 합니다 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기입니다.

     이 코드에서는 할당 합니다 <xref:System.Windows.Forms.BindingSource> 데이터 컨텍스트로 서 구성 요소 채웁니다 합니다 `Customers` 및 `Orders` 어댑터 개체입니다.

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. 다음 코드를 복사 합니다 `MainWindow` 클래스 정의 합니다.

     이 메서드를 처리 합니다 <xref:System.Windows.Data.CollectionView.CurrentChanged> 이벤트 및 데이터 바인딩의 현재 항목을 업데이트 합니다.

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]  
  
10. F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Visual Studio에서 XAML 디자인](/visualstudio/designers/designing-xaml-in-visual-studio)
- [하이브리드 응용 프로그램 샘플에서 데이터 바인딩](https://go.microsoft.com/fwlink/?LinkID=159983)
- [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
