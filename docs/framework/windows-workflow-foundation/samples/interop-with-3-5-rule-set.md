---
title: 3.5 규칙 집합과의 상호 운용성
ms.date: 03/30/2017
ms.assetid: 969f3295-d874-428c-a9c6-623e3d578e51
ms.openlocfilehash: 5ea5454ef80bfd83611ed20392782d99cd8c0c25
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44191250"
---
# <a name="interop-with-35-rule-set"></a>3.5 규칙 집합과의 상호 운용성
이 샘플의 사용법을 보여 줍니다.는 <xref:System.Activities.Statements.Interop> 에서 사용자 지정 활동과 통합 하는 활동 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 사용 하 여 <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` 및 규칙입니다. 이 샘플에서는 사용자 지정 활동에서 노출하는 종속성 속성에 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] 변수를 바인딩하여 사용자 지정 활동에 데이터를 전달합니다.  
  
## <a name="requirements"></a>요구 사항  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]  
  
2.  [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]  
  
3.  [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]  
  
## <a name="demonstrates"></a>세부 항목  
 <xref:System.Activities.Statements.Interop> 활동 <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` 활동에서 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 종속성 속성을 사용 하 여  
  
## <a name="discussion"></a>토론  
 이 샘플에서는 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 활동과의 통합에 대한 통합 시나리오 중 하나를 보여 줍니다. 이 샘플에 포함 되어는 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 를 호출 하는 사용자 지정 활동을 <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` 활동입니다.  
  
## <a name="travelrulelibrary"></a>TravelRuleLibrary  
 디자이너에서 TravelRuleSet.cs를 열면 다음과 같이 정책 활동이 들어 있는 사용자 지정 순차 활동이 표시됩니다.  
  
 ![Interop 활동](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulespolicy.jpg "InteropRulesPolicy")  
  
 두 번 클릭 합니다 **DiscountPolicy** 정책 활동 규칙을 검사 합니다. 규칙 편집기에 규칙이 표시됩니다.  
  
 ![규칙 집합 편집기](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesruleseteditor.jpg "InteropRulesRuleSetEditor")  
  
 마우스 오른쪽 단추로 클릭 합니다 **DiscountPolicy** 선택한 활동 합니다 **코드 보기** 코드 병행 C# 코드를이 작업을 검사 하는 옵션입니다. `DiscountLevel`의 종속성 속성 설정을 확인합니다. 이 설정은 <xref:System.Activities.Argument>의 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]에 해당합니다.  
  
```  
public static DependencyProperty DiscountLevelProperty = DependencyProperty.Register("DiscountLevel", typeof(int), typeof(TravelRuleSet));  
  
[DescriptionAttribute("DiscountLevel")]  
[CategoryAttribute("DiscountLevel Category")]  
[BrowsableAttribute(true)]  
[DesignerSerializationVisibilityAttribute(DesignerSerializationVisibility.Visible)]  
public int DiscountLevel  
{  
   get  
   {  
return ((int)base.GetValue(TravelRuleSet.DiscountLevelProperty)));  
   }  
   set  
   {  
base.SetValue(TravelRuleSet.DiscountLevelProperty, value);  
   }  
}  
```  
  
## <a name="interopwith35ruleset"></a>InteropWith35RuleSet  
 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] 활동을 사용하여 TravelRuleLibrary 프로젝트에 생성된 사용자 지정 규칙 집합과 통합하는 <xref:System.Activities.Statements.Interop> 순차 워크플로 프로젝트입니다. 다음과 같이 최상위 <xref:System.Activities.Statements.Sequence>에 변수가 만들어집니다.  
  
 ![변수](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesvariables.jpg "InteropRulesVariables")  
  
 ![솔루션 탐색기](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulessolutionexplorer.jpg "InteropRulesSolutionExplorer")  
  
 마지막으로 <xref:System.Activities.Statements.Interop> 활동을 사용하여 TravelRuleSet과 통합합니다. 이전에 <xref:System.Activities.Statements.Sequence>에 선언한 변수는 종속성 속성에 바인딩하는 데 사용됩니다.  
  
 ![활동 유형](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprules.jpg "InteropRules")  
  
 ![화살표](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesarrow.jpg "InteropRulesArrow")  
  
 ![속성](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesproperties.jpg "InteropRulesProperties")  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`
