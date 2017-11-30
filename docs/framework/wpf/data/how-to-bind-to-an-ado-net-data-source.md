---
title: "방법: ADO.NET 데이터 소스 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0eb555bb9f21385d2d0b66fe0dd39112c8350dec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-an-adonet-data-source"></a>방법: ADO.NET 데이터 소스 바인딩
바인딩하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> 컨트롤을 한 [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`합니다.  
  
## <a name="example"></a>예제  
 이 예에서는 `OleDbConnection` 개체를 사용하여 연결 문자열에 지정된 `Access MDB` 파일인 데이터 소스에 연결합니다. 연결이 설정되고 나면 `OleDbDataAdpater` 개체가 생성됩니다. `OleDbDataAdpater` 개체는 select [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] 명령문을 실행하여 데이터베이스에서 레코드 집합을 검색합니다. [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] 명령의 결과는 `OleDbDataAdapter`의 `Fill` 메서드를 호출하여 `DataSet`의 `DataTable`에 저장됩니다. 이 예에서 `DataTable`은 `BookTable`로 이름이 지정됩니다. 설정한 후는 <xref:System.Windows.FrameworkElement.DataContext%2A> 의 속성은 <xref:System.Windows.Controls.ListBox> 에 `DataSet` 개체입니다.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 그런 다음 바인딩할 수는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 의 속성은 <xref:System.Windows.Controls.ListBox> 를 `BookTable` 의 `DataSet`:  
  
 [!code-xaml[ADODataSet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]  
  
 `BookItemTemplate`이 <xref:System.Windows.DataTemplate> 데이터가 표시 되는 방식을 정의 하는 합니다.  
  
 [!code-xaml[ADODataSet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]  
  
 `IntColorConverter`는 `int`를 색상으로 변환합니다. 이 변환기를 사용 하 여는 <xref:System.Windows.Controls.TextBlock.Background%2A> 의 <xref:System.Windows.Controls.TextBlock> 녹색 표시 하는 경우의 값 `NumPages` 는 보다 작은 350 하 고 빨간색 그렇지 않으면입니다. 변환기의 구현은 여기에 표시되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Data.BindingListCollectionView>  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
