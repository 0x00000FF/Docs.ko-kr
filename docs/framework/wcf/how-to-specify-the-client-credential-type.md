---
title: "방법: 클라이언트 자격 증명 형식 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 35c3b5ee429f7c9337fa3c3e3eb0d0476e3f56d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="43f9c-102">방법: 클라이언트 자격 증명 형식 지정</span><span class="sxs-lookup"><span data-stu-id="43f9c-102">How to: Specify the Client Credential Type</span></span>
<span data-ttu-id="43f9c-103">전송 또는 메시지 보안 모드를 설정한 후에는 클라이언트 자격 증명 형식을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="43f9c-104">이 속성은 인증을 위한 서비스에 제공해야 할 자격 증명 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="43f9c-105">보안 모드 (클라이언트 자격 증명 형식을 설정 하기 전에 필요한 단계)를 참조 하는 설정 [하는 방법: 보안 모드 설정](../../../docs/framework/wcf/how-to-set-the-security-mode.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-105"> setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="43f9c-106">클라이언트 자격 증명 형식을 코드로 설정하려면</span><span class="sxs-lookup"><span data-stu-id="43f9c-106">To set the client credential type in code</span></span>  
  
1.  <span data-ttu-id="43f9c-107">서비스에서 사용할 바인딩의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="43f9c-108">이 예제에서는 <xref:System.ServiceModel.WSHttpBinding> 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2.  <span data-ttu-id="43f9c-109"><xref:System.ServiceModel.WSHttpSecurity.Mode%2A> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="43f9c-110">이 예제에서는 메시지 모드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-110">This example uses the Message mode.</span></span>  
  
3.  <span data-ttu-id="43f9c-111"><xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="43f9c-112">이 예제에서는 Windows 인증(<xref:System.ServiceModel.MessageCredentialType.Windows>)을 사용하도록 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="43f9c-113">클라이언트 자격 증명 형식을 구성에 설정하려면</span><span class="sxs-lookup"><span data-stu-id="43f9c-113">To set the client credential type in configuration</span></span>  
  
1.  <span data-ttu-id="43f9c-114">추가 [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소를 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-114">Add a [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2.  <span data-ttu-id="43f9c-115">자식 요소를 추가 하는 [ \<바인딩 >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-115">As a child element, add a [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3.  <span data-ttu-id="43f9c-116">적절한 바인딩을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-116">Add an appropriate binding.</span></span> <span data-ttu-id="43f9c-117">사용 하 여이 예제는 [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-117">This example uses the [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4.  <span data-ttu-id="43f9c-118">추가 [ \<바인딩 >](../../../docs/framework/misc/binding.md) 요소는 `name` 특성을 적절 한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-118">Add a [\<binding>](../../../docs/framework/misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="43f9c-119">이 예제에서는 "SecureBinding"을 이름으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-119">This example uses the name "SecureBinding".</span></span>  
  
5.  <span data-ttu-id="43f9c-120">`<security>` 바인딩을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-120">Add a `<security>` binding.</span></span> <span data-ttu-id="43f9c-121">`mode` 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="43f9c-122">이 예제에서는 `"Message"`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-122">This example sets it to `"Message"`.</span></span>  
  
6.  <span data-ttu-id="43f9c-123">보안 모드의 결정에 따라 `<message>` 또는 `<transport>` 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="43f9c-124">`clientCredentialType` 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="43f9c-125">이 예제에서는 `"Windows"`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43f9c-125">This example uses `"Windows"`.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="43f9c-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43f9c-126">See Also</span></span>  
 [<span data-ttu-id="43f9c-127">서비스에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="43f9c-127">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 [<span data-ttu-id="43f9c-128">방법: 보안 모드 설정</span><span class="sxs-lookup"><span data-stu-id="43f9c-128">How to: Set the Security Mode</span></span>](../../../docs/framework/wcf/how-to-set-the-security-mode.md)
