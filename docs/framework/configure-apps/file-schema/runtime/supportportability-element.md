---
title: '&lt;supportPortability&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a0332a642f9377eed2769ea5aedb1be85853274
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49122765"
---
# <a name="ltsupportportabilitygt-element"></a><span data-ttu-id="83a65-102">&lt;supportPortability&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="83a65-102">&lt;supportPortability&gt; Element</span></span>
<span data-ttu-id="83a65-103">응용 프로그램 이식성을 위해 어셈블리를 동일하게 간주하는 기본 동작을 사용하지 않도록 설정함으로써, 응용 프로그램이 .NET Framework의 서로 다른 두 구현에서 같은 어셈블리를 참조할 수 있도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
 <span data-ttu-id="83a65-104">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="83a65-104">\<configuration> Element</span></span>  
<span data-ttu-id="83a65-105">\<런타임 > 요소</span><span class="sxs-lookup"><span data-stu-id="83a65-105">\<runtime> Element</span></span>  
<span data-ttu-id="83a65-106">\<assemblyBinding > 요소</span><span class="sxs-lookup"><span data-stu-id="83a65-106">\<assemblyBinding> Element</span></span>  
<span data-ttu-id="83a65-107">\<supportPortability > 요소</span><span class="sxs-lookup"><span data-stu-id="83a65-107">\<supportPortability> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83a65-108">구문</span><span class="sxs-lookup"><span data-stu-id="83a65-108">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83a65-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="83a65-109">Attributes and Elements</span></span>  
 <span data-ttu-id="83a65-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83a65-111">특성</span><span class="sxs-lookup"><span data-stu-id="83a65-111">Attributes</span></span>  
  
|<span data-ttu-id="83a65-112">특성</span><span class="sxs-lookup"><span data-stu-id="83a65-112">Attribute</span></span>|<span data-ttu-id="83a65-113">설명</span><span class="sxs-lookup"><span data-stu-id="83a65-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="83a65-114">PKT</span><span class="sxs-lookup"><span data-stu-id="83a65-114">PKT</span></span>|<span data-ttu-id="83a65-115">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="83a65-116">문자열로 서 영향을 받는 어셈블리의 공개 키 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-116">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="83a65-117">사용</span><span class="sxs-lookup"><span data-stu-id="83a65-117">enabled</span></span>|<span data-ttu-id="83a65-118">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="83a65-119">지정된 된.NET Framework 어셈블리의 구현 간에 이식성에 대 한 지원의 활성화 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-119">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="83a65-120">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="83a65-120">enabled Attribute</span></span>  
  
|<span data-ttu-id="83a65-121">값</span><span class="sxs-lookup"><span data-stu-id="83a65-121">Value</span></span>|<span data-ttu-id="83a65-122">설명</span><span class="sxs-lookup"><span data-stu-id="83a65-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="83a65-123">true</span><span class="sxs-lookup"><span data-stu-id="83a65-123">true</span></span>|<span data-ttu-id="83a65-124">지정된 된.NET Framework 어셈블리의 구현 간에 이식성에 대 한 지원을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-124">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="83a65-125">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-125">This is the default.</span></span>|  
|<span data-ttu-id="83a65-126">False</span><span class="sxs-lookup"><span data-stu-id="83a65-126">false</span></span>|<span data-ttu-id="83a65-127">지정된 된.NET Framework 어셈블리의 구현 간에 이식성에 대 한 지원을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-127">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="83a65-128">이 통해 응용 프로그램을 지정된 된 어셈블리의 여러 구현 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-128">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83a65-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="83a65-129">Child Elements</span></span>  
 <span data-ttu-id="83a65-130">없음</span><span class="sxs-lookup"><span data-stu-id="83a65-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83a65-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="83a65-131">Parent Elements</span></span>  
  
|<span data-ttu-id="83a65-132">요소</span><span class="sxs-lookup"><span data-stu-id="83a65-132">Element</span></span>|<span data-ttu-id="83a65-133">설명</span><span class="sxs-lookup"><span data-stu-id="83a65-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="83a65-134">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="83a65-135">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-135">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="83a65-136">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-136">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83a65-137">설명</span><span class="sxs-lookup"><span data-stu-id="83a65-137">Remarks</span></span>  
 <span data-ttu-id="83a65-138">부터는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], 지원은.NET Framework의 두 구현 중 하나를 사용 하는 응용 프로그램에 대 한 자동으로 제공 됩니다 예를 들어.NET Framework 구현 또는.NET Framework for Silverlight 구현과 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-138">Beginning with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="83a65-139">특정.NET Framework 어셈블리의 두 가지 구현이 어셈블리 바인더를 통해 동등한 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-139">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="83a65-140">몇 가지 시나리오에서이 응용 프로그램 이식성 기능 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-140">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="83a65-141">이러한 시나리오에서는 `<supportPortability>` 기능을 해제 하는 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-141">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
 <span data-ttu-id="83a65-142">이러한 시나리오 중 하나는 특정 참조 어셈블리의 Silverlight 구현을 위해.NET Framework 및.NET Framework 구현을 참조 하는 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-142">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="83a65-143">예를 들어 Windows Presentation Foundation (WPF)에서 작성 된 XAML 디자이너를 디자이너의 사용자 인터페이스 및 Silverlight 구현과에 포함 된 WPF 하위 집합에 대 한 두는 WPF 데스크톱 구현을 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-143">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="83a65-144">기본적으로, 어셈블리 바인딩 시 두 어셈블리가 동등한 것으로 간주되기 때문에 서로 다른 참조를 사용할 경우 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-144">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="83a65-145">이 요소는 기본 동작을 사용 하지 않도록 설정 하 고 컴파일이 성공 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-145">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="83a65-146">공용 언어 런타임의 어셈블리 바인딩 논리에 정보를 전달 하려면 컴파일러에 대 한 순서 대로 사용 해야 합니다는 `/appconfig` 컴파일러 옵션을이 요소를 포함 하는 app.config 파일의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-146">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83a65-147">예제</span><span class="sxs-lookup"><span data-stu-id="83a65-147">Example</span></span>  
 <span data-ttu-id="83a65-148">다음 예제에서는 응용 프로그램에 두 구현 모두에 존재 하는 모든.NET Framework 어셈블리의 Silverlight 구현을 위해.NET Framework 및.NET Framework 구현에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-148">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="83a65-149">`/appconfig` 이 app.config 파일의 위치를 지정 하려면 컴파일러 옵션을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a65-149">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="83a65-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83a65-150">See Also</span></span>  
 [<span data-ttu-id="83a65-151">/appconfig (C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="83a65-151">/appconfig (C# Compiler Options)</span></span>](../../../../../docs/csharp/language-reference/compiler-options/appconfig-compiler-option.md)  
 [<span data-ttu-id="83a65-152">.NET framework 어셈블리 통합 개요</span><span class="sxs-lookup"><span data-stu-id="83a65-152">.NET Framework Assembly Unification Overview</span></span>](https://msdn.microsoft.com/library/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)
