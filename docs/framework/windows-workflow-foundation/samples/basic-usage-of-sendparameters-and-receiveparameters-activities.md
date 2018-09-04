---
title: SendParameters 및 ReceiveParameters 활동의 기본 사용법
ms.date: 03/30/2017
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
ms.openlocfilehash: c13999ad1571a6413e30e801b6c642000f8e4654
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504010"
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a>SendParameters 및 ReceiveParameters 활동의 기본 사용법
이 샘플에서는 <xref:System.ServiceModel.Activities.SendParametersContent> 및 <xref:System.ServiceModel.Activities.ReceiveParametersContent> 활동의 사용 방법을 보여 줍니다. 서비스에서는 문자열 인수를 받는 하나의 작업을 노출하고 해당 입력을 클라이언트에 다시 보냅니다. 이 샘플에서는 이러한 메시징 활동의 매개 변수를 설정하는 방법을 보여 줍니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a>이 샘플의 사용법  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에 프로젝트 솔루션을 로드하고 프로젝트를 빌드합니다.  
  
2.  먼저 [solution base directory]\EchoWorkflowService\bin\debug에 생성된 EchoWorkflowService 응용 프로그램을 실행합니다.  
  
3.  그 다음 [solution base directory]\EchoWorkflowClient\bin\debug에 생성된 EchoWorkflowClient 응용 프로그램을 실행합니다.  
  
4.  클라이언트에서 서비스에 대한 Echo 작업을 호출하고 결과를 출력합니다. 완료되면 Enter 키를 눌러 클라이언트와 서비스를 차례로 종료합니다.