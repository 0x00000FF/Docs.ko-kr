---
title: '방법: HTTPS를 사용하여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기'
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: f39325829cf4b548482a6a570a5aa1fd65e61a1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62039535"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a><span data-ttu-id="2cb2f-102">방법: HTTPS를 사용하여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="2cb2f-102">How to: Create a Custom Reliable Session Binding with HTTPS</span></span>

<span data-ttu-id="2cb2f-103">이 항목에서는 신뢰할 수 있는 세션에 SSL(Secure Sockets Layer) 전송 보안을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-103">This topic demonstrates the use of Secure Sockets Layer (SSL) transport security with reliable sessions.</span></span> <span data-ttu-id="2cb2f-104">HTTPS를 통해 신뢰할 수 있는 세션을 사용하려면 신뢰할 수 있는 세션 및 HTTPS 전송을 사용하는 사용자 지정 바인딩을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-104">To use a reliable session over HTTPS, you must create a custom binding that uses a reliable session and the HTTPS transport.</span></span> <span data-ttu-id="2cb2f-105">구성 파일에서 코드를 사용 하 여 명령적으로 또는 선언적으로 신뢰할 수 있는 세션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-105">You enable the reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="2cb2f-106">이 절차에서는 신뢰할 수 있는 세션을 사용 하도록 설정 하려면 클라이언트와 서비스 구성 파일을 사용 하며 [  **\<httpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-106">This procedure uses the client and service configuration files to enable the reliable session and the [**\<httpsTransport>**](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) element.</span></span>

<span data-ttu-id="2cb2f-107">이 절차의 핵심 부분을  **\<끝점 >** 구성 요소 포함을 `bindingConfiguration` 라는 사용자 지정 바인딩 구성을 참조 하는 특성 `reliableSessionOverHttps`.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-107">The key part of this procedure is that the **\<endpoint>** configuration element contain a `bindingConfiguration` attribute that references a custom binding configuration named `reliableSessionOverHttps`.</span></span> <span data-ttu-id="2cb2f-108">합니다 [  **\<바인딩 >** ](../../../../docs/framework/misc/binding.md) 신뢰할 수 있는 세션 및 HTTPS 전송을 포함 하 여 사용 되도록 지정 하려면이 이름을 참조 하는 구성 요소  **\< reliableSession >** 하 고  **\<httpsTransport >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-108">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to specify that a reliable session and the HTTPS transport are used by including **\<reliableSession>** and **\<httpsTransport>** elements.</span></span>

<span data-ttu-id="2cb2f-109">이 예제의 소스 복사에 대해서 [사용자 지정 바인딩 신뢰할 수 있는 세션 HTTPS 통한](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-109">For the source copy of this example, see [Custom Binding Reliable Session over HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span></span>

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="2cb2f-110">HTTPS를 사용 하 여 신뢰할 수 있는 세션을 사용 하려면 CustomBinding으로 서비스를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-110">Configure the service with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="2cb2f-111">서비스 유형에 대한 서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. <span data-ttu-id="2cb2f-112">서비스 클래스에 서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="2cb2f-113">서비스 구현 내 주소 또는 바인딩 정보는 지정 되지 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="2cb2f-114">구성 파일에서 주소 또는 바인딩 정보를 검색 하는 코드를 작성 하는 데 필요한 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. <span data-ttu-id="2cb2f-115">만들기는 *Web.config* 파일에 대 한 끝점을 구성 하는 `CalculatorService` 라는 사용자 지정 바인딩을 사용 하 여 `reliableSessionOverHttps` 신뢰할 수 있는 세션 및 HTTPS 전송을 사용 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` with a custom binding named `reliableSessionOverHttps` that uses a reliable session and the HTTPS transport.</span></span>

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. <span data-ttu-id="2cb2f-116">만들기는 *Service.svc* 줄이 포함 된 파일:</span><span class="sxs-lookup"><span data-stu-id="2cb2f-116">Create a *Service.svc* file that contains the line:</span></span>

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. <span data-ttu-id="2cb2f-117">위치는 *Service.svc* 인터넷 정보 서비스 (IIS) 가상 디렉터리의 파일에에서 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="2cb2f-118">HTTPS를 사용 하 여 신뢰할 수 있는 세션을 사용 하려면 CustomBinding으로 클라이언트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-118">Configure the client with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="2cb2f-119">사용 된 [ServiceModel Metadata 유틸리티 도구 (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 서비스 메타 데이터에서 코드를 생성 하려면 명령줄에서.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="2cb2f-120">생성 되는 클라이언트 포함 된 `ICalculator` 클라이언트 구현에서 충족 해야 하는 서비스 계약을 정의 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-120">The client that's generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. <span data-ttu-id="2cb2f-121">또한 생성된 클라이언트 애플리케이션에는 `ClientCalculator`의 구현이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="2cb2f-122">서비스 구현 내 주소 및 바인딩 정보는 지정 되지 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-122">Note that the address and binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="2cb2f-123">구성 파일에서 주소 및 바인딩 정보를 검색 하는 코드를 작성 하는 데 필요한 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-123">You aren't required to write code to retrieve the address and binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. <span data-ttu-id="2cb2f-124">명명 된 사용자 지정 바인딩을 구성 `reliableSessionOverHttps` 신뢰할 수 있는 세션 및 HTTPS 전송을 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-124">Configure a custom binding named `reliableSessionOverHttps` to use the HTTPS transport and reliable sessions.</span></span>

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. <span data-ttu-id="2cb2f-125">애플리케이션에서 `ClientCalculator`의 인스턴스를 만든 다음 서비스 작업을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-125">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. <span data-ttu-id="2cb2f-126">클라이언트를 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-126">Compile and run the client.</span></span>  

## <a name="net-framework-security"></a><span data-ttu-id="2cb2f-127">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="2cb2f-127">.NET Framework security</span></span>

<span data-ttu-id="2cb2f-128">이 샘플에 사용 된 인증서 사용 하 여 만든 테스트 인증서 이므로 *Makecert.exe*와 같은 HTTPS 주소에 액세스 하려고 할 때 보안 경고가 나타납니다 `https://localhost/servicemodelsamples/service.svc`, 브라우저에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb2f-128">Because the certificate used in this sample is a test certificate created with *Makecert.exe*, a security alert appears when you try to access an HTTPS address, such as `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="2cb2f-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="2cb2f-129">See also</span></span>

- [<span data-ttu-id="2cb2f-130">신뢰할 수 있는 세션</span><span class="sxs-lookup"><span data-stu-id="2cb2f-130">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
