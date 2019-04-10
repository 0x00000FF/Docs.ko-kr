---
title: '방법: 다른 부모에 기존 컨트롤 다시 할당'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: 2639322707c1c7e378f6d389a1dec80fd619841c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328220"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a>방법: 다른 부모에 기존 컨트롤 다시 할당
폼에 있는 컨트롤을 새 컨테이너 컨트롤에 할당할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-reassign-existing-controls-to-a-different-parent"></a>기존 컨트롤을 다른 부모에 다시 할당하려면  
  
1. <xref:System.Windows.Forms.Button> 도구 상자 **의 세** 컨트롤을 폼으로 끌어옵니다.  
  
     서로 정렬되지 않은 상태로 근처에 배치합니다.  
  
2. **도구 상자**에서 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤 아이콘을 클릭합니다.  
  
     아이콘을 폼으로 끌어오지 마세요.  
  
3. 마우스 포인터를 세 <xref:System.Windows.Forms.Button> 컨트롤 쪽으로 이동합니다.  
  
     포인터가 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤 아이콘이 연결된 십자형으로 바뀝니다.  
  
4. 마우스 단추를 길게 클릭합니다.  
  
5. 마우스 포인터를 끌어 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤의 윤곽선을 그립니다.  
  
6. 세 <xref:System.Windows.Forms.Button> 컨트롤 주위에 윤곽선을 그립니다.  
  
7. 마우스 단추를 놓습니다.  
  
     이제 세 <xref:System.Windows.Forms.Button> 컨트롤이 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤에 삽입됩니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Windows Forms에서 컨트롤 정렬](arranging-controls-on-windows-forms.md)
- [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
