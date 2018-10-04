---
title: '방법: TableLayoutPanel 컨트롤에서 열과 행 편집'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: 820d2f98290650bfaf377bd2d4b863dfb2e6e704
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500786"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a>방법: TableLayoutPanel 컨트롤에서 열과 행 편집
컬렉션 편집기를 사용할 수는 <xref:System.Windows.Forms.TableLayoutPanel> 호출을 **열 및 행 스타일** 대화 상자에서 행과 컨트롤의 열을 편집 하려면.  
  
> [!NOTE]
>  여러 행 또는 열에 걸쳐 제어를 설정 합니다 `RowSpan` 및 `ColumnSpan` 컨트롤의 속성입니다. 자세한 내용은 [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)을 참조하세요.  
>   
>  셀 내에 있는 컨트롤을 정렬 하려는 셀 내에서 확장 하려는 경우를 사용 하 여 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성입니다. 자세한 내용은 [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)을 참조하세요.  
>   
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-edit-rows-and-columns"></a>행 및 열 편집  
  
1.  끌어서를 <xref:System.Windows.Forms.TableLayoutPanel> 에서 제어 합니다 **도구 상자** 폼입니다.  
  
2.  클릭 합니다 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 스마트 태그 문자 모양 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 선택한 **행 및 열 편집** 열려는  **열 및 행 스타일** 대화 상자. 또한 마우스 오른쪽 단추로 클릭할 수에 합니다 <xref:System.Windows.Forms.TableLayoutPanel> 제어 하 고 선택 **행 및 열 편집** 바로 가기 메뉴에서.  
  
3.  를 추가 하거나 열을 제거 하려면 선택 **열** 에서 합니다 **멤버 유형을** 드롭다운 목록 상자입니다.  
  
4.  를 추가 하거나 행을 제거 하려면 선택 **행** 에서 합니다 **멤버 유형을** 드롭다운 목록 상자입니다.  
  
5.  클릭 합니다 **추가** 끝에 행 또는 열을 추가 하려면 단추를 **멤버** 목록입니다.  
  
6.  클릭 합니다 **삽입** 목록의 행 또는 현재 선택한 항목 앞에 열을 추가 하는 단추입니다.  
  
7.  행 또는 열을 추가 하는 경우 선택 합니다 **크기 형식** 새 행 또는 열에 대 한 합니다. 자세한 내용은 <xref:System.Windows.Forms.SizeType>을 참조하세요.  
  
8.  행 또는 열을 제거 하려면 클릭 합니다 **제거** 에서 현재 선택한 항목을 삭제 하려면 단추를 **멤버** 목록입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.SizeType>  
 [TableLayoutPanel 컨트롤](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
