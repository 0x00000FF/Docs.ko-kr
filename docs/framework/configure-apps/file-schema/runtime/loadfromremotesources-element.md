---
title: '&lt;loadFromRemoteSources&gt; 요소'
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3070e293fc335bb24dd1234007307773d152ceee
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611401"
---
# <a name="ltloadfromremotesourcesgt-element"></a><span data-ttu-id="60139-102">&lt;loadFromRemoteSources&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="60139-102">&lt;loadFromRemoteSources&gt; element</span></span>
<span data-ttu-id="60139-103">지정 여부를 원격 원본에서 로드 된 어셈블리의.NET Framework 4 이상 완전 신뢰를 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60139-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="60139-104">이 항목에서는 Visual Studio 프로젝트 오류 목록 또는 빌드 오류가 오류 메시지로 인해 연결 된, 참조 [방법: 웹에서 어셈블리를 사용 하 여 Visual Studio에서](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070)합니다.</span><span class="sxs-lookup"><span data-stu-id="60139-104">If you were directed to this topic because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span></span>  
  
 <span data-ttu-id="60139-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="60139-105">\<configuration></span></span>  
<span data-ttu-id="60139-106">\<runtime></span><span class="sxs-lookup"><span data-stu-id="60139-106">\<runtime></span></span>  
<span data-ttu-id="60139-107">\<loadFromRemoteSources></span><span class="sxs-lookup"><span data-stu-id="60139-107">\<loadFromRemoteSources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60139-108">구문</span><span class="sxs-lookup"><span data-stu-id="60139-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60139-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="60139-109">Attributes and elements</span></span>
 <span data-ttu-id="60139-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="60139-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60139-111">특성</span><span class="sxs-lookup"><span data-stu-id="60139-111">Attributes</span></span>  
  
|<span data-ttu-id="60139-112">특성</span><span class="sxs-lookup"><span data-stu-id="60139-112">Attribute</span></span>|<span data-ttu-id="60139-113">설명</span><span class="sxs-lookup"><span data-stu-id="60139-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="60139-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="60139-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="60139-115">지정 여부를 원격 원본에서 로드 된 어셈블리가 완전 신뢰를 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60139-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="60139-116">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="60139-116">enabled attribute</span></span>  
  
|<span data-ttu-id="60139-117">값</span><span class="sxs-lookup"><span data-stu-id="60139-117">Value</span></span>|<span data-ttu-id="60139-118">설명</span><span class="sxs-lookup"><span data-stu-id="60139-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="60139-119">원격 원본에서 응용 프로그램에 완전 신뢰를 부여 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="60139-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="60139-120">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="60139-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="60139-121">원격 원본에서 응용 프로그램에 완전 신뢰를 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="60139-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60139-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="60139-122">Child elements</span></span>  
 <span data-ttu-id="60139-123">없음</span><span class="sxs-lookup"><span data-stu-id="60139-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60139-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="60139-124">Parent elements</span></span>  
  
|<span data-ttu-id="60139-125">요소</span><span class="sxs-lookup"><span data-stu-id="60139-125">Element</span></span>|<span data-ttu-id="60139-126">설명</span><span class="sxs-lookup"><span data-stu-id="60139-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="60139-127">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="60139-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="60139-128">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="60139-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60139-129">설명</span><span class="sxs-lookup"><span data-stu-id="60139-129">Remarks</span></span>

<span data-ttu-id="60139-130">.NET Framework 3.5 및 이전 버전에서 원격 위치에서 어셈블리를 로드 하는 경우 어셈블리의 코드는이 로드 되는 영역에 따라 달라 지는 권한 부여 집합을 사용 하 여 부분 신뢰에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60139-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="60139-131">예를 들어, 웹 사이트에서 어셈블리를 로드 하는 경우 인터넷 영역으로 로드 하며 인터넷 권한 집합이 부여.</span><span class="sxs-lookup"><span data-stu-id="60139-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="60139-132">즉, 인터넷 샌드박스에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60139-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="60139-133">.NET Framework 4 부터는 코드 액세스 보안 (CA) 정책 비활성화 되 하 고 어셈블리는 완전 신뢰 수준에서 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60139-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="60139-134">일반적으로 사용 하 여 로드 된 어셈블리에 완전 신뢰를 부여는이 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> 있었던 이전에 샌드박스가 적용 된 메서드.</span><span class="sxs-lookup"><span data-stu-id="60139-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="60139-135">이 방지 하려면 원격 원본에서 로드 된 어셈블리에서 코드를 실행할 수는 기본적으로 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60139-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="60139-136">원격 어셈블리를 로드 하려고 하면 기본적으로는 <xref:System.IO.FileLoadException> 다음이 throw와 같은 예외 메시지:</span><span class="sxs-lookup"><span data-stu-id="60139-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

<span data-ttu-id="60139-137">에 어셈블리를 로드 하 고 해당 코드를 실행 하거나 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60139-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="60139-138">어셈블리에 대 한 샌드박스를 명시적으로 만들거나 (참조 [방법: 샌드박스에서 부분적으로 신뢰할 수 있는 코드 실행](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span><span class="sxs-lookup"><span data-stu-id="60139-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="60139-139">완전 신뢰에서 어셈블리의 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="60139-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="60139-140">구성 하 여이 작업을 수행 합니다 `<loadFromRemoteSources>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="60139-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="60139-141">이전 버전의.NET Framework에서 부분 신뢰로 실행 되는 어셈블리의.NET Framework 4 및 이후 버전에서 완전 신뢰에서 이제 실행 되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60139-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60139-142">어셈블리를 완전 신뢰로 실행 하지 않아야, 경우에이 구성 요소를 설정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="60139-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="60139-143">대신 샌드박스를 만들 <xref:System.AppDomain> 는 어셈블리를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="60139-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="60139-144">합니다 `enabled` 특성을 `<loadFromRemoteSources>` 요소 (CA) 코드 액세스 보안을 해제 하는 경우에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60139-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="60139-145">기본적으로 CAS 정책은.NET Framework 4 및 이후 버전에서 비활성화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="60139-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="60139-146">설정 하는 경우 `enabled` 에 `true`, 원격 어셈블리에 완전 신뢰가 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60139-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="60139-147">하는 경우 `enabled` 로 설정 되어 있지 `true`, <xref:System.IO.FileLoadException> 다음 조건 중 하나가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60139-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="60139-148">현재 도메인의 샌드 박싱 동작은.NET Framework 3.5에서의 동작과에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="60139-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="60139-149">샌드 박싱 할 필요가 현재 도메인과 CAS 정책을 사용 하지 않도록 설정할 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="60139-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="60139-150">로드 되는 어셈블리에서 아닙니다는 `MyComputer` 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="60139-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="60139-151">설정 된 `<loadFromRemoteSources>` 요소를 `true` 이 예외가 throw 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="60139-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="60139-152">하면 의존 하지 않고 샌드박스에 공용 언어 런타임 보안을 위해 로드 된 어셈블리를 지정할 수 있습니다 및에서 실행 하도록 허용 될 완전 신뢰 합니다.</span><span class="sxs-lookup"><span data-stu-id="60139-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="60139-153">노트</span><span class="sxs-lookup"><span data-stu-id="60139-153">Notes</span></span>

- <span data-ttu-id="60139-154">.NET Framework 4.5 및 이후 버전에서 로컬 네트워크 공유에 어셈블리가 완전 신뢰로 실행 기본적으로 사용 하도록 설정 해야 합니다 `<loadFromRemoteSources>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="60139-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="60139-155">응용 프로그램을 웹에서 복사한 경우, Windows에서는 해당 프로그램이 로컬 컴퓨터에 있더라도 웹 응용 프로그램이라는 플래그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="60139-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="60139-156">파일 속성을 변경 하 여 해당 명칭을 변경할 수 있습니다 또는 사용할 수는 `<loadFromRemoteSources>` 완전 신뢰 어셈블리에 부여할 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="60139-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="60139-157">또는 <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> 메서드를 사용하여 운영 체제가 웹에서 로드되었음을 표시하는 로컬 어셈블리를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60139-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="60139-158">표시 될 수 있습니다는 <xref:System.IO.FileLoadException> Windows Virtual PC 응용 프로그램을 실행 하는 응용 프로그램에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="60139-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="60139-159">이 호스팅 컴퓨터에서 연결 된 폴더에서 파일을 로드 하려고 할 때 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60139-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="60139-160">또한 통해 연결 된 폴더에서 파일을 로드 하려고 할 때 발생할 수 있습니다 [원격 데스크톱 서비스](https://go.microsoft.com/fwlink/?LinkId=182775) (터미널 서비스).</span><span class="sxs-lookup"><span data-stu-id="60139-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span></span> <span data-ttu-id="60139-161">예외를 방지 하려면 설정 `enabled` 에 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="60139-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="60139-162">구성 파일</span><span class="sxs-lookup"><span data-stu-id="60139-162">Configuration file</span></span>

<span data-ttu-id="60139-163">이 요소는 일반적으로 응용 프로그램 구성 파일에서 사용하지만 컨텍스트에 따라 다른 구성 파일에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60139-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="60139-164">자세한 내용은 문서 참조 [자세한 암시적 사용 하 여 CA 정책: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) .NET Security 블로그의 합니다.</span><span class="sxs-lookup"><span data-stu-id="60139-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="60139-165">예제</span><span class="sxs-lookup"><span data-stu-id="60139-165">Example</span></span>

<span data-ttu-id="60139-166">다음 예에서는 원격 원본에서 로드 된 어셈블리에 완전 신뢰를 부여 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="60139-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="60139-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60139-167">See also</span></span>

- [<span data-ttu-id="60139-168">CAS 정책의 암시적 사용: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="60139-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=266839)  
- [<span data-ttu-id="60139-169">방법: 샌드박스에서 부분적으로 신뢰할 수 있는 코드 실행</span><span class="sxs-lookup"><span data-stu-id="60139-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
- [<span data-ttu-id="60139-170">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="60139-170">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="60139-171">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="60139-171">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
