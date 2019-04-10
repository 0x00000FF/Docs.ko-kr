---
title: '방법: 로컬 발급자 구성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 15263371-514e-4ea6-90fb-14b4939154cd
ms.openlocfilehash: 46dbb39a31a1ef256bef0f5b7e1bbc41ce1eca3e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59306991"
---
# <a name="how-to-configure-a-local-issuer"></a><span data-ttu-id="ea193-102">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="ea193-102">How to: Configure a Local Issuer</span></span>
<span data-ttu-id="ea193-103">이 항목에서는 발급된 토큰에 로컬 발급자를 사용하도록 클라이언트를 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-103">This topic describes how to configure a client to use a local issuer for issued tokens.</span></span>  
  
 <span data-ttu-id="ea193-104">흔히 클라이언트가 페더레이션 서비스와 통신하는 경우, 이 서비스에서는 클라이언트가 페더레이션 서비스에 자신을 인증하는 데 사용하는 토큰을 발급할 보안 토큰 서비스의 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-104">Often, when a client communicates with a federated service, the service specifies the address of the security token service that is expected to issue the token the client will use to authenticate itself to the federated service.</span></span> <span data-ttu-id="ea193-105">경우에 따라 클라이언트를 사용 하도록 구성할 수 있습니다는 *로컬 발급자*합니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-105">In certain situations, the client may be configured to use a *local issuer*.</span></span>  
  
 <span data-ttu-id="ea193-106">Windows Communication Foundation (WCF) 페더레이션 바인딩의 발급자 주소가 되는 경우에는 로컬 발급자를 사용 하 여 `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` 또는 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-106">Windows Communication Foundation (WCF) uses a local issuer in cases where the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`.</span></span> <span data-ttu-id="ea193-107">이러한 경우 로컬 발급자와의 통신에 사용할 바인딩과 이 발급자의 주소를 사용하여 <xref:System.ServiceModel.Description.ClientCredentials>를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-107">In such cases, you must configure the <xref:System.ServiceModel.Description.ClientCredentials> with the address of the local issuer and the binding to use to communicate with that issuer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea193-108">경우는 <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> 의 속성을 `ClientCredentials` 클래스로 설정 됩니다 `true`, 로컬 발급자 주소를 지정 하지 않으면 및 발급자 주소 지정 하는 [ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) 또는 기타 페더레이션 바인딩에서 `http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self`, `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous`, 또는 `null`, Windows 다음 [!INCLUDE[infocard](../../../../includes/infocard-md.md)] 발급자 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-108">If the <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> property of the `ClientCredentials` class is set to `true`, a local issuer address is not specified, and the issuer address specified by the [\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) or other federated binding is `http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self`, `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous`, or is `null`, then the Windows [!INCLUDE[infocard](../../../../includes/infocard-md.md)] issuer is used.</span></span>  
  
### <a name="to-configure-the-local-issuer-in-code"></a><span data-ttu-id="ea193-109">로컬 발급자를 코드로 구성하려면</span><span class="sxs-lookup"><span data-stu-id="ea193-109">To configure the local issuer in code</span></span>  
  
1. <span data-ttu-id="ea193-110">형식의 변수 만들기</span><span class="sxs-lookup"><span data-stu-id="ea193-110">Create a variable of type</span></span> <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
2. <span data-ttu-id="ea193-111">해당 변수를 <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> 클래스의`ClientCredentials` 속성에서 반환된 인스턴스에 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-111">Set the variable to the instance returned from the <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> property of the `ClientCredentials` class.</span></span> <span data-ttu-id="ea193-112">이 인스턴스는 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>에서 상속된 클라이언트의<xref:System.ServiceModel.ClientBase%601> 속성이나 <xref:System.ServiceModel.ChannelFactory.Credentials%2A>의 <xref:System.ServiceModel.ChannelFactory> 속성에 의해 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-112">That instance is returned by the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the client (inherited from <xref:System.ServiceModel.ClientBase%601>) or the <xref:System.ServiceModel.ChannelFactory.Credentials%2A> property of the <xref:System.ServiceModel.ChannelFactory>:</span></span>  
  
     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]  
  
3. <span data-ttu-id="ea193-113">로컬 발급자의 주소가 생성자의 인수인 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A>의 새 인스턴스에 <xref:System.ServiceModel.EndpointAddress> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-113">Set the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> property to a new instance of the <xref:System.ServiceModel.EndpointAddress>, with the address of the local issuer as an argument to the constructor.</span></span>  
  
     [!code-csharp[c_CreateSTS#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#10)]
     [!code-vb[c_CreateSTS#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#10)]  
  
     <span data-ttu-id="ea193-114">또는 새 <xref:System.Uri> 인스턴스를 생성자의 인수로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-114">Alternatively, create a new <xref:System.Uri> instance as an argument to the constructor.</span></span>  
  
     [!code-csharp[c_CreateSTS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#11)]
     [!code-vb[c_CreateSTS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#11)]  
  
     <span data-ttu-id="ea193-115">합니다 `addressHeaders` 매개 변수는 배열이 <xref:System.ServiceModel.Channels.AddressHeader> 표시 된 것 처럼 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ea193-115">The `addressHeaders` parameter is an array of <xref:System.ServiceModel.Channels.AddressHeader> instances, as shown.</span></span>  
  
     [!code-csharp[c_CreateSTS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#12)]
     [!code-vb[c_CreateSTS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#12)]  
  
4. <span data-ttu-id="ea193-116">바인딩을 사용 하 여 로컬 발급자에 대해 설정 된 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-116">Set the binding for the local issuer using the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> property.</span></span>  
  
     [!code-csharp[c_CreateSTS#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#13)]
     [!code-vb[c_CreateSTS#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#13)]  
  
5. <span data-ttu-id="ea193-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-117">Optional.</span></span> <span data-ttu-id="ea193-118">로컬 발급자에 대해 구성된 엔드포인트 동작을 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A> 속성에서 반환된 컬렉션에 추가하여 이러한 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-118">Add configured endpoint behaviors for the local issuer by adding such behaviors to the collection returned by the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A> property.</span></span>  
  
     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]  
  
### <a name="to-configure-the-local-issuer-in-configuration"></a><span data-ttu-id="ea193-119">로컬 발급자를 구성에서 구성하려면</span><span class="sxs-lookup"><span data-stu-id="ea193-119">To configure the local issuer in configuration</span></span>  
  
1. <span data-ttu-id="ea193-120">만들기를 [ \<localIssuer >](../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md) 의 자식 요소로 합니다 [ \<issuedToken >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) 자식인 자체의 요소를 [ \<clientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 끝점 동작에는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-120">Create a [\<localIssuer>](../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md) element as a child of the [\<issuedToken>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) element that is itself a child of the [\<clientCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element in an endpoint behavior.</span></span>  
  
2. <span data-ttu-id="ea193-121">`address` 특성을 토큰 요청이 허용되는 로컬 발급자의 주소로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-121">Set the `address` attribute to the address of the local issuer that will accept token requests.</span></span>  
  
3. <span data-ttu-id="ea193-122">`binding` 및 `bindingConfiguration` 특성을 로컬 발급자 엔드포인트와 통신할 때 사용할 적합한 바인딩을 참조하는 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-122">Set the `binding` and `bindingConfiguration` attributes to values that reference the appropriate binding to use when communicating with the local issuer endpoint.</span></span>  
  
4. <span data-ttu-id="ea193-123">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-123">Optional.</span></span> <span data-ttu-id="ea193-124">설정 된 [ \<identity >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) 의 자식 요소로 <`localIssuer`> 요소 로컬 발급자의 id 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-124">Set the [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) element as a child of the <`localIssuer`> element and specify identity information for the local issuer.</span></span>  
  
5. <span data-ttu-id="ea193-125">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-125">Optional.</span></span> <span data-ttu-id="ea193-126">설정 합니다 [ \<헤더 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) 의 자식 요소로 <`localIssuer`> 요소 로컬 발급자 주소를 올바로 하는 데 필요한 추가 헤더를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-126">Set the [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) element as a child of the <`localIssuer`> element and specify additional headers that are required in order to correctly address the local issuer.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ea193-127">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="ea193-127">.NET Framework Security</span></span>  
 <span data-ttu-id="ea193-128">지정된 바인딩에 발급자 주소와 바인딩을 지정하지 않으면 해당 바인딩을 사용하는 엔드포인트에는 로컬 발급자가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-128">Note that if an issuer address and binding are specified for a given binding, the local issuer is not used for endpoints that use that binding.</span></span> <span data-ttu-id="ea193-129">로컬 발급자를 항상 사용해야 하는 클라이언트는 이러한 바인딩을 사용하지 않도록 해야 하며 발급자 주소가 `null`이 되도록 바인딩을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea193-129">Clients who expect to always use the local issuer should ensure that they do not use such a binding or that they modify the binding so that the issuer address is `null`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea193-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="ea193-130">See also</span></span>

- [<span data-ttu-id="ea193-131">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="ea193-131">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="ea193-132">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="ea193-132">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="ea193-133">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="ea193-133">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
