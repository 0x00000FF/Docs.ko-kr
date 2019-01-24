---
title: DataRepeater 컨트롤 문제 해결(Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, troubleshooting
ms.assetid: c0ab9469-eced-4f52-aa18-4bd8dd4f1a9a
ms.openlocfilehash: 7b045e1c45221cbde82c88286da8e698a763d844
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580605"
---
# <a name="troubleshooting-the-datarepeater-control-visual-studio"></a>DataRepeater 컨트롤 문제 해결(Visual Studio)
이 항목에서는 사용 하 여 작업할 때 발생할 수 있는 일반적인 문제는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.  
  
## <a name="datarepeater-keyboard-and-mouse-events-are-not-raised"></a>DataRepeater 키보드 및 마우스 이벤트를 발생 하지 않습니다.  
 일부 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 키보드 및 마우스 이벤트와 같은 컨트롤 이벤트를 발생 하지 않습니다. 이것은 의도적인 것입니다. 합니다 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 자체에 대 한 컨테이너인 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 개체 및 런타임에 액세스할 수 없습니다. <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 디자인 타임에 이벤트를 노출 하지 않습니다. 따라서 항목을 클릭 하거나 항목에 포커스가 있을 때 키를 눌러는 이벤트를 발생 하지 않습니다.  
  
 경우는 예외를 <xref:System.Windows.Forms.Control.Padding%2A> 속성은 큰 충분 한 값의 가장자리를 노출 하는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤입니다. 이 경우 노출된 여백을 클릭 마우스 이벤트가 발생 합니다.  
  
 이 문제를 해결 하려면 추가 <xref:System.Windows.Forms.Panel> 컨트롤을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 섹션을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 추가한 다음 컨트롤의 나머지 부분은 <xref:System.Windows.Forms.Panel>합니다. 코드를 추가할 수 있습니다는 <xref:System.Windows.Forms.Panel> 키보드 및 마우스 이벤트에 대 한 컨트롤의 이벤트 처리기입니다.  
  
## <a name="the-datarepeater-is-partially-hidden-behind-the-binding-navigator"></a>DataRepeater는 부분적으로 뒤에 숨겨져 바인딩에 탐색기  
 처음 추가 하면를 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 폼 컨트롤을 추가한 다음 데이터 바인딩된 컨트롤에서는 **데이터 원본** 창을 <xref:System.Windows.Forms.BindingNavigator> 컨트롤 위쪽에 나타날 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다. 알려진 제한 사항 합니다 **데이터 원본** 창와 같은 다른 컨트롤의 동작과 일치 하는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.  
  
 이동 하거나 할 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 보다 낮은 합니다 <xref:System.Windows.Forms.BindingNavigator> 디자인 타임에 컨트롤에 다음과 같은 코드를 추가 하거나는 `Load` 이벤트 처리기입니다.  
  
```vb  
DataRepeater1.Top = ProductsBindingNavigator.Height  
```  
  
```csharp  
dataRepeater1.Top = productsBindingNavigator.Height;  
```  
  
## <a name="controls-are-not-displayed-correctly-at-run-time"></a>런타임 시 컨트롤 올바르게 표시 되지 않습니다.  
 일부 컨트롤을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 실행 시 예상 대로 표시 될 수 있습니다. 컨트롤을 복제 하는 데 사용 하는 프로세스를 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 항상 모든 컨트롤의 모든 속성을 확인할 수 없습니다. 예를 들어, 바인딩되지 않은 추가 하는 경우 <xref:System.Windows.Forms.ListBox> 컨트롤을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 디자인 타임에 컨트롤을 채우는 해당 <xref:System.Windows.Forms.ListBox.Items%2A> 목록으로 구성 된 컬렉션을 <xref:System.Windows.Forms.ListBox> 런타임에 비어 있게 됩니다. 이 복제 프로세스 계정에 사용할 수 없습니다 때문에 <xref:System.Windows.Forms.ListBox.Items%2A> 속성입니다.  
  
 누락 된 속성을 복원 하 여 이와 같은 문제를 해결할 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> 기본 복제가 완료 된 후 발생 하는 이벤트입니다. 다음 예제에서는 복구 하는 방법에 설명 합니다 <xref:System.Windows.Forms.ListBox.Items%2A> 의 컬렉션을 <xref:System.Windows.Forms.ListBox> 에서 제어할는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> 이벤트 처리기입니다.  
  
 [!code-csharp[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/troubleshooting-the-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/troubleshooting-the-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="the-selection-symbol-on-the-item-header-is-missing"></a>항목 헤더에 선택 기호가 누락 되었습니다.  
 변경 하는 경우를 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 있는 항목 헤더의 속성을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 몇 가지 색 선택은 선택 기호가 표시 되지 않을 수 있습니다. 변경 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 속성 사라질 선택 기호 발생할 수 있습니다.  
  
 색 및 선택 하는 기호의 크기를 변경할 수 없습니다.  
  
-   설정한 경우에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 에 <xref:System.Drawing.Color.White%2A>, 항목을 처음 선택할 때 선택 기호가 표시 되지 것입니다.  
  
-   설정한 경우에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 에 <xref:System.Drawing.Color.Black%2A>, 컨트롤이 선택 되 고 컨트롤을 편집 모드에 있을 때 연필 기호 표시 되지 것입니다 선택 기호가 표시 되지 것입니다.  
  
-   경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 11 보다 작음 값 속성, 항목 헤더에 표시기 기호가 표시 되지 것입니다.  
  
 사용 하 여 사용자 고유의 항목 헤더 및 선택 기호를 제공할 수 있습니다를 <xref:System.Windows.Forms.PictureBox> 제어 및 모니터링를 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> 의 속성을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 의 이벤트는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤. 자세한 내용은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고자료
- [DataRepeater 컨트롤 소개](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [방법: DataRepeater 컨트롤의 바인딩된 데이터 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [방법: DataRepeater 컨트롤의 바인딩되지 않은 컨트롤 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)
- [방법: DataRepeater 컨트롤의 레이아웃 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)
- [방법: DataRepeater 컨트롤의 모양 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [방법: DataRepeater 컨트롤의 항목 머리글 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
- [방법: DataRepeater 항목 추가 및 삭제를 사용 하지 않도록 설정](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)
- [방법: DataRepeater 컨트롤의 데이터 검색](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)
- [방법: 두 개의 DataRepeater 컨트롤 (Visual Studio)를 사용 하 여 마스터/세부 폼 만들기](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
