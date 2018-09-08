---
title: .NET Framework의 보안 변경 내용
ms.date: 03/30/2017
helpviewer_keywords:
- Allow Partially Trusted Callers attribute
- .NET Framework 4, security changes
- .NET Framework security
- security-transparent code
- security-critical code
- code access security, changes
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c62a469b3e31283e5790c747092a8fe504ef8c2a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44191913"
---
# <a name="security-changes-in-the-net-framework"></a>.NET Framework의 보안 변경 내용
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 에서 보안에 대한 가장 중요한 변경 내용은 강력한 이름 지정입니다. 변경에 대한 설명은 [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) 을 참조하세요.  
  
 .NET Framework는 관리되는 응용 프로그램에 대한 2계층 보안 모델을 제공합니다. [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램은 리소스에 대한 액세스를 제한하는 Windows 보안 컨테이너에서 실행됩니다. 해당 컨테이너 내에서 관리되는 응용 프로그램은 완전히 신뢰할 수 있는 상태로 실행됩니다. CAS(코드 액세스 보안) 측면에서 개발자가 권한을 높이기 위해 수행할 수 있는 작업이 없습니다. Windows에서 부여된 권한에 대한 자세한 내용은 Windows 개발자 센터의 [앱 기능 선언(Windows 스토어 앱)](https://go.microsoft.com/fwlink/?LinkId=230436) 을 참조하세요. [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱 만들기에 대한 자세한 내용은 [C# 또는 Visual Basic을 사용하여 첫 Windows 스토어 앱 만들기](https://go.microsoft.com/fwlink/?LinkId=230461)를 참조하세요.
