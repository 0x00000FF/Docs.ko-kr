---
title: '&lt;netHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0d81ca0-87c5-4090-8baa-e390fd3656d2
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a7054102af46badc46ee7f987355cfce36860c6b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltnethttpbindinggt"></a><span data-ttu-id="2a119-102">&lt;netHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="2a119-102">&lt;netHttpBinding&gt;</span></span>
<span data-ttu-id="2a119-103">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스가 HTTP를 통해 통신할 수 있는 끝점을 구성 및 노출하는 데 사용할 수 있는 바인딩을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-103">Represents a binding that a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service can use to configure and expose endpoints that are able to communicate over HTTP.</span></span> <span data-ttu-id="2a119-104">이중 계약과 함께 사용하는 경우 WebSocket이 사용되고, 그렇지 않으면 HTTP가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-104">When used with a duplex contract, Web Sockets will be used, otherwise HTTP will be used.</span></span>  
  
 <span data-ttu-id="2a119-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2a119-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="2a119-106">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="2a119-106">\<bindings></span></span>  
<span data-ttu-id="2a119-107">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="2a119-107">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a119-108">구문</span><span class="sxs-lookup"><span data-stu-id="2a119-108">Syntax</span></span>  

```xml  
<netHttpBinding>  
   <binding   
       allowCookies="Boolean"  
       bypassProxyOnLocal="Boolean"  
       closeTimeout="TimeSpan"   
       hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
       maxBufferPoolSize="Integer"  
       maxBufferSize="Integer"  
       maxReceivedMessageSize="Integer"  
       messageEncoding="Binary/Text/Mtom"  
       name="string"   
       openTimeout="TimeSpan"   
       proxyAddress="URI"  
        receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan"  
              textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
              transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"  
       useDefaultWebProxy="Boolean"  
       <security mode="None/Transport/Message/TransportWithMessageCredential/TransportCredentialOnly">  
           <transport clientCredentialType="None/Basic/Digest/Ntlm/Windows/Certificate"  
                  proxyCredentialType="None/Basic/Digest/Ntlm/Windows"  
                                    realm="string" />  
           <message   
                 algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                            clientCredentialType="UserName/Certificate"/>  
       </security>  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"             maxNameTableCharCount="Integer"                maxStringContentLength="Integer" />  
   </binding>  
</netHttpBinding>  
```  
  
## <a name="type"></a><span data-ttu-id="2a119-109">형식</span><span class="sxs-lookup"><span data-stu-id="2a119-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a119-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2a119-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2a119-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a119-112">특성</span><span class="sxs-lookup"><span data-stu-id="2a119-112">Attributes</span></span>  
  
|<span data-ttu-id="2a119-113">특성</span><span class="sxs-lookup"><span data-stu-id="2a119-113">Attribute</span></span>|<span data-ttu-id="2a119-114">설명</span><span class="sxs-lookup"><span data-stu-id="2a119-114">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="2a119-115">클라이언트가 쿠키를 수락하고 이를 앞으로의 요청에서 전파할지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-115">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="2a119-116">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-116">The default is `false`.</span></span><br /><br /> <span data-ttu-id="2a119-117">쿠키를 사용하는 ASMX 웹 서비스와 상호 작용할 때 이 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-117">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="2a119-118">그러면 서버에서 반환된 쿠키가 해당 서비스에 대한 이후의 모든 클라이언트 요청에 자동으로 복사되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-118">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="2a119-119">로컬 주소에 대해 프록시 서버를 사용하지 않을 것인지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-119">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="2a119-120">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-120">The default is `false`.</span></span><br /><br /> <span data-ttu-id="2a119-121">주소가 로컬인 인터넷 리소스는 로컬 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-121">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="2a119-122">로컬 주소는 동일한 컴퓨터, 로컬 LAN 또는 인트라넷에 있는 주소이며, "http://webserver/" 및 "http://localhost/" 등의 URI와 같이 마침표(.)가 없는 구문으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-122">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs "http://webserver/" and "http://localhost/".</span></span><br /><br /> <span data-ttu-id="2a119-123">이 특성은 BasicHttpBinding으로 구성된 끝점이 로컬 리소스 액세스 시 프록시 서버를 사용할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-123">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="2a119-124">이 특성이 `true`이면 로컬 인터넷 리소스에 대한 요청은 프록시 서버를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-124">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="2a119-125">이 특성이 `true`로 설정된 경우 클라이언트가 동일한 시스템의 서비스와 통신할 때 프록시를 통하게 하려면 localhost 대신 호스트 이름을 사용해야 합니다</span><span class="sxs-lookup"><span data-stu-id="2a119-125">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="2a119-126">이 특성이 `false`이면 모든 인터넷 요청이 프록시 서버를 통해 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-126">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="2a119-127">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="2a119-128">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2a119-129">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-129">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="2a119-130">URI 구문 분석에 사용되는 HTTP 호스트 이름 비교 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-130">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="2a119-131">이 특성은 `System.ServiceModel.HostnameComparisonMode` 형식이며 URI에 대해 비교할 때 호스트 이름이 서비스에 연결하는 데 사용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-131">This attribute is of type `System.ServiceModel.HostnameComparisonMode`, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="2a119-132">기본값은 `StrongWildcard`>, 시 호스트 이름 무시 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-132">The default value is `StrongWildcard`>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="2a119-133">채널에서 메시지를 수신하는 메시지 버퍼 관리자가 사용하도록 할당된 최대 메모리를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-133">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="2a119-134">기본값은 524288(0x80000)바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-134">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="2a119-135">버퍼 관리자는 버퍼 풀을 사용하여 버퍼 사용 비용을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-135">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="2a119-136">버퍼는 메시지가 채널에서 나올 때 서비스를 이용하여 그 메시지를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-136">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="2a119-137">버퍼 풀에 메시지 로드를 처리하기에 충분한 메모리가 없는 경우 버퍼 관리자는 CLR 힙으로부터 추가 메모리를 할당해야 하며, 이로 인해 가비지 수집 오버헤드가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-137">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="2a119-138">CLR 가비지 힙으로부터 다량의 할당이 이루어지는 경우 버퍼 풀 크기가 너무 작은 것이므로, 이 특성으로 지정된 제한을 늘려 더 크게 할당하면 성능이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-138">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="2a119-139">이 바인딩으로 구성된 끝점에 대해 메시지가 처리되는 동안 해당 메시지를 저장하는 버퍼의 최대 크기(바이트)를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-139">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="2a119-140">기본값은 65,536바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-140">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="2a119-141">이 바인딩으로 구성된 채널에서 받을 수 있는 메시지(헤더 포함)의 최대 메시지 크기(바이트)를 정의하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-141">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="2a119-142">수신자에게 너무 큰 메시지를 보낸 발신자에게는 SOAP 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-142">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="2a119-143">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-143">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="2a119-144">기본값은 65,536바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-144">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="2a119-145">SOAP 메시지를 인코딩하는 데 사용되는 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-145">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="2a119-146">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-146">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2a119-147">-Text: 텍스트 메시지 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-147">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="2a119-148">Mtom: 조직 메커니즘 1.0 MTOM (Message Transmission) 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-148">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="2a119-149">기본값은 Text입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-149">The default is Text.</span></span> <span data-ttu-id="2a119-150">이 특성은 <xref:System.ServiceModel.WSMessageEncoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-150">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="2a119-151">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-151">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="2a119-152">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-152">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="2a119-153">각 바인딩에는 서비스의 메타데이터에서 함께 바인딩을 고유하게 식별하는 `name` 및 `namespace` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-153">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="2a119-154">또한 이 이름은 동일한 형식의 바인딩 간에 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-154">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="2a119-155">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-155">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="2a119-156">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-156">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`namespace`|<span data-ttu-id="2a119-157">바인딩의 XML 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-157">Specifies the XML namespace of the binding.</span></span> <span data-ttu-id="2a119-158">기본값은 "http://tempuri.org/Bindings"입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-158">The default value is "http://tempuri.org/Bindings".</span></span> <span data-ttu-id="2a119-159">각 바인딩에는 서비스의 메타데이터에서 함께 바인딩을 고유하게 식별하는 `name` 및 `namespace` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-159">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span>|  
|`openTimeout`|<span data-ttu-id="2a119-160">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="2a119-161">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2a119-162">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-162">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="2a119-163">HTTP 프록시의 주소를 포함하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-163">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="2a119-164">`useSystemWebProxy`를 `true`로 설정할 경우 이 설정은 `null`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-164">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="2a119-165">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-165">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="2a119-166">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-166">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="2a119-167">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-167">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2a119-168">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-168">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="2a119-169">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-169">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="2a119-170">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-170">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2a119-171">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-171">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="2a119-172">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-172">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="2a119-173">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-173">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2a119-174">-BigEndianUnicode: 유니코드 BigEndian 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-174">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="2a119-175">-Unicode: 16 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-175">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="2a119-176">UTF8: 8 비트 인코딩</span><span class="sxs-lookup"><span data-stu-id="2a119-176">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="2a119-177">기본값은 UTF8입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-177">The default is UTF8.</span></span> <span data-ttu-id="2a119-178">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-178">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="2a119-179">메시지가 요청 또는 응답에서 버퍼링되는지 또는 스트리밍되는지를 지정하는 유효한 <xref:System.ServiceModel.TransferMode> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-179">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="2a119-180">시스템의 자동 구성된 HTTP 프록시가 있는 경우 이를 사용할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-180">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="2a119-181">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-181">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="2a119-182">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2a119-182">Child Elements</span></span>  
  
|<span data-ttu-id="2a119-183">요소</span><span class="sxs-lookup"><span data-stu-id="2a119-183">Element</span></span>|<span data-ttu-id="2a119-184">설명</span><span class="sxs-lookup"><span data-stu-id="2a119-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a119-185">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="2a119-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="2a119-186">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-186">Defines the security settings for the binding.</span></span> <span data-ttu-id="2a119-187">이 요소는 `NetHttpSecurityElement` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-187">This element is of type `NetHttpSecurityElement`.</span></span>|  
|[<span data-ttu-id="2a119-188">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="2a119-188">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="2a119-189">이 바인딩으로 구성된 끝점에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-189">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="2a119-190">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-190">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a119-191">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2a119-191">Parent Elements</span></span>  
  
|<span data-ttu-id="2a119-192">요소</span><span class="sxs-lookup"><span data-stu-id="2a119-192">Element</span></span>|<span data-ttu-id="2a119-193">설명</span><span class="sxs-lookup"><span data-stu-id="2a119-193">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a119-194">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="2a119-194">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="2a119-195">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-195">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a119-196">설명</span><span class="sxs-lookup"><span data-stu-id="2a119-196">Remarks</span></span>  
 <span data-ttu-id="2a119-197">NetHttpBinding은 메시지를 보내기 위한 전송으로 HTTP를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-197">The NetHttpBinding uses HTTP as the transport for sending messages.</span></span> <span data-ttu-id="2a119-198">이중 계약과 함께 사용하는 경우 WebSocket이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-198">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="2a119-199">요청-회신 계약과 함께 사용하는 경우 NetHttpBinding은 이진 인코더를 사용하는 BasicHttpBinding처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-199">When used with a request-reply contract NetHttpBinding will behave like a BasicHttpBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="2a119-200">보안 기본적으로 꺼져 있지만의 모드 속성을 추가할 수는 [ \<보안 >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) 아닌 다른 값을 자식 요소가 `None`합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-200">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="2a119-201">이 요소는 기본적으로 "텍스트" 메시지 인코딩 및 UTF-8 텍스트 인코딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-201">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a119-202">예제</span><span class="sxs-lookup"><span data-stu-id="2a119-202">Example</span></span>  
 <span data-ttu-id="2a119-203">다음 예제에서는 첫 번째 및 두 번째 세대 웹 서비스와의 HTTP 통신 및 최대 상호 운용성을 제공하는 <xref:System.ServiceModel.NetHttpBinding>의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-203">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTP communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="2a119-204">클라이언트 및 서비스 구성 파일에 바인딩이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-204">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="2a119-205">바인딩 형식은 `binding` 요소의 `<endpoint>` 특성을 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-205">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="2a119-206">기본 바인딩을 구성하고 일부 설정을 변경하려면 바인딩 구성을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-206">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="2a119-207">끝점은 서비스에 대한 다음 구성 코드에 표시된 것처럼 `bindingConfiguration` 요소의 `<endpoint>` 특성을 사용하여 이름으로 바인딩 구성을 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-207">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>   
  <services>  
    <service   
        type="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
       <endpoint address=""  
             binding="netHttpBinding"  
             bindingConfiguration="Binding1"   
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
     <netHttpBinding>  
        <binding name="Binding1"   
               hostNameComparisonMode="StrongWildcard"   
               receiveTimeout="00:10:00"  
               sendTimeout="00:10:00"  
               openTimeout="00:10:00"  
               closeTimeout="00:10:00"  
               maxReceivedMessageSize="65536"   
               maxBufferSize="65536"   
               maxBufferPoolSize="524288"   
               transferMode="Buffered"   
               messageEncoding="Binary"   
               textEncoding="utf-8"  
               bypassProxyOnLocal="false"  
               useDefaultWebProxy="true" >  
              <security mode="None" />  
         </binding>  
     </netHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
## <a name="example"></a><span data-ttu-id="2a119-208">예제</span><span class="sxs-lookup"><span data-stu-id="2a119-208">Example</span></span>  
 <span data-ttu-id="2a119-209">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-209">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="2a119-210">끝점 주소에서 bindingConfiguration을 제거하고 바인딩에서 이름을 제거하면 이전 예제의 기능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-210">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name frm the binding.</span></span>  
  
```xml  
<system.serviceModel>   
  <services>  
    <service   
        type="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
       <endpoint address=""  
             binding="netHttpBinding"  
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
     <netHttpBinding>  
        <binding   
               hostNameComparisonMode="StrongWildcard"   
               receiveTimeout="00:10:00"  
               sendTimeout="00:10:00"  
               openTimeout="00:10:00"  
               closeTimeout="00:10:00"  
               maxReceivedMessageSize="65536"   
               maxBufferSize="65536"   
               maxBufferPoolSize="524288"   
               transferMode="Buffered"   
               messageEncoding="Binary"   
               textEncoding="utf-8"  
               bypassProxyOnLocal="false"  
               useDefaultWebProxy="true" >  
              <security mode="None" />  
         </binding>  
     </netHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="2a119-211">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a119-211">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a119-212">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a119-212">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="2a119-213">바인딩</span><span class="sxs-lookup"><span data-stu-id="2a119-213">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="2a119-214">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="2a119-214">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="2a119-215">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="2a119-215">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="2a119-216">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="2a119-216">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
