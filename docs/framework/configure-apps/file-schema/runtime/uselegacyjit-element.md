---
title: '&lt;useLegacyJit&gt; 요소'
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecf4d805feeb27a7c3fa08d2ab6dd05b6fff693a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648182"
---
# <a name="ltuselegacyjitgt-element"></a><span data-ttu-id="0d02e-102">&lt;useLegacyJit&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="0d02e-102">&lt;useLegacyJit&gt; Element</span></span>

<span data-ttu-id="0d02e-103">공용 언어 런타임이 Just-In-Time 컴파일에 레거시 64비트 JIT 컴파일러를 사용할지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
<span data-ttu-id="0d02e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0d02e-104">\<configuration></span></span>  
<span data-ttu-id="0d02e-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="0d02e-105">\<runtime></span></span>  
<span data-ttu-id="0d02e-106">\<useLegacyJit></span><span class="sxs-lookup"><span data-stu-id="0d02e-106">\<useLegacyJit></span></span>
  
## <a name="syntax"></a><span data-ttu-id="0d02e-107">구문</span><span class="sxs-lookup"><span data-stu-id="0d02e-107">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="0d02e-108">요소 이름을 `useLegacyJit` 대/소문자 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-108">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d02e-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0d02e-109">Attributes and elements</span></span>

<span data-ttu-id="0d02e-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d02e-111">특성</span><span class="sxs-lookup"><span data-stu-id="0d02e-111">Attributes</span></span>  
  
| <span data-ttu-id="0d02e-112">특성</span><span class="sxs-lookup"><span data-stu-id="0d02e-112">Attribute</span></span> | <span data-ttu-id="0d02e-113">설명</span><span class="sxs-lookup"><span data-stu-id="0d02e-113">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="0d02e-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-114">Required attribute.</span></span><br><br><span data-ttu-id="0d02e-115">런타임이 레거시 64 비트 JIT 컴파일러를 사용 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-115">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="0d02e-116">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="0d02e-116">enabled attribute</span></span>  
  
| <span data-ttu-id="0d02e-117">값</span><span class="sxs-lookup"><span data-stu-id="0d02e-117">Value</span></span> | <span data-ttu-id="0d02e-118">설명</span><span class="sxs-lookup"><span data-stu-id="0d02e-118">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="0d02e-119">0</span><span class="sxs-lookup"><span data-stu-id="0d02e-119">0</span></span>     | <span data-ttu-id="0d02e-120">공용 언어 런타임은.NET Framework 4.6 및 이상 버전에 포함 된 새로운 64 비트 JIT 컴파일러를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-120">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="0d02e-121">1</span><span class="sxs-lookup"><span data-stu-id="0d02e-121">1</span></span>     | <span data-ttu-id="0d02e-122">공용 언어 런타임에서 이전 64 비트 JIT 컴파일러를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-122">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="0d02e-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0d02e-123">Child elements</span></span>

<span data-ttu-id="0d02e-124">없음</span><span class="sxs-lookup"><span data-stu-id="0d02e-124">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="0d02e-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0d02e-125">Parent elements</span></span>  
  
| <span data-ttu-id="0d02e-126">요소</span><span class="sxs-lookup"><span data-stu-id="0d02e-126">Element</span></span>         | <span data-ttu-id="0d02e-127">설명</span><span class="sxs-lookup"><span data-stu-id="0d02e-127">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="0d02e-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="0d02e-129">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-129">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="0d02e-130">설명</span><span class="sxs-lookup"><span data-stu-id="0d02e-130">Remarks</span></span>  

<span data-ttu-id="0d02e-131">.NET Framework 4.6부터 공용 언어 런타임에서 사용 하 여 새 64 비트 컴파일러를 jit (JUST-IN-TIME) 컴파일에 기본적으로.</span><span class="sxs-lookup"><span data-stu-id="0d02e-131">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="0d02e-132">일부 경우에는 64 비트 JIT 컴파일러의 이전 버전에서 JIT-컴파일된 응용 프로그램 코드 로부터 동작의 차이에 따라서 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-132">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="0d02e-133">설정 하 여 합니다 `enabled` 특성을 `<useLegacyJit>` 요소를 `1`, 새로운 64 비트 JIT 컴파일러를 사용 하지 않도록 설정 하 고 대신 레거시 64 비트 JIT 컴파일러를 사용 하 여 앱을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-133">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d02e-134">`<useLegacyJit>` 요소 64 비트 JIT 컴파일의 경우에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-134">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="0d02e-135">32 비트 JIT 컴파일러를 사용 하 여 컴파일 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-135">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="0d02e-136">구성 파일 설정을 사용 하는 대신 다른 두 가지 방법으로 레거시 64 비트 JIT 컴파일러를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-136">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="0d02e-137">환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-137">Setting an environment variable</span></span>

  <span data-ttu-id="0d02e-138">설정 된 `COMPLUS_useLegacyJit` 환경 변수를 하나 `0` (새로운 64 비트 JIT 컴파일러 사용) 또는 `1` (이전 64 비트 JIT 컴파일러 사용):</span><span class="sxs-lookup"><span data-stu-id="0d02e-138">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="0d02e-139">환경 변수가 *전역 범위*, 즉, 영향을 주는 모든 응용 프로그램 컴퓨터에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-139">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="0d02e-140">경우 설정 재정의할 수 있습니다 응용 프로그램 구성 파일 설정에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-140">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="0d02e-141">환경 변수 이름이 대/소문자 구분 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-141">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="0d02e-142">레지스트리 키 추가</span><span class="sxs-lookup"><span data-stu-id="0d02e-142">Adding a registry key</span></span>

  <span data-ttu-id="0d02e-143">추가 하 여 레거시 64 비트 JIT 컴파일러를 사용할 수는 `REG_DWORD` 값 중 하나는 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` 또는 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` 레지스트리 키.</span><span class="sxs-lookup"><span data-stu-id="0d02e-143">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="0d02e-144">값 이름은 `useLegacyJit`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-144">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="0d02e-145">값이 0 이면 새로운 컴파일러 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-145">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="0d02e-146">값이 1 이면 레거시 64 비트 JIT 컴파일러를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-146">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="0d02e-147">레지스트리 값 이름이 대/소문자 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-147">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="0d02e-148">값을 추가 합니다 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` 키 컴퓨터에서 실행 되는 모든 앱에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-148">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="0d02e-149">값을 추가 합니다 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` 키 현재 사용자가 실행 되는 모든 앱에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-149">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="0d02e-150">컴퓨터를 여러 사용자 계정으로 구성 된 경우 현재 사용자가 실행 하는 앱만 영향을 받습니다를 값으로 다른 사용자에 대 한 레지스트리 키를 추가 하지 않으면.</span><span class="sxs-lookup"><span data-stu-id="0d02e-150">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="0d02e-151">추가 된 `<useLegacyJit>` 요소 구성 파일에 있는 경우 레지스트리 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-151">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d02e-152">예제</span><span class="sxs-lookup"><span data-stu-id="0d02e-152">Example</span></span>  

<span data-ttu-id="0d02e-153">다음 구성 파일 새 64 비트 JIT 컴파일러를 사용 하 여 컴파일 사용 하지 않도록 설정 하 고 대신 레거시 64 비트 JIT 컴파일러를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d02e-153">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d02e-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d02e-154">See also</span></span>

- [<span data-ttu-id="0d02e-155">\<런타임 > 요소</span><span class="sxs-lookup"><span data-stu-id="0d02e-155">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [<span data-ttu-id="0d02e-156">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="0d02e-156">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
- [<span data-ttu-id="0d02e-157">완화: 새로운 64 비트 JIT 컴파일러</span><span class="sxs-lookup"><span data-stu-id="0d02e-157">Mitigation: New 64-bit JIT Compiler</span></span>](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)
