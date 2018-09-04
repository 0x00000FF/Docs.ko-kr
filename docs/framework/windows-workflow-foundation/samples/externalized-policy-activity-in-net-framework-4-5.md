---
title: .NET Framework 4.5의에서 구체화 된 정책 활동
ms.date: 03/30/2017
ms.assetid: 92fd6f92-23a1-4adf-b96a-2754ea93ad3e
ms.openlocfilehash: 4d107188bbcb46006ba6a6eab491ccb97aa4a83d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503409"
---
# <a name="externalized-policy-activity-in-net-framework-45"></a>.NET Framework 4.5의에서 구체화 된 정책 활동

이 샘플에서는 ExternalizedPolicy4 활동을 통해 기존 실행 하는 방법을 보여 줍니다. [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] Windows Workflow Foundation (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> 개체 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] 규칙 엔진을 사용 하 여 직접 Windows Workflow Foundation (WF 4.5) WF 3.5에서 제공 됩니다. 이 활동을 사용하여 기존 WF 3.5 <xref:System.Workflow.Activities.Rules.RuleSet>을 열고 실행할 수 있습니다. Windows Workflow Foundation의 일부로 포함 된 WF 3.5 규칙 엔진에 대 한 자세한 내용은 읽어보세요 [Windows Workflow Foundation 규칙 엔진 소개](https://go.microsoft.com/fwlink/?LinkId=166079)합니다. 마이그레이션에 대 한 자세한 규칙을 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 에 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]에서 마이그레이션 지침을 참조 하세요 [마이그레이션 지침](../../../../docs/framework/windows-workflow-foundation/migration-guidance.md)합니다.

## <a name="projects-in-this-sample"></a>이 샘플의 프로젝트

|프로젝트 이름|설명|기본 파일|
|-|-|-|
|ExternalizedPolicy4|ExternalizedPolicy4 활동과 이 활동의 WF 4.5 디자이너가 들어 있습니다.|**ExternalizedPolicy4.cs**: 활동 정의 합니다.<br /><br /> **ExternalizedPolicy4Designer.xaml**: ExternalizedPolicy4 활동에 대 한 사용자 지정 디자이너입니다. 이 디자이너는 WF 3.5 규칙 엔진의 규칙 편집기(<xref:System.Workflow.Activities.Rules.Design.RuleSetDialog>)를 사용합니다.|
|ImperativeCodeClientSample|명령적 C# 코드를 사용하는 ExternalizedPolicy4 응용 프로그램을 사용하여 워크플로를 구성하고 실행하는 샘플 클라이언트 응용 프로그램입니다(디자이너가 사용되지 않음).|**ApplyDiscount.rules**: 파일 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 규칙을 정의 합니다.<br /><br /> **Order.cs**: 고객 주문을 나타내는 형식입니다. 이 형식의 개체에 규칙이 적용됩니다.<br /><br /> **Program.cs**: 구성 하 고 Order 개체의 인스턴스에 대 한 ApplyDiscount.rules에 정의 된 규칙을 적용 하는 Policy4 활동에는 워크플로 실행 합니다.<br /><br /> App.config: 규칙 파일의 경로가 있는 구성 파일입니다.|
|DesignerClientSample|[!INCLUDE[wf1](../../../../includes/wf1-md.md)] 디자이너에서 ExternalPolicy4 응용 프로그램을 사용하여 워크플로를 구성하고 실행하는 샘플 클라이언트 응용 프로그램입니다.|**Sequence1.xaml**: Policy4 활동을 사용 하 여 규칙 평가 수행 하는 순차 워크플로입니다.<br /><br /> **Program.cs**: Sequence1.xaml에 정의 된 워크플로의 인스턴스를 실행 합니다.|

## <a name="the-externalizedpolicy4-activity"></a>ExternalizedPolicy4 활동

ExternalizedPolicy4 활동은 WF 4.5 워크플로 내의 WF 3.5 <xref:System.Activities.NativeActivity> 개체를 실행할 수 있는 <xref:System.Workflow.Activities.Rules.RuleSet>입니다. 다음 예제는 활동의 공용 개체 모델에 대한 간략한 정의입니다.

```
public class ExternalizedPolicy4Activity<TResult>: CodeActivity
{
    public string RulesFilePath

    public string RuleSetName

    [RequiredArgument]
    public InArgument<T> TargetObject

    [RequiredArgument]
    public OutArgument<T> ResultObject

    public OutArgument<ValidationErrorCollection> ValidationErrors
}
```

|속성|설명|
|-|-|
|RuleSetFilePath|활동을 실행할 때 평가할 .NET Framework 3.5 <xref:System.Workflow.Activities.Rules.RuleSet> 파일의 경로입니다.|
|RuleSetName|.rules 파일 내에서 사용할 <xref:System.Workflow.Activities.Rules.RuleSet>의 이름입니다.|
|TargetObject|<xref:System.Workflow.Activities.Rules.Rule>의 <xref:System.Workflow.Activities.Rules.RuleSet> 개체를 평가할 기준 개체입니다.|
|ResultObject|규칙이 적용되는 결과 개체입니다. 예를 들어 규칙은 입력 인수에 대해 적용되고 결과는 결과 인수에 저장됩니다.|
|ValidationError|실행하기 전에 대상 개체에 대해 <xref:System.Workflow.Activities.Rules.RuleSet>의 유효성을 검사할 때 WF 3.5 규칙 엔진에서 반환하는 유효성 검사 오류 목록입니다.|

## <a name="externalizedpolicy4-activity-designer"></a>ExternalizedPolicy4 활동 디자이너

ExternalizedPolicy4 디자이너를 사용하면 코드를 작성하지 않고 기존 RuleSet을 사용하도록 활동을 구성할 수 있습니다. .rules 파일이 있는 경로를 설정하고 사용할 <xref:System.Workflow.Activities.Rules.RuleSet> 이름을 지정하기만 하면 됩니다. 이 디자이너를 사용하여 <xref:System.Workflow.Activities.Rules.RuleSet>을 수정할 수도 있습니다. 솔루션을 빌드한 후에는 도구 상자의 Microsoft.Samples.Activities.Rules 섹션에 있습니다. 디자이너를 사용하여 .rules 파일과 <xref:System.Workflow.Activities.Rules.RuleSet>을 선택할 수 있습니다. 경우는 **RuleSet 편집** 단추를 클릭할 WF 3.5 <xref:System.Workflow.Activities.Rules.Design.RuleSetDialog> 표시 됩니다. 이 대화 상자는 다시 호스트된 WF 3.5 규칙 편집기이며, ExternalizedPolicy4 활동에서 실행하는 규칙을 보고 편집하는 데 사용됩니다.

## <a name="policy4-and-externalpolicy4"></a>Policy4 및 ExternalPolicy4

합니다 [.NET Framework 4.5의 정책 활동](../../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) 활동을 만들고 WF 4.5 워크플로에.NET Framework 3.5 RuleSet을 실행할 수 있습니다. <xref:System.Workflow.Activities.Rules.RuleSet>은 Policy4 활동 XAML 정의에 serialize된 인라인입니다. ExternalizedPolicy4 샘플에서는 .rules 파일에 포함된 기존 외부 <xref:System.Workflow.Activities.Rules.RuleSet>을 사용하는 방법을 보여 줍니다.

## <a name="use-this-sample"></a>이 샘플 사용

이 샘플을 실행하기 위한 특별한 설정 작업은 필요하지 않습니다. Visual Studio에서 솔루션을 열고 다음 키를 누릅니다 **F5** 응용 프로그램을 실행 합니다.

이 샘플에는 두 개의 클라이언트 응용 프로그램인 ImperativeCodeClientSample과 DesignerClientSample이 포함되어 있습니다. ImperativeCodeClientSample 클라이언트에서는 C# 명령적 코드를 사용하여 ExternalizedPolicy4 활동을 구성 및 실행하는 방법을 보여 주고, DesignerClientSample에서는 디자이너를 사용하여 ExternalizedPolicy4 활동을 구성 및 실행하는 방법을 보여 줍니다.

### <a name="run-the-imperativecodeclientsample-application"></a>ImperativeCodeClientSample 응용 프로그램을 실행 합니다.

1.  Visual Studio를 사용 하 여 엽니다는 *Policy4sample.sln* 솔루션 파일입니다.

2.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **ImperativeCodeClientSample** 프로젝트를 선택한 **시작 프로젝트로 설정**합니다.

3.  키를 눌러 프로젝트를 실행 하려면 **Ctrl**+**F5**합니다.

### <a name="run-the-designerclientsample-application"></a>DesignerClientSample 응용 프로그램을 실행 합니다.

1.  Visual Studio를 사용 하 여 엽니다는 *Policy4sample.sln* 솔루션 파일입니다.

2.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **DesignerClientSample** 프로젝트를 선택한 **시작 프로젝트로 설정**합니다.

3.  키를 눌러 **Ctrl**+**Shift**+**B** 프로젝트를 컴파일합니다.

4.  키를 눌러 **Ctrl**+**F5** 프로젝트를 실행 합니다.

> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> 이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.
>
> 이 샘플은 다음 디렉터리에 있습니다.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-ExternalizedPolicy4`
