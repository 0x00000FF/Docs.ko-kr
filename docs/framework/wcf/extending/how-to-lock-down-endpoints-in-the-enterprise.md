---
title: '방법: 엔터프라이즈에서 끝점 잠그기'
ms.date: 03/30/2017
ms.assetid: 1b7eaab7-da60-4cf7-9d6a-ec02709cf75d
ms.openlocfilehash: 4ec14193bdcc24722ad8e2259781c4c185f3ca3f
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-lock-down-endpoints-in-the-enterprise"></a>방법: 엔터프라이즈에서 끝점 잠그기
대형 엔터프라이즈에서는 응용 프로그램을 엔터프라이즈 보안 정책에 따라 개발해야 하는 경우가 종종 있습니다. 다음 항목에서는 개발 하 고 컴퓨터에 설치 된 모든 Windows Communication Foundation (WCF) 클라이언트 응용 프로그램이 유효성을 검사 하는 데 사용할 수 있는 클라이언트 끝점 유효성 검사기를 설치 하는 방법에 설명 합니다.  
  
 이 끝점 동작은 클라이언트에 추가 되기 때문에 유효성 검사기는 클라이언트 유효성 검사기가이 경우 [ \<c o m m >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) machine.config 파일의 섹션입니다. WCF는 클라이언트 응용 프로그램에 대 한 공통 끝점 동작을 로드 하 고 서비스 응용 프로그램에 대 한 공통 서비스 동작을 로드 합니다. 서비스 응용 프로그램에 동일한 유효성 검사기를 설치하려면 유효성 검사기가 서비스 동작이어야 합니다. 자세한 내용은 참조는 [ \<c o m m >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) 섹션.  
  
> [!IMPORTANT]
>  서비스 또는 끝점 동작으로 표시 되어 있지는 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성 (APTCA)에 추가 되는 [ \<c o m m >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) 구성 파일의 섹션에는 응용 프로그램이 부분 신뢰에서 실행 될 때 실행 되지 않습니다 이 경우 환경과 예외가 throw 됩니다. 유효성 검사기와 같은 일반 동작을 실행하려면 다음을 수행해야 합니다.  
>   
>  -- 부분 신뢰 응용 프로그램으로 배포될 때 실행될 수 있도록 일반 동작을 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성으로 표시합니다. APTCA로 표시된 어셈블리가 실행되지 않도록 컴퓨터에 레지스트리 항목을 설정할 수 있습니다.  
>   
>  -- 부분 신뢰 환경에서 응용 프로그램을 실행하기 위해 사용자가 코드 액세스 보안 설정을 수정할 수 없는 완전 신뢰 응용 프로그램으로서 응용 프로그램이 배포되는지 확인합니다. 사용자가 보안 설정을 수정할 수 있는 경우 사용자 지정 유효성 검사기가 실행되지 않고 예외가 throw되지 않습니다. 이 보장 하 한 가지 방법은 참조는 `levelfinal` 옵션을 사용 하 여 [코드 액세스 보안 정책 도구 (Caspol.exe)](http://go.microsoft.com/fwlink/?LinkId=248222)합니다.  
>   
>  자세한 내용은 참조 [부분 신뢰 모범 사례](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) 및 [배포 시나리오 지원](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md)합니다.  
  
### <a name="to-create-the-endpoint-validator"></a>끝점 유효성 검사기를 만들려면  
  
1.  <xref:System.ServiceModel.Description.IEndpointBehavior> 메서드의 원하는 유효성 검사 단계를 사용하여 <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A>를 만듭니다. 코드 예제는 다음과 같습니다. (의 `InternetClientValidatorBehavior` 에서 가져온 것은 [보안 유효성 검사](../../../../docs/framework/wcf/samples/security-validation.md) 샘플.)  
  
     [!code-csharp[LockdownValidation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorbehavior.cs#2)]  
  
2.  1단계에서 만든 끝점 유효성 검사기를 등록할 새 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>를 만듭니다. 다음 코드 예제에서는 이를 보여 줍니다. (이 예제에 대 한 원본 코드는 [보안 유효성 검사](../../../../docs/framework/wcf/samples/security-validation.md) 샘플.)  
  
     [!code-csharp[LockdownValidation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorelement.cs#3)]  
  
3.  컴파일된 어셈블리가 강력한 이름으로 서명되어 있는지 확인합니다. 자세한 내용은 참조는 [강력한 이름 도구 (SN입니다. EXE)](http://go.microsoft.com/fwlink/?LinkId=248217) 및 해당 하는 언어에 대 한 컴파일러 명령입니다.  
  
### <a name="to-install-the-validator-into-the-target-computer"></a>대상 컴퓨터에 유효성 검사기를 설치하려면  
  
1.  적절한 메커니즘을 사용하여 끝점 유효성 검사기를 설치합니다. 엔터프라이즈에서는 그룹 정책 및 SMS(Systems Management Server)를 사용해 수행할 수 있습니다.  
  
2.  강력한 이름의 어셈블리를 사용 하 여 전역 어셈블리 캐시에 설치 된 [Gacutil.exe (전역 어셈블리 캐시 도구)](http://msdn.microsoft.com/library/ex0ss12c\(v=vs.110\).aspx)합니다.  
  
3.  다음 작업에 <xref:System.Configuration?displayProperty=nameWithType> 네임스페이스 형식을 사용합니다.  
  
    1.  확장을 추가 [ \<behaviorExtensions >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md) 완전히 정규화 된 유형 이름을 사용 하 여 섹션 및 고 요소를 잠급니다.  
  
         [!code-csharp[LockdownValidation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#5)]  
  
    2.  동작 요소를 추가 `EndpointBehaviors` 의 속성은 [ \<c o m m >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) 섹션 및 고 요소를 잠급니다. 서비스에 유효성 검사기를 설치하려면 유효성 검사기가 <xref:System.ServiceModel.Description.IServiceBehavior>이어야 하며 `ServiceBehaviors` 속성에 추가되어야 합니다. 다음 코드 예제에서는 a 및 b 단계 후 올바른 구성을 보여 줍니다. 단, 강력한 이름이 없다는 한 가지 예외가 있습니다.  
  
         [!code-csharp[LockdownValidation#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#6)]  
  
    3.  machine.config 파일을 저장합니다. 다음 코드 예제에서는 3단계의 모든 작업을 수행하며 수정된 machine.config 파일의 복사본을 로컬에 저장합니다.  
  
         [!code-csharp[LockdownValidation#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#7)]  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 일반 동작을 machine.config 파일에 추가하고 복사본을 디스크에 저장하는 방법을 보여 줍니다. `InternetClientValidatorBehavior` 에서 가져온 것은 [보안 유효성 검사](../../../../docs/framework/wcf/samples/security-validation.md) 샘플.  
  
 [!code-csharp[LockdownValidation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#1)]  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 구성 파일 요소를 암호화할 수도 있습니다. 자세한 내용은 참고 항목 단원을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [DPAPI를 사용 하 여 구성 파일 요소 암호화](http://go.microsoft.com/fwlink/?LinkId=94954)  
 [RSA를 사용 하 여 구성 파일 요소 암호화](http://go.microsoft.com/fwlink/?LinkId=94955)
