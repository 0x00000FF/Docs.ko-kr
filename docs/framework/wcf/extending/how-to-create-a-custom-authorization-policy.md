---
title: "방법: 사용자 지정 권한 부여 정책 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 05b0549b-882d-4660-b6f0-5678543e5475
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# 방법: 사용자 지정 권한 부여 정책 만들기
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 ID 모델 인프라에서는 클레임 기반의 권한 부여 모델을 지원합니다.클레임은 토큰에서 추출되어 사용자 지정 권한 부여 정책에 의해 선택적으로 처리된 다음,이후에 권한 부여를 결정하기 위해 검사할 수 있는 <xref:System.IdentityModel.Policy.AuthorizationContext>에 배치됩니다.사용자 지정 정책은 들어오는 토큰을 응용 프로그램에서 필요로 하는 클레임으로 변환하는 데 사용할 수 있습니다.이런 방식에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 지원하는 다른 토큰 유형이 사용된 서로 다른 클레임에 대한 세부 사항이 응용 프로그램 계층에 적용되지 않을 수 있습니다.이 항목에서는 사용자 지정 권한 부여 정책을 구현하는 방법과 이 정책을 서비스에 사용된 정책 컬렉션에 추가하는 방법에 대해 설명합니다.  
  
### 사용자 지정 권한 부여 정책을 구현하려면  
  
1.  <xref:System.IdentityModel.Policy.IAuthorizationPolicy>에서 파생되는 새 클래스를 정의합니다.  
  
2.  클래스에 대해 생성자에서 고유 문자열을 생성하고 속성에 액세스할 때마다 해당 문자열을 반환하여 읽기 전용 <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> 속성을 구현합니다.  
  
3.  정책 발급자를 나타내는<xref:System.IdentityModel.Claims.ClaimSet>를 반환하여 읽기 전용 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A> 속성을 구현합니다.이는 응용 프로그램을 나타내는 `ClaimSet`이거나 기본 제공된`ClaimSet`\(예를 들면 정적 <xref:System.IdentityModel.Claims.ClaimSet.System%2A> 속성에 의해 반환된 `ClaimSet`\)일 수 있습니다.  
  
4.  다음 절차에 따라 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> 메서드를 구현합니다.  
  
### Evaluate 메서드를 구현하려면  
  
1.  두 매개 변수인 개체 참조와 <xref:System.IdentityModel.Policy.EvaluationContext> 클래스의 인스턴스를 이 메서드에 전달합니다.  
  
2.  <xref:System.IdentityModel.Policy.EvaluationContext>의 현재 콘텐츠에 관계없이 사용자 지정 권한 부여 정책을 통해 <xref:System.IdentityModel.Claims.ClaimSet> 인스턴스를 추가하려면, <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> 메서드를 호출하여 각 `ClaimSet`를 추가하고 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> 메서드에서 `true`를 반환합니다.`true`가 반환되면 권한 부여 정책의 작업이 수행되어 이를 다시 호출할 필요가 없음을 권한 부여 인프라에 알립니다.  
  
3.  특정 클레임이 `EvaluationContext`에 이미 있는 경우에만 사용자 지정 권한 부여 정책을 통해 클레임 집합을 추가하려면 <xref:System.IdentityModel.Policy.EvaluationContext.ClaimSets%2A> 속성에 의해 반환된 `ClaimSet` 인스턴스를 검사하여 이러한 클레임을 찾습니다.클레임이 있으면 <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> 메서드를 호출하여 새로운 클레임 집합을 추가하고, 추가할 클레임 집합이 없으면 권한 부여 정책의 작업이 완료되었음을 권한 부여 인프라에 알리는 `true`를 반환합니다.클레임이 없으면 `false`를 반환하는 데, 이는 다른 권한 부여 정책을 통해 클레임 집합을 `EvaluationContext`에 추가하려면 권한 부여 정책을 다시 호출해야 함을 알립니다.  
  
4.  더 복잡한 처리 시나리오에서는 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> 메서드의 두 번째 매개 변수를 사용하여 상태 변수를 저장합니다. 이 상태 변수는 이후 각 호출 동안 특정 평가를 목적으로 권한 부여 인프라가 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> 메서드에 다시 전달하는 변수입니다.  
  
### 구성을 통해 사용자 지정 권한 부여 정책을 지정하려면  
  
1.  `serviceAuthorization` 요소에서 `authorizationPolicies` 요소에 있는 `add` 요소의 `policyType` 특성에 사용자 지정 권한 부여 정책 유형을 지정합니다.  
  
    ```  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
        <serviceAuthorization serviceAuthorizationManagerType=  
                  "Samples.MyServiceAuthorizationManager" >  
          <authorizationPolicies>         
            <add policyType="Samples.MyAuthorizationPolicy"  
          </authorizationPolicies>  
        </serviceAuthorization>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
### 코드를 통해 사용자 지정 권한 부여 정책을 지정하려면  
  
1.  <xref:System.IdentityModel.Policy.IAuthorizationPolicy>의 <xref:System.Collections.Generic.List%601>을 만듭니다.  
  
2.  사용자 지정 권한 부여 정책의 인스턴스를 만듭니다.  
  
3.  권한 부여 정책 인스턴스를 목록에 추가합니다.  
  
4.  각 사용자 지정 권한 부여 정책에 대해 2단계와 3단계를 반복합니다.  
  
5.  읽기 전용 버전의 목록을 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A> 속성에 할당합니다.  
  
     [!code-csharp[c_CustomAuthPol#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#8)]
     [!code-vb[c_CustomAuthPol#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#8)]  
  
## 예제  
 다음 예제에서는 전체 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 구현을 보여 줍니다.  
  
 [!code-csharp[c_CustomAuthPol#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#5)]
 [!code-vb[c_CustomAuthPol#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#5)]  
  
## 참고 항목  
 <xref:System.ServiceModel.ServiceAuthorizationManager>   
 [방법: 클레임 비교](../../../../docs/framework/wcf/extending/how-to-compare-claims.md)   
 [방법: 서비스에 대한 사용자 지정 권한 부여 관리자 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)   
 [권한 부여 정책](../../../../docs/framework/wcf/samples/authorization-policy.md)