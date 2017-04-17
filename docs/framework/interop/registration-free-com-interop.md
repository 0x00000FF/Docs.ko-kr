---
title: "등록이 필요 없는 COM Interop | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "어셈블리[.NET Framework], interop"
  - "COM interop, 등록이 필요 없는 COM interop"
  - "매니페스트[.NET Framework]"
  - "개체 활성화"
  - "등록이 필요 없는 활성화"
  - "등록이 필요 없는 COM interop"
  - "등록이 필요 없는 COM interop, 등록이 필요 없는 COM interop 정보"
ms.assetid: 90f308b9-82dc-414a-bce1-77e0155e56bd
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 등록이 필요 없는 COM Interop
등록이 필요 없는 COM interop는 Windows 레지스트리를 사용하여 어셈블리 정보를 저장하지 않고 구성 요소를 활성화합니다.  배포 중 컴퓨터에 구성 요소를 등록하는 대신 바인딩 및 활성화 정보를 포함하는 Win32 스타일의 매니페스트 파일을 디자인 타임에 만듭니다.  레지스트리 키 대신 이러한 매니페스트 파일에서 개체 활성화를 지시합니다.  
  
 배포 중에 등록하는 대신 어셈블리에 대해 등록이 필요 없는 활성화를 사용하면 다음 두 가지 이점이 있습니다.  
  
-   컴퓨터에 둘 이상의 버전을 설치할 때 활성화되는 DLL 버전을 제어할 수 있습니다.  
  
-   최종 사용자는 XCOPY 또는 FTP를 사용하여 해당 컴퓨터의 적절한 디렉터리에 응용 프로그램을 복사할 수 있습니다.  그런 다음 해당 디렉터리에서 응용 프로그램을 실행할 수 있습니다.  
  
 이 섹션에서는 등록이 필요 없는 COM interop에 필요한 두 가지 매니페스트 유형인 응용 프로그램 및 구성 요소 매니페스트를 설명합니다.  이러한 매니페스트는 XML 파일입니다.  응용 프로그램 개발자가 만드는 응용 프로그램 매니페스트에는 어셈블리와 어셈블리 종속성을 설명하는 메타데이터가 포함됩니다.  구성 요소 개발자가 만드는 구성 요소 매니페스트에는 그러지 않은 경우 Windows 레지스트리에 있는 정보가 포함됩니다.  
  
### 등록이 필요 없는 COM Interop에 대한 요구 사항  
  
1.  등록이 필요 없는 COM interop에 대한 지원은 라이브러리 어셈블리 형식, 특히 어셈블리가 관리되지 않는지\(COM Side\-by\-side\) 또는 관리되는지\(.NET 기반\)에 따라 약간씩 다릅니다.  다음 표에서는 각 어셈블리의 형식에 대한 운영 체제 및 .NET Framework 버전 요구 사항을 보여 줍니다.  
  
    |어셈블리 형식|운영 체제|.NET Framework 버전|  
    |-------------|-----------|-----------------------|  
    |동시 Side\-by\-side|Microsoft Windows XP|필요하지 않음.|  
    |.NET 기반|Windows XP SP2|.NET Framework 버전 1.1 이상|  
  
     Windows Server 2003 제품군은 .NET 기반 어셈블리에 대해서도 등록이 필요 없는 COM interop를 지원합니다.  
  
     .NET 기반 클래스가 COM의 등록이 필요 없는 활성화와 호환되려면 클래스에 기본 생성자가 있어야 하고 public이어야 합니다.  
  
### 등록이 필요 없는 활성화를 위한 COM 구성 요소 구성  
  
1.  COM 구성 요소가 등록이 필요 없는 활성화에 참여하려면 Side\-by\-side 어셈블리로 배포되어야 합니다.  Side\-by\-side 어셈블리는 관리되지 않는 어셈블리입니다.  자세한 내용은 MSDN 라이브러리에서 “Side\-by\-side 어셈블리 사용”을 참조하세요.  
  
     COM Side\-by\-side\-어셈블리를 사용하려면 .NET 기반 응용 프로그램 개발자가 바인딩 및 활성화 정보를 포함하는 응용 프로그램 매니페스트를 제공해야 합니다.  관리되지 않는 Side\-by\-side 어셈블리에 대한 지원은 Windows XP 운영 체제에 기본 제공됩니다.  운영 체제에서 지원하는 COM 런타임은 활성화되는 구성 요소가 레지스트리에 없는 경우 응용 프로그램 매니페스트에서 활성화 정보를 검색합니다.  
  
     Windows XP에 설치된 COM 구성 요소의 경우 등록이 필요 없는 활성화는 선택 사항입니다.  Side\-by\-side 어셈블리를 응용 프로그램에 추가하는 방법에 대한 자세한 내용을 보려면 MSDN 라이브러리에서 "Side\-by\-side 어셈블리 사용"을 검색하세요.  
  
    > [!NOTE]
    >  Side\-by\-side 실행은 여러 버전의 런타임 및 특정 런타임 버전을 사용하는 여러 버전의 응용 프로그램 및 구성 요소가 동시에 같은 컴퓨터에서 실행될 수 있도록 하는 .NET Framework 기능입니다.  Side\-by\-side 실행 및 Side\-by\-side 어셈블리는 Side\-by\-side 기능을 제공하는 서로 다른 메커니즘입니다.  
  
## 참고 항목  
 [방법: 등록이 필요 없는 활성화를 위한 .NET Framework 기반 COM 구성 요소 구성](../../../docs/framework/interop/configure-net-framework-based-com-components-for-reg.md)