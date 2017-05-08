---
title: "계약 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 계약
계약  
  
## 구문  
  
```  
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## 메서드  
 Contract 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 Contract 클래스에는 다음 속성이 있습니다.  
  
### AppDomainId  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 계약을 호스팅하는 appdomain의 appdomain ID입니다.  
  
### Behaviors  
 데이터 형식: Behavior array  
  
 액세스 형식: 읽기 전용  
  
 이 계약과 연결된 동작입니다.  
  
### Name  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 WSDL에 있는 계약의 이름입니다.  
  
### 네임스페이스  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 WSDL에 있는 `portType` 요소의 네임스페이스입니다.  
  
### Operations  
 데이터 형식: Operation array  
  
 액세스 형식: 읽기 전용  
  
 이 계약의 작업입니다.  
  
### ProcessId  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 계약을 호스팅하는 프로세스의 프로세스 ID입니다.  
  
### ref  
 데이터 형식: Contract  
  
 액세스 형식: 읽기 전용  
  
 계약이 이중 계약인 경우 콜백의 형식입니다.  
  
### SessionMode  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 계약에서 채널 세션을 사용하기 위해 이 계약과 연결된 바인딩이 필요한지 여부를 나타냅니다.  
  
### Type  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 계약의 형식입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|Namespace|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Description.ContractDescription>