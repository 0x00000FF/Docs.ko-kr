---
title: 권한 부여 정책
ms.date: 03/30/2017
ms.assetid: 1db325ec-85be-47d0-8b6e-3ba2fdf3dda0
ms.openlocfilehash: 78ca42abfd2df56edeeb273fcd8ba585aa16f635
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47198321"
---
# <a name="authorization-policy"></a><span data-ttu-id="ab1ed-102">권한 부여 정책</span><span class="sxs-lookup"><span data-stu-id="ab1ed-102">Authorization Policy</span></span>

<span data-ttu-id="ab1ed-103">이 샘플에서는 사용자 지정 클레임 권한 부여 정책 및 연관된 사용자 지정 서비스 인증 관리자를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-103">This sample demonstrates how to implement a custom claim authorization policy and an associated custom service authorization manager.</span></span> <span data-ttu-id="ab1ed-104">이 방법은 서비스에서 서비스 작업에 대해 클레임 기반 액세스 검사를 수행하는 경우에 유용하며 액세스 검사 전에 호출자에게 특정 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-104">This is useful when the service makes claim-based access checks to service operations and prior to the access checks, grants the caller certain rights.</span></span> <span data-ttu-id="ab1ed-105">이 샘플에서는 클레임을 추가하는 프로세스와 종료된 클레임 집합에 대해 액세스 검사를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-105">This sample shows both the process of adding claims as well as the process for doing an access check against the finalized set of claims.</span></span> <span data-ttu-id="ab1ed-106">클라이언트와 서버 간의 모든 응용 프로그램 메시지는 서명 및 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-106">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="ab1ed-107">기본적으로 `wsHttpBinding` 바인딩에서는 클라이언트에서 제공하는 사용자 이름과 암호를 사용하여 유효한 Windows NT 계정에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-107">By default with the `wsHttpBinding` binding, a username and password supplied by the client are used to logon to a valid Windows NT account.</span></span> <span data-ttu-id="ab1ed-108">이 샘플에서는 사용자 지정 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>를 사용하여 클라이언트를 인증하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-108">This sample demonstrates how to utilize a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> to authenticate the client.</span></span> <span data-ttu-id="ab1ed-109">이 샘플에서는 그 외에도 X.509 인증서를 사용하여 서비스에 대해 클라이언트를 인증하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-109">In addition this sample shows the client authenticating to the service using an X.509 certificate.</span></span> <span data-ttu-id="ab1ed-110">이 샘플에서는 서로의 사이에서 특정 사용자에 대해 서비스의 특정 메서드에 대한 액세스 권한을 부여하는 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 및 <xref:System.ServiceModel.ServiceAuthorizationManager> 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-110">This sample shows an implementation of <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and <xref:System.ServiceModel.ServiceAuthorizationManager>, which between them grant access to specific methods of the service for specific users.</span></span> <span data-ttu-id="ab1ed-111">이 샘플은 기반를 [메시지 보안 사용자 이름](../../../../docs/framework/wcf/samples/message-security-user-name.md), 하기 전에 클레임 변환을 수행 하는 방법에 설명 하지만 <xref:System.ServiceModel.ServiceAuthorizationManager> 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-111">This sample is based on the [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md), but demonstrates how to perform a claim transformation prior to the <xref:System.ServiceModel.ServiceAuthorizationManager> being called.</span></span>

> [!NOTE]
> <span data-ttu-id="ab1ed-112">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="ab1ed-113">즉, 이 샘플에서는 다음 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-113">In summary, this sample demonstrates how:</span></span>

-   <span data-ttu-id="ab1ed-114">사용자 이름 및 암호를 사용하여 클라이언트를 인증하는 방법.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-114">The client can be authenticated using a user name-password.</span></span>

-   <span data-ttu-id="ab1ed-115">X.509 인증서를 사용하여 클라이언트를 인증하는 방법.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-115">The client can be authenticated using an X.509 certificate.</span></span>

-   <span data-ttu-id="ab1ed-116">서버에서 사용자 지정 `UsernamePassword` 유효성 검사기를 기준으로 클라이언트의 유효성을 검증하는 방법.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-116">The server validates the client credentials against a custom `UsernamePassword` validator.</span></span>

-   <span data-ttu-id="ab1ed-117">서버의 X.509 인증서를 사용하여 서버를 인증하는 방법</span><span class="sxs-lookup"><span data-stu-id="ab1ed-117">The server is authenticated using the server's X.509 certificate.</span></span>

-   <span data-ttu-id="ab1ed-118">서버에서 <xref:System.ServiceModel.ServiceAuthorizationManager>를 사용하여 서비스에 있는 특정 메서드에 대한 액세스를 제어하는 방법.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-118">The server can use <xref:System.ServiceModel.ServiceAuthorizationManager> to control access to certain methods in the service.</span></span>

-   <span data-ttu-id="ab1ed-119"><xref:System.IdentityModel.Policy.IAuthorizationPolicy>를 구현하는 방법.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-119">How to implement <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>

<span data-ttu-id="ab1ed-120">서비스는 App.config 구성 파일을 사용하여 정의된, 서비스와의 통신에 사용되는 두 개의 엔드포인트를 노출합니다. 각 엔드포인트는 하나의 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-120">The service exposes two endpoints for communicating with the service, defined using the configuration file App.config. Each endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="ab1ed-121">한 바인딩은 WS-Security 및 클라이언트 사용자 이름 인증을 사용하는 표준 `wsHttpBinding` 바인딩으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-121">One binding is configured with a standard `wsHttpBinding` binding that uses WS-Security and client username authentication.</span></span> <span data-ttu-id="ab1ed-122">다른 바인딩은 WS-Security 및 클라이언트 인증서 인증을 사용하는 표준 `wsHttpBinding` 바인딩으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-122">The other binding is configured with a standard `wsHttpBinding` binding that uses WS-Security and client certificate authentication.</span></span> <span data-ttu-id="ab1ed-123">합니다 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 서비스 인증에 사용할 사용자 자격 증명이 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-123">The [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) specifies that the user credentials are to be used for service authentication.</span></span> <span data-ttu-id="ab1ed-124">서버 인증서에 대해 동일한 값을 포함 해야 합니다는 `SubjectName` 속성으로는 `findValue` 특성을 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="ab1ed-124">The server certificate must contain the same value for the `SubjectName` property as the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <!-- configure base address provided by host -->
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service"/>
        </baseAddresses>
      </host>
      <!-- use base address provided by host, provide two endpoints -->
      <endpoint address="username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <endpoint address="certificate"
                binding="wsHttpBinding"
                bindingConfiguration="Binding2"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>

  <bindings>
    <wsHttpBinding>
      <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
    <message clientCredentialType="UserName" />
        </security>
      </binding>
      <!-- X509 certificate binding -->
      <binding name="Binding2">
        <security mode="Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>

  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior" >
        <serviceDebug includeExceptionDetailInFaults ="true" />
        <serviceCredentials>
          <!--
          The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
          -->
          <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
          <!--
          The serviceCredentials behavior allows one to specify authentication constraints on client certificates.
          -->
          <clientCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it will be trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
          <!--
          The serviceCredentials behavior allows one to define a service certificate.
          A service certificate is used by a client to authenticate the service and provide message protection.
          This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
        </serviceCredentials>
        <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
          <!--
          The serviceAuthorization behavior allows one to specify custom authorization policies.
          -->
          <authorizationPolicies>
            <add policyType="Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary" />
          </authorizationPolicies>
        </serviceAuthorization>
      </behavior>
    </serviceBehaviors>
  </behaviors>

</system.serviceModel>
```

<span data-ttu-id="ab1ed-125">각 클라이언트 엔드포인트 구성은 구성 이름, 서비스 엔드포인트의 절대 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-125">Each client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="ab1ed-126">에 경우 지정 된 대로 적절 한 보안 모드를 사용 하 여 클라이언트 바인딩에 구성 합니다 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) 하 고 `clientCredentialType` 에 지정 된 대로 합니다 [ \<메시지 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ab1ed-126">The client binding is configured with the appropriate security mode as specified in this case in the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) and `clientCredentialType` as specified in the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).</span></span>

```xml
<system.serviceModel>

    <client>
      <!-- Username based endpoint -->
      <endpoint name="Username"
            address="http://localhost:8001/servicemodelsamples/service/username"
    binding="wsHttpBinding"
    bindingConfiguration="Binding1"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator" >
      </endpoint>
      <!-- X509 certificate based endpoint -->
      <endpoint name="Certificate"
                        address="http://localhost:8001/servicemodelsamples/service/certificate"
                binding="wsHttpBinding"
            bindingConfiguration="Binding2"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
          <message clientCredentialType="UserName" />
        </security>
      </binding>
        <!-- X509 certificate binding -->
        <binding name="Binding2">
          <security mode="Message">
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
    </wsHttpBinding>
    </bindings>

    <behaviors>
      <behavior name="ClientCertificateBehavior">
        <clientCredentials>
          <serviceCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust
            means that if the certificate
            is in the user's Trusted People store, then it will be
            trusted without performing a
            validation of the certificate's issuer chain. This setting
            is used here for convenience so that the
            sample can be run without having to have certificates
            issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust.
            The security implications of this
            setting should be carefully considered before using
            PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode = "PeerOrChainTrust" />
          </serviceCertificate>
        </clientCredentials>
      </behavior>
    </behaviors>

  </system.serviceModel>
```

<span data-ttu-id="ab1ed-127">사용자 이름 기반 엔드포인트의 경우 클라이언트 구현에서 사용할 사용자 이름 및 암호를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-127">For the user name-based endpoint, the client implementation sets the user name and password to use.</span></span>

```csharp
// Create a client with Username endpoint configuration
CalculatorClient client1 = new CalculatorClient("Username");

client1.ClientCredentials.UserName.UserName = "test1";
client1.ClientCredentials.UserName.Password = "1tset";

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client1.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client1.Close();
```

<span data-ttu-id="ab1ed-128">인증서 기반 엔드포인트의 경우 클라이언트 구현에서 사용할 클라이언트 인증서를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-128">For the certificate-based endpoint, the client implementation sets the client certificate to use.</span></span>

```csharp
// Create a client with Certificate endpoint configuration
CalculatorClient client2 = new CalculatorClient("Certificate");

client2.ClientCredentials.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "test1");

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client2.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client2.Close();
```

<span data-ttu-id="ab1ed-129">이 샘플에서는 사용자 지정 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>를 사용하여 사용자 이름 및 암호의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-129">This sample uses a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> to validate user names and passwords.</span></span> <span data-ttu-id="ab1ed-130">이 샘플에서는 `MyCustomUserNamePasswordValidator`에서 파생된 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-130">The sample implements `MyCustomUserNamePasswordValidator`, derived from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span> <span data-ttu-id="ab1ed-131">자세한 내용은 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>에 대한 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-131">See the documentation about <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> for more information.</span></span> <span data-ttu-id="ab1ed-132"><xref:System.IdentityModel.Selectors.UserNamePasswordValidator>와의 통합을 보여 주기 위해 이 사용자 지정 유효성 검사기 샘플에서는 다음 코드에 표시된 것과 같이 사용자 이름과 암호가 일치되는 사용자 이름/암호 쌍을 받도록 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-132">For the purposes of demonstrating the integration with the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, this custom validator sample implements the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method to accept user name/password pairs where the user name matches the password as shown in the following code.</span></span>

```csharp
public class MyCustomUserNamePasswordValidator : UserNamePasswordValidator
{
  // This method validates users. It allows in two users,
  // test1 and test2 with passwords 1tset and 2tset respectively.
  // This code is for illustration purposes only and
  // MUST NOT be used in a production environment because it
  // is NOT secure.
  public override void Validate(string userName, string password)
  {
    if (null == userName || null == password)
    {
      throw new ArgumentNullException();
    }

    if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))
    {
      throw new SecurityTokenException("Unknown Username or Password");
    }
  }
}
```

<span data-ttu-id="ab1ed-133">서비스 코드에 유효성 검사기를 구현하고 나면 사용할 유효성 검사기 인스턴스에 대한 정보를 서비스 호스트에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-133">Once the validator is implemented in service code, the service host must be informed about the validator instance to use.</span></span> <span data-ttu-id="ab1ed-134">이것은 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-134">This is done using the following code:</span></span>

```csharp
Servicehost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;
serviceHost.Credentials.UserNameAuthentication.CustomUserNamePasswordValidator = new MyCustomUserNamePasswordValidatorProvider();
```

<span data-ttu-id="ab1ed-135">또는 구성에서 동일한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-135">Or you can do the same thing in configuration:</span></span>

```xml
<behavior ...>
    <serviceCredentials>
      <!--
      The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
      -->
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
    ...
    </serviceCredentials>
</behavior>
```

<span data-ttu-id="ab1ed-136">Windows Communication Foundation (WCF) 액세스 검사를 수행 하는 것에 대 한 풍부한 클레임 기반 모델을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-136">Windows Communication Foundation (WCF) provides a rich claims-based model for performing access checks.</span></span> <span data-ttu-id="ab1ed-137"><xref:System.ServiceModel.ServiceAuthorizationManager> 개체는 액세스 검사를 수행하는 데 사용되며 클라이언트에 연결된 클레임이 서비스 메서드에 액세스하는 데 필요한 요구 사항을 충족시키는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-137">The <xref:System.ServiceModel.ServiceAuthorizationManager> object is used to perform the access check and determine whether the claims associated with the client satisfy the requirements necessary to access the service method.</span></span>

<span data-ttu-id="ab1ed-138">설명을 위해이 샘플 구현을 보여 줍니다 <xref:System.ServiceModel.ServiceAuthorizationManager> 를 구현 하는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 형식의 클레임을 기반으로 하는 방법에 대 한 사용자의 액세스를 허용 하는 방법 http://example.com/claims/allowedoperation 값으로 가지는 작업의 동작 URI가 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-138">For the purposes of demonstration, this sample shows an implementation of <xref:System.ServiceModel.ServiceAuthorizationManager> that implements the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method to allow a user's access to methods based on claims of type http://example.com/claims/allowedoperation whose value is the Action URI of the operation that is allowed to be called.</span></span>

```csharp
public class MyServiceAuthorizationManager : ServiceAuthorizationManager
{
  protected override bool CheckAccessCore(OperationContext operationContext)
  {
    string action = operationContext.RequestContext.RequestMessage.Headers.Action;
    Console.WriteLine("action: {0}", action);
    foreach(ClaimSet cs in operationContext.ServiceSecurityContext.AuthorizationContext.ClaimSets)
    {
      if ( cs.Issuer == ClaimSet.System )
      {
        foreach (Claim c in cs.FindClaims("http://example.com/claims/allowedoperation", Rights.PossessProperty))
        {
          Console.WriteLine("resource: {0}", c.Resource.ToString());
          if (action == c.Resource.ToString())
            return true;
        }
      }
    }
    return false;
  }
}
```

<span data-ttu-id="ab1ed-139">사용자 지정 <xref:System.ServiceModel.ServiceAuthorizationManager>가 구현되면 사용할 <xref:System.ServiceModel.ServiceAuthorizationManager>에 대한 정보를 서비스 호스트에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-139">Once the custom <xref:System.ServiceModel.ServiceAuthorizationManager> is implemented, the service host must be informed about the <xref:System.ServiceModel.ServiceAuthorizationManager> to use.</span></span> <span data-ttu-id="ab1ed-140">이 작업은 다음 코드에 표시된 것과 같이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-140">This is done as shown in the following code.</span></span>

```xml
<behavior ...>
    ...
    <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
        ...
    </serviceAuthorization>
</behavior>
```

<span data-ttu-id="ab1ed-141">구현할 중요한 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 메서드는 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-141">The primary <xref:System.IdentityModel.Policy.IAuthorizationPolicy> method to implement is the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method.</span></span>

```csharp
public class MyAuthorizationPolicy : IAuthorizationPolicy
{
    string id;

    public MyAuthorizationPolicy()
    {
    id =  Guid.NewGuid().ToString();
    }

    public bool Evaluate(EvaluationContext evaluationContext,
                                            ref object state)
    {
        bool bRet = false;
        CustomAuthState customstate = null;

        if (state == null)
        {
            customstate = new CustomAuthState();
            state = customstate;
        }
        else
            customstate = (CustomAuthState)state;
        Console.WriteLine("In Evaluate");
        if (!customstate.ClaimsAdded)
        {
           IList<Claim> claims = new List<Claim>();

           foreach (ClaimSet cs in evaluationContext.ClaimSets)
              foreach (Claim c in cs.FindClaims(ClaimTypes.Name,
                                         Rights.PossessProperty))
                  foreach (string s in
                        GetAllowedOpList(c.Resource.ToString()))
                  {
                       claims.Add(new
               Claim("http://example.com/claims/allowedoperation",
                                    s, Rights.PossessProperty));
                            Console.WriteLine("Claim added {0}", s);
                      }
                   evaluationContext.AddClaimSet(this,
                           new DefaultClaimSet(this.Issuer,claims));
                   customstate.ClaimsAdded = true;
                   bRet = true;
                }
         else
         {
              bRet = true;
         }
         return bRet;
     }
...
}
```

<span data-ttu-id="ab1ed-142">이전 코드에서는 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> 메서드가 처리에 영향을 주는 새 클레임이 추가되지 않았는지 확인하고 특정 클레임을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-142">The previous code shows how the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method checks that no new claims have been added that affect the processing and adds specific claims.</span></span> <span data-ttu-id="ab1ed-143">허용되는 클레임은 사용자가 수행할 수 있는 작업의 특정 목록을 반환하도록 구현된 `GetAllowedOpList` 메서드를 통해 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-143">The claims that are allowed are obtained from the `GetAllowedOpList` method, which is implemented to return a specific list of operations that the user is allowed to perform.</span></span> <span data-ttu-id="ab1ed-144">권한 부여 정책에서는 특정 작업에 액세스하기 위한 클레임을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-144">The authorization policy adds claims for accessing the particular operation.</span></span> <span data-ttu-id="ab1ed-145">이 값은 나중에 <xref:System.ServiceModel.ServiceAuthorizationManager>에서 액세스 확인 여부를 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-145">This is later used by the <xref:System.ServiceModel.ServiceAuthorizationManager> to perform access check decisions.</span></span>

<span data-ttu-id="ab1ed-146">사용자 지정 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>가 구현되면 사용할 권한 부여 정책에 대한 정보를 서비스 호스트에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-146">Once the custom <xref:System.IdentityModel.Policy.IAuthorizationPolicy> is implemented, the service host must be informed about the authorization policies to use.</span></span>

```xml
<serviceAuthorization ...>
       <authorizationPolicies>
            <add policyType='Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary' />
       </authorizationPolicies>
</serviceAuthorization>
```

<span data-ttu-id="ab1ed-147">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-147">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="ab1ed-148">클라이언트에서는 Add, Subtract 및 Multiple 메서드를 성공적으로 호출하며 Divide 메서드를 호출하려 하면 "액세스가 거부되었습니다." 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-148">The client successfully calls the Add, Subtract and Multiple methods and gets an "Access is denied" message when trying to call the Divide method.</span></span> <span data-ttu-id="ab1ed-149">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-149">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="ab1ed-150">설치 배치 파일</span><span class="sxs-lookup"><span data-stu-id="ab1ed-150">Setup Batch File</span></span>

<span data-ttu-id="ab1ed-151">이 샘플에 포함된 Setup.bat 배치 파일을 사용하면 서버 인증서 기반 보안이 필요한 자체 호스팅 응용 프로그램을 실행하도록 관련 인증서가 있는 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-151">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span>

<span data-ttu-id="ab1ed-152">다음 부분에는 적절한 구성으로 실행되게 수정할 수 있도록 배치 파일의 다양한 섹션에 대한 간략한 개요가 소개되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-152">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration:</span></span>

-   <span data-ttu-id="ab1ed-153">서버 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="ab1ed-153">Creating the server certificate.</span></span>

     <span data-ttu-id="ab1ed-154">Setup.bat 배치 파일에서 다음 행은 사용할 서버 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-154">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="ab1ed-155">%SERVER_NAME% 변수는 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-155">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="ab1ed-156">이 변수를 변경하여 고유의 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-156">Change this variable to specify your own server name.</span></span> <span data-ttu-id="ab1ed-157">기본값은 localhost입니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-157">The default value is localhost.</span></span>

    ```
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

-   <span data-ttu-id="ab1ed-158">클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="ab1ed-158">Installing the server certificate into client's trusted certificate store.</span></span>

     <span data-ttu-id="ab1ed-159">Setup.bat 배치 파일에서 다음 행은 클라이언트의 신뢰할 수 있는 사용자 저장소로 서버 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-159">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="ab1ed-160">이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 시스템에서 암시적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-160">This step is required because certificates that are generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="ab1ed-161">Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-161">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

-   <span data-ttu-id="ab1ed-162">클라이언트 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="ab1ed-162">Creating the client certificate.</span></span>

     <span data-ttu-id="ab1ed-163">Setup.bat 배치 파일에서 다음 줄은 사용할 클라이언트 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-163">The following lines from the Setup.bat batch file create the client certificate to be used.</span></span> <span data-ttu-id="ab1ed-164">%USER_NAME% 변수는 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-164">The %USER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="ab1ed-165">이 값은 `IAuthorizationPolicy`에서 찾는 이름이기 때문에 "test1"으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-165">This value is set to "test1" because this is the name the `IAuthorizationPolicy` looks for.</span></span> <span data-ttu-id="ab1ed-166">%USER_NAME% 값을 변경하는 경우 `IAuthorizationPolicy.Evaluate` 메서드에서 해당 값을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-166">If you change the value of %USER_NAME% you must change the corresponding value in the `IAuthorizationPolicy.Evaluate` method.</span></span>

     <span data-ttu-id="ab1ed-167">인증서는 CurrentUser 저장소 위치에 있는 My (Personal) 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-167">The certificate is stored in My (Personal) store under the CurrentUser store location.</span></span>

    ```
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

-   <span data-ttu-id="ab1ed-168">서버의 신뢰할 수 있는 인증서 저장소에 클라이언트 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="ab1ed-168">Installing the client certificate into server's trusted certificate store.</span></span>

     <span data-ttu-id="ab1ed-169">Setup.bat 배치 파일에서 다음 줄은 신뢰할 수 있는 사용자 저장소로 클라이언트 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-169">The following lines in the Setup.bat batch file copy the client certificate into the trusted people store.</span></span> <span data-ttu-id="ab1ed-170">이 단계는 Makecert.exe에서 생성한 인증서를 서버 시스템에서 암시적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-170">This step is required because certificates that are generated by Makecert.exe are not implicitly trusted by the server system.</span></span> <span data-ttu-id="ab1ed-171">Microsoft에서 발급한 인증서와 같이 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 서버 인증서 저장소를 클라이언트 인증서로 채우는 이 단계는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-171">If you already have a certificate that is rooted in a trusted root certificate—for example, a Microsoft issued certificate—this step of populating the server certificate store with the client certificate is not required.</span></span>

    ```
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="ab1ed-172">샘플을 설치하고 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="ab1ed-172">To set up and build the sample</span></span>

1. <span data-ttu-id="ab1ed-173">지침에 따라 솔루션을 빌드하려면 [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-173">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

2. <span data-ttu-id="ab1ed-174">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행하려면 다음 지침을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-174">To run the sample in a single- or cross-computer configuration, use the following instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="ab1ed-175">Svcutil.exe를 사용하여 이 샘플에 대한 구성을 다시 생성할 경우 클라이언트 구성에서 엔드포인트 이름을 클라이언트 코드와 일치하도록 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-175">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="ab1ed-176">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="ab1ed-176">To run the sample on the same computer</span></span>

1. <span data-ttu-id="ab1ed-177">관리자 권한으로 Visual Studio 용 개발자 명령 프롬프트를 열고 및 실행 *Setup.bat* 샘플 설치 폴더에서.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-177">Open Developer Command Prompt for Visual Studio with administrator privileges and run *Setup.bat* from the sample install folder.</span></span> <span data-ttu-id="ab1ed-178">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-178">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab1ed-179">Setup.bat 배치 파일은 Visual Studio 용 개발자 명령 프롬프트에서 실행 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-179">The Setup.bat batch file is designed to be run from Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="ab1ed-180">PATH 환경 변수 설정 개발자 명령 프롬프트 내에서 Visual Studio에 필요한 실행 파일이 포함 된 디렉터리를 가리키는 합니다 *Setup.bat* 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-180">The PATH environment variable set within Developer Command Prompt for Visual Studio points to the directory that contains executables required by the *Setup.bat* script.</span></span>

1. <span data-ttu-id="ab1ed-181">Service.exe를 실행 *service\bin*합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-181">Launch Service.exe from *service\bin*.</span></span>

1. <span data-ttu-id="ab1ed-182">Client.exe를 실행 *\client\bin*합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-182">Launch Client.exe from *\client\bin*.</span></span> <span data-ttu-id="ab1ed-183">클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-183">Client activity is displayed on the client console application.</span></span>

  <span data-ttu-id="ab1ed-184">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-184">If the client and service are not able to communicate, see [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>

### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="ab1ed-185">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="ab1ed-185">To run the sample across computers</span></span>

1. <span data-ttu-id="ab1ed-186">서비스 컴퓨터에 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-186">Create a directory on the service computer.</span></span>

2. <span data-ttu-id="ab1ed-187">서비스 프로그램 파일을 복사 *\service\bin* 서비스 컴퓨터의 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-187">Copy the service program files from *\service\bin* to the directory on the service computer.</span></span> <span data-ttu-id="ab1ed-188">Setup.bat, Cleanup.bat, GetComputerName.vbs 및 ImportClientCert.bat 파일도 서비스 컴퓨터에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-188">Also copy the Setup.bat, Cleanup.bat, GetComputerName.vbs and ImportClientCert.bat files to the service computer.</span></span>

3. <span data-ttu-id="ab1ed-189">클라이언트 컴퓨터에 클라이언트 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-189">Create a directory on the client computer for the client binaries.</span></span>

4. <span data-ttu-id="ab1ed-190">클라이언트 프로그램 파일을 클라이언트 컴퓨터의 클라이언트 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-190">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="ab1ed-191">Setup.bat, Cleanup.bat 및 ImportServiceCert.bat 파일도 클라이언트로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-191">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>

5. <span data-ttu-id="ab1ed-192">서버에서 실행 `setup.bat service` 관리자 권한으로 연 Visual Studio 용 개발자 명령 프롬프트에서.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-192">On the server, run `setup.bat service` in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

   <span data-ttu-id="ab1ed-193">실행 중인 `setup.bat` 사용 하 여 합니다 `service` 인수가 컴퓨터의 정규화 된 도메인 이름 서비스 인증서를 만들고 라는 파일에 서비스 인증서를 내보냅니다 *Service.cer*합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-193">Running `setup.bat` with the `service` argument creates a service certificate with the fully qualified domain name of the computer, and exports the service certificate to a file named *Service.cer*.</span></span>

6. <span data-ttu-id="ab1ed-194">편집 *Service.exe.config* 새 인증서 이름을 반영 하도록 (에 `findValue` 특성을 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) 정규화 된 도메인 이름과 같습니다 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-194">Edit *Service.exe.config* to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully qualified domain name of the computer.</span></span> <span data-ttu-id="ab1ed-195">변경할 수도 합니다 **computername** 에 \<서비스 > /\<baseAddresses > localhost에서 서비스 컴퓨터의 정규화 된 이름으로 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-195">Also change the **computername** in the \<service>/\<baseAddresses> element from localhost to the fully qualified name of your service computer.</span></span>

7. <span data-ttu-id="ab1ed-196">복사 합니다 *Service.cer* 클라이언트 컴퓨터의 클라이언트 디렉터리로 서비스 디렉터리에서 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-196">Copy the *Service.cer* file from the service directory to the client directory on the client computer.</span></span>

8. <span data-ttu-id="ab1ed-197">클라이언트에서 실행 `setup.bat client` 관리자 권한으로 연 Visual Studio 용 개발자 명령 프롬프트에서.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-197">On the client, run `setup.bat client` in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

   <span data-ttu-id="ab1ed-198">실행 중인 `setup.bat` 사용 하 여는 `client` 인수 이라는 클라이언트 인증서를 만듭니다 **test1** 라는 파일에 클라이언트 인증서를 내보냅니다 *Client.cer*합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-198">Running `setup.bat` with the `client` argument creates a client certificate named **test1** and exports the client certificate to a file named *Client.cer*.</span></span>

9. <span data-ttu-id="ab1ed-199">에 *Client.exe.config* 클라이언트 컴퓨터의 파일, 서비스의 새 주소와 일치 하도록 끝점의 주소 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-199">In the *Client.exe.config* file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="ab1ed-200">대체 하 여이 작업을 수행할 **localhost** 서버의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-200">Do this by replacing **localhost** with the fully qualified domain name of the server.</span></span>

10. <span data-ttu-id="ab1ed-201">클라이언트 디렉터리에서 서버의 서비스 디렉터리로 Client.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-201">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>

11. <span data-ttu-id="ab1ed-202">클라이언트에서 실행할 *ImportServiceCert.bat* 관리자 권한으로 연 Visual Studio 용 개발자 명령 프롬프트에서.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-202">On the client, run *ImportServiceCert.bat* in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

   <span data-ttu-id="ab1ed-203">Service.cer 파일에서 서비스 인증서를 가져오고이 **CurrentUser-TrustedPeople** 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-203">This imports the service certificate from the Service.cer file into the **CurrentUser - TrustedPeople** store.</span></span>

12. <span data-ttu-id="ab1ed-204">서버에서 실행 *ImportClientCert.bat* 관리자 권한으로 연 Visual Studio 용 개발자 명령 프롬프트에서.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-204">On the server, run *ImportClientCert.bat* in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

   <span data-ttu-id="ab1ed-205">클라이언트 인증서를 Client.cer 파일에서 가져옵니다 합니다 **LocalMachine-TrustedPeople** 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-205">This imports the client certificate from the Client.cer file into the **LocalMachine - TrustedPeople** store.</span></span>

13. <span data-ttu-id="ab1ed-206">서버 컴퓨터의 명령 프롬프트 창에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-206">On the server computer, launch Service.exe from the command prompt window.</span></span>

14. <span data-ttu-id="ab1ed-207">클라이언트 컴퓨터의 명령 프롬프트 창에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-207">On the client computer, launch Client.exe from a command prompt window.</span></span>

   <span data-ttu-id="ab1ed-208">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-208">If the client and service are not able to communicate, see [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>

### <a name="clean-up-after-the-sample"></a><span data-ttu-id="ab1ed-209">샘플 실행 후 정리</span><span class="sxs-lookup"><span data-stu-id="ab1ed-209">Clean up after the sample</span></span>

<span data-ttu-id="ab1ed-210">샘플 실행 후 정리를 실행할 *Cleanup.bat* 샘플 실행을 마쳤으면 샘플 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-210">To clean up after the sample, run *Cleanup.bat* in the samples folder when you have finished running the sample.</span></span> <span data-ttu-id="ab1ed-211">그러면 인증서 저장소에서 서버 및 클라이언트 인증서가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-211">This removes the server and client certificates from the certificate store.</span></span>

> [!NOTE]
> <span data-ttu-id="ab1ed-212">다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-212">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="ab1ed-213">컴퓨터 인증서를 사용 하 여 CurrentUser-에 설치 된 서비스 인증서를 지워야 하는 WCF 샘플을 실행 한 경우 TrustedPeople 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ed-213">If you have run WCF samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="ab1ed-214">이를 수행하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다(예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="ab1ed-214">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>