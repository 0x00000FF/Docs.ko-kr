---
title: "Bad checksum value, non hex digits or odd number of hex digits | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc42033"
  - "vbc42033"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42033"
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Bad checksum value, non hex digits or odd number of hex digits
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

체크섬 값의 16진수가 잘못되었거나 자릿수가 홀수입니다.  
  
 ASP.NET은 Visual Basic 소스 파일\(확장명 .vb\)을 생성할 때 체크섬을 계산하여 `#externalchecksum`으로 식별되는 숨겨진 소스 파일에 저장합니다.  .vb 파일을 생성하는 사용자도 이 작업을 수행할 수 있지만 해당 프로세스는 내부용으로 유지하는 것이 가장 좋습니다.  
  
 이 메시지는 기본적으로 경고입니다.  경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC42033  
  
### 이 오류를 해결하려면  
  
1.  ASP.NET에서 Visual Basic 소스 파일을 생성하는 경우 프로젝트 빌드를 다시 시작합니다.  
  
2.  빌드를 다시 시작한 후에도 이 경고가 계속 발생하면 ASP.NET을 다시 설치하고 빌드를 다시 시도합니다.  
  
3.  그래도 경고가 계속 발생하거나 ASP.NET을 사용하고 있지 않으면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.  
  
## 참고 항목  
 [ASP.NET Overview](../Topic/ASP.NET%20Overview.md)   
 [의견 보내기](/visual-studio/ide/talk-to-us)