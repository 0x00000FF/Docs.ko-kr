---
title: '&lt;mexHttpsBinding&gt;'
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: d56e90162f2a852ff4d0b66abcf3fe03c4110c37
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48777307"
---
# <a name="ltmexhttpsbindinggt"></a><span data-ttu-id="d81ad-102">&lt;mexHttpsBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="d81ad-102">&lt;mexHttpsBinding&gt;</span></span>
<span data-ttu-id="d81ad-103">HTTPS를 통한 WS-MEX(WS-MetadataExchange) 메시지 교환에 사용되는 바인딩의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
 <span data-ttu-id="d81ad-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d81ad-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d81ad-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="d81ad-105">\<bindings></span></span>  
<span data-ttu-id="d81ad-106">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="d81ad-106">\<mexHttpsBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d81ad-107">구문</span><span class="sxs-lookup"><span data-stu-id="d81ad-107">Syntax</span></span>  
  
```xml  
<mexHttpsBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexHttpsBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d81ad-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d81ad-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d81ad-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d81ad-110">특성</span><span class="sxs-lookup"><span data-stu-id="d81ad-110">Attributes</span></span>  
  
|<span data-ttu-id="d81ad-111">특성</span><span class="sxs-lookup"><span data-stu-id="d81ad-111">Attribute</span></span>|<span data-ttu-id="d81ad-112">설명</span><span class="sxs-lookup"><span data-stu-id="d81ad-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="d81ad-113">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="d81ad-114">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d81ad-115">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="d81ad-116">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="d81ad-117">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="d81ad-118">각 바인딩에는 서비스의 메타데이터에서 함께 바인딩을 고유하게 식별하는 `name` 및 `namespace` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="d81ad-119">또한 이 이름은 동일한 형식의 바인딩 간에 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="d81ad-120">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="d81ad-121">기본 구성 및 이름 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 하세요. [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) 하 고 [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="d81ad-122">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="d81ad-123">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d81ad-124">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="d81ad-125">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="d81ad-126">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d81ad-127">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="d81ad-128">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="d81ad-129">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d81ad-130">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d81ad-131">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d81ad-131">Child Elements</span></span>  
 <span data-ttu-id="d81ad-132">없음</span><span class="sxs-lookup"><span data-stu-id="d81ad-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d81ad-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d81ad-133">Parent Elements</span></span>  
  
|<span data-ttu-id="d81ad-134">요소</span><span class="sxs-lookup"><span data-stu-id="d81ad-134">Element</span></span>|<span data-ttu-id="d81ad-135">설명</span><span class="sxs-lookup"><span data-stu-id="d81ad-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d81ad-136">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d81ad-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="d81ad-137">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d81ad-138">설명</span><span class="sxs-lookup"><span data-stu-id="d81ad-138">Remarks</span></span>  
 <span data-ttu-id="d81ad-139">이 바인딩은 기본적으로 인증서를 사용하여 전송 수준에서 보안을 지원할 수 있는 `WSHttpBinding` 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-139">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="d81ad-140">구성 및 메타 데이터 끝점을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법:는 사용자 지정 Ws-metadata Exchange 바인딩 구성](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)를 [방법: 검색 메타 데이터를 통해가 아닌-MEX 바인딩을](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), 및 샘플 [사용자 지정 보안 메타 데이터 끝점](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d81ad-140">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d81ad-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d81ad-141">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>  
 [<span data-ttu-id="d81ad-142">방법: 구성 파일을 사용하여 서비스의 메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="d81ad-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="d81ad-143">사용자 지정 바인딩을 통해 메타데이터 게시 및 검색</span><span class="sxs-lookup"><span data-stu-id="d81ad-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="d81ad-144">방법: 사용자 지정 WS-Metadata Exchange 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="d81ad-144">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)  
 [<span data-ttu-id="d81ad-145">방법: MEX가 아닌 바인딩을 통해 메타데이터 검색</span><span class="sxs-lookup"><span data-stu-id="d81ad-145">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)  
 [<span data-ttu-id="d81ad-146">사용자 지정 보안 메타 데이터 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="d81ad-146">Custom Secure Metadata Endpoint</span></span>](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)  
 [<span data-ttu-id="d81ad-147">메타데이터</span><span class="sxs-lookup"><span data-stu-id="d81ad-147">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="d81ad-148">바인딩</span><span class="sxs-lookup"><span data-stu-id="d81ad-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d81ad-149">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="d81ad-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="d81ad-150">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="d81ad-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="d81ad-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="d81ad-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
