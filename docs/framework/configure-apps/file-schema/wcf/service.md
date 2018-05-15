---
title: '&lt;서비스&gt;'
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 6e83e988920d24c6fe7615e40334919caf21652e
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
---
# <a name="ltservicegt"></a><span data-ttu-id="d3c03-102">&lt;서비스&gt;</span><span class="sxs-lookup"><span data-stu-id="d3c03-102">&lt;service&gt;</span></span>
<span data-ttu-id="d3c03-103">`service` 요소에는 WCF(Windows Communication Foundation) 서비스 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-103">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="d3c03-104">이 요소에는 서비스를 공개하는 끝점도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-104">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="d3c03-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d3c03-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d3c03-106">\<services></span><span class="sxs-lookup"><span data-stu-id="d3c03-106">\<services></span></span>  
<span data-ttu-id="d3c03-107">\<서비스 ></span><span class="sxs-lookup"><span data-stu-id="d3c03-107">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3c03-108">구문</span><span class="sxs-lookup"><span data-stu-id="d3c03-108">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration=String"  
        name="String">  
</service>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3c03-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d3c03-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d3c03-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3c03-111">특성</span><span class="sxs-lookup"><span data-stu-id="d3c03-111">Attributes</span></span>  
  
|<span data-ttu-id="d3c03-112">특성</span><span class="sxs-lookup"><span data-stu-id="d3c03-112">Attribute</span></span>|<span data-ttu-id="d3c03-113">설명</span><span class="sxs-lookup"><span data-stu-id="d3c03-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3c03-114">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="d3c03-114">behaviorConfiguration</span></span>|<span data-ttu-id="d3c03-115">서비스 인스턴스화에 사용할 동작의 동작 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-115">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="d3c03-116">동작 이름은 서비스가 정의된 지점의 범위에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-116">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="d3c03-117">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-117">The default value is an empty string.</span></span>|  
|<span data-ttu-id="d3c03-118">name</span><span class="sxs-lookup"><span data-stu-id="d3c03-118">name</span></span>|<span data-ttu-id="d3c03-119">인스턴스화할 서비스 형식을 지정하는 필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-119">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="d3c03-120">이 설정은 유효한 형식을 사용해야 하며,</span><span class="sxs-lookup"><span data-stu-id="d3c03-120">This setting must equate to a valid type.</span></span> <span data-ttu-id="d3c03-121">Namespace.Class`Namespace.Class.` 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-121">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3c03-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d3c03-122">Child Elements</span></span>  
  
|<span data-ttu-id="d3c03-123">요소</span><span class="sxs-lookup"><span data-stu-id="d3c03-123">Element</span></span>|<span data-ttu-id="d3c03-124">설명</span><span class="sxs-lookup"><span data-stu-id="d3c03-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3c03-125">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="d3c03-125">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|<span data-ttu-id="d3c03-126">이 서비스를 공개하는 `endpoint` 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-126">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="d3c03-127">\<호스트 ></span><span class="sxs-lookup"><span data-stu-id="d3c03-127">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="d3c03-128">이 서비스 인스턴스의 호스트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-128">Specifies the host of this service instance.</span></span> <span data-ttu-id="d3c03-129">이 요소는 <xref:System.ServiceModel.Configuration.HostElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-129">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d3c03-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d3c03-130">Parent Elements</span></span>  
  
|<span data-ttu-id="d3c03-131">요소</span><span class="sxs-lookup"><span data-stu-id="d3c03-131">Element</span></span>|<span data-ttu-id="d3c03-132">설명</span><span class="sxs-lookup"><span data-stu-id="d3c03-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3c03-133">\<services></span><span class="sxs-lookup"><span data-stu-id="d3c03-133">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="d3c03-134">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-134">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3c03-135">설명</span><span class="sxs-lookup"><span data-stu-id="d3c03-135">Remarks</span></span>  
 <span data-ttu-id="d3c03-136">서비스는 구성 파일의 `services` 섹션에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-136">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="d3c03-137">어셈블리에는 여러 개의 서비스가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-137">An assembly can contain any number of services.</span></span> <span data-ttu-id="d3c03-138">서비스별로 해당 `service` 구성 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-138">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="d3c03-139">이 단원 및 내용에서는 특정 서비스의 서비스 계약, 동작 및 끝점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-139">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="d3c03-140">`behaviorConfiguration` 요소도 선택적 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-140">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="d3c03-141">서비스가 사용하는 동작을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-141">It identifies the behavior the service uses.</span></span> <span data-ttu-id="d3c03-142">이 특성에 지정된 동작은 동일한 구성 파일의 범위에 있는 동작에 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-142">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="d3c03-143">각 서비스는 하나 이상의 끝점을 노출하는데, 여기에는 자체 주소 및 바인딩이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-143">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="d3c03-144">구성 파일 내에서 사용되는 모든 바인딩은 파일 범위 내에서 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-144">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="d3c03-145">바인딩은 `name` 및 `bindingConfiguration` 특성 조합을 통해 끝점에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-145">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="d3c03-146">`name` 특성은 바인딩이 정의된 섹션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-146">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="d3c03-147">`bindingConfiguration` 특성은 바인딩 섹션 내에서 사용되는 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-147">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="d3c03-148">바인딩 섹션에서는 여러 개의 구성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-148">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3c03-149">예제</span><span class="sxs-lookup"><span data-stu-id="d3c03-149">Example</span></span>  
 <span data-ttu-id="d3c03-150">서비스 구성의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d3c03-150">This is an example of a service configuration.</span></span>  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"   
     name="HelloWorld">  
     <endpoint   
        address="/HelloWorld2/"  
        name="test"  
        bindingNamespace="http://www.cohowinery.com/"  
        binding="basicHttpBinding"  
        contract="IHelloWorld" />  
</service>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3c03-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3c03-151">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceElement>  
 [<span data-ttu-id="d3c03-152">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="d3c03-152">Configuring Services</span></span>](../../../../../docs/framework/wcf/configuring-services.md)
