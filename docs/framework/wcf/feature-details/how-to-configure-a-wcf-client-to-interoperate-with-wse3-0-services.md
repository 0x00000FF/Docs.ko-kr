---
title: '방법: WSE3.0 서비스와 상호 운용하도록 WCF 클라이언트 구성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: 62642651516274a27c44abfc19e94dc529690ea9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699554"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a><span data-ttu-id="b8b26-102">방법: WSE3.0 서비스와 상호 운용하도록 WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="b8b26-102">How to: Configure a WCF Client to interoperate with WSE3.0 Services</span></span>
<span data-ttu-id="b8b26-103">Windows Communication Foundation (WCF) 클라이언트 WCF 클라이언트가 2004 년 8 월 버전의 Ws-addressing 사양 사용 하도록 구성 된 경우 Microsoft.NET (WSE) 서비스에 대 한 Web Services Enhancements 3.0과 유선 수준으로 호환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-103">Windows Communication Foundation (WCF) clients are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) services when WCF clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a><span data-ttu-id="b8b26-104">WSE 3.0 웹 서비스와 상호 운용하도록 WCF 클라이언트를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="b8b26-104">To configure a WCF client to interoperate with a WSE 3.0 Web service</span></span>  
  
1. <span data-ttu-id="b8b26-105">실행 합니다 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) WSE 3.0 웹 서비스에 대 한 WCF 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-105">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="b8b26-106">WSE 웹 서비스의 경우 WCF 클라이언트 클래스 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-106">For a WSE Web service, a WCF client class is created.</span></span>  
  
     <span data-ttu-id="b8b26-107">WCF 클라이언트 만들기에 대 한 자세한 내용은 참조는 [방법: 클라이언트를 만드는](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-107">For details about creating a WCF client, see the [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2. <span data-ttu-id="b8b26-108">WSE 3.0 웹 서비스와 통신할 수 있는 바인딩을 나타내는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-108">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="b8b26-109">다음 클래스의 일부인 합니다 [WSE와의 상호 운용](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-109">The following class is part of the [Interoperating with WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) sample.</span></span>  
  
    1. <span data-ttu-id="b8b26-110"><xref:System.ServiceModel.Channels.Binding> 클래스에서 파생되는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-110">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="b8b26-111">다음 코드 예제에서는 `WseHttpBinding` 클래스로부터 파생되는 <xref:System.ServiceModel.Channels.Binding>이라는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-111">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2. <span data-ttu-id="b8b26-112">WSE 턴키 어설션, 파생된 키가 필요한지 여부, 보안 세션이 사용되는지 여부, 서명 확인이 필요한지 여부 및 메시지 보호 설정을 지정하는 클래스에 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-112">Add properties to the class that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span>  
  
         <span data-ttu-id="b8b26-113">다음 코드 예제에서는 정의 된 `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext`, 및 `MessageProtectionOrder` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-113">The following code example defines the `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext`, and `MessageProtectionOrder` properties.</span></span> <span data-ttu-id="b8b26-114">WSE 턴키 어설션, 파생된 클래스가 필요한 지 여부, 보안 세션이 사용 되는지 여부, 서명 확인이 필요한 지 여부 및 메시지 보호 설정을 각각 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-114">They specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3. <span data-ttu-id="b8b26-115"><xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> 메서드를 재정의하여 바인딩 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-115">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="b8b26-116">다음 코드 예제에서는 `SecurityAssertion` 및 `MessageProtectionOrder` 속성의 값을 가져옴으로써 전송, 메시지 인코딩, 메시지 보호 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-116">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3. <span data-ttu-id="b8b26-117">클라이언트 응용 프로그램 코드에서 바인딩 속성을 설정하기 위해 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-117">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="b8b26-118">다음 코드 예제에서는 WSE 3.0에서 정의 된 대로 메시지 보호 및 인증이 WCF 클라이언트 사용 하도록 지정 `AnonymousForCertificate` 턴키 보안 어설션 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-118">The following code example specifies that the WCF client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="b8b26-119">또한 보안 세션 및 파생된 키도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-119">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="b8b26-120">예제</span><span class="sxs-lookup"><span data-stu-id="b8b26-120">Example</span></span>  
 <span data-ttu-id="b8b26-121">다음 코드 예제에서는 WSE 3.0 턴키 보안 어설션의 속성에 해당하는 속성을 노출하는 사용자 지정 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-121">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="b8b26-122">라고 하는 사용자 지정 바인딩 `WseHttpBinding`, WCF 클라이언트에 대 한 바인딩 속성을 지정 하려면 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b26-122">The custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a WCF client.</span></span>  

[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="b8b26-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="b8b26-123">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- [<span data-ttu-id="b8b26-124">WSE와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="b8b26-124">Interoperating with WSE</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29)
