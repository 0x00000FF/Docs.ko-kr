---
title: '방법: ListView 컨트롤에 검색 기능 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
ms.openlocfilehash: 2049638998f7a8d099e14fab9c95384a49c67833
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a>방법: ListView 컨트롤에 검색 기능 추가
에 있는 항목의 큰 목록으로 작업 하는 경우에 종종는 <xref:System.Windows.Forms.ListView> 사용자에 게 검색 기능을 제공 하려는 컨트롤을 합니다. <xref:System.Windows.Forms.ListView> 제어는 두 가지 방법으로이 기능을 제공: 텍스트 일치 및 위치를 검색 합니다.  
  
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A> 메서드를 사용 하면에서 텍스트 검색을 수행 하는 <xref:System.Windows.Forms.ListView> 검색 문자열 및 선택적 시작 및 끝 인덱스가 지정 된 목록 또는 자세히 보기에서 합니다. 반면,는 <xref:System.Windows.Forms.ListView.FindNearestItem%2A> 메서드에서 항목을 찾을 수 있습니다는 <xref:System.Windows.Forms.ListView> 아이콘 또는 tile 보기에서 x 및 y 좌표와 검색 방향을 집합이 제공 합니다.  
  
### <a name="to-find-an-item-using-text"></a>텍스트를 사용 하는 항목을 찾습니다.  
  
1.  만들기는 <xref:System.Windows.Forms.ListView> 와 <xref:System.Windows.Forms.ListView.View%2A> 속성이로 설정 <xref:System.Windows.Forms.View.Details> 또는 <xref:System.Windows.Forms.View.List>, 다음 채웁니다는 <xref:System.Windows.Forms.ListView> 항목과 합니다.  
  
2.  호출의 <xref:System.Windows.Forms.ListView.FindItemWithText%2A> 메서드를 찾을 하려는 항목의 텍스트를 전달 합니다.  
  
3.  다음 코드 예제에는 기본을 만드는 방법을 보여 줍니다 <xref:System.Windows.Forms.ListView>고 항목을 채우고, 사용자가 입력 한 텍스트를 사용 하 여 목록의 항목을 찾습니다.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a>X 및 y 좌표를 사용 하는 항목을 찾습니다.  
  
1.  만들기는 <xref:System.Windows.Forms.ListView> 와 <xref:System.Windows.Forms.View> 속성이로 설정 <xref:System.Windows.Forms.View.SmallIcon> 또는 <xref:System.Windows.Forms.View.LargeIcon>, 다음 채웁니다는 <xref:System.Windows.Forms.ListView> 항목과 합니다.  
  
2.  호출 된 <xref:System.Windows.Forms.ListView.FindNearestItem%2A> 메서드를 원하는 x 및 y-좌표 및 방향을 검색 하 시겠습니까 전달 합니다.  
  
3.  다음 코드 예제에서는 기본 아이콘을 만드는 방법을 보여 줍니다. <xref:System.Windows.Forms.ListView>, 항목 및 캡처를 채웁니다는 <xref:System.Windows.Forms.Control.MouseDown> 이벤트 위쪽 방향에서 가장 가까운 항목을 찾습니다.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A>  
 <xref:System.Windows.Forms.ListView.FindNearestItem%2A>  
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
