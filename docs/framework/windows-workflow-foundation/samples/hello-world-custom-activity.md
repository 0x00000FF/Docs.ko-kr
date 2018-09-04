---
title: Hello World 사용자 지정 활동
ms.date: 03/30/2017
ms.assetid: 72b1dd0a-9aad-47d5-95a9-a1024ee1d0a1
ms.openlocfilehash: fde745fae7470ec763b6b5030a60436a6525e3c0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43533498"
---
# <a name="hello-world-custom-activity"></a>Hello World 사용자 지정 활동
이 샘플의 Windows WF (Workflow Foundation), 간단한 사용자 지정 활동을 만드는 방법을 비롯 한 몇 가지 주요 기능을 보여 줍니다. 이러한 기능에는 C#으로 사용자 지정 활동을 만들고 `in` 및 `out` 인수(<xref:System.Activities.InArgument> 및 <xref:System.Activities.OutArgument>)를 사용하는 기능이 포함됩니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\HelloWorld`  
  
## <a name="creating-a-workflow-in-code"></a>코드로 워크플로 만들기  
 이 샘플에서는 C# 코드를 사용하여 두 개의 사용자 지정 활동을 만듭니다. 두 사용자 지정 활동 모두 <xref:System.Activities.Activity%601>에서 직접 또는 간접적으로 상속하여 단일 값을 반환합니다. 비네제릭 <xref:System.Activities.Activity> 클래스에서 상속하지 않고 제네릭 반환 값을 사용하면 <xref:System.Activities.Statements.Assign>과 같은 일부 활동이 구성된 활동의 일부로 사용될 때 반환 값에 액세스할 수 있다는 장점이 있습니다.  
  
 AppendString  
 이 활동은 <xref:System.Activities.Activity%601>에서 상속하고, 두 문자열을 연결하는 <xref:System.Activities.Statements.Assign> 활동을 사용합니다.  
  
 PrependString  
 이 활동은 <xref:System.Activities.CodeActivity%601>에서 직접 상속하며, 기존 활동으로 구성되지 않고 코드로 구현된 논리를 사용하는 `AppendString` 활동과 비슷한 기능을 만듭니다.  
  
 이 프로젝트에 포함되어 있는 파일은 다음과 같습니다.  
  
 AppendString.cs  
 문자열을 추가하는 사용자 지정 활동입니다. 문자열에서 사용 하 고 리터럴 텍스트 문자열을 사용 하 여 결합 "says hello world" 폼 전체 메시지를 출력 합니다.  
  
 PrependString.cs  
 이 활동은 미리 정의된 문자열을 입력 문자열의 접두사로 추가합니다.  
  
 Sequence1.xaml  
 `AppendString` 및 `PrependString` 사용자 지정 활동을 사용하는 워크플로입니다.  
  
 Program.cs  
 워크플로를 실행하는 프로그램입니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 HelloWorld.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  F5 키를 눌러 솔루션을 실행합니다.