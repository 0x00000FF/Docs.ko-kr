---
title: '방법: Windows Forms 컨트롤 작성'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], creating
- UserControl class [Windows Forms], Windows Forms
- custom controls [Windows Forms], creating
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
ms.openlocfilehash: 844d165cef05e46d25960f113af3bf99dd35e14f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340336"
---
# <a name="how-to-author-controls-for-windows-forms"></a>방법: Windows Forms 컨트롤 작성
컨트롤은 사용자와 프로그램 간의 그래픽 링크를 나타냅니다. 컨트롤은 데이터를 제공하거나 처리하고, 사용자 입력을 허용하고, 사용자 및 애플리케이션을 연결하는 다른 함수의 구성원을 합니다. 컨트롤이 기본적으로 그래픽 인터페이스를 사용하는 구성 요소이기 때문에 사용자 상호 작용을 제공할 뿐만 아니라 구성 요소가 수행하는 모든 함수를 제공할 수 있습니다. 컨트롤은 특정 목적을 수행하기 위해 만들어지며 컨트롤 작성은 다른 프로그래밍 작업입니다. 이 점을 염두하면서 다음 단계는 컨트롤 작성 프로세스의 개요를 나타냅니다. 링크는 각 단계에 대한 추가 정보를 제공합니다.  
  
> [!NOTE]
>  Web Forms에서 사용할 사용자 지정 컨트롤을 작성하려는 경우 [사용자 지정 ASP.NET 서버 컨트롤 개발](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100))을 참조하세요.  
>   
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-author-a-control"></a>컨트롤을 작성하려면  
  
1. 컨트롤이 수행하려는 항목 또는 애플리케이션에서 컨트롤이 맡은 역할을 결정합니다. 고려해야 하는 요인은 다음과 같습니다.  
  
    -   어떤 종류의 그래픽 인터페이스가 필요한가요?  
  
    -   이 컨트롤이 다룰 특정 사용자 인터페이스는 무엇인가요?  
  
    -   기존 컨트롤에서 필요한 기능을 제공하나요?  
  
    -   여러 Windows Forms 컨트롤을 결합하여 필요한 기능을 얻을 수 있나요?  
  
2. 컨트롤에 대한 개체 모델이 필요한 경우 개체 모델 전체에 기능을 분산할 방법을 결정하고 컨트롤과 하위 개체 간의 기능을 분리합니다. 개체 모델은 복잡한 컨트롤 계획하거나 여러 기능을 통합하려는 경우에 유용할 수 있습니다.  
  
3. 필요한 컨트롤의 형식을 확인합니다(예: 사용자 정의 컨트롤, 사용자 지정 컨트롤, 상속된 Windows Forms 컨트롤). 자세한 내용은 [컨트롤 형식 권장 사항](control-type-recommendations.md) 및 [사용자 지정 컨트롤의 종류](varieties-of-custom-controls.md)를 참조하세요.  
  
4. 기능을 컨트롤의 속성, 메서드 및 이벤트 및 해당 하위 개체 또는 보조 구조로 나타내고 적절한 액세스 수준(예: 공용, 보호 등)을 할당합니다.  
  
5. 컨트롤에 사용자 지정 그리기가 필요한 경우 코드를 추가합니다. 자세한 내용은 [사용자 지정 컨트롤 그리기 및 렌더링](custom-control-painting-and-rendering.md)을 포함합니다.  
  
6. 컨트롤에서 상속 하는 경우 <xref:System.Windows.Forms.UserControl>, 컨트롤 프로젝트를 빌드하고에서 실행 하 여 런타임 동작을 테스트할 수 있습니다 합니다 **UserControl 테스트 컨테이너**합니다. 자세한 내용은 [방법: UserControl의 런타임 동작 테스트](how-to-test-the-run-time-behavior-of-a-usercontrol.md)합니다.  
  
7. 또한 Windows 애플리케이션과 같이 새 프로젝트를 만들고 컨테이너에 배치하여 컨트롤을 테스트하고 디버그할 수 있습니다. 이 프로세스의 일부로 설명 됩니다 [연습: Visual Basic에서 합성 컨트롤 제작](walkthrough-authoring-a-composite-control-with-visual-basic.md)합니다.  
  
8. 각 기능을 추가하면 기능을 테스트 프로젝트에 추가하여 새 기능을 실행합니다.  
  
9. 반복하여 디자인을 구체화합니다.  
  
10. 컨트롤을 패키지하고 배포합니다. 자세한 내용은 참조 하세요 [Visual Studio에서 배포를 먼저 살펴보겠습니다](/visualstudio/deployment/deploying-applications-services-and-components)합니다.  
  
## <a name="see-also"></a>참고자료

- [연습: Visual Basic을 사용하여 복합 컨트롤 작성](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [방법: UserControl 클래스에서 상속](how-to-inherit-from-the-usercontrol-class.md)
- [방법: Control 클래스에서 상속](how-to-inherit-from-the-control-class.md)
- [방법: 기존 Windows Forms 컨트롤에서 상속](how-to-inherit-from-existing-windows-forms-controls.md)
- [방법: UserControl의 런타임 동작 테스트](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [사용자 지정 컨트롤의 종류](varieties-of-custom-controls.md)
