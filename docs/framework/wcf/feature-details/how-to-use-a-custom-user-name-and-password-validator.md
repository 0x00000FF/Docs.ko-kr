---
title: '방법: 사용자 지정 사용자 이름 및 암호에 대한 유효성 검사기 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 5ad53700590c3f3683663d306e15fcbe857f625e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59308512"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="3a1b2-102">방법: 사용자 지정 사용자 이름 및 암호에 대한 유효성 검사기 사용</span><span class="sxs-lookup"><span data-stu-id="3a1b2-102">How to: Use a Custom User Name and Password Validator</span></span>
<span data-ttu-id="3a1b2-103">기본적으로 사용자 이름 및 암호 인증을 위해 사용 되는 경우 Windows Communication Foundation (WCF)를 사용 하 여 Windows 사용자 이름 및 암호의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-103">By default, when a user name and password is used for authentication, Windows Communication Foundation (WCF) uses Windows to validate the user name and password.</span></span> <span data-ttu-id="3a1b2-104">그러나 WCF에서는 사용자 지정 사용자 이름 및 암호 인증 체계에 대 한 라고도 *유효성 검사기*합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-104">However, WCF allows for custom user name and password authentication schemes, also known as *validators*.</span></span> <span data-ttu-id="3a1b2-105">사용자 지정 사용자 이름 및 암호 유효성 검사기를 통합하려면 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>에서 파생되는 클래스를 만들어 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-105">To incorporate a custom user name and password validator, create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> and then configure it.</span></span>  
  
 <span data-ttu-id="3a1b2-106">샘플 응용 프로그램을 참조 하세요 [사용자 이름 암호 유효성 검사기](../../../../docs/framework/wcf/samples/user-name-password-validator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-106">For a sample application, see [User Name Password Validator](../../../../docs/framework/wcf/samples/user-name-password-validator.md).</span></span>  
  
### <a name="to-create-a-custom-user-name-and-password-validator"></a><span data-ttu-id="3a1b2-107">사용자 지정 사용자 이름 및 암호 유효성 검사기를 만들려면</span><span class="sxs-lookup"><span data-stu-id="3a1b2-107">To create a custom user name and password validator</span></span>  
  
1. <span data-ttu-id="3a1b2-108"><xref:System.IdentityModel.Selectors.UserNamePasswordValidator>에서 파생되는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-108">Create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span>  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2. <span data-ttu-id="3a1b2-109"><xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드를 재정의하여 사용자 지정 인증 스키마를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-109">Implement the custom authentication scheme by overriding the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
     <span data-ttu-id="3a1b2-110">다음 예제에서는 프로덕션 환경에서 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드를 재정의하는 코드를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-110">Do not use the code in the following example that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="3a1b2-111">코드를 사용자 지정 사용자 이름 및 암호 유효성 검사 스키마로 바꿉니다. 이 스키마는 데이터베이스에서 사용자 이름과 암호 쌍을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-111">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>  
  
     <span data-ttu-id="3a1b2-112">인증 오류를 다시 클라이언트에 반환하려면 <xref:System.ServiceModel.FaultException> 메서드에서 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-112">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="3a1b2-113">사용자 지정 사용자 이름 및 암호 유효성 검사기를 사용하도록 서비스를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="3a1b2-113">To configure a service to use a custom user name and password validator</span></span>  
  
1. <span data-ttu-id="3a1b2-114">HTTP(S)를 통해 전송 또는 전송 수준 보안에서 메시지 보안을 사용하는 바인딩을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-114">Configure a binding that uses message security over any transport or transport-level security over HTTP(S).</span></span>  
  
     <span data-ttu-id="3a1b2-115">메시지 보안을 사용 하는 경우 시스템 제공 바인딩 중 하나 같은 추가 된 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), 또는 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 지원 하는 메시지 보안 및 `UserName` 자격 증명 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-115">When using message security, add one of the system-provided bindings, such as a  [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that supports message security and the `UserName` credential type.</span></span>  
  
     <span data-ttu-id="3a1b2-116">전송 수준 보안 HTTP (S)를 통해 사용 하는 경우 추가 합니다 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 하거나 [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [ \< netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) 또는 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) HTTP (S)를 사용 하 고 `Basic` 인증 체계입니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-116">When using transport-level security over HTTP(S), add either the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that uses HTTP(S) and the `Basic` authentication scheme.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a1b2-117">[!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] 이상을 사용하는 경우 메시지 및 전송 보안과 함께 사용자 지정 사용자 이름 및 암호 유효성 검사기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-117">When [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] or later is used, you can use a custom username and password validator with message and transport security.</span></span> <span data-ttu-id="3a1b2-118">[!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]를 사용하는 경우에는 메시지 보안에서만 사용자 지정 사용자 이름 및 암호 유효성 검사기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-118">With [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], a custom username and password validator can only be used with message security.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="3a1b2-119">사용 하 여 대 한 자세한 내용은 \<netTcpBinding >이 컨텍스트에서 참조 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="3a1b2-119">For more information on using \<netTcpBinding> in this context, see [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span></span>  
  
    1.  <span data-ttu-id="3a1b2-120">구성 파일에 아래 합니다 [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소를 추가 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 요소.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-120">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
    2.  <span data-ttu-id="3a1b2-121">추가 된 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 하거나 [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) 요소를 바인딩 섹션.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-121">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element to the bindings section.</span></span> <span data-ttu-id="3a1b2-122">WCF 바인딩 요소를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 구성에서 서비스 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-122">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
    3.  <span data-ttu-id="3a1b2-123">설정 합니다 `mode` 특성을 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) 또는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) 를 `Message`, `Transport`, 또는 `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-123">Set the `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) or [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>  
  
    4.  <span data-ttu-id="3a1b2-124">설정 합니다 `clientCredentialType` 특성을 [ \<메시지 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) 또는 [ \<전송 >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-124">Set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>  
  
         <span data-ttu-id="3a1b2-125">메시지 보안을 사용할 때 설정 합니다 `clientCredentialType` 특성을 [ \<메시지 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) 를 `UserName`.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-125">When using message security, set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) to `UserName`.</span></span>  
  
         <span data-ttu-id="3a1b2-126">HTTP (S)를 통해 전송 수준 보안 사용 하 여 설정 합니다 `clientCredentialType` 특성을 [ \<전송 >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) 또는 [ \<전송 >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) 에 `Basic`입니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-126">When using transport-level security over HTTP(S), set the `clientCredentialType` attribute of the [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) to `Basic`.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3a1b2-127">WCF 서비스에서 인터넷 정보 서비스 (IIS) 전송 수준 보안을 사용 하 여 호스팅된 경우 및 <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> 속성이 <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, 사용자 지정 인증 체계는 Windows 인증의 하위 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-127">When a WCF service is hosted in Internet Information Services (IIS) using transport-level security and the <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> property is set to <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, the custom authentication scheme uses a subset of Windows authentication.</span></span> <span data-ttu-id="3a1b2-128">이것은 IIS이이 시나리오에서는 WCF 사용자 지정 인증자를 호출 하기 전에 Windows 인증을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-128">That is because in this scenario, IIS performs Windows authentication prior to WCF invoking the custom authenticator.</span></span>  
  
     <span data-ttu-id="3a1b2-129">WCF 바인딩 요소를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 구성에서 서비스 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-129">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
     <span data-ttu-id="3a1b2-130">다음 예제에서는 바인딩에 대한 구성 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-130">The following example shows the configuration code for the binding.</span></span>  
  
    ```xml  
    <system.serviceModel>   
      <bindings>  
      <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="UserName" />  
            </security>  
          </binding>          
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
2. <span data-ttu-id="3a1b2-131">사용자 지정 사용자 이름 및 암호 유효성 검사기를 사용하여 들어오는 <xref:System.IdentityModel.Tokens.UserNameSecurityToken> 보안 토큰에 대한 사용자 이름과 암호 쌍의 유효성을 검사하도록 지정하는 동작을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-131">Configure a behavior that specifies that a custom user name and password validator is used to validate user name and password pairs for incoming <xref:System.IdentityModel.Tokens.UserNameSecurityToken> security tokens.</span></span>  
  
    1.  <span data-ttu-id="3a1b2-132">에 자식 항목으로 [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소에 추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-132">As a child to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
    2.  <span data-ttu-id="3a1b2-133">추가 된 [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) 에 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-133">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
    3.  <span data-ttu-id="3a1b2-134">추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) 요소를 `name` 특성을 적절 한 값으로.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-134">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
    4.  <span data-ttu-id="3a1b2-135">추가 된 [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) 에 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) 요소.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-135">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>  
  
    5.  <span data-ttu-id="3a1b2-136">추가 된 [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) 에 [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-136">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span></span>  
  
    6.  <span data-ttu-id="3a1b2-137">`userNamePasswordValidationMode`를 `Custom`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-137">Set the `userNamePasswordValidationMode` to `Custom`.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="3a1b2-138">경우는 `userNamePasswordValidationMode` 값 설정 하지 않으면, WCF 사용자 지정 사용자 이름 및 암호 유효성 검사기 대신 Windows 인증을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-138">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the custom user name and password validator.</span></span>  
  
    7.  <span data-ttu-id="3a1b2-139">`customUserNamePasswordValidatorType`을 사용자 지정 사용자 이름 및 암호 유효성 검사기를 나타내는 형식으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-139">Set the `customUserNamePasswordValidatorType` to the type that represents your custom user name and password validator.</span></span>  
  
     <span data-ttu-id="3a1b2-140">다음 예제에서는 이 지점에 대한 `<serviceCredentials>` 단편을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-140">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>  
  
    ```xml  
    <serviceCredentials>  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />  
    </serviceCredentials>  
    ```  
  
## <a name="example"></a><span data-ttu-id="3a1b2-141">예제</span><span class="sxs-lookup"><span data-stu-id="3a1b2-141">Example</span></span>  
 <span data-ttu-id="3a1b2-142">다음 코드 예제에서는 사용자 지정 사용자 이름 및 암호 유효성 검사기를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-142">The following code example demonstrates how to create a custom user name and password validator.</span></span> <span data-ttu-id="3a1b2-143">프로덕션 환경에서는 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드를 재정의하는 코드를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-143">Do not use the code that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="3a1b2-144">코드를 사용자 지정 사용자 이름 및 암호 유효성 검사 스키마로 바꿉니다. 이 스키마는 데이터베이스에서 사용자 이름과 암호 쌍을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1b2-144">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>  
  
 [!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
 [!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]  
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="3a1b2-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="3a1b2-145">See also</span></span>

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [<span data-ttu-id="3a1b2-146">방법: ASP.NET 멤버 자격 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="3a1b2-146">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
- [<span data-ttu-id="3a1b2-147">인증</span><span class="sxs-lookup"><span data-stu-id="3a1b2-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)
