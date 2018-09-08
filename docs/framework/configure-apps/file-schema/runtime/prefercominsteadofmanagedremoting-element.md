---
title: '&lt;PreferComInsteadOfManagedRemoting&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c05e27226a58086c806e8977ba50a55873d1167e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44222664"
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a><span data-ttu-id="78bf3-102">&lt;PreferComInsteadOfManagedRemoting&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="78bf3-102">&lt;PreferComInsteadOfManagedRemoting&gt; Element</span></span>
<span data-ttu-id="78bf3-103">런타임에서 사용할지 여부를 COM interop 원격 대신 모든 호출에 대 한 응용 프로그램 도메인 경계에 걸쳐 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78bf3-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="78bf3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="78bf3-104">\<configuration></span></span>  
<span data-ttu-id="78bf3-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="78bf3-105">\<runtime></span></span>  
<span data-ttu-id="78bf3-106">\<PreferComInsteadOfManagedRemoting ></span><span class="sxs-lookup"><span data-stu-id="78bf3-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78bf3-107">구문</span><span class="sxs-lookup"><span data-stu-id="78bf3-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78bf3-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="78bf3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="78bf3-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="78bf3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78bf3-110">특성</span><span class="sxs-lookup"><span data-stu-id="78bf3-110">Attributes</span></span>  
  
|<span data-ttu-id="78bf3-111">특성</span><span class="sxs-lookup"><span data-stu-id="78bf3-111">Attribute</span></span>|<span data-ttu-id="78bf3-112">설명</span><span class="sxs-lookup"><span data-stu-id="78bf3-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="78bf3-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="78bf3-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="78bf3-114">런타임에서 사용할지 여부를 COM interop 원격 대신 응용 프로그램 도메인 경계를 넘어 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="78bf3-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="78bf3-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="78bf3-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="78bf3-116">값</span><span class="sxs-lookup"><span data-stu-id="78bf3-116">Value</span></span>|<span data-ttu-id="78bf3-117">설명</span><span class="sxs-lookup"><span data-stu-id="78bf3-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="78bf3-118">런타임에서 응용 프로그램 도메인 경계를 넘어 remoting을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78bf3-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="78bf3-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="78bf3-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="78bf3-120">런타임에 응용 프로그램 도메인 경계를 넘어 COM interop를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78bf3-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78bf3-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="78bf3-121">Child Elements</span></span>  
 <span data-ttu-id="78bf3-122">없음</span><span class="sxs-lookup"><span data-stu-id="78bf3-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78bf3-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="78bf3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="78bf3-124">요소</span><span class="sxs-lookup"><span data-stu-id="78bf3-124">Element</span></span>|<span data-ttu-id="78bf3-125">설명</span><span class="sxs-lookup"><span data-stu-id="78bf3-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="78bf3-126">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="78bf3-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="78bf3-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="78bf3-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78bf3-128">설명</span><span class="sxs-lookup"><span data-stu-id="78bf3-128">Remarks</span></span>  
 <span data-ttu-id="78bf3-129">설정한 경우 합니다 `enabled` 특성을 `true`, 런타임에서 다음과 같이 동작:</span><span class="sxs-lookup"><span data-stu-id="78bf3-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
-   <span data-ttu-id="78bf3-130">런타임에서 호출 하지 않습니다 [iunknown:: Queryinterface](https://go.microsoft.com/fwlink/?LinkID=144867) 에 대 한는 [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) 인터페이스는 [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) 인터페이스는 COM 인터페이스를 통해 도메인을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="78bf3-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="78bf3-131">구문 대신에 [런타임 호출 가능 래퍼](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) 개체 주위 합니다.</span><span class="sxs-lookup"><span data-stu-id="78bf3-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
-   <span data-ttu-id="78bf3-132">런타임에서 받으면 E_NOINTERFACE가 반환 됩니다를 `QueryInterface` 에 대 한 호출는 [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) 인터페이스에 대 한 [COM 호출 가능 래퍼](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW)는이 도메인에 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="78bf3-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="78bf3-133">이러한 두 가지 동작 COM에 대 한 모든 호출 응용 프로그램 도메인 경계 사용 COM에서 관리 되는 개체 사이의 원격 대신 COM interop 인터페이스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="78bf3-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78bf3-134">예제</span><span class="sxs-lookup"><span data-stu-id="78bf3-134">Example</span></span>  
 <span data-ttu-id="78bf3-135">다음 예와 런타임에서 COM을 사용 해야 함을 지정 하는 방법을 interop 격리 경계를 넘어:</span><span class="sxs-lookup"><span data-stu-id="78bf3-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="78bf3-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78bf3-136">See Also</span></span>  
 [<span data-ttu-id="78bf3-137">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="78bf3-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="78bf3-138">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="78bf3-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
