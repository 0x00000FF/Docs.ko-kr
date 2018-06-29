---
title: 메시징 프로토콜
ms.date: 03/30/2017
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
ms.openlocfilehash: d188c79d3879ef383d24f56c81d66973266636bc
ms.sourcegitcommit: 9e18e4a18284ae9e54c515e30d019c0bbff9cd37
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37072724"
---
# <a name="messaging-protocols"></a><span data-ttu-id="5a7ca-102">메시징 프로토콜</span><span class="sxs-lookup"><span data-stu-id="5a7ca-102">Messaging Protocols</span></span>
<span data-ttu-id="5a7ca-103">Windows Communication Foundation (WCF) 채널 스택에서 인코딩 및 전송 채널 내부 메시지 표현을 통신 형식으로 변환 하 고 특정 전송을 사용 하 여 보낼을 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-103">The Windows Communication Foundation (WCF) channel stack employs encoding and transport channels to transform internal message representation into its wire format and send it by using a particular transport.</span></span> <span data-ttu-id="5a7ca-104">웹 서비스 상호 운용성을 위해 사용되는 가장 일반적인 전송은 HTTP이고, 웹 서비스에 사용되는 가장 일반적인 인코딩은 XML 기반 SOAP 1.1, SOAP 1.2 및 MTOM(Message Transmission Optimization Mechanism)입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-104">The most common transport used for Web services interoperability is HTTP, and the most common encodings used by Web services are XML-based SOAP 1.1, SOAP 1.2, and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="5a7ca-105">이 항목에서는 WCF 구현 세부 정보에서 다음 프로토콜에 대 한 설명 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-105">This topic covers WCF implementation details for the following protocols employed by <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span>  
  
|<span data-ttu-id="5a7ca-106">사양/문서</span><span class="sxs-lookup"><span data-stu-id="5a7ca-106">Specification/document</span></span>|<span data-ttu-id="5a7ca-107">링크</span><span class="sxs-lookup"><span data-stu-id="5a7ca-107">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="5a7ca-108">HTTP 1.1</span><span class="sxs-lookup"><span data-stu-id="5a7ca-108">HTTP 1.1</span></span>|http://www.ietf.org/rfc/rfc2616.txt|  
|<span data-ttu-id="5a7ca-109">SOAP 1.1 HTTP 바인딩</span><span class="sxs-lookup"><span data-stu-id="5a7ca-109">SOAP 1.1 HTTP Binding</span></span>|<span data-ttu-id="5a7ca-110">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/섹션 7</span><span class="sxs-lookup"><span data-stu-id="5a7ca-110">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/, Section 7</span></span>|  
|<span data-ttu-id="5a7ca-111">SOAP 1.2 HTTP 바인딩</span><span class="sxs-lookup"><span data-stu-id="5a7ca-111">SOAP 1.2 HTTP Binding</span></span>|<span data-ttu-id="5a7ca-112">http://www.w3.org/TR/soap12-part2/섹션 7</span><span class="sxs-lookup"><span data-stu-id="5a7ca-112">http://www.w3.org/TR/soap12-part2/, Section 7</span></span>|  
  
 <span data-ttu-id="5a7ca-113">다음 프로토콜에 대 한이 항목에서는 WCF 구현 세부 정보를 다룹니다 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> 및 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-113">This topic covers WCF implementation details for the following protocols  that <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employ.</span></span>  
  
|<span data-ttu-id="5a7ca-114">사양/문서</span><span class="sxs-lookup"><span data-stu-id="5a7ca-114">Specification/Document</span></span>|<span data-ttu-id="5a7ca-115">링크</span><span class="sxs-lookup"><span data-stu-id="5a7ca-115">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="5a7ca-116">XML</span><span class="sxs-lookup"><span data-stu-id="5a7ca-116">XML</span></span>|http://www.w3.org/TR/REC-xml|  
|<span data-ttu-id="5a7ca-117">SOAP 1.1</span><span class="sxs-lookup"><span data-stu-id="5a7ca-117">SOAP 1.1</span></span>|http://www.w3.org/TR/2000/NOTE-SOAP-20000508/|  
|<span data-ttu-id="5a7ca-118">SOAP 1.2 Core</span><span class="sxs-lookup"><span data-stu-id="5a7ca-118">SOAP 1.2 Core</span></span>|http://www.w3.org/TR/soap12-part1/|  
|<span data-ttu-id="5a7ca-119">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="5a7ca-119">WS-Addressing 2004/08</span></span>|http://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/|  
|<span data-ttu-id="5a7ca-120">W3C Web Services Addressing 1.0 - Core</span><span class="sxs-lookup"><span data-stu-id="5a7ca-120">W3C Web Services Addressing 1.0 - Core</span></span>|http://www.w3.org/TR/2006/REC-ws-addr-core-20060509|  
|<span data-ttu-id="5a7ca-121">W3C Web Services Addressing 1.0 - SOAP 바인딩</span><span class="sxs-lookup"><span data-stu-id="5a7ca-121">W3C Web Services Addressing 1.0 - SOAP Binding</span></span>|http://www.w3.org/TR/2006/REC-ws-addr-soap-20060509|  
|<span data-ttu-id="5a7ca-122">W3C Web Services Addressing 1.0 - WSDL 바인딩</span><span class="sxs-lookup"><span data-stu-id="5a7ca-122">W3C Web Services Addressing 1.0 - WSDL Binding</span></span>|http://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/|  
<span data-ttu-id="5a7ca-123">W3C Web Services Addressing 1.0 - Metadata</span><span class="sxs-lookup"><span data-stu-id="5a7ca-123">W3C Web Services Addressing 1.0 - Metadata</span></span>|http://www.w3.org/TR/ws-addr-metadata/|  
|<span data-ttu-id="5a7ca-124">WSDL SOAP1.1 바인딩</span><span class="sxs-lookup"><span data-stu-id="5a7ca-124">WSDL SOAP1.1 Binding</span></span>|http://www.w3.org/TR/wsdl/|  
|<span data-ttu-id="5a7ca-125">WSDL SOAP1.2 바인딩</span><span class="sxs-lookup"><span data-stu-id="5a7ca-125">WSDL SOAP1.2 Binding</span></span>|http://www.w3.org/Submission/wsdl11soap12/|  
  
 <span data-ttu-id="5a7ca-126">다음 프로토콜에 대 한이 항목에서는 WCF 구현 세부 정보를 다룹니다 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> 을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-126">This topic covers WCF implementation details for the following protocols that <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employs.</span></span>  
  
|<span data-ttu-id="5a7ca-127">사양/문서</span><span class="sxs-lookup"><span data-stu-id="5a7ca-127">Specification/document</span></span>|<span data-ttu-id="5a7ca-128">링크</span><span class="sxs-lookup"><span data-stu-id="5a7ca-128">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="5a7ca-129">XOP</span><span class="sxs-lookup"><span data-stu-id="5a7ca-129">XOP</span></span>|http://www.w3.org/TR/xop10/|  
|<span data-ttu-id="5a7ca-130">MTOM + SOAP 1.2 바인딩</span><span class="sxs-lookup"><span data-stu-id="5a7ca-130">MTOM + SOAP 1.2 Binding</span></span>|http://www.w3.org/TR/soap12-mtom/|  
|<span data-ttu-id="5a7ca-131">MTOM SOAP 1.1 바인딩</span><span class="sxs-lookup"><span data-stu-id="5a7ca-131">MTOM SOAP 1.1 Binding</span></span>|http://www.w3.org/Submission/soap11mtom10/|  
|<span data-ttu-id="5a7ca-132">MTOM WS-Policy Assertion</span><span class="sxs-lookup"><span data-stu-id="5a7ca-132">MTOM WS-Policy Assertion</span></span>|<span data-ttu-id="5a7ca-133">http://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-133">http://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/.</span></span>|  
  
 <span data-ttu-id="5a7ca-134">다음 XML 네임스페이스 및 관련 접두사는 이 항목 전체에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-134">The following XML namespaces and associated prefixes are used throughout this topic.</span></span>  
  
|<span data-ttu-id="5a7ca-135">접두사</span><span class="sxs-lookup"><span data-stu-id="5a7ca-135">Prefix</span></span>|<span data-ttu-id="5a7ca-136">네임스페이스 URI(Uniform Resource Identifier)</span><span class="sxs-lookup"><span data-stu-id="5a7ca-136">Namespace Uniform Resource Identifier (URI)</span></span>|  
|------------|---------------------------------------------------|  
|<span data-ttu-id="5a7ca-137">s11</span><span class="sxs-lookup"><span data-stu-id="5a7ca-137">s11</span></span>|http://schemas.xmlsoap.org/soap/envelope|  
|<span data-ttu-id="5a7ca-138">s12</span><span class="sxs-lookup"><span data-stu-id="5a7ca-138">s12</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="5a7ca-139">wsa</span><span class="sxs-lookup"><span data-stu-id="5a7ca-139">wsa</span></span>|http://www.w3.org/2004/08/addressing|  
|<span data-ttu-id="5a7ca-140">wsam</span><span class="sxs-lookup"><span data-stu-id="5a7ca-140">wsam</span></span>|http://www.w3.org/2007/05/addressing/metadata|  
|<span data-ttu-id="5a7ca-141">wsap</span><span class="sxs-lookup"><span data-stu-id="5a7ca-141">wsap</span></span>|http://schemas.xmlsoap.org/ws/2004/09/policy/addressing|  
|<span data-ttu-id="5a7ca-142">wsa10</span><span class="sxs-lookup"><span data-stu-id="5a7ca-142">wsa10</span></span>|http://www.w3.org/2005/08/addressing|  
|<span data-ttu-id="5a7ca-143">wsaw10</span><span class="sxs-lookup"><span data-stu-id="5a7ca-143">wsaw10</span></span>|http://www.w3.org/2006/05/addressing/wsdl|  
|<span data-ttu-id="5a7ca-144">xop</span><span class="sxs-lookup"><span data-stu-id="5a7ca-144">xop</span></span>|http://www.w3.org/2004/08/xop/include|  
|<span data-ttu-id="5a7ca-145">xmime</span><span class="sxs-lookup"><span data-stu-id="5a7ca-145">xmime</span></span>|http://www.w3.org/2004/06/xmlmime<br /><br /> http://www.w3.org/2005/05/xmlmime|  
<span data-ttu-id="5a7ca-146">dp</span><span class="sxs-lookup"><span data-stu-id="5a7ca-146">dp</span></span>|http://schemas.microsoft.com/net/2006/06/duplex|  
  
## <a name="soap-11-and-soap-12"></a><span data-ttu-id="5a7ca-147">SOAP 1.1 및 SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="5a7ca-147">SOAP 1.1 and SOAP 1.2</span></span>  
  
### <a name="envelope-and-processing-model"></a><span data-ttu-id="5a7ca-148">봉투 및 처리 모델</span><span class="sxs-lookup"><span data-stu-id="5a7ca-148">Envelope and Processing Model</span></span>  
 <span data-ttu-id="5a7ca-149">WCF는 SOAP 1.1 봉투 처리 Basic Profile 1.1 (에서는 BP11) 및 Basic Profile 1.0 (SSBP10)을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-149">WCF implements SOAP 1.1 envelope processing following Basic Profile 1.1 (BP11) and Basic Profile 1.0 (SSBP10).</span></span> <span data-ttu-id="5a7ca-150">SOAP 1.2 봉투 처리는 SOAP12-Part1에 따라 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-150">SOAP 1.2 Envelope processing is implemented following SOAP12-Part1.</span></span>  
  
 <span data-ttu-id="5a7ca-151">이 섹션에서는 BP11 및 SOAP12 1 부와 관련 하 여 WCF에서 특정 구현 선택 항목에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-151">This section explains certain implementation choices taken by WCF with regard to BP11 and SOAP12-Part1.</span></span>  
  
#### <a name="mandatory-header-processing"></a><span data-ttu-id="5a7ca-152">필수 헤더 처리</span><span class="sxs-lookup"><span data-stu-id="5a7ca-152">Mandatory Header Processing</span></span>  
 <span data-ttu-id="5a7ca-153">WCF 헤더 처리에 대 한 규칙을 따르는 `mustUnderstand` 변형 하 여 SOAP 1.1과 SOAP 1.2 사양에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-153">WCF follows rules for processing headers marked `mustUnderstand` described in the SOAP 1.1 and SOAP 1.2 specifications, with the following variations.</span></span>  
  
 <span data-ttu-id="5a7ca-154">예를 들어 관련된 바인딩 요소로 구성 된 개별 채널, 텍스트 메시지 인코딩, 보안, 신뢰할 수 있는 메시징 및 트랜잭션을 사용 하 고 WCF 채널 스택이 입력 하는 메시지를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-154">A message that enters the WCF channel stack is processed by individual channels configured by associated binding elements, for example, Text Message Encoding, Security, Reliable Messaging, and Transactions.</span></span> <span data-ttu-id="5a7ca-155">각 채널은 연결된 네임스페이스에서 헤더를 인식한 후 인식된 것으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-155">Each channel recognizes headers from the associated namespace and marks them as understood.</span></span> <span data-ttu-id="5a7ca-156">메시지가 디스패처에 전달되면 작업 포맷터는 해당 메시지/작업 계약에 필요한 헤더를 읽고 인식된 것으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-156">Once a message enters the dispatcher, the operation formatter reads headers expected by the corresponding message/operation contract and marks them understood.</span></span> <span data-ttu-id="5a7ca-157">그런 다음 디스패처는 나머지 헤더가 인식되지 않았지만 `mustUnderstand`로 표시되지 않았는지 확인하고 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-157">Then the dispatcher verifies whether any remaining headers are not understood but marked as `mustUnderstand` and throws an exception.</span></span> <span data-ttu-id="5a7ca-158">받는 사람을 대상으로 하는 `mustUnderstand` 헤더가 포함된 메시지는 받는 사람 응용 프로그램 코드로 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-158">Messages that contain `mustUnderstand` headers that are targeted at the recipient are not processed by recipient application code.</span></span>  
  
 <span data-ttu-id="5a7ca-159">이러한 계층화된 처리를 사용하면 SOAP 노드의 응용 프로그램 계층과 인프라 계층을 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-159">Such layered processing allows for separation between infrastructure layers and application layers of the SOAP node:</span></span>  
  
-   <span data-ttu-id="5a7ca-160">B1111: 인식 되지 않는 헤더 검색 메시지를 WCF 인프라 채널 스택에서 처리 나 응용 프로그램에서 처리 되기 전에</span><span class="sxs-lookup"><span data-stu-id="5a7ca-160">B1111: Headers that are not understood are detected after the message is processed by the WCF infrastructure channel stack, but before it is processed by application</span></span>  
  
     <span data-ttu-id="5a7ca-161">SOAP 1.1과 SOAP 1.2의 `mustUnderstand` 헤더 값은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-161">The `mustUnderstand` header value differs between SOAP 1.1 and SOAP 1.2.</span></span> <span data-ttu-id="5a7ca-162">Basic Profile 1.1에서 SOAP 1.1 메시지의 `mustUnderstand` 값은 0 또는 1이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-162">Basic Profile 1.1 requires that the `mustUnderstand` value be 0 or 1 for SOAP 1.1 messages.</span></span> <span data-ttu-id="5a7ca-163">SOAP 1.2에서는 0, 1, `false` 및 `true`를 값으로 사용할 수 있지만 정식으로 표현된 `xs:boolean` 값(`false`, `true`)을 내보내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-163">SOAP 1.2 allows 0, 1, `false`, and `true` as values, but recommends emitting a canonical representation of `xs:boolean` values (`false`, `true`).</span></span>  
  
-   <span data-ttu-id="5a7ca-164">B1112: WCF 내보냅니다 `mustUnderstand` 값 0과 1 SOAP 1.1 및 SOAP 1.2 버전 모두에 대 한 SOAP 봉투의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-164">B1112: WCF emits `mustUnderstand` values 0 and 1 for both SOAP 1.1 and SOAP 1.2 versions of the SOAP envelope.</span></span> <span data-ttu-id="5a7ca-165">전체 값 공간을 허용 하는 WCF `xs:boolean` 에 대 한는 `mustUnderstand` 헤더 (0, 1, `false`, `true`)</span><span class="sxs-lookup"><span data-stu-id="5a7ca-165">WCF accepts the entire value space of `xs:boolean` for the `mustUnderstand` header (0, 1, `false`, `true`)</span></span>  
  
#### <a name="soap-faults"></a><span data-ttu-id="5a7ca-166">SOAP 오류</span><span class="sxs-lookup"><span data-stu-id="5a7ca-166">SOAP Faults</span></span>  
 <span data-ttu-id="5a7ca-167">다음은 WCF 관련 SOAP 오류 구현 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-167">The following is a list of WCF-specific SOAP fault implementations.</span></span>  
  
-   <span data-ttu-id="5a7ca-168">B2121: WCF SOAP 1.1 오류 코드는 다음 반환: `s11:mustUnderstand`, `s11:Client`, 및 `s11:Server`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-168">B2121: WCF returns the following SOAP 1.1 Fault Codes: `s11:mustUnderstand`, `s11:Client`, and `s11:Server`.</span></span>  
  
-   <span data-ttu-id="5a7ca-169">B2122: WCF SOAP 1.2 오류 코드는 다음 반환: `s12:MustUnderstand`, `s12:Sender`, 및 `s12:Receiver`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-169">B2122: WCF returns the following SOAP 1.2 Fault Codes: `s12:MustUnderstand`, `s12:Sender`, and `s12:Receiver`.</span></span>  
  
### <a name="http-binding"></a><span data-ttu-id="5a7ca-170">HTTP 바인딩</span><span class="sxs-lookup"><span data-stu-id="5a7ca-170">HTTP Binding</span></span>  
  
#### <a name="soap-11-http-binding"></a><span data-ttu-id="5a7ca-171">SOAP 1.1 HTTP 바인딩</span><span class="sxs-lookup"><span data-stu-id="5a7ca-171">SOAP 1.1 HTTP Binding</span></span>  
 <span data-ttu-id="5a7ca-172">WCF에서는 Basic Profile 1.1 사양 단원 3.4에 따라 SOAP1.1 HTTP 바인딩을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-172">WCF implements SOAP1.1 HTTP binding following the Basic Profile 1.1 specification section 3.4 with the following clarifications:</span></span>  
  
-   <span data-ttu-id="5a7ca-173">B2211: WCF 서비스 HTTP POST 요청의 리디렉션을 구현 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-173">B2211: WCF service does not implement redirection of HTTP POST requests.</span></span>  
  
-   <span data-ttu-id="5a7ca-174">B2212: WCF 클라이언트 3.4.8에 따라 HTTP 쿠키를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-174">B2212: WCF clients support HTTP Cookies in accordance with 3.4.8.</span></span>  
  
#### <a name="soap-12-http-binding"></a><span data-ttu-id="5a7ca-175">SOAP 1.2 HTTP 바인딩</span><span class="sxs-lookup"><span data-stu-id="5a7ca-175">SOAP 1.2 HTTP Binding</span></span>  
 <span data-ttu-id="5a7ca-176">WCF는 SOAP 1.2-2 (SOAP12Part2) 사양에에 설명 된 대로 SOAP 1.2 HTTP 바인딩을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-176">WCF implements SOAP 1.2 HTTP binding as described in the SOAP 1.2-part 2 (SOAP12Part2) specification with the following clarifications.</span></span>  
  
 <span data-ttu-id="5a7ca-177">SOAP 1.2에는 `application/soap+xml` 미디어 유형에 대한 선택적 작업 매개 변수가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-177">SOAP 1.2 introduced an optional action parameter for the `application/soap+xml` media type.</span></span> <span data-ttu-id="5a7ca-178">이 매개 변수는 WS-Addressing을 사용하지 않을 때 SOAP 메시지 본문을 구문 분석할 필요 없이 메시지 디스패치를 최적화하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-178">This parameter is useful to optimize message dispatch without requiring that the body of the SOAP message be parsed when WS-Addressing is not used.</span></span>  
  
-   <span data-ttu-id="5a7ca-179">R2221: `application/soap+xml` 작업 매개 변수(SOAP 1.2 요청에 있는 경우)는 해당 WSDL 바인딩 내 `soapAction` 요소의 `wsoap12:operation` 특성과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-179">R2221: The `application/soap+xml` action parameter, when present on a SOAP 1.2 request, must match the `soapAction` attribute on the `wsoap12:operation` element inside the corresponding WSDL binding.</span></span>  
  
-   <span data-ttu-id="5a7ca-180">R2222: WS-Addressing 2004/08 또는 WS-Addressing 1.0을 사용할 경우 `application/soap+xml` 작업 매개 변수(SOAP 1.2 메시지에 있는 경우)가 `wsa:Action`과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-180">R2222: The `application/soap+xml` action parameter, when present on a SOAP 1.2 message, must match `wsa:Action` when WS-Addressing 2004/08 or WS-Addressing 1.0 are used.</span></span>  
  
 <span data-ttu-id="5a7ca-181">WS-Addressing을 사용하지 않고 들어오는 요청에 작업 매개 변수가 없는 경우 메시지 `Action`이 지정되지 않은 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-181">When WS-Addressing is disabled and an incoming request does not contain an action parameter, message `Action` is considered not specified.</span></span>  
  
## <a name="ws-addressing"></a><span data-ttu-id="5a7ca-182">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="5a7ca-182">WS-Addressing</span></span>  
 <span data-ttu-id="5a7ca-183">WCF는 세 가지 버전의 Ws-addressing을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-183">WCF implements 3 versions of WS-Addressing:</span></span>  
  
-   <span data-ttu-id="5a7ca-184">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="5a7ca-184">WS-Addressing 2004/08</span></span>  
  
-   <span data-ttu-id="5a7ca-185">W3C Web Services Addressing 1.0 Core(ADDR10-CORE) 및 SOAP 바인딩(ADDR10-SOAP)</span><span class="sxs-lookup"><span data-stu-id="5a7ca-185">W3C Web Services Addressing 1.0 Core  (ADDR10-CORE) and SOAP Binding (ADDR10-SOAP)</span></span>  
  
-   <span data-ttu-id="5a7ca-186">WS-Addressing 1.0 - Metadata</span><span class="sxs-lookup"><span data-stu-id="5a7ca-186">WS-Addressing 1.0 - Metadata</span></span>  
  
### <a name="endpoint-references"></a><span data-ttu-id="5a7ca-187">끝점 참조</span><span class="sxs-lookup"><span data-stu-id="5a7ca-187">Endpoint References</span></span>  
 <span data-ttu-id="5a7ca-188">모든 버전의 Ws-addressing WCF에서 구현 하는 끝점 참조를 사용 하 여 끝점을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-188">All versions of WS-Addressing that WCF implements use endpoint references to describe endpoints.</span></span>  
  
#### <a name="endpoint-references-and-ws-addressing-versions"></a><span data-ttu-id="5a7ca-189">끝점 참조 및 WS-Addressing 버전</span><span class="sxs-lookup"><span data-stu-id="5a7ca-189">Endpoint References and WS-Addressing Versions</span></span>  
 <span data-ttu-id="5a7ca-190">WCF Ws-addressing을 사용 하는 인프라 프로토콜의 하며 특히 많은 구현는 `EndpointReference` 요소 및 `W3C.WsAddressing.EndpointReferenceType` 클래스 (예: Ws-reliablemessaging, Ws-secureconversation, 및 WS-트러스트).</span><span class="sxs-lookup"><span data-stu-id="5a7ca-190">WCF implements a number of the infrastructure protocols that use WS-Addressing and in particular the `EndpointReference` element and `W3C.WsAddressing.EndpointReferenceType` class (for example, WS-ReliableMessaging, WS-SecureConversation, and WS-Trust).</span></span> <span data-ttu-id="5a7ca-191">WCF 다른 인프라 프로토콜과 함께 Ws-addressing의 두 버전의 사용을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-191">WCF supports the use of either version of WS-Addressing with other infrastructure protocols.</span></span> <span data-ttu-id="5a7ca-192">WCF 끝점 끝점당 한 버전의 Ws-addressing을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-192">WCF endpoints support one version of WS-Addressing per endpoint.</span></span>  
  
 <span data-ttu-id="5a7ca-193">3111,에 대 한 네임 스페이스는 `EndpointReference` 요소 또는 메시지와 WCF 끝점 교환에 사용 되는 형식에는 ws-addressing이 끝점에서 구현 된 버전과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-193">For R3111, the namespace for the `EndpointReference` element or type used in messages exchanged with a WCF endpoint must match the version of WS-Addressing implemented by this endpoint.</span></span>  
  
 <span data-ttu-id="5a7ca-194">예를 들어, WCF 끝점에서 Ws-reliablemessaging을 구현 하는 경우는 `AcksTo` 헤더 내의 끝점에서 반환 된 `CreateSequenceResponse` Ws-addressing 버전을 사용 하 여 하는 `EncodingBinding` 이 끝점에 대 한 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-194">For example, if a WCF endpoint implements WS-ReliableMessaging, the `AcksTo` header returned by such an endpoint inside `CreateSequenceResponse` uses the WS-Addressing version that the `EncodingBinding` element specifies for this endpoint.</span></span>  
  
#### <a name="endpoint-references-and-metadata"></a><span data-ttu-id="5a7ca-195">끝점 참조 및 메타데이터</span><span class="sxs-lookup"><span data-stu-id="5a7ca-195">Endpoint References and Metadata</span></span>  
 <span data-ttu-id="5a7ca-196">대부분의 시나리오에서는 지정된 끝점에 대해 메타데이터 또는 메타데이터 참조를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-196">A number of scenarios require communicating metadata or a reference to metadata for a given endpoint.</span></span>  
  
 <span data-ttu-id="5a7ca-197">B3121: WCF에서는 값 이나 참조로 끝점 참조에 대 한 메타 데이터를 포함 하도록 섹션 6 Ws-metadataexchange (MEX) 사양에서 설명 하는 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-197">B3121: WCF employs mechanisms described in the WS-MetadataExchange (MEX) specification Section 6 to include metadata for endpoint references by value or by reference.</span></span>  
  
 <span data-ttu-id="5a7ca-198">WCF 서비스에서 토큰 발급자가 발급 한 SAML Security Assertions Markup Language () 토큰을 사용 하 여 인증이 필요로 하는 경우를 생각해 볼 http://sts.fabrikam123.com합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-198">Consider a scenario where a WCF service requires authentication using a Security Assertions Markup Language (SAML) token issued by the token issuer at http://sts.fabrikam123.com.</span></span> <span data-ttu-id="5a7ca-199">WCF 끝점 사용 하 여이 인증 요구 사항을 설명 `sp:IssuedToken` 중첩 된와 함께 어설션을 `sp:Issuer` 토큰 발급자를 가리키는 어설션 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-199">The WCF endpoint describes this authentication requirement by using `sp:IssuedToken` assertion with a nested `sp:Issuer` assertion pointing to the token issuer.</span></span> <span data-ttu-id="5a7ca-200">`sp:Issuer` 어설션에 액세스하는 클라이언트 응용 프로그램은 토큰 발급자 끝점과 통신하는 방법을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-200">Client applications that access the `sp:Issuer` assertion need to know how to communicate with the token issuer endpoint.</span></span> <span data-ttu-id="5a7ca-201">클라이언트는 토큰 발급자에 대한 메타데이터를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-201">The client needs to know metadata about the token issuer.</span></span> <span data-ttu-id="5a7ca-202">MEX에 정의 된 끝점 참조 메타 데이터 확장을 사용 하 여 WCF 토큰 발급자 메타 데이터에 대 한 참조를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-202">Using the endpoint reference metadata extensions defined in MEX, WCF provides a reference to the token issuer metadata.</span></span>  
  
```xml  
<sp:IssuedToken>  
  <sp:Issuer>  
    <wsa10:Address>  
      http://sts.fabrikam123.com  
    </wsa10:Address>  
    <wsa10:Metadata>  
      <mex:Metadata>  
        <mex:MetadataSection>  
          <mex:MetadataReference>  
            <wsa10:Address>  
              http://sts.fabrikam123.com/mex  
            </wsa10:Address>  
          </mex:MetadataReference>  
        </mex:MetadataSection>  
      </mex:Metadata>  
    </wsa10:Metadata>  
  </sp:Issuer>  
</sp:IssuedToken>  
```  
  
### <a name="message-addressing-headers"></a><span data-ttu-id="5a7ca-203">메시지 주소 지정 헤더</span><span class="sxs-lookup"><span data-stu-id="5a7ca-203">Message Addressing Headers</span></span>  
  
#### <a name="message-headers"></a><span data-ttu-id="5a7ca-204">메시지 헤더</span><span class="sxs-lookup"><span data-stu-id="5a7ca-204">Message Headers</span></span>  
 <span data-ttu-id="5a7ca-205">두 Ws-addressing 버전에 대해 WCF 사용 하 여 다음과 같은 메시지 헤더 사양에 설명 된 대로 `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`, 및 `wsa:RelatesTo`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-205">For both WS-Addressing versions, WCF uses the following message headers as prescribed by the specifications `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`,and `wsa:RelatesTo`.</span></span>  
  
 <span data-ttu-id="5a7ca-206">B3211: 모든 Ws-addressing 버전에 대 한 WCF 하지만 기본적으로 Ws-addressing 메시지 헤더 생성 하지 않으므로 `wsa:FaultTo` 및 `wsa:From`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-206">B3211: For all WS-Addressing versions, WCF honors, but does not produce out of the box, WS-Addressing message headers `wsa:FaultTo` and `wsa:From`.</span></span>  
  
 <span data-ttu-id="5a7ca-207">WCF 응용 프로그램과 응용 프로그램 상호 작용 하는 이러한 메시지 헤더 및 WCF는 적절히 처리를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-207">Applications that interact with WCF applications can add these message headers and WCF will process them accordingly.</span></span>  
  
#### <a name="reference-parameters-and-properties"></a><span data-ttu-id="5a7ca-208">참조 매개 변수 및 속성</span><span class="sxs-lookup"><span data-stu-id="5a7ca-208">Reference Parameters and Properties</span></span>  
 <span data-ttu-id="5a7ca-209">WCF 끝점 참조 매개 변수 및 참조 속성의 처리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-209">WCF implements processing of endpoint reference parameters and reference p</span></span>  
  
 <span data-ttu-id="5a7ca-210">해당 사양에 따라 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-210">roperties in accordance with respective specifications.</span></span>  
  
 <span data-ttu-id="5a7ca-211">B3221: Ws-addressing 2004/08을 사용 하도록 구성, 참조 속성과 참조 매개 변수 처리 WCF 끝점 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-211">B3221: When configured to use WS-Addressing 2004/08, WCF endpoints do not differentiate between processing Reference Properties and Reference Parameters.</span></span>  
  
### <a name="message-exchange-patterns"></a><span data-ttu-id="5a7ca-212">메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="5a7ca-212">Message Exchange Patterns</span></span>  
 <span data-ttu-id="5a7ca-213">웹 서비스 작업 호출에 관련 된 메시지의 시퀀스 라고는 *메시지 교환 패턴*합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-213">The sequence of messages involved in the Web service operation invocation is referred to as the *message exchange pattern*.</span></span> <span data-ttu-id="5a7ca-214">WCF에서는 단방향, 요청-회신 및 이중 메시지 교환 패턴을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-214">WCF supports one-way, request-reply, and duplex message exchange patterns.</span></span> <span data-ttu-id="5a7ca-215">이 단원에서는 사용 중인 메시지 교환 패턴에 따른 메시지 처리에 대한 WS-Addressing 요구 사항에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-215">This section clarifies WS-Addressing requirements on message processing depending on the message exchange pattern being used.</span></span>  
  
 <span data-ttu-id="5a7ca-216">이 단원에서 요청자는 첫 번째 메시지를 보내고 응답자는 첫 번째 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-216">Throughout this section, the requester sends the first message and the responder receives the first message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="5a7ca-217">단방향 메시지</span><span class="sxs-lookup"><span data-stu-id="5a7ca-217">One-Way Message</span></span>  
 <span data-ttu-id="5a7ca-218">WCF 끝점을 사용 하 여 메시지를 지원 하도록 구성 된 경우는 주어진 `Action` 단방향 패턴을 따르도록는 WCF 끝점은 다음과 같은 동작 및 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-218">When a WCF endpoint is configured to support messages with a given `Action` to follow a one-way pattern, the WCF endpoint follows the following behaviors and requirements.</span></span> <span data-ttu-id="5a7ca-219">달리 지정 하지 않는 한 동작과 규칙 두 버전의 Ws-addressing WCF에서 지원에 대해 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-219">Unless otherwise specified, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>  
  
-   <span data-ttu-id="5a7ca-220">R3311: 요청자는 `wsa:To`, `wsa:Action` 및 끝점 참조에 지정된 모든 참조 매개 변수에 대한 헤더를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-220">R3311: The requester must include `wsa:To`, `wsa:Action`, and headers for all reference parameters specified by the endpoint reference.</span></span> <span data-ttu-id="5a7ca-221">WS-Addressing 2004/08을 사용하고 [reference properties]이 끝점 참조에 지정된 경우에도 해당 헤더를 메시지에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-221">When WS-Addressing 2004/08 is used and [reference properties] are specified by the endpoint reference, the corresponding headers must be added to the message too.</span></span>  
  
-   <span data-ttu-id="5a7ca-222">B3312: 요청자가 `MessageID`, `ReplyTo` 및 `FaultTo` 헤더를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-222">B3312: The requester may include `MessageID`, `ReplyTo`, and `FaultTo` headers.</span></span> <span data-ttu-id="5a7ca-223">이러한 헤더는 수신자 인프라에서 무시되고 응용 프로그램으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-223">The receiver infrastructure will ignore them, and they will be passed to the application.</span></span>  
  
-   <span data-ttu-id="5a7ca-224">R3313: HTTP를 사용하고 HTTP 응답 레그에 전송 중인 메시지가 없을 때 응답자는 HTTP 202 상태 코드와 함께 본문이 빈 HTTP 응답을 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-224">R3313: When HTTP is used and no message is being sent on the HTTP response leg, the responder must send an HTTP response with an empty body and an HTTP 202 status code.</span></span>  
  
     <span data-ttu-id="5a7ca-225">HTTP 전송을 사용 중이고 작업 계약에 메시지가 단방향으로 선언되어 있는 경우에도 인프라 메시지를 보내는 데 HTTP 응답을 사용할 수 있습니다. 예를 들어, 신뢰할 수 있는 메시징을 사용하여 HTTP 응답에서 `SequenceAcknowledgement` 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-225">When the HTTP transport is in use and the operation contract declares a message one-way, the HTTP response can still be used for sending infrastructure messages—for example, reliable messaging can send a `SequenceAcknowledgement` message on an HTTP response.</span></span>  
  
-   <span data-ttu-id="5a7ca-226">B3314: WCF 응답자는 단방향 메시지에 대 한 응답에서 오류 메시지를 전송 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-226">B3314: The WCF responder does not send a fault message in response to a one-way message.</span></span>  
  
#### <a name="request-reply"></a><span data-ttu-id="5a7ca-227">요청-회신</span><span class="sxs-lookup"><span data-stu-id="5a7ca-227">Request-Reply</span></span>  
 <span data-ttu-id="5a7ca-228">WCF 끝점 인 메시지에 대해 구성 된 경우는 주어진 `Action` 요청-회신 패턴을 따르도록 WCF 끝점 동작 및 요구 사항을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-228">When a WCF endpoint is configured for a message with a given `Action` to follow the request-reply pattern, the WCF endpoint follows the behaviors and requirements below.</span></span> <span data-ttu-id="5a7ca-229">지정 하지 않으면 두 버전의 Ws-addressing wcf에서 지원에 대 한 동작과 규칙 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-229">Unless specified otherwise, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>  
  
-   <span data-ttu-id="5a7ca-230">R3321: 요청자는 요청에 포함 해야 `wsa:To`, `wsa:Action`, `wsa:MessageID`, 모든 참조 매개 변수 또는 참조 속성 (또는 둘 다) 끝점 참조에 지정 된에 대 한 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-230">R3321: The requester must include in the request `wsa:To`, `wsa:Action`, `wsa:MessageID`, and headers for all reference parameters or reference properties (or both) specified by the endpoint reference.</span></span>  
  
-   <span data-ttu-id="5a7ca-231">R3322: WS-Addressing 2004/08을 사용하는 경우 `ReplyTo`도 요청에 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-231">R3322: When WS-Addressing 2004/08 is used, `ReplyTo` must also be included in the request.</span></span>  
  
-   <span data-ttu-id="5a7ca-232">R3323: Ws-addressing 1.0을 사용 하는 경우 및 `ReplyTo` 같음 [address] 속성을 사용 하 여 기본 끝점 참조 요청에 없는 "http://www.w3.org/2005/08/addressing/anonymous" 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-232">R3323: When WS-Addressing 1.0 is used and `ReplyTo` is not present in the request, a default endpoint reference with the [address] property equal to "http://www.w3.org/2005/08/addressing/anonymous" is used.</span></span>  
  
-   <span data-ttu-id="5a7ca-233">R3324: 요청자 있어야 `wsa:To`, `wsa:Action`, 및 `wsa:RelatesTo` 회신 메시지의 헤더 뿐 아니라 모든 참조 매개 변수 또는 참조 속성 (또는 둘 다)으로 지정 된 헤더는 `ReplyTo` 끝점 참조에는 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-233">R3324: The requester must include `wsa:To`, `wsa:Action`, and `wsa:RelatesTo` headers in the reply message, as well as headers for all reference parameters or reference properties (or both) specified by the `ReplyTo` endpoint reference in the request.</span></span>  
  
### <a name="web-services-addressing-faults"></a><span data-ttu-id="5a7ca-234">Web Services Addressing 오류</span><span class="sxs-lookup"><span data-stu-id="5a7ca-234">Web Services Addressing Faults</span></span>  
 <span data-ttu-id="5a7ca-235">R3411: WCF Ws-addressing 2004/08에 정의 된 다음 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-235">R3411: WCF produces the following faults defined by WS-Addressing 2004/08.</span></span>  
  
|<span data-ttu-id="5a7ca-236">코드</span><span class="sxs-lookup"><span data-stu-id="5a7ca-236">Code</span></span>|<span data-ttu-id="5a7ca-237">원인</span><span class="sxs-lookup"><span data-stu-id="5a7ca-237">Cause</span></span>|  
|----------|-----------|  
|<span data-ttu-id="5a7ca-238">wsa:DestinationUnreachable</span><span class="sxs-lookup"><span data-stu-id="5a7ca-238">wsa:DestinationUnreachable</span></span>|<span data-ttu-id="5a7ca-239">이 채널에 대해 설정된 회신 주소와 다른 `ReplyTo`를 사용하여 메시지가 도착했습니다. 받는 사람 헤더에 지정된 주소에서 수신 대기하는 끝점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-239">The message arrived with a `ReplyTo` that is different from the reply address established for this channel; there is no endpoint listening at the address specified in the To header.</span></span>|  
|<span data-ttu-id="5a7ca-240">wsa:ActionNotSupported</span><span class="sxs-lookup"><span data-stu-id="5a7ca-240">wsa:ActionNotSupported</span></span>|<span data-ttu-id="5a7ca-241">끝점과 연결된 인프라 채널 또는 디스패처가 `Action` 헤더에 지정된 동작을 인식하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-241">the infrastructure channels or dispatcher associated with the endpoint do not recognize the action specified in the `Action` header.</span></span>|  
  
 <span data-ttu-id="5a7ca-242">R3412: WCF Ws-addressing 1.0에 정의 된 다음 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-242">R3412: WCF produces the following faults defined by WS-Addressing 1.0.</span></span>  
  
|<span data-ttu-id="5a7ca-243">코드</span><span class="sxs-lookup"><span data-stu-id="5a7ca-243">Code</span></span>|<span data-ttu-id="5a7ca-244">원인</span><span class="sxs-lookup"><span data-stu-id="5a7ca-244">Cause</span></span>|  
|----------|-----------|  
|<span data-ttu-id="5a7ca-245">wsa10:InvalidAddressingHeader</span><span class="sxs-lookup"><span data-stu-id="5a7ca-245">wsa10:InvalidAddressingHeader</span></span>|<span data-ttu-id="5a7ca-246">중복 `wsa:To`, `wsa:ReplyTo`, `wsa:From` 또는 `wsa:MessageID`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-246">Duplicate `wsa:To`, `wsa:ReplyTo`, `wsa:From` or `wsa:MessageID`.</span></span> <span data-ttu-id="5a7ca-247">중복 `wsa:RelatesTo` 같은 `RelationshipType`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-247">Duplicate `wsa:RelatesTo` with the same `RelationshipType`.</span></span>|  
|<span data-ttu-id="5a7ca-248">wsa10:MessageAddressingHeaderRequired</span><span class="sxs-lookup"><span data-stu-id="5a7ca-248">wsa10:MessageAddressingHeaderRequired</span></span>|<span data-ttu-id="5a7ca-249">필수 주소 지정 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-249">The required Addressing header is missing.</span></span>|  
|<span data-ttu-id="5a7ca-250">wsa10:DestinationUnreachable</span><span class="sxs-lookup"><span data-stu-id="5a7ca-250">wsa10:DestinationUnreachable</span></span>|<span data-ttu-id="5a7ca-251">이 채널에 대해 설정된 회신 주소와 다른 `ReplyTo`를 사용하여 메시지가 도착했습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-251">The message arrived with a `ReplyTo` that is different from the reply address established for this channel.</span></span> <span data-ttu-id="5a7ca-252">받는 사람 헤더에 지정된 주소에서 수신 대기하는 끝점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-252">There is no endpoint listening at the address specified in the To header.</span></span>|  
|<span data-ttu-id="5a7ca-253">wsa10:ActionNotSupported</span><span class="sxs-lookup"><span data-stu-id="5a7ca-253">wsa10:ActionNotSupported</span></span>|<span data-ttu-id="5a7ca-254">`Action` 헤더에 지정된 동작이 끝점과 연결된 디스패처 또는 인프라 채널에서 인식되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-254">An action specified in the `Action` header is not recognized by the infrastructure channels or dispatcher associated with the endpoint.</span></span>|  
|<span data-ttu-id="5a7ca-255">wsa10:EndpointUnavailable</span><span class="sxs-lookup"><span data-stu-id="5a7ca-255">wsa10:EndpointUnavailable</span></span>|<span data-ttu-id="5a7ca-256">RM 채널에서 이 오류를 다시 보냅니다. 이는 끝점에서 `CreateSequence` 메시지의 주소 지정 헤더를 검사하여 시퀀스를 처리하지 않는다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-256">The RM channel sends this fault back, indicating the endpoint will not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>|  
  
 <span data-ttu-id="5a7ca-257">위 표의 코드가 SOAP 1.1의 경우 `FaultCode`에 매핑되고 SOAP 1.2의 경우 `SubCode`(Code=Sender)에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-257">Code in the preceding tables maps to `FaultCode` in SOAP 1.1 and `SubCode` (with Code=Sender) in SOAP 1.2.</span></span>  
  
### <a name="wsdl-11-binding-and-ws-policy-assertions"></a><span data-ttu-id="5a7ca-258">WSDL 1.1 바인딩 및 WS-Policy Assertion</span><span class="sxs-lookup"><span data-stu-id="5a7ca-258">WSDL 1.1 Binding and WS-Policy Assertions</span></span>  
  
#### <a name="indicating-use-of-ws-addressing"></a><span data-ttu-id="5a7ca-259">WS-Addressing 사용 지정</span><span class="sxs-lookup"><span data-stu-id="5a7ca-259">Indicating Use of WS-Addressing</span></span>  
 <span data-ttu-id="5a7ca-260">WCF 정책 어설션을 사용 하 여 특정 Ws-addressing 버전에 대 한 끝점 지원을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-260">WCF uses policy assertions to indicate endpoint support for a particular WS-Addressing version.</span></span>  
  
 <span data-ttu-id="5a7ca-261">다음 정책 어설션은 끝점 정책 주체가 [WS-PA]이고 끝점에서 보내거나 받은 메시지가 WS-Addressing 2004/08을 사용해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-261">The following policy assertion has Endpoint Policy Subject [WS-PA] and indicates messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>  
  
```xml  
<wsap:UsingAddressing />  
```  
  
 <span data-ttu-id="5a7ca-262">이 정책 어설션은 WS-Addressing 2004/08 사양을 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-262">This policy assertion augments the WS-Addressing 2004/08 specification.</span></span>  
  
 <span data-ttu-id="5a7ca-263">다음 정책 어설션은 보내거나 받은 메시지가 WS-Addressing 1.0을 사용해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-263">The following policy assertion this indicates that messages sent/received must use WS-Addressing 1.0.</span></span>  
  
```xml
<wsam:Addressing/>   
```  
  
 <span data-ttu-id="5a7ca-264">다음 정책 어설션은 끝점 정책 주체가 [WS-PA]이고 끝점에서 보내거나 받은 메시지가 WS-Addressing 2004/08을 사용해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-264">The following policy assertion has an Endpoint Policy Subject [WS-PA] and indicates that messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>  
  
```xml  
<wsaw10:UsingAddressing />  
```  
  
 <span data-ttu-id="5a7ca-265">`wsaw10:UsingAddressing` 요소는 [WS-Addressing-WSDL]에서 가져온 것이며 해당 사양 단원 3.1.2에 따라 WS-Policy 컨텍스트에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-265">The `wsaw10:UsingAddressing` element is borrowed from [WS-Addressing-WSDL] and is used in the context of WS-Policy in compliance with that specification, section 3.1.2.</span></span>  
  
 <span data-ttu-id="5a7ca-266">주소 지정을 사용해도 WSDL 1.1, SOAP 1.1 및 SOAP 1.2 HTTP 바인딩의 의미 체계가 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-266">Use of Addressing does not alter the semantics of WSDL 1.1, SOAP 1.1, and SOAP 1.2 HTTP Bindings.</span></span> <span data-ttu-id="5a7ca-267">예를 들어, 주소 지정 및 WSDL SOAP 1.x HTTP 바인딩을 사용하는 끝점에 보낸 요청에 대한 회신이 필요한 경우 HTTP 응답을 사용하여 회신을 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-267">For example, if a reply is expected to a request that is sent to an endpoint that uses Addressing and WSDL SOAP 1.x HTTP binding, the reply must be sent by using the HTTP response.</span></span>  
  
 <span data-ttu-id="5a7ca-268">http 응답을 통해 전송되는 회신의 경우 WS-AM 어설션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-268">For replies sent over the http response, the WS-AM assertion is:</span></span>  
  
```xml  
<wsam:AnonymousResponses/>  
```  
  
 <span data-ttu-id="5a7ca-269">완성된 정책 어설션은 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-269">The complete policy assertion might look like this:</span></span>  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
        <wsam:AnonymousResponses />   
    </wsp:Policy>  
</wsam:Addressing>  
```  
  
 <span data-ttu-id="5a7ca-270">그러나 요청자와 응답자 간에 설정된 두 개의 독립적인 역방향 HTTP 연결을 활용하는 메시지 교환 패턴이 있습니다(예: 응답자가 보낸 원하지 않은 단방향 메시지).</span><span class="sxs-lookup"><span data-stu-id="5a7ca-270">However, there are message exchange patterns that benefit from having two independent converse HTTP connections established between the requester and the responder, for example, unsolicited one-way messages sent by the responder.</span></span>  
  
 <span data-ttu-id="5a7ca-271">WCF에서는 두 기본 전송 채널 기준인 다른 출력 메시지에 사용 되 고 있는 입력된 메시지에 하나의 채널이 사용 되 고, 복합 이중 채널을 설정할 수 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-271">WCF offers a feature by which two underlying transport channels can form a Composite Duplex channel, where one channel is used for input messages and the other is used for output messages.</span></span> <span data-ttu-id="5a7ca-272">HTTP 전송의 경우 복합 이중 채널은 두 개의 역방향 HTTP 연결을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-272">In the case of the HTTP Transport, Composite Duplex provides two converse HTTP connections.</span></span> <span data-ttu-id="5a7ca-273">요청자가 한 연결을 사용하여 메시지를 응답자에게 보내고, 응답자는 다른 연결을 사용하여 메시지를 요청자에게 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-273">The requester uses one connection to send messages to the responder, and the responder uses the other to send messages back to the requester.</span></span>  
  
 <span data-ttu-id="5a7ca-274">별도의 http 요청을 통해 전송되는 회신의 경우 WS-AM 어설션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-274">For replies sent over separate http requests, the ws-am assertion is</span></span>  
  
```xml  
<wsam:NonAnonymousResponses/>  
```  
  
 <span data-ttu-id="5a7ca-275">완성된 정책 어설션은 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-275">The complete policy assertion might look like this:</span></span>  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
      <wsam:NonAnonymousResponses />   
   </wsp:Policy>  
  </wsam:Addressing>  
```  
  
 <span data-ttu-id="5a7ca-276">WSDL 1.1 SOAP 1.x HTTP 바인딩을 사용하는 끝점에서 끝점 정책 주체가 [WS-PA]인 다음 어설션을 사용하려면 요청자와 응답자 간에 주고 받는 메시지 흐름에 각각 사용할 두 개의 개별적인 역방향 HTTP 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-276">Use of the following assertion that has Endpoint Policy Subject [WS-PA] on endpoints that use WSDL 1.1 SOAP 1.x HTTP bindings requires two separate converse HTTP connections to be used for messages flowing from requester to responder and responder to requester, respectively.</span></span>  
  
```xml  
<cdp:CompositeDuplex/>  
```  
  
 <span data-ttu-id="5a7ca-277">앞의 문에 따라 요청 메시지의 `wsa:ReplyTo` 헤더에 대해 다음 요구 사항이 충족되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-277">The previous statement leads to the following requirements on the `wsa:ReplyTo` header for request messages:</span></span>  
  
-   <span data-ttu-id="5a7ca-278">R3514: 요청 메시지는 끝점에 보낸는 `ReplyTo` 헤더는 `[address]` 속성 같지 않음 "http://www.w3.org/2005/08/addressing/anonymous" 끝점이 WSDL 1.1 SOAP 1.x HTTP 바인딩을 사용 하 고 않은 정책 대안이 있는 경우는 `wsap10:UsingAddressing` 또는 `wsap:UsingAddressing` 와 결합 되어 어설션 `cdp:CompositeDuplex` 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-278">R3514: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property not equal to "http://www.w3.org/2005/08/addressing/anonymous" if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with a `wsap10:UsingAddressing` or `wsap:UsingAddressing` assertion coupled with `cdp:CompositeDuplex` attached.</span></span>  
  
-   <span data-ttu-id="5a7ca-279">R3515: 요청 메시지는 끝점에 보낸는 `ReplyTo` 헤더는 `[address]` 속성에 "http://www.w3.org/2005/08/addressing/anonymous", 수도 있고 한 `ReplyTo` 끝점이 WSDL 1.1 SOAP 1.x HTTP 바인딩을 사용 하 고 정책 대안이 있는 경우 헤더 와 `wsap10:UsingAddressing` 어설션은 `cdp:CompositeDuplex` 어설션은 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-279">R3515: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property equal to "http://www.w3.org/2005/08/addressing/anonymous", or not have a `ReplyTo` header at all, if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap10:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>  
  
-   <span data-ttu-id="5a7ca-280">R3516: 요청 메시지는 끝점에 보낸는 `ReplyTo` 헤더는 `[address]` 속성에 "http://www.w3.org/2005/08/addressing/anonymous" 끝점이 WSDL 1.1 SOAP 1.x HTTP 바인딩을 사용 하 고 않은 정책 대안이 있는 `wsap:UsingAddressing` 어설션은 고 없는 `cdp:CompositeDuplex`어설션은 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-280">R3516: Request messages sent to an endpoint must have a `ReplyTo` header with an `[address]` property equal to "http://www.w3.org/2005/08/addressing/anonymous" if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>  
  
 <span data-ttu-id="5a7ca-281">WS-addressing WSDL 사양에서는 세 개의 텍스트 값(required, optional, prohibited)을 가진 `<wsaw:Anonymous/>`wsa:ReplyTo 요소를 추가하여`wsa:ReplyTo` 헤더(단원 3.2)에 대한 요구 사항을 나타냄으로써 비슷한 프로토콜 바인딩을 설명하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-281">The WS-addressing WSDL specification attempts to describe similar protocol bindings by introducing an element `<wsaw:Anonymous/>` with three textual values (required, optional, and prohibited) to indicate requirements on the `wsa:ReplyTo` header (section 3.2).</span></span> <span data-ttu-id="5a7ca-282">그러나 해당 요소를 어설션으로 사용하여 대안 교차를 지원하려면 도메인별 확장이 필요하므로, 이러한 요소 정의는 WS-Policy 컨텍스트에서 어설션으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-282">Unfortunately, such element definition is not particularly usable as an assertion in the context of WS-Policy, because it requires domain-specific extensions to support the intersection of alternatives using such an element as an assertion.</span></span> <span data-ttu-id="5a7ca-283">또한 이러한 요소 정의는 통신 중인 끝점 동작과 반대로 `ReplyTo` 헤더 값을 나타내므로 HTTP 전송에만 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-283">Such element definition also indicates the value of the `ReplyTo` header as opposed to the endpoint behavior on the wire, which makes it specific to HTTP transport.</span></span>  
  
#### <a name="action-definition"></a><span data-ttu-id="5a7ca-284">동작 정의</span><span class="sxs-lookup"><span data-stu-id="5a7ca-284">Action Definition</span></span>  
 <span data-ttu-id="5a7ca-285">WS-Addressing 2004/08에서는 `wsa:Action` 요소에 대한 `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-285">WS-Addressing 2004/08 defines a `wsa:Action` attribute for the `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements.</span></span> <span data-ttu-id="5a7ca-286">WS-ADDR10-WSDL(WS-Addressing 1.0 WSDL 바인딩)에서는 비슷한 특성인 `wsaw10:Action`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-286">WS-Addressing 1.0 WSDL Binding (WS-ADDR10-WSDL) defines a similar attribute, `wsaw10:Action`.</span></span>  
  
 <span data-ttu-id="5a7ca-287">둘 간에는 WS-ADDR의 단원 3.3.2와 WS-ADDR10-WSDL의 단원 4.4.4에 각각 설명된 기본 동작 패턴의 의미 체계만 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-287">The only difference between the two is the default Action pattern semantics described in section 3.3.2 of WS-ADDR and section 4.4.4 of WS-ADDR10-WSDL, respectively.</span></span>  
  
 <span data-ttu-id="5a7ca-288">이 동일한 공유 하는 두 개의 끝점을 바람직합니다 `portType` (또는 계약 WCF 용어로) 하지만 서로 다른 버전의 Ws-addressing을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-288">It is a reasonable to have two endpoints that share the same `portType` (or contract, in WCF terminology) but using different versions of WS-Addressing.</span></span> <span data-ttu-id="5a7ca-289">그러나 동작이 `portType`에 정의되어 있고 `portType`을 구현하는 끝점을 통해 변경되지 않아야 할 경우 두 기본 동작 패턴을 모두 지원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-289">But given that Action is defined by the `portType` and should not change across the endpoints that implement the `portType`, it becomes impossible to support both default action patterns.</span></span>  
  
 <span data-ttu-id="5a7ca-290">이 문제를 해결 하려면 WCF 지원 단일 버전의는 `Action` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-290">To resolve this controversy, WCF supports a single version of the `Action` attribute.</span></span>  
  
 <span data-ttu-id="5a7ca-291">B3521: 사용 하 여 WCF는 `wsaw10:Action` 특성을 `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` WS-ADDR10-결정 WSDL에 정의 된 대로 요소는 `Action` 끝점에서 사용 되는 Ws-addressing 버전에 관계 없이 해당 메시지에 대 한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-291">B3521: WCF uses the `wsaw10:Action` attribute on `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements as defined in WS-ADDR10-WSDL to determine the `Action` URI for the corresponding messages irrespective of the WS-Addressing version used by the endpoint.</span></span>  
  
#### <a name="use-endpoint-reference-inside-wsdl-port"></a><span data-ttu-id="5a7ca-292">WSDL 포트에서 끝점 참조 사용</span><span class="sxs-lookup"><span data-stu-id="5a7ca-292">Use Endpoint Reference Inside WSDL Port</span></span>  
 <span data-ttu-id="5a7ca-293">WS-ADDR10-WSDL 단원 4.1에서는 `wsdl:port` 자식 요소를 포함하도록 `<wsa10:EndpointReference…/>` 요소를 확장하여 WS-Addressing 용어로 끝점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-293">WS-ADDR10-WSDL section 4.1 extends the `wsdl:port` element to include the `<wsa10:EndpointReference…/>` child element to describe the endpoint in WS-Addressing terms.</span></span> <span data-ttu-id="5a7ca-294">WCF 확장 Ws-addressing 2004/08에서이 유틸리티 허용 `<wsa:EndpointReference…/>` 의 자식 요소로 나타낼 `wsdl:port`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-294">WCF expands this utility on WS-Addressing 2004/08, allowing `<wsa:EndpointReference…/>` to appear as a child element of `wsdl:port`.</span></span>  
  
-   <span data-ttu-id="5a7ca-295">R3531: 끝점에 `<wsaw10:UsingAddressing/>` 정책 어설션과 연결된 정책 대안이 있는 경우 해당`wsdl:port` 요소는`<wsa10:EndpointReference …/>` 자식 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-295">R3531: If an endpoint has an attached policy alternative with a `<wsaw10:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa10:EndpointReference …/>`.</span></span>  
  
-   <span data-ttu-id="5a7ca-296">R3532: 경우는 `wsdl:port` 에 자식 요소가 `<wsa10:EndpointReference …/>`, `wsa10:EndpointReference/wsa10:Address` 자식 요소 값의 값과 일치 해야는 `@address` 형제의 특성 `wsdl:port` / `wsdl:location` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-296">R3532: If a `wsdl:port` contains a child element `<wsa10:EndpointReference …/>`, the `wsa10:EndpointReference/wsa10:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>  
  
-   <span data-ttu-id="5a7ca-297">R3533: 끝점에 `<wsap:UsingAddressing/>``wsdl:port` 정책 어설션과 연결된 정책 대안이 있는 경우 해당 `<wsa:EndpointReference …/>` 요소는 자식 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-297">R3533: If an endpoint has an attached policy alternative with `<wsap:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa:EndpointReference …/>`.</span></span>  
  
-   <span data-ttu-id="5a7ca-298">R3534: 경우는 `wsdl:port` 에 자식 요소가 `<wsa:EndpointReference …/>`, `wsa:EndpointReference/wsa:Address` 자식 요소 값의 값과 일치 해야는 `@address` 형제의 특성 `wsdl:port` / `wsdl:location` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-298">R3534: If a `wsdl:port` contains a child element `<wsa:EndpointReference …/>`, the `wsa:EndpointReference/wsa:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>  
  
### <a name="composition-with-ws-security"></a><span data-ttu-id="5a7ca-299">WS-Security를 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="5a7ca-299">Composition with WS-Security</span></span>  
 <span data-ttu-id="5a7ca-300">WS-ADDR 및 WS-ADDR10의 보안 고려 사항 단원에 따르면 모든 주소 지정 메시지 헤더를 메시지 본문과 함께 서명하여 바인딩하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-300">According to security consideration sections in WS-ADDR and WS-ADDR10, all addressing message headers are recommended to be signed together with the message body to bind them together.</span></span>  
  
 <span data-ttu-id="5a7ca-301">WS-Security가 메시지 무결성 보호를 위해 사용될 경우 WS-Addressing 메시지 헤더뿐 아니라 참조 매개 변수 또는 속성(또는 둘 모두)에서 생성된 헤더를 메시지 본문과 함께 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-301">When WS-Security is used for message integrity protection, WS-Addressing message headers as well as headers resulted from reference parameters or properties (or both) must be signed together with the body of the message.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="5a7ca-302">예제</span><span class="sxs-lookup"><span data-stu-id="5a7ca-302">Examples</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="5a7ca-303">단방향 메시지</span><span class="sxs-lookup"><span data-stu-id="5a7ca-303">One-Way Message</span></span>  
 <span data-ttu-id="5a7ca-304">이 시나리오에서 발신자는 수신자에게 단방향 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-304">In this scenario, the sender sends a one-way message to the receiver.</span></span> <span data-ttu-id="5a7ca-305">SOAP 1.2, HTTP 1.1 및 W3C WS-Addressing 1.0이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-305">SOAP 1.2, HTTP 1.1, and W3C WS-Addressing 1.0 are used.</span></span>  
  
 <span data-ttu-id="5a7ca-306">요청 메시지 구조: 메시지 헤더는 `wsa10:To` 및 `wsa10:Action` 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-306">The Request Message Structure: The message headers include `wsa10:To` and `wsa10:Action` elements.</span></span> <span data-ttu-id="5a7ca-307">메시지 본문은 응용 프로그램 네임스페이스의 특정 `<app:Ping>` 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-307">The message body includes a specific `<app:Ping>` element from the application namespace.</span></span>  
  
 <span data-ttu-id="5a7ca-308">HTTP 헤더: POST의 대상이 URI에서 일치 하는 `wsa10:To` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-308">HTTP Headers: The destination in POST matches the URI in the `wsa10:To` element.</span></span>  
  
 <span data-ttu-id="5a7ca-309">Content-Type 헤더에는 SOAP 1.2에 필요한 `application/soap+xml` 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-309">The Content-Type header has the value of `application/soap+xml` as required by SOAP 1.2.</span></span> <span data-ttu-id="5a7ca-310">`charset` 및 `action` 매개 변수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-310">Parameters `charset` and `action` are included.</span></span> <span data-ttu-id="5a7ca-311">Content-Type 헤더의 `action` 매개 변수가 `wsa10:Action` 메시지 헤더의 값과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-311">The `action` parameter of the Content-Type header matches the value of the `wsa10:Action` message header.</span></span>  
  
```  
POST http://fabrikam123.com/Service HTTP/1.1  
Content-Type: application/soap+xml; charset=utf-8;    
              action="http://fabrikam123.com/Service/OneWay"  
Host: 131.107.72.15  
Content-Length: 1501  
Expect: 100-continue  
Proxy-Connection: Keep-Alive  
<s12:Envelope>  
  <s12:Header>  
    <wsa10:To s12:mustUnderstand="1">  
        http://fabrikam123.com/Service  
    </wsa10:To>  
    <wsa10:Action s12:mustUnderstand="1">  
        http://fabrikam123.com/Service/OneWay   
    </wsa10:Action>  
  </s12:Header>  
  <s12:Body>  
    <Ping xmlns="http://fabrikam123.com/Service/">  
      <Text>Hello World</Text>  
    </Ping>  
  </s12:Body>  
</s12:Envelope>  
```  
  
 <span data-ttu-id="5a7ca-312">수신자는 빈 HTTP 응답 및 상태 202를 사용하여 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-312">The receiver responds with an empty HTTP response and status 202.</span></span> <span data-ttu-id="5a7ca-313">HTTP 응답의 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-313">An example of the HTTP response:</span></span>  
  
```  
HTTP/1.1 202 Accepted  
Date: Fri, 15 Jul 2005 08:56:07 GMT  
Server: Microsoft-IIS/6.0  
MicrosoftOfficeWebServer: 5.0_Pub  
X-Powered-By: ASP.NET  
X-AspNet-Version: 2.0.50215  
Cache-Control: private  
Content-Length: 0  
```  
  
## <a name="soap-message-transmission-optimization-mechanism"></a><span data-ttu-id="5a7ca-314">SOAP MTOM(Message Transmission Optimization Mechanism)</span><span class="sxs-lookup"><span data-stu-id="5a7ca-314">SOAP Message Transmission Optimization Mechanism</span></span>  
 <span data-ttu-id="5a7ca-315">이 섹션에서는 HTTP SOAP MTOM에 대 한 WCF 구현 세부 정보를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-315">This section describes the WCF implementation details for the HTTP SOAP MTOM.</span></span> <span data-ttu-id="5a7ca-316">MTOM 기술은 기존 텍스트/x m L 인코딩 또는 WCF 이진 인코딩과 동일한 클래스의 SOAP 메시지 인코딩 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-316">MTOM technology is SOAP message encoding mechanism of the same class as traditional text/XML encoding or WCF Binary encoding.</span></span> <span data-ttu-id="5a7ca-317">MTOM에는 다음과 같은 내용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-317">MTOM includes the following:</span></span>  
  
-   <span data-ttu-id="5a7ca-318">base64 인코딩된 이진 데이터를 개별 이진 부분으로 포함하는 XML 정보 항목을 최적화하는 [XOP]에 설명된 XML 인코딩 및 패키징 메커니즘</span><span class="sxs-lookup"><span data-stu-id="5a7ca-318">An XML encoding and packaging mechanism described by [XOP] that optimizes XML information items containing base64-encoded binary data into separate binary parts.</span></span>  
  
-   <span data-ttu-id="5a7ca-319">XOP 패키지의 각 이진 부분 및 XML Infoset을 개별 MIME 부분으로 serialize하는 XOP 패키지의 MIME 캡슐화</span><span class="sxs-lookup"><span data-stu-id="5a7ca-319">A MIME encapsulation of the XOP package that serializes the XML Infoset and each binary part of the XOP package into a separate MIME part.</span></span>  
  
-   <span data-ttu-id="5a7ca-320">SOAP 1.x 봉투에 적용되는 MIME XOP 인코딩</span><span class="sxs-lookup"><span data-stu-id="5a7ca-320">A MIME XOP encoding applied to SOAP 1.x Envelope.</span></span>  
  
-   <span data-ttu-id="5a7ca-321">HTTP 전송 바인딩</span><span class="sxs-lookup"><span data-stu-id="5a7ca-321">An HTTP transport binding.</span></span>  
  
 <span data-ttu-id="5a7ca-322">WCF와 함께 HTTP 이외의 전송을 사용 MTOM을 사용 하는 것이 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-322">It is possible to use MTOM with non-HTTP transports with WCF.</span></span> <span data-ttu-id="5a7ca-323">그러나 이 항목에서는 HTTP에 중점을 두어 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-323">However, in this topic we will focus on HTTP.</span></span>  
  
 <span data-ttu-id="5a7ca-324">MTOM 형식에서는 MTOM 자체와 XOP 및 MIME을 포함한 다양한 사양을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-324">The MTOM format leverages a large set of specifications covering MTOM itself, XOP, and MIME.</span></span> <span data-ttu-id="5a7ca-325">이 사양의 모듈성으로 인해 형식 및 처리 의미 체계에 대한 정확한 요구 사항을 재구성하기가 다소 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-325">Modularity of this specification set makes it somewhat difficult to reconstruct exact requirements on the format and processing semantics.</span></span> <span data-ttu-id="5a7ca-326">이 단원에서는 MTOM HTTP 바인딩의 형식 및 처리 요구 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-326">This section describes the format and processing requirements for MTOM HTTP binding.</span></span>  
  
### <a name="mtom-message-encoding"></a><span data-ttu-id="5a7ca-327">MTOM 메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="5a7ca-327">MTOM Message Encoding</span></span>  
  
#### <a name="generating-mtom-messages"></a><span data-ttu-id="5a7ca-328">MTOM 메시지 생성</span><span class="sxs-lookup"><span data-stu-id="5a7ca-328">Generating MTOM messages</span></span>  
 <span data-ttu-id="5a7ca-329">[XOP] 단원 3.1에서는 base64 값을 추상적으로 정의된 XOP 패키지에 포함하는 요소 정보 항목을 사용하여 XML을 인코딩하는 프로세스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-329">The [XOP] section 3.1 describes the process of encoding XML with element information items that contain base64 values into an abstractly defined XOP package.</span></span>  
  
 <span data-ttu-id="5a7ca-330">다음 단계에서는 MTOM 관련 인코딩 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-330">The following sequence of steps describes the MTOM-specific encoding process:</span></span>  
  
1.  <span data-ttu-id="5a7ca-331">인코딩할 SOAP 봉투와 요소 정보 항목이 포함 되어 있는지 확인 한 `[namespace name]` 의 "http://www.w3.org/2004/08/xop/include"와 `[local name]` 의 `Include`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-331">Ensure that the SOAP Envelope to be encoded contains no element information item with a `[namespace name]` of "http://www.w3.org/2004/08/xop/include" and a `[local name]` of `Include`.</span></span>  
  
2.  <span data-ttu-id="5a7ca-332">빈 MIME 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-332">Create an empty MIME package.</span></span>  
  
3.  <span data-ttu-id="5a7ca-333">원본 XML Infoset에서 최적화할 요소 정보 항목을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-333">Identify within the Original XML Infoset the element information items to be optimized.</span></span> <span data-ttu-id="5a7ca-334">항목을 최적화하려면 요소 정보 항목의 `[children]`을 구성하는 문자가 `xs:base64Binary`의 정규 형식(XSD-2, 3.2.16 base64Binary 참조)이고 공백 없는 콘텐츠 앞, 옆 또는 다음에 공백 문자를 포함하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-334">For the items to be optimized, the characters that make up the `[children]` of the element information item must be in the canonical form of `xs:base64Binary` (see XSD-2, 3.2.16 base64Binary) and must not contain any whitespace characters preceding, inline with, or following the non-whitespace content.</span></span>  
  
4.  <span data-ttu-id="5a7ca-335">원본 SOAP 봉투의 복사본인 XOP SOAP 봉투를 만듭니다. 단, 이전 단계에서 식별된 각 요소 정보 항목의 자식을 다음과 같이 구성된 `xop:Include` 요소 정보 항목으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-335">Create an XOP SOAP Envelope that is a copy of the Original SOAP Envelope, but with the children of each element information item identified in the previous step replaced by an `xop:Include` element information item constructed as follows:</span></span>  
  
    1.  <span data-ttu-id="5a7ca-336">대체된 문자를 base64 인코딩된 데이터로 처리하여 이진 데이터로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-336">Transform the replaced characters into binary data by processing them as base64-encoded data.</span></span>  
  
    2.  <span data-ttu-id="5a7ca-337">R3133 및 R3134 요구 사항을 충족하는 고유한 Content-ID 헤더 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-337">Generate a unique Content-ID header value that satisfies requirements R3133 and R3134.</span></span>  
  
    3.  <span data-ttu-id="5a7ca-338">이진 값을 사용하여 Content-Transfer-Encoding MIME 헤더를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-338">Generate a Content-Transfer-Encoding MIME header with the value binary.</span></span>  
  
    4.  <span data-ttu-id="5a7ca-339">최적화할 요소 정보 항목(새로 삽입된 `xop:Include` 요소 정보 항목의 [parent])에 `xmime:contentType` 특성 정보 항목이 있는 경우 `xmime:contentType` 특성 값을 사용하여 Content-Type MIME 헤더를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-339">If the element information item being optimized (the [parent] of the newly inserted `xop:Include` element information item) has an `xmime:contentType` attribute information item, generate a Content-Type MIME header with the value of the `xmime:contentType` attribute.</span></span>  
  
    5.  <span data-ttu-id="5a7ca-340">base64, 4b의 Content-ID 헤더, 4c의 Content- Transfer-Encoding 헤더, Content-Type 헤더(4d 단계에서 생성된 경우)로 처리된 대체 문자에서 디코딩된 이진 데이터로 형성된 콘텐츠를 사용하여 새 이진 MIME 부분을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-340">Generate a new binary MIME part with content formed by binary data decoded from the replaced characters processed as base64, Content-ID header from 4b, Content- Transfer-Encoding header from 4c, Content-Type header if generated in step 4d.</span></span>  
  
    6.  <span data-ttu-id="5a7ca-341">4b 단계에서 생성된 Content-ID 헤더 값에서 파생된 cid: uri 값을 사용하여 `href` 특성을 `xop:Include` 요소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-341">Add an `href` attribute to the `xop:Include` element with the value cid: uri derived from Content-ID header value generated in step 4b.</span></span> <span data-ttu-id="5a7ca-342">묶는 제거 "\<" 및 ">" 문자를 이스케이프 URL 문자열 및 접두사를 추가 합니다. 나머지 `cid:`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-342">Remove the enclosing "\<" and ">" characters, URL-escape the remaining string, and add the prefix `cid:`.</span></span> <span data-ttu-id="5a7ca-343">RFC1738 및 RFC2396으로 이스케이프하려면 다음과 같은 최소 문자 집합이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-343">The following minimum character set is required to be escaped by RFC1738 and RFC2396.</span></span> <span data-ttu-id="5a7ca-344">다른 문자를 이스케이프할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-344">Other characters can be escaped.</span></span>  
  
        ```  
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">  
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"  
        ```  
  
5.  <span data-ttu-id="5a7ca-345">4단계의 XOP SOAP 봉투를 사용하여 루트 MIME 부분을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-345">Create a root MIME part with the XOP SOAP Envelope from step 4.</span></span>  
  
6.  <span data-ttu-id="5a7ca-346">HTTP Content-Type 헤더를 포함하여 HTTP 헤더를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-346">Write the HTTP headers, including the HTTP Content-Type header.</span></span>  
  
7.  <span data-ttu-id="5a7ca-347">MIME 패키지를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-347">Write the MIME package.</span></span>  
  
#### <a name="processing-mtom-messages"></a><span data-ttu-id="5a7ca-348">MTOM 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="5a7ca-348">Processing MTOM messages</span></span>  
 <span data-ttu-id="5a7ca-349">MTOM 메시지 처리 과정은 이전 "MTOM 메시지 생성" 단원에서 설명한 프로세스와 정확히 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-349">Processing of an MTOM message is the exact reverse of the process described in the preceding "Generating MTOM messages" section:</span></span>  
  
1.  <span data-ttu-id="5a7ca-350">루트 MIME 부분에 Content-Type `application/xop+xml`이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-350">Ensure the root MIME part has the Content-Type `application/xop+xml`.</span></span>  
  
2.  <span data-ttu-id="5a7ca-351">패키지의 루트 MIME 부분을 구문 분석하여 SOAP 봉투를 XML 문서로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-351">Construct a SOAP Envelope by parsing the root MIME part of the package as an XML document.</span></span> <span data-ttu-id="5a7ca-352">문자 인코딩은 루트 MIME 부분 Content-Type의 `charset` 매개 변수에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-352">Character encoding is determined by the `charset` parameter of the Content-Type of the root MIME part.</span></span>  
  
3.  <span data-ttu-id="5a7ca-353">`xop:Include` 요소 정보 항목을 [children] 속성의 단독 멤버로 가진 구성된 SOAP 봉투의 각 요소 정보 항목의 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-353">For each element information item in the constructed SOAP Envelope, which has, as the sole member of its [children] property, an `xop:Include` element information item:</span></span>  
  
    1.  <span data-ttu-id="5a7ca-354">`cid:` 접두사를 제거하고 `@href` 요소의 `xop:Include` 특성 값에서 모든 URI 이스케이프 시퀀스(RFC 2396)를 이스케이프 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-354">Remove the `cid:` prefix and unescape all URI-escape sequences (RFC 2396) in the value of the `@href` attribute of the `xop:Include` element.</span></span> <span data-ttu-id="5a7ca-355">결과 문자열을 묶습니다 "\<", ">"입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-355">Enclose the result string in "\<", ">".</span></span>  
  
    2.  <span data-ttu-id="5a7ca-356">3a 단계에서 파생된 문자열과 일치하는 Content-ID 헤더 값을 가진 MIME 부분을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-356">Locate the MIME part with the Content-ID header value that matches the string derived in step 3a.</span></span>  
  
    3.  <span data-ttu-id="5a7ca-357">각 항목의 `xop:Include` 속성에 나타나는 `children` 요소 정보 항목을 3b 단계에서 식별된 MIME 부분의 엔터티 본문의 정규 base64 인코딩(XSD-2, 3.2.16 base64Binary 참조)을 나타내는 문자 정보 항목으로 대체합니다. 즉, `xop:Include` 요소 정보 항목을 패키지 부분에서 재구성된 데이터로 효과적으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-357">Replace the `xop:Include` element information item that appears in the `children` property of each item with the character information items that represent the canonical base64 encoding (see XSD-2, 3.2.16 base64Binary) of the entity body of the MIME part identified in step 3b (effectively replace the `xop:Include` element information item with the data reconstructed from the package part).</span></span>  
  
#### <a name="http-content-type-header"></a><span data-ttu-id="5a7ca-358">HTTP Content-Type 헤더</span><span class="sxs-lookup"><span data-stu-id="5a7ca-358">HTTP Content-Type Header</span></span>  
 <span data-ttu-id="5a7ca-359">SOAP 1.x MTOM 인코딩된 메시지 고 MTOM 사양 자체에 명시 된 요구 사항에서 파생 된의 HTTP Content-type 헤더 형식에 대 한 WCF 설명의 목록은 आ स ा MTOM 및 RFC 2387에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-359">The following is a list of WCF clarifications for the format of the HTTP Content-Type header of a SOAP 1.x MTOM-encoded message derived from requirements stated in the MTOM specification itself and are derived from MTOM and RFC 2387.</span></span>  
  
-   <span data-ttu-id="5a7ca-360">R4131: HTTP Content-Type 헤더에는 multipart/related(대/소문자 구분 안 함) 값 및 해당 매개 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-360">R4131: An HTTP Content-Type header must have the value of multipart/related (case-insensitive) and its parameters.</span></span> <span data-ttu-id="5a7ca-361">매개 변수 이름은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-361">Parameter names are case-insensitive.</span></span> <span data-ttu-id="5a7ca-362">매개 변수의 순서는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-362">Parameter order is not significant.</span></span>  
  
-   <span data-ttu-id="5a7ca-363">MIME 메시지에 대한 Content-Type 헤더의 전체 BNF(Backus-Naur Form)는 RFC 2045, 단원 5.1에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-363">The full Backus-Naur Form (BNF) of the Content-Type header for MIME messages is listed in RFC 2045, section 5.1.</span></span>  
  
-   <span data-ttu-id="5a7ca-364">R4132: HTTP Content-Type 헤더에는 큰따옴표로 묶은 `application/xop+xml` 값을 가진 형식 매개 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-364">R4132: An HTTP Content-Type header must have a type parameter with the value `application/xop+xml` enclosed in double quotation marks.</span></span>  
  
 <span data-ttu-id="5a7ca-365">큰따옴표 사용 요구 사항이 없으면 RFC 2387 텍스트에서 모든 multipart/related 미디어 형식 매개 변수가 주로 같은 예약 된 문자를 포함할 수 "\@" 또는 "/" 큰따옴표 필요 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-365">While the requirement to use double quotation marks is not explicit in RFC 2387, the text observes that all of the multipart/related media type parameters most likely contain reserved characters like "\@" or "/" and therefore need double quotation marks.</span></span>  
  
-   <span data-ttu-id="5a7ca-366">R4133: HTTP Content-Type 헤더에는 SOAP 1.x 봉투를 포함하는 MIMI 부분의 Content-ID 헤더 값이 큰따옴표로 묶인 시작 매개 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-366">R4133: An HTTP Content-Type header should have a start parameter with the value of the Content-ID header of the MIME part that contains the SOAP 1.x Envelope, enclosed in double quotation marks.</span></span> <span data-ttu-id="5a7ca-367">시작 매개 변수가 생략된 경우 첫 번째 MIME 부분에 SOAP 1.x 봉투가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-367">If the start parameter is omitted, the first MIME part must contain the SOAP 1.x Envelope.</span></span>  
  
-   <span data-ttu-id="5a7ca-368">R4134: SOAP 1.1 MTOM 인코딩된 메시지의 HTTP Content-Type 헤더는 큰따옴표로 묶인 text/xml 값을 가진 start-info 매개 변수를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-368">R4134: An HTTP Content-Type header for a SOAP 1.1 MTOM encoded message must include the start-info parameter with the value of text/xml, enclosed in double quotation marks.</span></span>  
  
-   <span data-ttu-id="5a7ca-369">R4135: SOAP 1.2 MTOM 인코딩된 메시지의 HTTP Content-Type 헤더는 큰따옴표로 묶인 `application/soap+xml` 값을 가진 start-info 매개 변수를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-369">R4135: An HTTP Content-Type header for a SOAP 1.2 MTOM-encoded message must include the start-info parameter with the value of `application/soap+xml`, enclosed in double quotation marks.</span></span>  
  
-   <span data-ttu-id="5a7ca-370">R4136: SOAP 1.x MTOM 인코딩된 메시지의 HTTP Content-Type 헤더에는 RFC 2046, 단원 5.1.1에 정의된 MIME 경계 BNF와 일치하는 큰따옴표로 묶인 값을 가진 boundary 매개 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-370">R4136: HTTP Content-Type header for a SOAP 1.x MTOM-encoded message must have the boundary parameter with the value (enclosed in double quotation marks) that matches the MIME boundary BNF defined in RFC 2046, section 5.1.1</span></span>  
  
    ```  
    boundary := 0*69<bchars> bcharsnospace   
    bchars := bcharsnospace / " "   
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+"   
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"  
    ```  
  
     <span data-ttu-id="5a7ca-371">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-371">Examples:</span></span>  
  
     <span data-ttu-id="5a7ca-372">올바른 예</span><span class="sxs-lookup"><span data-stu-id="5a7ca-372">CORRECT</span></span>  
  
    ```  
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"  
    ```  
  
     <span data-ttu-id="5a7ca-373">올바른 예</span><span class="sxs-lookup"><span data-stu-id="5a7ca-373">CORRECT</span></span>  
  
    ```  
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"  
    ```  
  
     <span data-ttu-id="5a7ca-374">잘못된 예</span><span class="sxs-lookup"><span data-stu-id="5a7ca-374">INCORRECT</span></span>  
  
    ```  
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"   
    ```  
  
#### <a name="infoset-mime-part"></a><span data-ttu-id="5a7ca-375">Infoset MIME 부분</span><span class="sxs-lookup"><span data-stu-id="5a7ca-375">Infoset MIME Part</span></span>  
 <span data-ttu-id="5a7ca-376">SOAP 1.x 봉투는 XOP MIME 패키지의 루트 부분으로 캡슐화되며 `infoset` 부분이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-376">The SOAP 1.x Envelope is encapsulated as a root part of the XOP MIME package and is often called the `infoset` part.</span></span>  
  
-   <span data-ttu-id="5a7ca-377">R4141: SOAP 1.x 봉투는 XOP MIME 패키지의 루트 부분으로 캡슐화되어야 하고, `infoset` 부분이라고도 하며, HTTP Content-Type에서 참조되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-377">R4141: The SOAP 1.x Envelope must be encapsulated as a root part of the XOP MIME package, called the `infoset` part and referenced from the HTTP Content-Type.</span></span>  
  
-   <span data-ttu-id="5a7ca-378">R4142: SOAP `Infoset` 부분은 `Content-ID`, `Content-Transfer-Encoding` 및 `Content-Type` MIME 헤더를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-378">R4142: The SOAP `Infoset` part must include the following MIME headers: `Content-ID`, `Content-Transfer-Encoding`, and `Content-Type`.</span></span>  
  
 <span data-ttu-id="5a7ca-379">Content-ID 헤더의 형식은 RFC 2045에 다음과 같이 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-379">The format of the Content-ID header is defined by RFC 2045 as</span></span>  
  
```  
"Content-ID" ":" msg-id  
```  
  
 <span data-ttu-id="5a7ca-380">`msg-id`는 RFC 2822(RFC 822보다 우선하며, RFC 2045에서 참조됨)에 다음과 같이 정의되어 있으며</span><span class="sxs-lookup"><span data-stu-id="5a7ca-380">where `msg-id` is defined in RFC 2822 (that supersedes RFC 822, referenced in RFC 2045) as:</span></span>  
  
```  
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]  
```  
  
 <span data-ttu-id="5a7ca-381">효과적으로 전자 메일 주소 내에 포함 되어 및 "\<" 및 ">"입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-381">and is effectively an email address enclosed within "\<" and  ">".</span></span> <span data-ttu-id="5a7ca-382">`[CFWS]` 접두사와 접미사는 설명을 전달하기 위해 RFC 2822에 추가되었지만 상호 운용성을 유지하려면 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-382">The `[CFWS]` prefix and suffix were added in RFC 2822 to carry comments and should not be used to preserve interoperability.</span></span>  
  
 <span data-ttu-id="5a7ca-383">R4143: Infoset MIME 부분의 Content-ID 헤더 값은 `msg-id` 접두사 및 접미사 부분을 생략한 상태의 RFC 2822의 `[CFWS]` 생성을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-383">R4143: The value of the Content-ID header for the Infoset MIME part must follow `msg-id` production from RFC 2822 with the `[CFWS]` prefix and suffix parts omitted.</span></span>  
  
 <span data-ttu-id="5a7ca-384">많은 MIME 구현 내에 포함 된 값에 대 한 요구 사항 완화 "\<" 및 ">" 전자 메일 주소를 사용 하 고 `absoluteURI` 묶인 "\<", ">" 전자 메일 주소와 함께 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-384">A number of MIME implementations relaxed requirements for the value enclosed within "\<" and ">" to be an email address and used `absoluteURI` enclosed in "\<" , ">" in addition to the email address.</span></span> <span data-ttu-id="5a7ca-385">이 버전의 WCF에서는 형식의 CONTENT-ID MIME 헤더의 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-385">This version of WCF uses values of the Content-ID MIME header of the form:</span></span>  
  
```  
Content-ID: <http://tempuri.org/0>   
```  
  
 <span data-ttu-id="5a7ca-386">R4144: MTOM 프로세서는 다음과 같은 완화된 `msg-id`와 일치하는 Content-ID 헤더 값을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-386">R4144: MTOM processors should accept Content-ID header values that match the following relaxed `msg-id`.</span></span>  
  
```  
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]  
mail-address   =     id-left "@" id-right  
```  
  
 <span data-ttu-id="5a7ca-387">MIME(RFC 2045)은 MIME 부분의 콘텐츠 인코딩을 전달하기 위해 Content-Transfer-Encoding 헤더를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-387">MIME (RFC 2045) provides the Content-Transfer-Encoding header to communicate encoding of the content of the MIME part.</span></span> <span data-ttu-id="5a7ca-388">Content-Transfer-Encoding에 대해 정의된 기본값은 7비트로 대부분의 SOAP 메시지에 적합하지 않으므로 상호 운용성 향상을 위해 Content-Transfer-Encoding 헤더가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-388">The default defined for Content-Transfer-Encoding is 7-bit, which is not suitable for most SOAP messages, so the Content-Transfer-Encoding header is needed for greater interoperability:</span></span>  
  
-   <span data-ttu-id="5a7ca-389">R4145: SOAP Infoset 부분은 Content-Transfer-Encoding 헤더를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-389">R4145: The SOAP Infoset part must contain the Content-Transfer-Encoding header.</span></span>  
  
-   <span data-ttu-id="5a7ca-390">R4146: SOAP 봉투 문자 인코딩이 UTF-8이면 Content-Transfer-Encoding 헤더 값이 8비트여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-390">R4146: If the SOAP Envelope character encoding is UTF-8, the value of the Content-Transfer-Encoding header must be 8-bit.</span></span>  
  
-   <span data-ttu-id="5a7ca-391">R4147: SOAP 봉투 문자 인코딩이 UTF-16이면 Content-Transfer-Encoding 헤더 값이 이진이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-391">R4147: If the SOAP Envelope character encoding is UTF-16, the value of the Content-Transfer-Encoding header must be binary.</span></span>  
  
-   <span data-ttu-id="5a7ca-392">[XOP] 단원 5에 따르면</span><span class="sxs-lookup"><span data-stu-id="5a7ca-392">According to [XOP] section 5,</span></span>  
  
-   <span data-ttu-id="5a7ca-393">R4148: SOAP1.1 Infoset 부분은 미디어 형식이 application/xop + xml 콘텐츠 형식 헤더를 포함 해야 하 고 매개 변수가 type = "text/xml" 및 charset</span><span class="sxs-lookup"><span data-stu-id="5a7ca-393">R4148: SOAP1.1 Infoset part must contain Content-Type header with media type application/xop+xml and parameters type="text/xml" and charset</span></span>  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="text/xml"  
    ```  
  
-   <span data-ttu-id="5a7ca-394">R4149: SOAP 1.2 Infoset 부분은 미디어 유형으로 Content-type 헤더를 포함 해야 `application/xop+xml` 고 매개 변수가 type = "`application/soap+xml`" 및 `charset`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-394">R4149: The SOAP 1.2 Infoset part must contain the Content-Type header with media type `application/xop+xml` and parameters type="`application/soap+xml`" and `charset`.</span></span>  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="application/soap+xml"  
    ```  
  
     <span data-ttu-id="5a7ca-395">XOP에서는 `charset`의 `application/xop+xml` 매개 변수를 선택적 요소로 정의하고 있지만, `charset` 미디어 형식의 `text/xml` 매개 변수에 대한 BP 1.1 요구 사항과 마찬가지로 상호 운용성을 위해 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-395">While XOP defines the `charset` parameter for `application/xop+xml` to be optional, it is needed for interoperability similar to the BP 1.1 requirement on the `charset` parameter for the `text/xml` media type.</span></span>  
  
-   <span data-ttu-id="5a7ca-396">R41410: `type` 및 `charset` 매개 변수가 SOAP 1.x Infoset 부분의 Content-Type 헤더에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-396">R41410: The `type` and `charset` parameters must be present on the Content-Type header of the SOAP 1.x Infoset part.</span></span>  
  
#### <a name="wcf-endpoint-support-for-mtom"></a><span data-ttu-id="5a7ca-397">MTOM에 대한 WCF 끝점 지원</span><span class="sxs-lookup"><span data-stu-id="5a7ca-397">WCF Endpoint Support for MTOM</span></span>  
 <span data-ttu-id="5a7ca-398">MTOM의 목적은 SOAP 메시지를 인코딩하여 base64 인코딩된 데이터를 최적화하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-398">The purpose of MTOM is to encode a SOAP message to optimize base64-encoded data.</span></span> <span data-ttu-id="5a7ca-399">다음은 제약 조건 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-399">The following is a list of constraints:</span></span>  
  
-   <span data-ttu-id="5a7ca-400">R4151: base64 인코딩된 데이터를 포함하는 모든 요소 정보 항목이 최적화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-400">R4151: Any element information item that contains base64-encoded data may be optimized.</span></span>  
  
-   <span data-ttu-id="5a7ca-401">B4152: WCF base64 인코딩된 데이터를 포함 하 고 길이가 1024 바이트를 초과 하는 요소 정보 항목을 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-401">B4152: WCF optimizes element information items that contain base64-encoded data and exceed 1024 bytes in length.</span></span>  
  
 <span data-ttu-id="5a7ca-402">MTOM을 사용 하도록 구성 하는 WCF 끝점은 MTOM 인코딩된 메시지를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-402">A WCF endpoint configured to use MTOM will always send MTOM-encoded messages.</span></span> <span data-ttu-id="5a7ca-403">필수 조건을 충족하는 부분이 없더라도 MTOM 인코딩된 메시지를 보냅니다. 이 메시지는 단일 MIME 부분에서 SOAP 봉투를 포함하는 MIME 패키지로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-403">Even if no parts meet the required criteria, the message is still MTOM-encoded (serialized as a MIME package with a single MIME part containing the SOAP envelope).</span></span>  
  
### <a name="ws-policy-assertion-for-mtom"></a><span data-ttu-id="5a7ca-404">MTOM WS-Policy Assertion</span><span class="sxs-lookup"><span data-stu-id="5a7ca-404">WS-Policy Assertion for MTOM</span></span>  
 <span data-ttu-id="5a7ca-405">WCF는 다음 정책 어설션은 사용 하 여 끝점에서 MTOM 사용을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-405">WCF uses the following policy assertion to indicate MTOM usage by endpoint:</span></span>  
  
```xml  
<wsoma:OptimizedMimeSerialization ... />  
```  
  
-   <span data-ttu-id="5a7ca-406">R4211: 이전 정책 어설션은 끝점 정책 주체를 포함하고 MTOM을 사용하여 끝점에서 보내거나 받은 모든 메시지를 최적화하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-406">R4211: The preceding policy assertion has an Endpoint Policy Subject and specifies that all messages sent to and received from the endpoint must be optimized using MTOM.</span></span>  
  
-   <span data-ttu-id="5a7ca-407">B4212: MTOM 최적화를 사용 하도록 구성, WCF 끝점 추가 MTOM 정책 어설션을 해당 요소에 연결 된 정책에 `wsdl:binding`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-407">B4212: When configured to use MTOM optimization, an WCF endpoint adds an MTOM Policy assertion to the policy attached to the corresponding `wsdl:binding`.</span></span>  
  
### <a name="composition-with-ws-security"></a><span data-ttu-id="5a7ca-408">WS-Security를 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="5a7ca-408">Composition with WS-Security</span></span>  
 <span data-ttu-id="5a7ca-409">MTOM은 비슷한 인코딩 메커니즘 `text/xml` 및 WCF 이진 XML입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-409">MTOM is an encoding mechanism that is similar to `text/xml` and WCF Binary XML.</span></span> <span data-ttu-id="5a7ca-410">MTOM은 WS-Security 및 기타 WS-\* 프로토콜을 사용하여 자연스러운 구성을 제공합니다. WS-Security를 사용하여 보안된 메시지는 MTOM을 사용하여 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-410">MTOM offers natural composition with WS-Security and other WS-\* protocols: a message secured using WS-Security can be optimized using MTOM.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="5a7ca-411">예제</span><span class="sxs-lookup"><span data-stu-id="5a7ca-411">Examples</span></span>  
  
#### <a name="wcf-soap-11-message-encoded-using-mtom"></a><span data-ttu-id="5a7ca-412">MTOM을 사용하여 인코딩한 WCF SOAP 1.1 메시지</span><span class="sxs-lookup"><span data-stu-id="5a7ca-412">WCF SOAP 1.1 Message Encoded Using MTOM</span></span>  
  
```  
POST http://131.107.72.15/Mtom/svc/service.svc/Soap11MtomUTF8 HTTP/1.1  
SOAPAction: "http://xmlsoap.org/echoBinaryAsString"  
Content-Type: multipart/related;type="application/xop+xml";  
              start="<http://tempuri.org/0>";start-info="text/xml";  
       boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"  
Host: 131.107.72.15  
Content-Length: 1501  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1  
Content-ID: <http://tempuri.org/0>  
Content-Transfer-Encoding: 8bit  
Content-Type: application/xop+xml;charset=utf-8;type="text/xml"  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Body>  
    <EchoBinaryAsString xmlns="http://xmlsoap.org/Ping">  
      <array>  
        <xop:Include   
         href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206521093670"   
         xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
      </array>  
    </EchoBinaryAsString>  
  </s:Body>  
</s:Envelope>  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1  
Content-ID: <http://tempuri.org/1/632618206521093670>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
…Binary Content..  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1  
```  
  
#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a><span data-ttu-id="5a7ca-413">MTOM을 사용하여 인코딩한 WCF Secure SOAP 1.2 메시지</span><span class="sxs-lookup"><span data-stu-id="5a7ca-413">WCF Secure SOAP 1.2 Message Encoded Using MTOM</span></span>  
 <span data-ttu-id="5a7ca-414">이 예제에서 메시지는 WS-Security를 사용하여 보호된 SOAP 1.2 및 MTOM을 사용하여 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-414">In this example, a message is encoded using MTOM and SOAP 1.2 that is protected using WS-Security.</span></span> <span data-ttu-id="5a7ca-415">인코딩을 위해 식별되는 이진 부분은 `BinarySecurityToken`의 콘텐츠로서, 암호화된 서명 및 암호화된 본문에 해당하는 `CipherValue`의 `EncryptedData`입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-415">The binary parts identified for encoding are the contents of the `BinarySecurityToken`, `CipherValue` of the `EncryptedData` corresponding to the encrypted signature and encrypted body.</span></span> <span data-ttu-id="5a7ca-416">`CipherValue` 의 `EncryptedKey` 하지 식별 최적화에 대 한 WCF, 길이가 1024 바이트 미만 이므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-416">Note that the `CipherValue` of the `EncryptedKey` was not identified for optimization by WCF, because its length is less then 1024 bytes.</span></span>  
  
```  
POST http://131.107.72.15/Mtom/service.svc/Soap12MtomSecureSignEncrypt HTTP/1.1  
Content-Type: multipart/related; type="application/xop+xml";  
              start="<http://tempuri.org/0>";  
            boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3";  
              start-info="application/soap+xml";   
              action="http://xmlsoap.org/echoBinaryAsString"  
Host: 131.107.72.15  
Content-Length: 1941  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/0>  
Content-Transfer-Encoding: 8bit  
Content-Type: application/xop+xml;charset=utf-8;type="application/soap+xml"  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/" xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
  <s:Header>  
    <o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-5">  
        <u:Created>2005-09-09T06:57:32.488Z</u:Created>  
        <u:Expires>2005-09-09T07:02:32.488Z</u:Expires>  
      </u:Timestamp>  
      <o:BinarySecurityToken u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-2" ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3" EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">  
        <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
      </o:BinarySecurityToken>  
      <e:EncryptedKey Id="_1" xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#rsa-oaep-mgf1p"/>  
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">  
          <o:SecurityTokenReference>  
            <o:KeyIdentifier ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509SubjectKeyIdentifier">Xeg55vRyK3ZhAEhEf+YT0z986L0=</o:KeyIdentifier>  
          </o:SecurityTokenReference>  
        </KeyInfo>  
        <e:CipherData>          <e:CipherValue>oQfpxwT8/SAGyZQzKE2b4yO6dXuQj7pwJ+5CGL3Rf7C06bQ5ttMoQ9GLJcQYkXTzin+WwHEgs5bj5ml9HKTW9QAU5JJ6lksdymmQvWP5ZtGPBVchO4sofEGoCKmBiZL/DYS/cnbzgnc/3a6NYnc10y2fWGaGLiqa00zijAw7o0Y=</e:CipherValue>  
        </e:CipherData>  
      </e:EncryptedKey>  
      <c:DerivedKeyToken u:Id="_2" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc">  
        <o:SecurityTokenReference>  
          <o:Reference URI="#_1"/>  
        </o:SecurityTokenReference>  
        <c:Nonce>OrEPRX7fISIS4sXYWPMv3g==</c:Nonce>  
      </c:DerivedKeyToken>  
      <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
        <e:DataReference URI="#_3"/>  
        <e:DataReference URI="#_4"/>  
      </e:ReferenceList>  
      <e:EncryptedData Id="_4" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>  
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">  
          <o:SecurityTokenReference>  
            <o:Reference URI="#_2"/>  
          </o:SecurityTokenReference>  
        </KeyInfo>  
        <e:CipherData>  
          <e:CipherValue>  
            <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F2%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
          </e:CipherValue>  
        </e:CipherData>  
      </e:EncryptedData>  
    </o:Security>  
  </s:Header>  
  <s:Body u:Id="_0">  
    <e:EncryptedData Id="_3" Type="http://www.w3.org/2001/04/xmlenc#Content" xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
      <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>  
      <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <o:SecurityTokenReference xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
          <o:Reference URI="#_2"/>  
        </o:SecurityTokenReference>  
      </KeyInfo>  
      <e:CipherData>  
        <e:CipherValue>  
          <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F3%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
        </e:CipherValue>  
      </e:CipherData>  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/1/632618206525089430>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
...Binary content of BinarySecurityToken - X509 Certificate...  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/2/632618206525089430>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
...Binary serialization of the encrypted primary signature...  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/3/632618206525089430>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
...Binary serialization of the encrypted Body...  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3--  
```
