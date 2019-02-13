---
title: UI 자동화를 사용하여 표의 콘텐츠 노출
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables, exposing content of
- UI Automation, exposing content of tables
- exposing content of tables using UI Automation
ms.assetid: ac3c5eaa-49c7-4653-b83e-532e2a2604a2
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 2145888b76077056988652418fd1eab878348258
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219349"
---
# <a name="expose-the-content-of-a-table-using-ui-automation"></a>UI 자동화를 사용하여 표의 콘텐츠 노출
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. 에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.  
  
 이 항목에서는 어떻게 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 테이블 형식 컨트롤 내에 있는 각 셀의 콘텐츠 및 내장 속성 노출 데 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 가져오는 방법을 보여 줍니다는 <xref:System.Windows.Automation.AutomationElement> 테이블 셀의 내용을 나타내는; 행 및 열 인덱스, 행 및 열 범위, 행 및 열 헤더 정보 등의 셀 속성은 가져올 수도 있습니다. 이 예에서는 포커스 변경 이벤트 처리기를 구현 하는 테이블 형식 컨트롤의 키보드 탐색을 시뮬레이션 하기 위해 사용 하 여 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]입니다. 각 테이블 항목에 대 한 정보를 포커스 변경 이벤트에 노출 됩니다.  
  
> [!NOTE]
>  포커스가 변경 전역 데스크톱 이벤트 되므로 테이블 외부 포커스 변경 이벤트를 필터링 해야 합니다. 참조 된 [TrackFocus 샘플](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771428(v=vs.90)) 관련된 구현에 대 한 합니다.  
  
 [!code-csharp[UIATableItemPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#starttarget)]
 [!code-vb[UIATableItemPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#starttarget)]  
[!code-csharp[UIATableItemPattern_snip#GetTableElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#gettableelement)]
[!code-vb[UIATableItemPattern_snip#GetTableElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#gettableelement)]  
[!code-csharp[UIATableItemPattern_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#101)]
[!code-vb[UIATableItemPattern_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#101)]  
[!code-csharp[UIATableItemPattern_snip#1015](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#1015)]
[!code-vb[UIATableItemPattern_snip#1015](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#1015)]  
[!code-csharp[UIATableItemPattern_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#102)]
[!code-vb[UIATableItemPattern_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#102)]  
[!code-csharp[UIATableItemPattern_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#103)]
[!code-vb[UIATableItemPattern_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#103)]  
  
## <a name="see-also"></a>참고자료
- [UI 자동화 컨트롤 패턴 개요](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [클라이언트용 UI 자동화 컨트롤 패턴](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [UI 자동화 Table 컨트롤 패턴 구현](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)
- [UI 자동화 TableItem 컨트롤 패턴 구현](../../../docs/framework/ui-automation/implementing-the-ui-automation-tableitem-control-pattern.md)
- [UI 자동화 Grid 컨트롤 패턴 구현](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)
- [UI 자동화 GridItem 컨트롤 패턴 구현](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)
