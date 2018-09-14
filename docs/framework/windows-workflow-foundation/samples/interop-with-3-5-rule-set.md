---
title: 3.5 규칙 집합과의 상호 운용성
ms.date: 03/30/2017
ms.assetid: 969f3295-d874-428c-a9c6-623e3d578e51
ms.openlocfilehash: 5ea5454ef80bfd83611ed20392782d99cd8c0c25
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45510149"
---
# <a name="interop-with-35-rule-set"></a><span data-ttu-id="ffb00-102">3.5 규칙 집합과의 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="ffb00-102">Interop with 3.5 Rule Set</span></span>
<span data-ttu-id="ffb00-103">이 샘플의 사용법을 보여 줍니다.는 <xref:System.Activities.Statements.Interop> 에서 사용자 지정 활동과 통합 하는 활동 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 사용 하 여 <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` 및 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-103">This sample demonstrates the use of the <xref:System.Activities.Statements.Interop> activity to integrate with a custom activity in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] using <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` and rules.</span></span> <span data-ttu-id="ffb00-104">이 샘플에서는 사용자 지정 활동에서 노출하는 종속성 속성에 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] 변수를 바인딩하여 사용자 지정 활동에 데이터를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-104">It passes data to the custom activity by binding [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] variables to the dependency properties exposed by the custom activity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffb00-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ffb00-105">Requirements</span></span>  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]  
  
2.  [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]  
  
3.  [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]  
  
## <a name="demonstrates"></a><span data-ttu-id="ffb00-106">세부 항목</span><span class="sxs-lookup"><span data-stu-id="ffb00-106">Demonstrates</span></span>  
 <span data-ttu-id="ffb00-107"><xref:System.Activities.Statements.Interop> 활동 <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` 활동에서 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 종속성 속성을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="ffb00-107"><xref:System.Activities.Statements.Interop> activity, <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` activity in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] with dependency properties</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="ffb00-108">토론</span><span class="sxs-lookup"><span data-stu-id="ffb00-108">Discussion</span></span>  
 <span data-ttu-id="ffb00-109">이 샘플에서는 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 활동과의 통합에 대한 통합 시나리오 중 하나를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-109">The sample demonstrates one of the integration scenarios for integrating with a [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] activity.</span></span> <span data-ttu-id="ffb00-110">이 샘플에 포함 되어는 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 를 호출 하는 사용자 지정 활동을 <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-110">This sample includes a [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] custom activity that invokes a <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` activity.</span></span>  
  
## <a name="travelrulelibrary"></a><span data-ttu-id="ffb00-111">TravelRuleLibrary</span><span class="sxs-lookup"><span data-stu-id="ffb00-111">TravelRuleLibrary</span></span>  
 <span data-ttu-id="ffb00-112">디자이너에서 TravelRuleSet.cs를 열면 다음과 같이 정책 활동이 들어 있는 사용자 지정 순차 활동이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-112">Opening TravelRuleSet.cs in the designer shows a custom sequential activity that contains a Policy activity as follows</span></span>  
  
 <span data-ttu-id="ffb00-113">![Interop 활동](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulespolicy.jpg "InteropRulesPolicy")</span><span class="sxs-lookup"><span data-stu-id="ffb00-113">![Interop Activity](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulespolicy.jpg "InteropRulesPolicy")</span></span>  
  
 <span data-ttu-id="ffb00-114">두 번 클릭 합니다 **DiscountPolicy** 정책 활동 규칙을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-114">Double-click the **DiscountPolicy** policy activity to examine the rules.</span></span> <span data-ttu-id="ffb00-115">규칙 편집기에 규칙이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-115">The Rules editor appears to show the rules.</span></span>  
  
 <span data-ttu-id="ffb00-116">![규칙 집합 편집기](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesruleseteditor.jpg "InteropRulesRuleSetEditor")</span><span class="sxs-lookup"><span data-stu-id="ffb00-116">![Rule Set Editor](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesruleseteditor.jpg "InteropRulesRuleSetEditor")</span></span>  
  
 <span data-ttu-id="ffb00-117">마우스 오른쪽 단추로 클릭 합니다 **DiscountPolicy** 선택한 활동 합니다 **코드 보기** 코드 병행 C# 코드를이 작업을 검사 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-117">Right-click the **DiscountPolicy** activity and select the **View Code** option to examine the code-beside C# code that goes with this activity.</span></span> <span data-ttu-id="ffb00-118">`DiscountLevel`의 종속성 속성 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-118">Observe the dependency property setting for `DiscountLevel`.</span></span> <span data-ttu-id="ffb00-119">이 설정은 <xref:System.Activities.Argument>의 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-119">This is equivalent to an <xref:System.Activities.Argument> in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span></span>  
  
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
  
## <a name="interopwith35ruleset"></a><span data-ttu-id="ffb00-120">InteropWith35RuleSet</span><span class="sxs-lookup"><span data-stu-id="ffb00-120">InteropWith35RuleSet</span></span>  
 <span data-ttu-id="ffb00-121">[!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] 활동을 사용하여 TravelRuleLibrary 프로젝트에 생성된 사용자 지정 규칙 집합과 통합하는 <xref:System.Activities.Statements.Interop> 순차 워크플로 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-121">This is a [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] sequential workflow project that uses the <xref:System.Activities.Statements.Interop> activity to integrate with the custom rule set created in the TravelRuleLibrary project.</span></span> <span data-ttu-id="ffb00-122">다음과 같이 최상위 <xref:System.Activities.Statements.Sequence>에 변수가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-122">Variables are created on the top-level <xref:System.Activities.Statements.Sequence> as follows.</span></span>  
  
 <span data-ttu-id="ffb00-123">![변수](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesvariables.jpg "InteropRulesVariables")</span><span class="sxs-lookup"><span data-stu-id="ffb00-123">![Variables](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesvariables.jpg "InteropRulesVariables")</span></span>  
  
 <span data-ttu-id="ffb00-124">![솔루션 탐색기](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulessolutionexplorer.jpg "InteropRulesSolutionExplorer")</span><span class="sxs-lookup"><span data-stu-id="ffb00-124">![Solution Explorer](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulessolutionexplorer.jpg "InteropRulesSolutionExplorer")</span></span>  
  
 <span data-ttu-id="ffb00-125">마지막으로 <xref:System.Activities.Statements.Interop> 활동을 사용하여 TravelRuleSet과 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-125">Lastly, the <xref:System.Activities.Statements.Interop> activity is used to integrate with the TravelRuleSet.</span></span> <span data-ttu-id="ffb00-126">이전에 <xref:System.Activities.Statements.Sequence>에 선언한 변수는 종속성 속성에 바인딩하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-126">The variables that were declared earlier on the <xref:System.Activities.Statements.Sequence> are used to bind to the dependency properties.</span></span>  
  
 <span data-ttu-id="ffb00-127">![활동 유형](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprules.jpg "InteropRules")</span><span class="sxs-lookup"><span data-stu-id="ffb00-127">![Activity Type](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprules.jpg "InteropRules")</span></span>  
  
 <span data-ttu-id="ffb00-128">![화살표](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesarrow.jpg "InteropRulesArrow")</span><span class="sxs-lookup"><span data-stu-id="ffb00-128">![Arrow](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesarrow.jpg "InteropRulesArrow")</span></span>  
  
 <span data-ttu-id="ffb00-129">![속성](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesproperties.jpg "InteropRulesProperties")</span><span class="sxs-lookup"><span data-stu-id="ffb00-129">![Properties](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesproperties.jpg "InteropRulesProperties")</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ffb00-130">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ffb00-131">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ffb00-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ffb00-132">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="ffb00-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ffb00-133">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffb00-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`
