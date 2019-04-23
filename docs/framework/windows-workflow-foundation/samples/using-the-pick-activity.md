---
title: Pick 활동 사용
ms.date: 03/30/2017
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
ms.openlocfilehash: 0b2fbeb9b32406dd913d7e1ee87ac167113d0f28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59302983"
---
# <a name="using-the-pick-activity"></a>Pick 활동 사용
이 샘플에서는 <xref:System.Activities.Statements.Pick> 활동을 사용하는 방법을 보여 줍니다.

 <xref:System.Activities.Statements.Pick> 활동은 이벤트 기반의 제어 모델링을 제공합니다. 이는 `switch` 문의 분기 중 하나에서만 실행되는 C# `switch` 문과 비슷한 방식으로 작동합니다. 그러나 값을 기준으로 분기가 실행되는 `switch` 문과 달리 <xref:System.Activities.Statements.Pick> 활동은 활동의 완료 방식을 기준으로 분기가 실행됩니다.

 이 샘플에서는 지정된 시간 내에 사용자의 이름을 입력하라는 메시지를 콘솔에 표시합니다. 이 샘플의 <xref:System.Activities.Statements.Pick> 활동에는 사용자가 이름을 5초 안에 입력했는지 여부를 기준으로 실행되는 두 개의 분기가 있습니다. 사용자가 이름을 5초 안에 입력하면 사용자 지정 `ReadLine` 활동이 포함된 첫째 분기가 실행되고, 사용자가 이름을 5초 안에 입력하지 않으면 <xref:System.Activities.Statements.Delay> 활동이 포함된 둘째 분기가 실행됩니다. 사용자가 콘솔에 이름을 입력하고 나면 해당 이름이 콘솔에 출력됩니다. 이름을 5초 안에 입력하지 않으면 작업 제한 시간이 초과합니다.

## <a name="demonstrates"></a>세부 항목
 <xref:System.Activities.Statements.Pick> 활동

## <a name="discussion"></a>토론
 이 샘플에는 디자이너 워크플로와 코딩된 워크플로가 포함되어 있습니다.

 디자이너는 워크플로 디자이너 버전의 샘플에는 디자이너에서 워크플로 만드는 방법을 보여 줍니다. 여기에 포함되는 파일은 다음과 같습니다.

-   Program.cs: 포함 된 `Main` 샘플 워크플로 실행 하는 함수입니다.

-   ReadString.cs: 사용자 지정 활동을 콘솔에서 일부 입력을 읽습니다.

-   Sequence1.xaml: Pick을 사용 하는 디자이너를 사용 하 여 만든 워크플로.

 코딩 된 버전의 샘플 코딩 된 워크플로 디자이너에서 워크플로 만드는 방법을 보여 줍니다. 여기에 포함되는 파일은 다음과 같습니다.

-   Program.cs: 포함 된 `Main` 샘플 워크플로 실행 하는 함수입니다.

-   ReadString.cs: 사용자 지정 활동을 콘솔에서 일부 입력을 읽습니다.

#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면

1. Pick.sln 솔루션 파일을 열고 Visual Studio 2010을 사용 합니다.

2. Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.

3. F5 키를 눌러 솔루션을 실행합니다.

> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`