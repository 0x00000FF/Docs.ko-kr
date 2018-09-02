---
title: '방법: 활동 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: deb1b6ca5c6fc996a015e32dd5e0c7b9bd6530fa
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402509"
---
# <a name="how-to-create-an-activity"></a>방법: 활동 만들기
활동은 [!INCLUDE[wf1](../../../includes/wf1-md.md)]에서 동작의 핵심 단위입니다. 활동의 실행 논리는 관리 코드에서 구현하거나 다른 활동을 사용하여 구현할 수 있습니다. 이 항목에서는 두 개의 활동을 만드는 방법을 보여 줍니다. 첫 번째 활동은 코드를 사용하여 실행 논리를 구현하는 간단한 활동입니다. 두 번째 활동의 구현은 다른 활동을 사용하여 정의됩니다. 이러한 활동은 자습서의 다음 단계에서 사용됩니다.  
  
> [!NOTE]
>  이 자습서의 전체 버전을 다운로드 하려면 [Windows Workflow Foundation(wf45 ()-초보자를 위한 자습서](https://go.microsoft.com/fwlink/?LinkID=248976)합니다.  
  
### <a name="to-create-the-activity-library-project"></a>활동 라이브러리 프로젝트를 만들려면  
  
1.  오픈 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 선택한 **새로 만들기**, **프로젝트** 에서 합니다 **파일** 메뉴.  
  
2.  확장 합니다 **기타 프로젝트 형식** 에서 노드를 **설치 됨**를 **템플릿** 나열 하 고 선택 **Visual Studio 솔루션**합니다.  
  
3.  선택 **빈 솔루션** 에서 합니다 **Visual Studio 솔루션** 목록입니다. .NET Framework 버전 드롭다운 목록에서 **.NET Framework 4.5** 가 선택되어 있는지 확인합니다. 형식 `WF45GettingStartedTutorial` 에 **이름** 상자 하 고 클릭 **확인**합니다.  
  
4.  마우스 오른쪽 단추로 클릭 **WF45GettingStartedTutorial** 에서 **솔루션 탐색기** 선택한 **추가**하십시오 **새 프로젝트**합니다.  
  
    > [!TIP]
    >  **솔루션 탐색기** 창이 표시되어 있지 않으면 **보기** 메뉴에서 **솔루션 탐색기** 를 선택합니다.  
  
5.  **설치됨** 노드에서 **Visual C#**, **워크플로** (또는 **Visual Basic**, **워크플로**)를 차례로 선택합니다. 했는지 **.NET Framework 4.5** 에서 선택한는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 버전 드롭다운 목록입니다. 선택 **활동 라이브러리** 에서 합니다 **워크플로** 목록입니다. 형식 `NumberGuessWorkflowActivities` 에 **이름** 상자 하 고 클릭 **확인**합니다.  
  
    > [!NOTE]
    >  **설치됨** 노드의 **다른 언어** 노드 아래에는 Visual Studio에서 기본 언어로 구성된 프로그래밍 언어에 따라 **Visual C#** 또는 **Visual Basic** 노드가 표시될 수 있습니다.  
  
6.  마우스 오른쪽 단추로 클릭 **Activity1.xaml** 에 **솔루션 탐색기** 선택한 **삭제**합니다. **확인** 을 클릭하여 확인합니다.  
  
### <a name="to-create-the-readint-activity"></a>ReadInt 활동을 만들려면  
  
1.  선택할 **새 항목 추가** 에서 합니다 **프로젝트** 메뉴.  
  
2.  에 **설치 됨**를 **공통 항목** 노드를 선택 **워크플로**합니다. 선택 **코드 활동** 에서 합니다 **워크플로** 목록입니다.  
  
3.  형식 `ReadInt` 에 **이름** 상자 하 고 클릭 **추가**합니다.  
  
4.  기존 `ReadInt` 정의를 다음 정의로 바꿉니다.  
  
     [!code-csharp[CFX_WF_GettingStarted#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]  
  
    > [!NOTE]
    >  `ReadInt` 활동은 코드 활동 템플릿의 기본값인 <xref:System.Activities.NativeActivity%601> 대신 <xref:System.Activities.CodeActivity>에서 파생됩니다. 활동이 <xref:System.Activities.CodeActivity%601> 인수를 통해 노출되는 단일 결과를 제공하는 경우 <xref:System.Activities.Activity%601.Result%2A>를 사용할 수 있지만 <xref:System.Activities.CodeActivity%601>는 책갈피 사용을 지원하지 않으므로 <xref:System.Activities.NativeActivity%601>가 사용됩니다.  
  
### <a name="to-create-the-prompt-activity"></a>Prompt 활동을 만들려면  
  
1.  Ctrl+Shift+B를 눌러 프로젝트를 빌드합니다. 프로젝트를 빌드하면 이 프로젝트의 `ReadInt` 활동을 사용하여 이 단계의 사용자 지정 활동을 빌드할 수 있습니다.  
  
2.  선택할 **새 항목 추가** 에서 합니다 **프로젝트** 메뉴.  
  
3.  에 **설치 됨**를 **공통 항목** 노드를 선택 **워크플로**합니다. 선택 **활동** 에서 합니다 **워크플로** 목록입니다.  
  
4.  형식 `Prompt` 에 **이름** 상자 하 고 클릭 **추가**합니다.  
  
5.  두 번 클릭 **Prompt.xaml** 에 **솔루션 탐색기** 아직 표시 되지 않은 경우 디자이너에 표시 합니다.  
  
6.  클릭 **인수** 표시할 activity designer의 왼쪽 아래에에서는 **인수** 창입니다.  
  
7.  클릭 **인수를 만드는**합니다.  
  
8.  형식 `BookmarkName` 에 **이름** 상자에서 **에서** 에서 합니다 **방향** 드롭 다운 목록에서 **문자열** 합니다 에서**인수 형식** 드롭 다운 목록 및 다음 인수를 저장 하려면 ENTER 키를 누릅니다.  
  
9. 클릭 **인수를 만드는**합니다.  
  
10. 형식 `Result` 에 **이름** 새로 추가 된 아래에 있는 상자 `BookmarkName` 인수 **Out** 에서 **방향** 드롭 다운 목록에서 **Int32** 에서 합니다 **인수 형식** 드롭 다운 목록 및 다음 ENTER 키를 누릅니다.  
  
11. 클릭 **인수를 만드는**합니다.  
  
12. 형식 `Text` 에 **이름** 상자에서 **에서** 에서 합니다 **방향** 드롭 다운 목록에서 **문자열** 합니다 에서**인수 형식** 드롭 다운 목록 및 다음 인수를 저장 하려면 ENTER 키를 누릅니다.  
  
     이 세 가지 인수는 다음 단계에서 <xref:System.Activities.Statements.WriteLine> 활동에 추가되는 `ReadInt` 및 `Prompt` 활동의 해당 인수에 바인딩됩니다.  
  
13. 클릭 **인수** 닫으려면 activity designer의 왼쪽 아래에에서는 **인수** 창입니다.  
  
14. 끌어서를 **시퀀스** 활동에서는 **제어 흐름** 부분을 **도구 상자** 놓습니다를 **여기에 작업 놓기** 레이블의 **프롬프트** 활동 디자이너입니다.  
  
    > [!TIP]
    >  경우는 **도구 상자** 창이 표시 되지 않으면, 선택 **도구 상자** 에서 합니다 **뷰** 메뉴.  
  
15. 끌어서를 **WriteLine** 활동에서는 **기본** 부분을 **도구 상자** 놓습니다를 **여기에 작업 놓기** 레이블의 **시퀀스** 활동입니다.  
  
16. 바인딩를 **텍스트** 인수를 **WriteLine** 활동을를 **텍스트** 인수를 **프롬프트** 입력 하 여 작업 `Text` 에 **C# 식 입력** 또는 **VB 식 입력** 상자에 **속성** 창과 누릅니다 탭 키를 두 번입니다. 그러면 IntelliSense 목록 멤버 창이 사라지고 속성에서 선택 항목을 이동하여 속성 값이 저장됩니다. 입력 하 여이 속성을 설정할 수도 있습니다 `Text` 에 **C# 식 입력** 또는 **VB 식 입력** 활동 자체는 상자입니다.  
  
    > [!TIP]
    >  경우는 **속성 창** 표시를 선택 하지 않는 **속성 창** 에서 합니다 **뷰** 메뉴.  
  
17. 끌어서를 **ReadInt** 활동에서는 **NumberGuessWorkflowActivities** 부분을 **도구 상자** 놓습니다를 **시퀀스** 활동 오도록 합니다 **WriteLine** 활동입니다.  
  
18. 바인딩를 **BookmarkName** 인수를 **ReadInt** 활동을는 **BookmarkName** 인수의 **프롬프트** 입력하여활동`BookmarkName` 에 **VB 식 입력** 오른쪽의 상자에는 **BookmarkName** 인수에는 **속성 창**, 두 탭 키를 누릅니다 IntelliSense 목록 멤버 창을 닫고 속성을 저장 하려면 시간이 됩니다.  
  
19. 바인딩를 **결과** 인수를 **ReadInt** 활동을를 **결과** 인수를 **프롬프트** 입력 하 여 작업 `Result` 에 **VB 식 입력** 의 오른쪽 상자에는 **결과** 인수에는 **속성 창**, 탭 키를 두 번 누릅니다 하 고 합니다.  
  
20. Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
     이러한 활동을 사용 하 여 워크플로 만드는 방법에 대 한 지침 자습서에서 다음 단계를 참조 하세요 [방법: 워크플로 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Activities.CodeActivity>  
 <xref:System.Activities.NativeActivity%601>  
 [사용자 지정 활동 디자인 및 구현](../../../docs/framework/windows-workflow-foundation/designing-and-implementing-custom-activities.md)  
 [초보자를 위한 자습서](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [방법: 워크플로 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)  
 [사용자 지정 작업 디자이너에서 ExpressionTextBox 사용](../../../docs/framework/windows-workflow-foundation/samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
