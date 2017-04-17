---
title: "Flowchart 활동에서 TryCatch를 사용하여 오류 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Flowchart 활동에서 TryCatch를 사용하여 오류 처리
이 샘플에서는 복잡한 제어 흐름 활동 내에서 <xref:System.Activities.Statements.TryCatch> 활동을 사용하는 방법을 보여 줍니다.  
  
 이 샘플에서는 승격 코드에 해당하는 식을 기반으로 할인율을 계산하는 <xref:System.Activities.Statements.Flowchart> 활동에 승격 코드와 자식 수를 변수로 전달합니다.이 샘플에는 샘플의 명령적 코드 및 Workflow Designer 버전이 포함되어 있습니다.  
  
 다음 표에서는 `CreateFlowchartWithFaults` 활동의 변수에 대해 자세히 설명합니다.  
  
|매개 변수|설명|  
|-----------|--------|  
|promoCode|승격 코드입니다.형식: String<br /><br /> 가능한 값은 다음과 같으며 괄호 안에 설명이 포함되어 있습니다.<br /><br /> -   Single\(미혼\)<br />-   MNK\(기혼이지만 자녀는 없음\)<br />-   MWK\(기혼이며 자녀가 있음\)|  
|numKids|자식 수입니다.형식: int|  
  
 `CreateFlowchartWithFaults` 활동은 `promoCode` 인수로 전환하고 다음 수식을 사용하여 할인율을 계산하는 <xref:System.Activities.Statements.FlowSwitch%601> 활동을 사용합니다.  
  
|`promoCode`의 값|할인율\(%\)|  
|--------------------|--------------|  
|Single|10|  
|MNK|15|  
|MWK|15 \+ \(1 – 1\/`numberOfKids`\)\*10 **Note:**  이 계산에서 <xref:System.DivideByZeroException>을 throw할 수도 있으므로할인율 계산은 <xref:System.DivideByZeroException> 예외를 catch하고 할인율을 0으로 설정하는 <xref:System.Activities.Statements.TryCatch> 활동에 래핑됩니다.|  
  
#### 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 FlowchartWithFaultHandling.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  F5 키를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## 참고 항목  
 [순서도 워크플로](../../../../docs/framework/windows-workflow-foundation//flowchart-workflows.md)   
 [예외](../../../../docs/framework/windows-workflow-foundation//exceptions.md)