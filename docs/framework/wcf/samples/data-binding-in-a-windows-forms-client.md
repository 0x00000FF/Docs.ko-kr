---
title: "Windows 폼 클라이언트 내 데이터 바인딩 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Windows 폼 클라이언트 내 데이터 바인딩
이 샘플에서는 Windows Forms 응용 프로그램에서 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스에 의해 반환되는 데이터에 바인딩하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 문서의 끝부분에 나와 있습니다.  
  
 이 샘플에서는 요청\-회신 통신 패턴을 정의하는 계약을 구현하는 서비스를 보여 줍니다.이 샘플은 클라이언트 Windows Forms 응용 프로그램\(.exe\)과 IIS\(인터넷 정보 서비스\)에서 호스팅하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스로 구성됩니다.  
  
 계약은 `GetWeatherData`라는 작업을 노출시키는 `IWeatherService` 인터페이스에 의해 정의됩니다.이 작업은 도시 배열을 사용하여 도시의 최고 및 최저 예상 기온을 나타내는 `WeatherData` 개체의 배열을 반환합니다.  
  
 데이터 바인딩은 Windows Forms 응용 프로그램의 클라이언트에서 발생합니다.데이터의 그래픽 표시인 `DataGridView`는 Windows Forms 디자이너에서 정의됩니다.또한 `BindingSource`라는 매개자가 만들어집니다.`BindingSource`의 데이터 소스는 서비스에서 반환하는 데이터 배열로 설정됩니다.`BindingSource`의 용도는 데이터와 데이터 뷰 간의 간접 참조 계층을 제공하기 위한 것입니다.탐색, 정렬, 필터링 및 업데이트와 같은 데이터와의 모든 상호 작용은 `BindingSource` 구성 요소를 호출하여 수행됩니다.`DataGridView`에 대해 데이터 바인딩을 수행하려면 `DataGridView`의 `datasource`를 `BindingSource` 개체로 설정합니다.그러면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 반환된 모든 데이터가 그래픽으로 표시됩니다.사용자가 단추를 클릭할 때마다 반환된 데이터가 데이터 바인딩된 `DataGridView`에 자동으로 업데이트됩니다.  
  
### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행했는지 확인합니다.  
  
2.  C\# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)의 지침을 따릅니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
  
## 참고 항목