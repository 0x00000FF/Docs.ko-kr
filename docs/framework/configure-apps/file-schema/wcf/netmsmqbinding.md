---
title: <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: a68b44d7-7799-43a3-9e63-f07c782810a6
ms.openlocfilehash: 4bc8884b2d4cb6f8201e2038894c69d0805bddda
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738827"
---
# <a name="netmsmqbinding"></a><span data-ttu-id="5532c-101">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="5532c-101">\<netMsmqBinding></span></span>
<span data-ttu-id="5532c-102">시스템 간 통신에 적합한 대기 중인 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-102">Defines a queued binding suitable for cross-machine communication.</span></span>  
  
<span data-ttu-id="5532c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5532c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5532c-104">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="5532c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5532c-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="5532c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="5532c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<netMsmqBinding >**</span><span class="sxs-lookup"><span data-stu-id="5532c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netMsmqBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5532c-107">구문</span><span class="sxs-lookup"><span data-stu-id="5532c-107">Syntax</span></span>  
  
```xml  
<netMsmqBinding>
  <binding closeTimeout="TimeSpan"
           customDeadLetterQueue="Uri"
           deadLetterQueue="Uri"
           durable="Boolean"
           exactlyOnce="Boolean"
           maxBufferPoolSize="Integer"
           maxReceivedMessageSize="Integer"
           maxRetryCycles="Integer"
           name="String"
           openTimeout="TimeSpan"
           poisonMessageHandling="Disabled/EnabledIfSupported"
           queueTransferProtocol="Native/Srmp/SrmpSecure"
           receiveErrorHandling="Drop/Fault/Move/Reject"
           receiveTimeout="TimeSpan"
           receiveRetryCount="Integer"
           rejectAfterLastRetry="Boolean"
           retryCycleDelay="TimeSpan"
           sendTimeout="TimeSpan"
           timeToLive="TimeSpan"
           useActiveDirectory="Boolean"
           useMsmqTracing="Boolean"
           useSourceJournal="Boolean">
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/InfoCard" />
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5532c-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5532c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5532c-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5532c-110">특성</span><span class="sxs-lookup"><span data-stu-id="5532c-110">Attributes</span></span>  
  
|<span data-ttu-id="5532c-111">특성</span><span class="sxs-lookup"><span data-stu-id="5532c-111">Attribute</span></span>|<span data-ttu-id="5532c-112">설명</span><span class="sxs-lookup"><span data-stu-id="5532c-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="5532c-113">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="5532c-114">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5532c-115">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-115">The default is 00:01:00.</span></span>|  
|`customDeadLetterQueue`|<span data-ttu-id="5532c-116">애플리케이션별 배달 못 한 편지 큐의 위치를 포함하는 URI입니다. 이 큐에는 만료되었거나 전송 또는 배달하지 못한 메시지가 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-116">A URI that contains the location of the per-application dead letter queue, where messages that have expired or that have failed transfer or delivery are placed.</span></span><br /><br /> <span data-ttu-id="5532c-117">배달 못 한 편지 큐는 송신 애플리케이션의 큐 관리자에서 관리하는 큐로, 배달하지 못한 만료된 메시지가 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-117">The dead letter queue is a queue on the queue manager of the sending application for expired messages that have failed to be delivered.</span></span><br /><br /> <span data-ttu-id="5532c-118"><xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A>에서 지정 하는 URI는 net.tcp 체계를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-118">The URI that is specified by <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> must use the net.msmq scheme.</span></span>|  
|`deadLetterQueue`|<span data-ttu-id="5532c-119">배달 못 한 편지 큐가 있는 경우 큐의 형식을 지정하는 <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-119">A <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> value specifying which type of dead-letter queue to use, if any.</span></span><br /><br /> <span data-ttu-id="5532c-120">배달 못 한 편지 큐는 애플리케이션에 배달하지 못한 메시지가 전송되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-120">A dead-letter queue is the place where messages that have failed to be delivered to the application will be transferred.</span></span><br /><br /> <span data-ttu-id="5532c-121">`exactlyOnce` 보증을 요구하는 메시지(`exactlyOnce` 특성이 `true`로 설정)의 경우 이 특성은 기본적으로 MSMQ의 시스템 전체 트랜잭션 배달 못 한 편지 큐로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-121">For messages that require `exactlyOnce` assurance (that is, the `exactlyOnce` attribute is set to `true`), this attribute defaults to the system-wide transactional dead-letter queue in MSMQ.</span></span><br /><br /> <span data-ttu-id="5532c-122">보증이 필요하지 않은 메시지의 경우 이 특성은 기본적으로 `null`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-122">For messages that require no assurances, this attribute defaults to `null`.</span></span>|  
|`durable`|<span data-ttu-id="5532c-123">큐의 메시지가 지속적인지 또는 일시적인지를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-123">A Boolean value that indicates whether the message is durable or volatile in the queue.</span></span> <span data-ttu-id="5532c-124">영구 메시지는 큐 관리자의 충돌을 발생 시키는 반면, 휘발성 메시지는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-124">A durable message survives a queue manager crash, while a volatile message does not.</span></span> <span data-ttu-id="5532c-125">애플리케이션에서 더 낮은 대기 시간을 요구하며 어느 정도의 메시지 손실을 허용할 수 있다면 일시적 메시지가 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-125">Volatile messages are useful when applications require lower latency and can tolerate occasional lost messages.</span></span> <span data-ttu-id="5532c-126">`exactlyOnce` 특성을 `true`로 설정하면 메시지는 지속적이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-126">If the `exactlyOnce` attribute is set to `true`, the messages must be durable.</span></span> <span data-ttu-id="5532c-127">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-127">The default is `true`.</span></span>|  
|`exactlyOnce`|<span data-ttu-id="5532c-128">이 바인딩에서 처리하는 각 메시지가 한 번만 배달되는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-128">A Boolean value that indicates whether each message processed by this binding is delivered only once.</span></span> <span data-ttu-id="5532c-129">배달이 실패하면 발신자는 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-129">The sender will then be notified of delivery failures.</span></span> <span data-ttu-id="5532c-130">`durable`이 `false`이면 이 특성은 무시되고 배달 보증 없이 메시지가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-130">When `durable` is `false`, this attribute is ignored and messages are transferred without delivery assurance.</span></span> <span data-ttu-id="5532c-131">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-131">The default is `true`.</span></span> <span data-ttu-id="5532c-132">자세한 내용은 <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5532c-132">For more information, see <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="5532c-133">이 바인딩의 최대 버퍼 풀 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-133">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="5532c-134">기본값은 8입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-134">The default is 8.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="5532c-135">이 바인딩에 의해 처리되는 최대 메시지 크기(헤더 포함)(바이트)를 정의하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-135">A positive integer that defines the maximum message size, in bytes, including headers, that is processed by this binding.</span></span> <span data-ttu-id="5532c-136">이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-136">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="5532c-137">수신자는 메시지를 삭제 하 고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-137">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="5532c-138">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-138">The default is 65536.</span></span> <span data-ttu-id="5532c-139">이 메시지 크기 제한은 DoS (서비스 거부) 공격에 대 한 노출을 제한 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-139">This bound on message size is intended to limit exposure to Denial of Service (DoS) attacks.</span></span>|  
|`maxRetryCycles`|<span data-ttu-id="5532c-140">포이즌 메시지 검색 기능에 사용되는 재시도 주기 수를 나타내는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-140">An integer that indicates the number of retry cycles used by the poison-message detection feature.</span></span> <span data-ttu-id="5532c-141">모든 주기의 모든 배달 시도가 실패할 경우 메시지는 포이즌 메시지가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-141">A message becomes a poison message when it fails all delivery attempts of all cycles.</span></span> <span data-ttu-id="5532c-142">기본값은 3입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-142">The default is 3.</span></span> <span data-ttu-id="5532c-143">자세한 내용은 <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5532c-143">For more information, see <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>.</span></span>|  
|`name`|<span data-ttu-id="5532c-144">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-144">Required attribute.</span></span> <span data-ttu-id="5532c-145">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-145">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="5532c-146">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-146">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="5532c-147">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-147">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="5532c-148">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5532c-148">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="5532c-149">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="5532c-150">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5532c-151">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-151">The default is 00:01:00.</span></span>|  
|`QueueTransferProtocol`|<span data-ttu-id="5532c-152">이 바인딩에서 사용하는 대기 중인 통신 채널 전송을 지정하는 유효한 <xref:System.ServiceModel.QueueTransferProtocol> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-152">A valid <xref:System.ServiceModel.QueueTransferProtocol> value that specifies the queued communication channel transport that this binding uses.</span></span> <span data-ttu-id="5532c-153">MSMQ는 SOAP 신뢰할 수 있는 메시징 프로토콜을 사용 하는 경우 Active Directory 주소 지정을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-153">MSMQ does not support Active Directory addressing when using SOAP Reliable Messaging Protocol.</span></span> <span data-ttu-id="5532c-154">따라서 `useActiveDirectory` 특성이 `true`로 설정 된 경우이 특성을 `Srmp` 또는 `Srmps`로 설정 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-154">Therefore, you should not set this attribute to `Srmp` or `Srmps` when the `useActiveDirectory` attribute is set to `true`.</span></span>|  
|`receiveErrorHandling`|<span data-ttu-id="5532c-155">포이즌 및 비 dispatchable 메시지를 처리 하는 방법을 지정 하는 <xref:System.ServiceModel.ReceiveErrorHandling> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-155">A <xref:System.ServiceModel.ReceiveErrorHandling> value that specifies how poison and nondispatchable messages are handled.</span></span>|  
|`receiveRetryCount`|<span data-ttu-id="5532c-156">메시지를 재시도 큐로 전송하기 전에 큐 관리자가 메시지 전송을 시도하는 최대 횟수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-156">An integer that specifies the maximum number of times the queue manager should attempt to send a message before transferring it to the retry queue.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="5532c-157">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-157">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="5532c-158">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-158">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5532c-159">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-159">The default is 00:10:00.</span></span>|  
|`retryCycleDelay`|<span data-ttu-id="5532c-160">전달하지 못한 메시지를 즉시 다시 전달하려고 시도할 때 재시도 주기 사이의 지연 시간을 지정하는 TimeSpan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-160">A TimeSpan value that specifies the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span> <span data-ttu-id="5532c-161">실제 대기 시간이 더 길 수 있으므로 이 값은 최소 대기 시간만 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-161">The value defines only the minimum wait time because actual wait time can be longer.</span></span> <span data-ttu-id="5532c-162">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-162">The default value is 00:10:00.</span></span> <span data-ttu-id="5532c-163">자세한 내용은 <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5532c-163">For more information, see <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>.</span></span>|  
|`sendTimeout`|<span data-ttu-id="5532c-164">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="5532c-165">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5532c-166">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-166">The default is 00:01:00.</span></span>|  
|`timeToLive`|<span data-ttu-id="5532c-167">메시지가 만료되어 배달 못 한 큐에 추가되기 전에 메시지가 유효한 기간을 지정하는 TimeSpan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-167">A TimeSpan value that specifies how long the messages are valid before they are expired and put into the dead-letter queue.</span></span> <span data-ttu-id="5532c-168">기본값은 1.00:00:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-168">The default is 1.00:00:00.</span></span><br /><br /> <span data-ttu-id="5532c-169">이 특성은 시간을 다투는 메시지가 수신 애플리케이션에서 처리되기 전에 무효화되지 않도록 하기 위해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-169">This attribute is set to ensure that time-sensitive messages do not become stale before they are processed by the receiving applications.</span></span> <span data-ttu-id="5532c-170">지정된 시간 간격 내에 수신 애플리케이션에서 사용하지 않은 큐의 메시지는 만료된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-170">A message in a queue that is not consumed by the receiving application within the time interval specified is said to be expired.</span></span> <span data-ttu-id="5532c-171">만료된 메시지는 배달 못한 편지 큐라는 특수 큐로 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-171">Expired messages are sent to special queue called the dead letter queue.</span></span> <span data-ttu-id="5532c-172">배달 못 한 편지 큐의 위치는 보증에 따라 `DeadLetterQueue` 특성으로 설정되거나 해당 기본값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-172">The location of the dead letter queue is set with the `DeadLetterQueue` attribute or to the appropriate default, based on assurances.</span></span>|  
|`usingActiveDirectory`|<span data-ttu-id="5532c-173">Active Directory를 사용하여 큐 주소를 변환해야 하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-173">A Boolean value that specifies if queue addresses should be converted using Active Directory.</span></span><br /><br /> <span data-ttu-id="5532c-174">MSMQ 큐 주소는 경로 이름이 나 직접 형식 이름으로 구성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-174">MSMQ queue addresses can consist of path names or direct format names.</span></span> <span data-ttu-id="5532c-175">직접 형식 이름을 사용할 경우 MSMQ는 DNS, NetBIOS 또는 IP를 사용하여 컴퓨터 이름을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-175">With a direct format name, MSMQ resolves the computer name using DNS, NetBIOS or IP.</span></span> <span data-ttu-id="5532c-176">경로 이름을 사용할 경우 MSMQ는 Active Directory를 사용하여 컴퓨터 이름을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-176">With a path name, MSMQ resolves the computer name using Active Directory.</span></span><br /><br /> <span data-ttu-id="5532c-177">기본적으로 Windows Communication Foundation (WCF) 대기 중인 전송은 메시지 큐의 URI를 직접 형식 이름으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-177">By default, Windows Communication Foundation (WCF) queued transport converts the URI of a message queue to a direct format name.</span></span> <span data-ttu-id="5532c-178">`UseActiveDirectory` 속성을 true로 설정하면 대기 중 전송이 DNS, NetBIOS 또는 IP 대신 Active Directory를 사용하여 컴퓨터 이름을 확인하도록 애플리케이션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-178">By setting the `UseActiveDirectory` property to true, an application can specify that the queued transport should resolve the computer name using Active Directory rather than DNS, NetBIOS, or IP.</span></span>|  
|`useMsmqTracing`|<span data-ttu-id="5532c-179">이 바인딩이 처리하는 메시지를 추적할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-179">A Boolean value that specifies whether messages processed by this binding should be traced.</span></span> <span data-ttu-id="5532c-180">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-180">The default is `false`.</span></span> <span data-ttu-id="5532c-181">추적 기능을 사용하면 메시지가 메시지 큐 컴퓨터에 들어가거나 나올 때마다 보고서 메시지가 만들어진 후 보고서 큐로 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-181">When tracing is enabled, report messages are created and sent to the report queue each time the message leaves or arrives at a Message Queuing computer.</span></span>|  
|`useSourceJournal`|<span data-ttu-id="5532c-182">이 바인딩에서 처리하는 메시지의 복사본을 소스 업무 일지에 저장할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-182">A Boolean value that specifies copies of messages processed by this binding should be stored in the source journal.</span></span> <span data-ttu-id="5532c-183">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-183">The default is `false`.</span></span><br /><br /> <span data-ttu-id="5532c-184">대기 중 애플리케이션에서 컴퓨터의 나가는 큐를 떠난 메시지의 레코드를 보존해야 할 경우 메시지를 업무 일지 큐에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-184">Queued applications that want to keep a record of messages that have left the computer's outgoing queue can copy the messages to a journal queue.</span></span> <span data-ttu-id="5532c-185">메시지가 나가는 큐를 떠난 후 대상 컴퓨터에서 메시지가 수신 되었다는 승인이 수신 되 면 메시지 복사본이 보내는 컴퓨터의 시스템 업무 일지 큐에 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-185">Once a message leaves the outgoing queue and an acknowledgment is received that the message was received on the destination computer, a copy of the message is kept in the sending computer's system journal queue.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5532c-186">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5532c-186">Child Elements</span></span>  
  
|<span data-ttu-id="5532c-187">요소</span><span class="sxs-lookup"><span data-stu-id="5532c-187">Element</span></span>|<span data-ttu-id="5532c-188">설명</span><span class="sxs-lookup"><span data-stu-id="5532c-188">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5532c-189">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5532c-189">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="5532c-190">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-190">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="5532c-191">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-191">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="5532c-192">\<security ></span><span class="sxs-lookup"><span data-stu-id="5532c-192">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="5532c-193">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-193">Defines the security settings for the binding.</span></span> <span data-ttu-id="5532c-194">이 요소는 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-194">This element is of type <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5532c-195">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5532c-195">Parent Elements</span></span>  
  
|<span data-ttu-id="5532c-196">요소</span><span class="sxs-lookup"><span data-stu-id="5532c-196">Element</span></span>|<span data-ttu-id="5532c-197">설명</span><span class="sxs-lookup"><span data-stu-id="5532c-197">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5532c-198">\<bindings ></span><span class="sxs-lookup"><span data-stu-id="5532c-198">\<bindings></span></span>](bindings.md)|<span data-ttu-id="5532c-199">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-199">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5532c-200">주의</span><span class="sxs-lookup"><span data-stu-id="5532c-200">Remarks</span></span>  
 <span data-ttu-id="5532c-201">`netMsmqBinding` 바인딩은 MSMQ(Microsoft Message Queuing)를 전송으로 활용하면서 큐에 대한 지원을 제공하며, 느슨하게 결합된 애플리케이션, 실패 격리, 로드 조정 및 연결이 끊긴 작업을 지원할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5532c-201">The `netMsmqBinding` binding provides support for queuing by leveraging Microsoft Message Queuing (MSMQ) as a transport and enables support for loosely coupled applications, failure isolation, load leveling and disconnected operations.</span></span> <span data-ttu-id="5532c-202">이러한 기능에 대 한 설명은 [WCF의 큐](../../../wcf/feature-details/queues-in-wcf.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5532c-202">For a discussion of these features, see [Queues in WCF](../../../wcf/feature-details/queues-in-wcf.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5532c-203">예제</span><span class="sxs-lookup"><span data-stu-id="5532c-203">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <netMsmqBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 deadLetterQueue="net.msmq://localhost/blah"
                 durable="true"
                 exactlyOnce="true"
                 maxReceivedMessageSize="1000"
                 maxRetries="11"
                 maxRetryCycles="12"
                 poisonMessageHandling="Disabled"
                 rejectAfterLastRetry="false"
                 retryCycleDelay="00:05:55"
                 timeToLive="00:11:11"
                 sourceJournal="true"
                 useMsmqTracing="true"
                 useActiveDirectory="true">
          <security>
            <message clientCredentialType="Windows" />
          </security>
        </binding>
      </netMsmqBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="5532c-204">참조</span><span class="sxs-lookup"><span data-stu-id="5532c-204">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement>
- [<span data-ttu-id="5532c-205">\<binding ></span><span class="sxs-lookup"><span data-stu-id="5532c-205">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="5532c-206">바인딩</span><span class="sxs-lookup"><span data-stu-id="5532c-206">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5532c-207">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="5532c-207">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5532c-208">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="5532c-208">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5532c-209">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="5532c-209">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
