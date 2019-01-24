---
title: '&lt;namedPipeTransport&gt;'
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: cdb2863ff376a92f7c4b679f4812b895ac3f2234
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518841"
---
# <a name="ltnamedpipetransportgt"></a><span data-ttu-id="b8a23-102">&lt;namedPipeTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="b8a23-102">&lt;namedPipeTransport&gt;</span></span>
<span data-ttu-id="b8a23-103">사용자 지정 바인딩에 포함될 때 채널에서 명명된 파이프를 사용하여 메시지를 전송하도록 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-103">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="b8a23-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b8a23-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b8a23-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b8a23-105">\<bindings></span></span>  
<span data-ttu-id="b8a23-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b8a23-106">\<customBinding></span></span>  
<span data-ttu-id="b8a23-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="b8a23-107">\<binding></span></span>  
<span data-ttu-id="b8a23-108">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="b8a23-108">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8a23-109">구문</span><span class="sxs-lookup"><span data-stu-id="b8a23-109">Syntax</span></span>  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpopint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8a23-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b8a23-110">Attributes and Elements</span></span>  
<span data-ttu-id="b8a23-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8a23-112">특성</span><span class="sxs-lookup"><span data-stu-id="b8a23-112">Attributes</span></span>  
<span data-ttu-id="b8a23-113">없음</span><span class="sxs-lookup"><span data-stu-id="b8a23-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b8a23-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b8a23-114">Child Elements</span></span>  
  
|<span data-ttu-id="b8a23-115">요소</span><span class="sxs-lookup"><span data-stu-id="b8a23-115">Element</span></span>|<span data-ttu-id="b8a23-116">설명</span><span class="sxs-lookup"><span data-stu-id="b8a23-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b8a23-117">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="b8a23-117">ChannelInitializationTimeout</span></span>|<span data-ttu-id="b8a23-118">연결이 끊어지기 전에 채널이 초기화 상태를 유지할 수 있는 최대 시간을 결정하는 <xref:System.TimeSpan>을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-118">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="b8a23-119">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="b8a23-119">ConnectionBufferSize</span></span>|<span data-ttu-id="b8a23-120">통신 중에 클라이언트나 서비스로부터 serialize된 메시지 청크를 전송할 때 사용되는 버퍼의 크기를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-120">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="b8a23-121">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="b8a23-121">hostNameComparisonMode</span></span>|<span data-ttu-id="b8a23-122">URI 비교 시 서비스에 액세스하는 데 호스트 이름이 사용되는지 여부를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-122">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="b8a23-123">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="b8a23-123">manualAddressing</span></span>|<span data-ttu-id="b8a23-124">메시지의 주소를 수동으로 지정해야 하는지 여부를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-124">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="b8a23-125">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="b8a23-125">maxBufferPoolSize</span></span>|<span data-ttu-id="b8a23-126">전송에 사용되는 버퍼 풀의 최대 크기(바이트)를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-126">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="b8a23-127">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="b8a23-127">maxBufferSize</span></span>|<span data-ttu-id="b8a23-128">사용할 버퍼의 최대 크기를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-128">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="b8a23-129">스트리밍된 메시지의 경우 이 값은 버퍼링된 모드에서 읽어오는 메시지 헤더의 최대 예상 크기 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-129">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="b8a23-130">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="b8a23-130">maxOutputDelay</span></span>|<span data-ttu-id="b8a23-131">메시지 청크 또는 전체 메시지를 보내기 전에 메모리에 버퍼링된 상태로 유지할 수 있는 최대 시간 간격을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-131">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="b8a23-132">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="b8a23-132">maxPendingAccepts</span></span>|<span data-ttu-id="b8a23-133">서비스에 들어오는 연결을 처리하기 위해 수신기에서 서비스가 대기할 수 있는 최대 채널 수를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-133">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="b8a23-134">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="b8a23-134">maxPendingConnections</span></span>|<span data-ttu-id="b8a23-135">서비스에서 디스패치를 대기하는 최대 연결 수를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-135">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="b8a23-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="b8a23-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="b8a23-137">받을 수 있는 최대 메시지 크기(바이트)를 가져오고 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-137">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="b8a23-138">transferMode</span><span class="sxs-lookup"><span data-stu-id="b8a23-138">transferMode</span></span>|<span data-ttu-id="b8a23-139">메시지가 연결 지향 전송을 사용하여 버퍼링되는지 아니면 스트리밍되는지를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-139">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="b8a23-140">\<connectionPoolSettings> of \<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="b8a23-140">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="b8a23-141">명명된 파이프 바인딩의 추가 연결 풀 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-141">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b8a23-142">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b8a23-142">Parent Elements</span></span>  
  
|<span data-ttu-id="b8a23-143">요소</span><span class="sxs-lookup"><span data-stu-id="b8a23-143">Element</span></span>|<span data-ttu-id="b8a23-144">설명</span><span class="sxs-lookup"><span data-stu-id="b8a23-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8a23-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="b8a23-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b8a23-146">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-146">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8a23-147">설명</span><span class="sxs-lookup"><span data-stu-id="b8a23-147">Remarks</span></span>  
<span data-ttu-id="b8a23-148">이 전송은 "net.pipe://hostname/path" 형식의 URI를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-148">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="b8a23-149">다른 URI 구성 요소는 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-149">Other URI components are optional.</span></span>  
  
<span data-ttu-id="b8a23-150">`namedPipeTransport` 요소는 명명된 파이프 전송 프로토콜을 구현하는 사용자 지정 바인딩을 만들기 위한 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-150">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="b8a23-151">이 전송은 WCF(Windows Communication Foundation)와 WCF 사이의 컴퓨터 통신에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8a23-151">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a23-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="b8a23-152">See also</span></span>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b8a23-153">전송</span><span class="sxs-lookup"><span data-stu-id="b8a23-153">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="b8a23-154">전송 선택</span><span class="sxs-lookup"><span data-stu-id="b8a23-154">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="b8a23-155">바인딩</span><span class="sxs-lookup"><span data-stu-id="b8a23-155">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b8a23-156">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="b8a23-156">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b8a23-157">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="b8a23-157">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b8a23-158">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b8a23-158">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
