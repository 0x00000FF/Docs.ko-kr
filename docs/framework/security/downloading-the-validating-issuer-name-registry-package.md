---
title: "발급자 이름 레지스트리 유효성 검사 패키지 다운로드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
caps.latest.revision: 3
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 3
---
# 발급자 이름 레지스트리 유효성 검사 패키지 다운로드
이 항목에서는 프로젝트에서 VINR\(유효성 검사 발급자 이름 레지스트리\)을 다운로드하고 사용하는 방법에 대해 설명합니다.  
  
## 유효성 검사 발급자 이름 레지스트리 다운로드  
 VINR은 프로젝트에 필요한 어셈블리 및 참조를 추가하는 NuGet 패키지로 사용할 수 있습니다.  NuGet이 아직 설치되지 않은 경우 [nuget.org](http://nuget.org)으로 이동하여 설치하십시오.  NuGet의 해당 페이지 [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)를 방문하여 확장에 대한 버전 기록을 볼 수 있습니다.  
  
#### 패키지 관리자 GUI를 사용하여 유효성 검사 발급자 이름 레지스트리 다운로드  
  
1.  Visual Studio의 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **NuGet 패키지 관리**를 선택합니다.  
  
2.  **NuGet 패키지 관리** 창에서 검색 상자를 클릭하고 `ValidatingIssuerNameRegistry`를 입력한 후 **Enter** 키를 누릅니다.  
  
3.  결과 창에서 **설치** 단추를 클릭하여 첫 번째 결과를 확인합니다.  
  
4.  패키지 다운로드가 시작됩니다.  프로젝트에 추가하기 전에 라이센스 수락 대화 상자가 나타납니다.  라이선스 약관에 동의하면 **동의함**을 클릭합니다.  
  
5.  최신 VINR 어셈블리가 다운로드되고 프로젝트에 추가됩니다.  
  
#### 패키지 관리자 콘솔을 사용하여 유효성 검사 발급자 이름 레지스트리 다운로드  
  
1.  Visual Studio 에서 **도구**, **라이브러리 패키지 관리자**, **패키지 관리자 콘솔**을 클릭합니다.  
  
2.  **패키지 관리자 콘솔** 창이 열립니다.  다음 텍스트를 입력하고 **Enter** 키를 누릅니다.  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry  
    ```  
  
3.  최신 VINR 어셈블리가 다운로드되고 프로젝트에 추가됩니다.