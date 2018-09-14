---
title: '&lt;속성&gt; 요소(.NET 네이티브)'
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47ed75d377814a740edece2b6a69e44acbd8ef0c
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45527713"
---
# <a name="ltpropertygt-element-net-native"></a><span data-ttu-id="8c49b-102">&lt;속성&gt; 요소(.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="8c49b-102">&lt;Property&gt; Element (.NET Native)</span></span>
<span data-ttu-id="8c49b-103">런타임 리플렉션 정책을 속성에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c49b-104">구문</span><span class="sxs-lookup"><span data-stu-id="8c49b-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c49b-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8c49b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8c49b-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c49b-107">특성</span><span class="sxs-lookup"><span data-stu-id="8c49b-107">Attributes</span></span>  
  
|<span data-ttu-id="8c49b-108">특성</span><span class="sxs-lookup"><span data-stu-id="8c49b-108">Attribute</span></span>|<span data-ttu-id="8c49b-109">특성 형식</span><span class="sxs-lookup"><span data-stu-id="8c49b-109">Attribute type</span></span>|<span data-ttu-id="8c49b-110">설명</span><span class="sxs-lookup"><span data-stu-id="8c49b-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="8c49b-111">일반</span><span class="sxs-lookup"><span data-stu-id="8c49b-111">General</span></span>|<span data-ttu-id="8c49b-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-112">Required attribute.</span></span> <span data-ttu-id="8c49b-113">속성 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="8c49b-114">반사</span><span class="sxs-lookup"><span data-stu-id="8c49b-114">Reflection</span></span>|<span data-ttu-id="8c49b-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-115">Optional attribute.</span></span> <span data-ttu-id="8c49b-116">속성에 대한 정보 쿼리 또는 속성 열거는 제어하지만 런타임에 동적 호출을 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="8c49b-117">반사</span><span class="sxs-lookup"><span data-stu-id="8c49b-117">Reflection</span></span>|<span data-ttu-id="8c49b-118">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-118">Optional attribute.</span></span> <span data-ttu-id="8c49b-119">동적 프로그래밍을 수행할 수 있도록 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="8c49b-120">이 정책을 통해 런타임에 속성을 동적으로 설정하거나 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="8c49b-121">Serialization</span><span class="sxs-lookup"><span data-stu-id="8c49b-121">Serialization</span></span>|<span data-ttu-id="8c49b-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-122">Optional attribute.</span></span> <span data-ttu-id="8c49b-123">Newtonsoft JSON serializer 등의 라이브러리를 통해 형식 인스턴스를 serialize하거나 데이터 바인딩에 사용할 수 있도록 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="8c49b-124">Name 특성</span><span class="sxs-lookup"><span data-stu-id="8c49b-124">Name attribute</span></span>  
  
|<span data-ttu-id="8c49b-125">값</span><span class="sxs-lookup"><span data-stu-id="8c49b-125">Value</span></span>|<span data-ttu-id="8c49b-126">설명</span><span class="sxs-lookup"><span data-stu-id="8c49b-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8c49b-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="8c49b-127">*method_name*</span></span>|<span data-ttu-id="8c49b-128">속성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-128">The property name.</span></span> <span data-ttu-id="8c49b-129">속성의 형식은 부모 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 또는 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-129">The type of the property is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="8c49b-130">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="8c49b-130">All other attributes</span></span>  
  
|<span data-ttu-id="8c49b-131">값</span><span class="sxs-lookup"><span data-stu-id="8c49b-131">Value</span></span>|<span data-ttu-id="8c49b-132">설명</span><span class="sxs-lookup"><span data-stu-id="8c49b-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8c49b-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="8c49b-133">*policy_setting*</span></span>|<span data-ttu-id="8c49b-134">속성에 대해 이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="8c49b-135">가능한 값은 `Auto`, `Excluded`, `Included` 및 `Required`입니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="8c49b-136">자세한 내용은 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c49b-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c49b-137">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8c49b-137">Child Elements</span></span>  
 <span data-ttu-id="8c49b-138">없음</span><span class="sxs-lookup"><span data-stu-id="8c49b-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c49b-139">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8c49b-139">Parent Elements</span></span>  
  
|<span data-ttu-id="8c49b-140">요소</span><span class="sxs-lookup"><span data-stu-id="8c49b-140">Element</span></span>|<span data-ttu-id="8c49b-141">설명</span><span class="sxs-lookup"><span data-stu-id="8c49b-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c49b-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="8c49b-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="8c49b-143">형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="8c49b-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="8c49b-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="8c49b-145">생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c49b-146">설명</span><span class="sxs-lookup"><span data-stu-id="8c49b-146">Remarks</span></span>  
 <span data-ttu-id="8c49b-147">속성의 정책이 명시적으로 정의되어 있지 않으면 부모 요소의 런타임 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-147">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c49b-148">예제</span><span class="sxs-lookup"><span data-stu-id="8c49b-148">Example</span></span>  
 <span data-ttu-id="8c49b-149">다음 예제에서는 리플렉션을 사용하여 `Book` 개체를 인스턴스화하고 해당 속성 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-149">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="8c49b-150">프로젝트의 원본 default.rd.xml 파일은 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-150">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="8c49b-151">이 파일은 `All` 클래스에 대해 `Activate` 값을 `Book` 정책에 적용합니다. 따라서 리플렉션을 통해 클래스 생성자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-151">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="8c49b-152">`Browse`에 대한 `Book` 정책은 부모 네임스페이스에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-152">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="8c49b-153">이 정책은 런타임에 메타데이터를 사용할 수 있도록 하는 `Required Public`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-153">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="8c49b-154">다음은 예제의 소스 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-154">The following is the source code for the example.</span></span> <span data-ttu-id="8c49b-155">`outputBlock` 변수는 [TextBlock](https://msdn.microsoft.com/library/windows.ui.xaml.controls.textblock.aspx) 제어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-155">The `outputBlock` variable represents a [TextBlock](https://msdn.microsoft.com/library/windows.ui.xaml.controls.textblock.aspx) control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="8c49b-156">그러나 이 예제를 컴파일하고 실행하면 [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-156">However, compiling and executing this example throws a [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="8c49b-157">`Book` 형식에 대해 메타데이터는 제공했지만 속성 getter의 구현은 동적으로 제공하지 못했기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-157">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="8c49b-158">두 가지 방법 중 하나를 사용하여 이 오류를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-158">We can correct this error by either in one of two ways:</span></span>  
  
-   <span data-ttu-id="8c49b-159">`Book` 형식에 대해 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 요소에서 `Dynamic` 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-159">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element.</span></span>  
  
-   <span data-ttu-id="8c49b-160">다음 default.rd.xml 파일에서와 같이 getter를 호출할 각 속성에 대해 중첩된 [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8c49b-160">By adding a nested [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
    ```xml  
    <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
       <Application>  
          <Namespace Name="LibraryApplications"  Browse="Required Public" >  
             <Type Name="Book"   Activate="All" >  
                <Property Name="Title" Dynamic="Required" />  
                <Property Name="Author" Dynamic="Required" />  
                  <Property Name="ISBN" Dynamic="Required" />  
             </Type>  
          </Namespace>  
       </Application>  
    </Directives>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8c49b-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c49b-161">See Also</span></span>  
 [<span data-ttu-id="8c49b-162">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="8c49b-162">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="8c49b-163">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="8c49b-163">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="8c49b-164">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="8c49b-164">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
