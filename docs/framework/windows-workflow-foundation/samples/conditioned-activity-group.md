---
title: "조건화된 활동 그룹"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f76ef924-34ce-48ae-8c8d-48faf9697754
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e0df4ddc6f2cc5404c8153b30df66cda41487691
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="conditioned-activity-group"></a>조건화된 활동 그룹
이 샘플에서는 여행 예약 응용 프로그램을 보여 줍니다. <xref:System.Workflow.Activities.ConditionedActivityGroup>(CAG)에는 Car 동작과 Airline 동작이라는 두 개의 코드 동작이 있습니다. `SimpleCAGWorkflow` 생성자에서 "travelNeedType" ArrayList 개체는 필요한 여행 예약 유형으로 채워집니다. `travelNeeds.Add` 문 중 하나 또는 두 개 모두를 주석으로 처리하여 이에 맞게 CAG 동작을 수정합니다. Car 동작과 Airline 동작 모두 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> 조건이 <xref:System.Workflow.Activities.CodeCondition>으로 채워집니다. Car 동작은 `travelNeeds` 컬렉션에 `TravelNeeds.Car` 항목이 있을 때만 실행되고, Airline 동작은 `travelNeeds` 컬렉션에 `TravelNeeds.Airline` 항목이 있을 때만 실행됩니다.  
  
 각 동작이 실행되면 해당 항목이 컬렉션에서 제거됩니다. 기본 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> 조건은 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> 조건에 따라 실행 중이거나 실행 준비된 자식 항목이 없을 경우 CAG가 종료되도록 지정합니다. 이 샘플에서는 `travelNeeds` 컬렉션이 비어 있을 때 CAG가 종료됩니다.  
  
### <a name="to-build-the-sample"></a>이 샘플을 빌드하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 솔루션을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 디버깅 없이 솔루션을 실행합니다.  
  
### <a name="to-run-the-sample"></a>이 샘플을 실행하려면  
  
-   SDK 명령 프롬프트 창에서 샘플의 주 폴더 아래에 있는 SimpleCAG\bin\debug 폴더 또는 SimpleCAG\bin 폴더(Visual Basic 버전 샘플의 경우)의 .exe 파일을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\SimpleCAG`  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Workflow.Activities.ConditionedActivityGroup>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>  
 <xref:System.Workflow.Activities.CodeCondition>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>
