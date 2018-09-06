---
title: 오류 보내기 및 처리
ms.date: 03/30/2017
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
ms.openlocfilehash: 896f209e7daeeab2bb33c1fde15298aae96c8776
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43733367"
---
# <a name="sending-and-handling-faults"></a>오류 보내기 및 처리
이 샘플에서는 <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 메시징 활동을 사용하여 예상된 오류와 예기치 않은 오류를 주고받는 방법을 보여 줍니다. 이 시나리오에서는 맨 처음 클라이언트 요청의 결과로 <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> 컬렉션에 포함되어 있는 예상된 오류가 발생합니다. 그 이후 몇 번의 클라이언트 요청의 결과로 예기치 않은 오류가 발생한 다음 마지막 요청이 성공합니다.  
  
## <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  오픈 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 마우스 오른쪽 단추로 클릭 하 여 높은 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 아이콘을 선택 하 고 **관리자 권한으로 실행**합니다.  
  
2.  Faults.sln 솔루션 파일을 엽니다.  
  
3.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
4.  서비스 프로젝트를 실행합니다.  
  
    1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 `FaultService` 프로젝트를 마우스 **시작 프로젝트로 설정**합니다.  
  
    2.  Ctrl+F5를 누릅니다.  
  
5.  다른 복사본을 엽니다 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 마우스 오른쪽 단추로 클릭 하 여 높은 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 아이콘과 선택 **관리자 권한으로 실행**합니다.  
  
6.  Faults.sln 솔루션 파일을 엽니다.  
  
7.  클라이언트 프로젝트를 실행합니다.  
  
    1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 `FaultClient` 프로젝트를 마우스 **시작 프로젝트로 설정**합니다.  
  
    2.  Ctrl+F5를 누릅니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`