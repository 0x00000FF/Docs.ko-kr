---
title: Authorizing Access to Service Operations
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2bcd3739cebf852e69cc2551350a83e247274e0a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="authorizing-access-to-service-operations"></a>Authorizing Access to Service Operations
이 샘플에 사용 하는 방법을 보여 줍니다는 [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) 사용할 수 있도록는 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 특성을 서비스 작업에 대 한 액세스 권한을 부여 합니다. 이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 샘플. 서비스와 클라이언트를 사용 하 여 구성 된는 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)합니다. `mode` 특성에는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 가로 설정 된 `Message` 및 `clientCredentialType` 가로 설정 된 `Windows`합니다. <xref:System.Security.Permissions.PrincipalPermissionAttribute>는 각 서비스 메서드에 적용되고 각 작업에 대한 액세스를 제한하는 데 사용됩니다. 호출자는 각 작업에 액세스하기 위해 Windows 관리자여야 합니다.  
  
 이 샘플에서 클라이언트는 콘솔 응용 프로그램(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 서비스 구성 파일에서는 [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) 설정 하 여 `principalPermissionMode` 특성:  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior>   
      <!-- The serviceAuthorization behavior sets the  
           principalPermissionMode to UseWindowsGroups.  
           This puts a WindowsPrincipal on the current thread when a   
           service is invoked. -->  
      <serviceAuthorization principalPermissionMode="UseWindowsGroups" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 `principalPermissionMode`를 `UseWindowsGroups`로 설정하면 Windows 그룹 이름에 기초하여 <xref:System.Security.Permissions.PrincipalPermissionAttribute>를 사용할 수 있게 됩니다.  
  
 다음 샘플 코드와 같이 <xref:System.Security.Permissions.PrincipalPermissionAttribute>가 각 작업에 적용되어 호출자가 Windows 관리자 그룹의 일부여야 한다는 것을 요구합니다.  
  
```  
[PrincipalPermission(SecurityAction.Demand,   
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다. 클라이언트는 관리자 그룹의 일부인 계정으로 실행 중인 경우 각 작업과 통신할 수 있고, 그렇지 않은 경우 액세스가 거부됩니다. 권한 부여 오류를 테스트하려면 관리자 그룹의 일부가 아닌 계정으로 클라이언트를 실행합니다. 클라이언트를 종료하려면 콘솔 창에서 Enter 키를 누릅니다.  
  
 <xref:System.ServiceModel.Dispatcher.IErrorHandler>를 구현하여 권한 부여 오류를 서비스에 알릴 수 있습니다. 참조 [확장 제어를 통해 오류를 처리 하 고 보고](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) 구현에 대 한 내용은 `IErrorHandler`합니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
## <a name="see-also"></a>참고 항목
