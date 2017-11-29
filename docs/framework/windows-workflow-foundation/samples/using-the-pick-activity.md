---
title: "Pick 활동 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5a95567afd955848b81bc343109acfe3fd138c7f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-pick-activity"></a>Pick 활동 사용
이 샘플에서는 <xref:System.Activities.Statements.Pick> 활동을 사용하는 방법을 보여 줍니다.  
  
 <xref:System.Activities.Statements.Pick> 활동은 이벤트 기반의 제어 모델링을 제공합니다. 이는 `switch` 문의 분기 중 하나에서만 실행되는 C# `switch` 문과 비슷한 방식으로 작동합니다. 그러나 값을 기준으로 분기가 실행되는 `switch` 문과 달리 <xref:System.Activities.Statements.Pick> 활동은 활동의 완료 방식을 기준으로 분기가 실행됩니다.  
  
 이 샘플에서는 지정된 시간 내에 사용자의 이름을 입력하라는 메시지를 콘솔에 표시합니다. 이 샘플의 <xref:System.Activities.Statements.Pick> 활동에는 사용자가 이름을 5초 안에 입력했는지 여부를 기준으로 실행되는 두 개의 분기가 있습니다. 사용자가 이름을 5초 안에 입력하면 사용자 지정 `ReadLine` 활동이 포함된 첫째 분기가 실행되고, 사용자가 이름을 5초 안에 입력하지 않으면 <xref:System.Activities.Statements.Delay> 활동이 포함된 둘째 분기가 실행됩니다. 사용자가 콘솔에 이름을 입력하고 나면 해당 이름이 콘솔에 출력됩니다. 이름을 5초 안에 입력하지 않으면 작업 제한 시간이 초과합니다.  
  
## <a name="demonstrates"></a>세부 항목  
 <xref:System.Activities.Statements.Pick> 활동  
  
## <a name="discussion"></a>토론  
 이 샘플에는 디자이너 워크플로와 코딩된 워크플로가 포함되어 있습니다.  
  
 디자이너 워크플로  
 디자이너 버전의 샘플에서는 디자이너를 사용하여 워크플로를 만드는 방법을 보여 줍니다. 여기에 포함되는 파일은 다음과 같습니다.  
  
-   Program.cs: 샘플 워크플로를 실행하는 `Main` 함수가 포함됩니다.  
  
-   ReadString.cs: 콘솔에서 입력을 읽는 사용자 지정 활동입니다.  
  
-   Sequence1.xaml: Pick을 사용하는 디자이너를 통해 만들어진 워크플로입니다.  
  
 코딩된 워크플로  
 코딩된 버전의 샘플에서는 코드를 사용하여 워크플로를 만드는 방법을 보여 줍니다. 여기에 포함되는 파일은 다음과 같습니다.  
  
-   Program.cs: 샘플 워크플로를 실행하는 `Main` 함수가 포함됩니다.  
  
-   ReadString.cs: 콘솔에서 입력을 읽는 사용자 지정 활동입니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 Pick.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  F5 키를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`  
  
## <a name="see-also"></a>참고 항목
