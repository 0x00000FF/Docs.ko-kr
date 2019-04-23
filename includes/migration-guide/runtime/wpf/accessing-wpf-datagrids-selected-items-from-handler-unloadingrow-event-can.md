---
ms.openlocfilehash: cda5df4b673412a7c8c59f80f89c19c13dc81dc1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804538"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a>DataGrid의 UnloadingRow 이벤트 처리기에서 WPF DataGrid의 선택된 항목에 액세스하면 NullReferenceException이 발생할 수 있습니다.

|   |   |
|---|---|
|세부 정보|.NET Framework 4.5의 버그로 인해 행 제거와 관련된 <xref:System.Windows.Controls.DataGrid> 이벤트의 이벤트 처리기는 <xref:System.Windows.Controls.DataGrid>의 <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> 또는 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> 속성에 액세스하는 경우 <xref:System.NullReferenceException?displayProperty=name>이 throw될 수 있습니다.|
|제안 해결 방법|이 문제는 .NET Framework 4.6에서 해결되었으며, 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다.|
|범위|부|
|버전|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
