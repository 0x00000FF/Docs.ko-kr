---
title: "WCF의 &lt;participants&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d99dbddc-0057-4e18-8e42-f91411d39970
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# WCF의 &lt;participants&gt;
런타임에서 내보내지는 추적 레코드를 수신하는 추적 참가자의 목록을 직접 구성하고 구성된 방식대로 처리합니다.  여기에는 특정 출력\(예: 파일, 콘솔, ETW\)에 쓰기, 레코드 처리\/집계 또는 필요한 기타 조합이 포함됩니다.  
  
 워크플로 추적 및 추적 참가자에 대한 자세한 내용은 [워크플로 추적](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md) 및 [추적 참가자](../../../../../docs/framework/windows-workflow-foundation//tracking-participants.md)를 참조하세요.  
  
## 구문  
  
```vb  
  
<tracking>   
   <participants>   
      <add name="String"   
           profileName="String"  
           type="String" />   
   </participants>   
</tracking>  
  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/add-of-participants.md)|추적 참가자에 대한 설정을 포함합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<tracking\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|워크플로 서비스에 대한 추적 설정을 정의하기 위한 구성 섹션을 나타냅니다.|  
  
## 설명  
 추적 참가자는 워크플로에서 내보내지는 추적 데이터를 가져오고 이 데이터를 다른 미디어에 저장하기 위해 사용됩니다.  마찬가지로 추적 레코드에 대한 모든 사후 처리를 추적 참가자 내에서 수행할 수도 있습니다.  
  
 여러 추적 참가자가 추적 이벤트를 동시에 사용할 수 있습니다.  각 추적 참가자는 서로 다른 추적 프로필과 연결될 수 있습니다.  
  
 ETW 세션에 추적 레코드를 작성하는 표준 추적 참가자가 제공됩니다.  추적 참가자는 워크플로 서비스에서 구성 파일에 추적별 동작을 추가하여 구성할 수 있습니다.  ETW 추적 참가자를 사용하여 이벤트 뷰어에서 추적 레코드를 볼 수 있습니다.  표준 참가자가 요구 사항에 맞지 않는 경우 사용자 지정 추적 참가자를 작성할 수도 있습니다.  
  
## 예제  
 다음 구성 예제에서는 Web.config 파일에서 구성되는 표준 ETW 추적 참가자를 보여 줍니다.  
  
 ETW 추적 참가자에서 ETW에 추적 레코드를 작성하기 위해 사용하는 공급자 ID는 `<diagnostics>` 섹션에서 정의됩니다.  추적 참가자에는 구독하는 추적 레코드를 지정하기 위해 연결된 프로필이 있습니다.  이 프로필은 `<add>` 요소의 `profileName` 특성에서 정의됩니다.  프로필이 정의되면 추적 참가자가 `<etwTracking>` 서비스 동작에 추가됩니다.  이렇게 하면 선택된 추적 참가자가 워크플로 인스턴스의 확장에 추가되어 추적 레코드를 받기 시작합니다.  
  
```  
  
<configuration>   
  <system.web>   
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>   
  </system.web>   
  <system.serviceModel>   
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />                
    <tracking>   
      <participants>   
        <add name="EtwTrackingParticipant"   
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
             profileName="HealthMonitoring_Tracking_Profile"/>   
      </participants>   
    </tracking>   
    <behaviors>   
      <serviceBehaviors>   
        <behavior>   
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>   
      </serviceBehaviors>   
    </behaviors>   
  </system.serviceModel>   
</configuration>  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>   
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>   
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehavior>   
 [워크플로 추적](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [추적 참가자](../../../../../docs/framework/windows-workflow-foundation//tracking-participants.md)