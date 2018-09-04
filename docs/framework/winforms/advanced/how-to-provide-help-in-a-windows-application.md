---
title: '방법: Windows 응용 프로그램에서 도움말 제공'
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
ms.openlocfilehash: 98ed6d4e10d0eb80b99a36172980fcb33186c8ca
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561872"
---
# <a name="how-to-provide-help-in-a-windows-application"></a>방법: Windows 응용 프로그램에서 도움말 제공
사용할 수 있습니다는 <xref:System.Windows.Forms.HelpProvider> Windows Forms에서 특정 컨트롤에 도움말 파일 내의 도움말 항목을 연결할 구성 요소입니다. 도움말 파일은 HTML 또는 HTMLHelp 1.x 이상의 형식이 될 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-provide-help"></a>도움말을 제공하려면  
  
1.  **도구 상자**를 끌어를 <xref:System.Windows.Forms.HelpProvider> 구성 요소를 폼입니다.  
  
     구성 요소가 Windows Forms 디자이너 아래쪽의 트레이너에 있습니다.  
  
2.  에 **속성** 창에서 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 속성을.chm,.col 또는.htm 도움말 파일로.  
  
3.  폼에 있고에 다른 컨트롤을 선택 합니다 **속성** 창에서 <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> 속성입니다.  
  
     통과 하는 문자열을 <xref:System.Windows.Forms.HelpProvider> 해당 도움말 항목을 호출 하 여 도움말 파일에 구성 요소입니다.  
  
4.  에 **속성** 창에서 <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> 속성의 값을는 <xref:System.Windows.Forms.HelpNavigator> 열거형입니다.  
  
     이 값은 **HelpKeyword** 속성이 도움말 시스템에 전달되는 방식을 결정합니다. 다음 표에서는 가능한 설정과 해당 설명을 보여 줍니다.  
  
    |멤버 이름|설명|  
    |-----------------|-----------------|  
    |AssociateIndex|지정한 항목에 대한 인덱스가 지정한 URL에서 수행되도록 지정합니다.|  
    |Find|지정한 URL의 검색 페이지가 표시되도록 지정합니다.|  
    |인덱스|지정한 URL의 인덱스가 표시되도록 지정합니다.|  
    |KeywordIndex|검색할 키워드와 지정한 URL에서 수행할 동작을 지정합니다.|  
    |TableOfContents|HTML 1.0 도움말 파일의 목차가 표시되도록 지정합니다.|  
    |항목|지정한 URL에서 참조하는 항목이 표시되도록 지정합니다.|  
  
 런타임에 F1 키를 누르면 때 컨트롤-설정한에 대 한 합니다 **HelpKeyword** 및 **HelpNavigator** 속성-에 포커스와 연결 된 도움말 파일이 열립니다 <xref:System.Windows.Forms.HelpProvider> 구성 요소입니다.  
  
 현재 **HelpNamespace** 속성은 HTMLHelp 1.x, HTMLHelp 2.0 및 HTML 형식의 도움말 파일을 지원합니다. 따라서 **HelpNamespace** 속성을 웹 페이지와 같은 http:// 주소로 설정할 수 있습니다. 이렇게 설정하면 앵커로 사용된 **HelpKeyword** 속성에 지정된 문자열이 있는 웹 페이지가 기본 브라우저에서 열립니다. 앵커는 HTML 페이지의 특정 부분으로 이동하는 데 사용됩니다.  
  
> [!IMPORTANT]
>  클라이언트에서 보낸 정보는 응용 프로그램에서 사용하기 전에 반드시 검사해야 합니다. 악의적인 사용자가 실행 스크립트, SQL 문 또는 다른 코드를 보내거나 삽입하려고 시도할 수 있습니다. 사용자의 입력을 표시하거나 데이터베이스에 저장하거나 사용하기 전에 잠재적으로 안전하지 않은 정보가 포함되어 있지 않은지 검사합니다. 일반적인 검사 방법은 사용자가 입력을 받을 때 정규식을 사용하여 "SCRIPT"와 같은 키워드를 검색하는 것입니다.  
  
 사용할 수도 있습니다는 <xref:System.Windows.Forms.HelpProvider> 에 Windows Forms에서 컨트롤에 대 한 도움말 파일을 표시 하도록 구성 된 경우에 팝업 도움말을 표시할 구성 요소입니다. 자세한 내용은 [방법: 팝업 도움말 표시](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 팝업 도움말 표시](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 [ToolTip을 사용한 컨트롤 도움말](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [Windows Forms에 사용자 도움말 통합](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [Windows Forms](../../../../docs/framework/winforms/index.md)
