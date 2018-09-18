---
title: .NET Framework 4.5의에서 정책 작업
ms.date: 03/30/2017
ms.assetid: 8e375e0c-d7c1-4d69-88ab-36d52db0aa7e
ms.openlocfilehash: 9d8983f2f1d3f75beffeacfff4b673f6c23c4204
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2018
ms.locfileid: "45994379"
---
# <a name="policy-activity-in-net-framework-45"></a>.NET Framework 4.5의에서 정책 작업
Policy4 활동에서 Windows Workflow Foundation을 통해 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> 개체에서 Windows Workflow Foundation에서 사용할 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) WF 3.5에서 제공 되는 규칙 엔진을 사용 하 여 직접. 이 활동을 사용하여 WF 3.5 <xref:System.Workflow.Activities.Rules.RuleSet>을 만들고 실행할 수 있습니다. Windows Workflow Foundation의 일부로 포함 된 WF 3.5 규칙 엔진에 대 한 자세한 내용은 Windows Workflow Foundation 규칙 엔진 소개를 참조 하세요. 마이그레이션에 대 한 자세한 내용은 규칙을 WF [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]를 참조 하세요 [마이그레이션 지침](../../../../docs/framework/windows-workflow-foundation/migration-guidance.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-Policy4`  
  
## <a name="projects-in-this-sample"></a>이 샘플의 프로젝트  
  
|프로젝트 이름|설명|기본 파일|  
|------------------|-----------------|----------------|  
|Policy4|Policy4 활동과 이 활동의 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 디자이너가 들어 있습니다.|**Policy4.cs**: Policy4 활동 정의 합니다.<br /><br /> **PolicyDesigner.xaml**: Policy4 활동에 대 한 사용자 지정 디자이너입니다. 규칙 편집기를 사용 하 여 ([RuleSetDialog 클래스](https://go.microsoft.com/fwlink/?LinkId=150378))에서 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 규칙 엔진입니다.|  
|ImperativeCodeClientSample|명령적 C# 코드를 사용하는 Policy4 응용 프로그램을 사용하여 워크플로를 구성하고 실행하는 샘플 클라이언트 응용 프로그램입니다([!INCLUDE[wf1](../../../../includes/wf1-md.md)] 디자이너가 사용되지 않음).|**ApplyDiscount.rules**: 파일 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 규칙을 정의 합니다.<br /><br /> **Order.cs**: 고객 주문을 나타내는 형식입니다. 이 형식의 개체에 규칙이 적용됩니다.<br /><br /> **Program.cs**: 구성 하 고 Order 개체의 인스턴스에 대 한 ApplyDiscount.rules에 정의 된 규칙을 적용 하는 Policy4 활동에는 워크플로 실행 합니다.<br /><br /> **App.config**: 규칙 파일의 경로 사용 하 여 구성 파일입니다.|  
|DesignerClientSample|[!INCLUDE[wf1](../../../../includes/wf1-md.md)] 디자이너에서 Policy4 응용 프로그램을 사용하여 워크플로를 구성하고 실행하는 샘플 클라이언트 응용 프로그램입니다.|**Sequence1.xaml**: Policy4 활동을 사용 하 여 규칙 평가 수행 하는 순차 워크플로입니다.<br /><br /> `Program.cs`: Sequence1.xaml에 정의된 워크플로의 인스턴스를 실행합니다.|  
  
## <a name="the-policy4-activity"></a>Policy4 활동  
 Policy4 활동은 워크플로가 <xref:System.Activities.NativeActivity%601> RuleSet을 실행할 수 있도록 하는 [!INCLUDE[wf1](../../../../includes/wf1-md.md)]에서 파생되는 클래스입니다. 다음 코드 예제는 활동의 공용 OM에 대한 간략한 정의입니다.  
  
```csharp  
public class Policy4Activity<TResult>: NativeActivity<TResult>  
{  
    public RuleSet RuleSet  
  
    [IsRequired]  
    public InArgument Input  
  
    public OutArgument<ValidationErrorCollection> ValidationErrors  
}  
```  
  
|속성|설명|  
|--------------|-----------------|  
|RuleSet|WF [RuleSet Class](https://go.microsoft.com/fwlink/?LinkId=150379) 활동이 실행 될 때 평가할.NET Framework 3.5에 대 한 합니다.|  
|TargetObject|대상 개체의 규칙을 [RuleSet Class](https://go.microsoft.com/fwlink/?LinkId=150379) 평가 됩니다.|  
|ValidationError|반환 하는 유효성 검사 오류 목록을 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 유효성을 검사할 때.NET Framework 3.5에 대 한 규칙 엔진 합니다 [RuleSet 클래스](https://go.microsoft.com/fwlink/?LinkId=150379) 실행 하기 전에 대상 개체에 대 한 합니다.|  
  
## <a name="policy4-activity-designer"></a>Policy4 활동 디자이너  
 Policy4 디자이너는 코드를 작성하지 않고 Policy4 활동을 구성할 수 있는 기능을 추가합니다. 솔루션을 빌드한 후 있습니다 도구 상자에서 단원의 **Microsoft.Samples.Activities.Rules**합니다.  
  
 WF 디자이너를 사용하면 대상 개체와 RuleSet을 구성할 수 있습니다. 경우는 **RuleSet 편집** 단추를 클릭할 WF [RuleSetDialog 클래스](https://go.microsoft.com/fwlink/?LinkId=150378) 에 대 한 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 표시 됩니다. 이 대화 상자는 다시 호스트된 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 규칙 편집기입니다. 이 편집기를 사용하여 Policy4 활동이 실행하는 규칙을 만들고 편집할 수 있습니다.  
  
## <a name="using-this-sample"></a>이 샘플의 사용법  
 이 샘플을 실행하기 위한 특별한 설정 작업은 필요하지 않습니다. Visual Studio에서 솔루션을 열고 F5 키를 누르기만 하면 응용 프로그램이 실행됩니다.  
  
 이 샘플에는 두 개의 클라이언트 응용 프로그램인 ImperativeCodeClientSample과 DesignerClientSample이 포함되어 있습니다. ImperativeCodeClientSample 클라이언트에서는 C# 명령적 코드를 사용하여 Policy4 활동을 구성 및 실행하는 방법을 보여 주고, DesignerClientSample에서는 디자이너를 사용하여 Policy4 활동을 구성 및 실행하는 방법을 보여 줍니다.  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a>ImperativeCodeClientSample 클라이언트 응용 프로그램을 실행하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 사용하여 Policy4Sample.sln 솔루션 파일을 엽니다.  
  
2.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **ImperativeCodeClientSample** 프로젝트를 선택한 **시작 프로젝트로 설정**합니다.  
  
3.  Ctrl+F5를 눌러 프로젝트를 실행합니다.  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a>ImperativeCodeClientSample 클라이언트 응용 프로그램을 실행하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 사용하여 Policy4Sample.sln 솔루션 파일을 엽니다.  
  
2.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **DesignerClientSample** 프로젝트입니다.  
  
    -   선택 **시작 프로젝트로 설정**합니다.  
  
3.  프로젝트를 컴파일하려면 Ctrl+Shift+B를 누릅니다.  
  
4.  Ctrl+F5를 눌러 프로젝트를 실행합니다.