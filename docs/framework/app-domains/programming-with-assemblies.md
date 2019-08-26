---
title: 어셈블리를 사용한 프로그래밍
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f427e2260fb26be7db0a29c47f38a3cb32dd34e9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921429"
---
# <a name="programming-with-assemblies"></a><span data-ttu-id="4c5ff-102">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="4c5ff-102">Programming with Assemblies</span></span>
<span data-ttu-id="4c5ff-103">어셈블리는 .NET Framework의 문서 블록으로서 배포, 버전 제어, 다시 사용, 활성화 범위 지정 및 보안 권한의 기본 단위를 형성합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-103">Assemblies are the building blocks of the .NET Framework; they form the fundamental unit of deployment, version control, reuse, activation scoping, and security permissions.</span></span> <span data-ttu-id="4c5ff-104">어셈블리는 형식 구현을 인식하는 데 필요한 정보와 함께 공용 언어 런타임을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-104">An assembly provides the common language runtime with the information it needs to be aware of type implementations.</span></span> <span data-ttu-id="4c5ff-105">어셈블리는 서로 함께 사용되어 논리적 기능 단위를 형성하도록 빌드되는 형식 및 리소스의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-105">It is a collection of types and resources that are built to work together and form a logical unit of functionality.</span></span> <span data-ttu-id="4c5ff-106">런타임에 대해, 형식은 어셈블리 컨텍스트 외부에 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-106">To the runtime, a type does not exist outside the context of an assembly.</span></span>  
  
 <span data-ttu-id="4c5ff-107">이 섹션에서는 모듈을 만들고, 모듈에서 어셈블리를 만들고, 키 쌍을 만들고, 강력한 이름으로 어셈블리에 서명하고, 전역 어셈블리 캐시에 어셈블리를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-107">This section describes how to create modules, create assemblies from modules, create a key pair and sign an assembly with a strong name, and install an assembly into the global assembly cache.</span></span> <span data-ttu-id="4c5ff-108">또한 이 섹션에서는 [MSIL 디스어셈블러(Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하여 어셈블리 매니페스트 정보를 보는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-108">In addition, this section describes how to use the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view assembly manifest information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c5ff-109">.NET Framework 버전 2.0부터 런타임은 현재 로드된 런타임보다 높은 버전 번호를 가진 .NET Framework 버전으로 컴파일된 어셈블리를 로드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-109">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="4c5ff-110">이는 버전 번호의 주 버전 및 부 버전 구성 요소 조합에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-110">This applies to the combination of the major and minor components of the version number.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c5ff-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="4c5ff-111">In This Section</span></span>  
 [<span data-ttu-id="4c5ff-112">어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="4c5ff-112">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 <span data-ttu-id="4c5ff-113">단일 파일 어셈블리와 다중 파일 어셈블리에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-113">Provides an overview of single-file and multifile assemblies.</span></span>  
  
 [<span data-ttu-id="4c5ff-114">어셈블리 이름</span><span class="sxs-lookup"><span data-stu-id="4c5ff-114">Assembly Names</span></span>](../../../docs/framework/app-domains/assembly-names.md)  
 <span data-ttu-id="4c5ff-115">어셈블리 명명에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-115">Provides an overview of assembly naming.</span></span>  
  
 [<span data-ttu-id="4c5ff-116">방법: 어셈블리의 정규화된 이름 식별</span><span class="sxs-lookup"><span data-stu-id="4c5ff-116">How to: Determine an Assembly's Fully Qualified Name</span></span>](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 <span data-ttu-id="4c5ff-117">어셈블리의 정규화된 이름을 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-117">Describes how to determine the fully qualified name of an assembly.</span></span>  
  
 [<span data-ttu-id="4c5ff-118">완전 신뢰 모드에서 인트라넷 애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="4c5ff-118">Running Intranet Applications in Full Trust</span></span>](../../../docs/framework/app-domains/running-intranet-applications-in-full-trust.md)  
 <span data-ttu-id="4c5ff-119">인트라넷 공유에 있는 완전 신뢰 어셈블리에 대해 레거시 보안 정책을 지정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-119">Describes how to specify legacy security policy for full-trust assemblies on an intranet share.</span></span>  
  
 [<span data-ttu-id="4c5ff-120">어셈블리 위치</span><span class="sxs-lookup"><span data-stu-id="4c5ff-120">Assembly Location</span></span>](../../../docs/framework/app-domains/assembly-location.md)  
 <span data-ttu-id="4c5ff-121">어셈블리를 찾을 위치를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-121">Provides an overview of where to locate assemblies.</span></span>  
  
 [<span data-ttu-id="4c5ff-122">방법: 단일 파일 어셈블리 빌드</span><span class="sxs-lookup"><span data-stu-id="4c5ff-122">How to: Build a Single-File Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 <span data-ttu-id="4c5ff-123">단일 파일 어셈블리를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-123">Describes how to create a single-file assembly.</span></span>  
  
 [<span data-ttu-id="4c5ff-124">다중 파일 어셈블리</span><span class="sxs-lookup"><span data-stu-id="4c5ff-124">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)  
 <span data-ttu-id="4c5ff-125">다중 파일 어셈블리를 만드는 이유를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-125">Describes reasons for creating multifile assemblies.</span></span>  
  
 [<span data-ttu-id="4c5ff-126">방법: 다중 파일 어셈블리 빌드</span><span class="sxs-lookup"><span data-stu-id="4c5ff-126">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 <span data-ttu-id="4c5ff-127">다중 파일 어셈블리를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-127">Describes how to create a multifile assembly.</span></span>  
  
 [<span data-ttu-id="4c5ff-128">어셈블리 특성 설정</span><span class="sxs-lookup"><span data-stu-id="4c5ff-128">Setting Assembly Attributes</span></span>](../../../docs/framework/app-domains/set-assembly-attributes.md)  
 <span data-ttu-id="4c5ff-129">어셈블리 특성 및 설정 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-129">Describes assembly attributes and how to set them.</span></span>  
  
 [<span data-ttu-id="4c5ff-130">강력한 이름의 어셈블리 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="4c5ff-130">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 <span data-ttu-id="4c5ff-131">강력한 이름으로 어셈블리에 서명하는 방법과 이유를 설명하고 방법 도움말 항목을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-131">Describes how and why you sign an assembly with a strong name, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="4c5ff-132">어셈블리 서명 연기</span><span class="sxs-lookup"><span data-stu-id="4c5ff-132">Delay Signing an Assembly</span></span>](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 <span data-ttu-id="4c5ff-133">어셈블리 서명을 연기하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-133">Describes how to delay-sign an assembly.</span></span>  
  
 [<span data-ttu-id="4c5ff-134">어셈블리 및 전역 어셈블리 캐시 사용</span><span class="sxs-lookup"><span data-stu-id="4c5ff-134">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 <span data-ttu-id="4c5ff-135">전역 어셈블리 캐시에 어셈블리를 추가하는 방법과 이유를 설명하고 방법 도움말 항목을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-135">Describes how and why you add assemblies to the global assembly cache, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="4c5ff-136">방법: 어셈블리 콘텐츠 보기</span><span class="sxs-lookup"><span data-stu-id="4c5ff-136">How to: View Assembly Contents</span></span>](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 <span data-ttu-id="4c5ff-137">MSIL 디스어셈블러(Ildasm.exe)를 사용하여 어셈블리 내용을 보는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-137">Describes how to use the MSIL Disassembler (Ildasm.exe) to view assembly contents.</span></span>  
  
 [<span data-ttu-id="4c5ff-138">공용 언어 런타임의 형식 전달</span><span class="sxs-lookup"><span data-stu-id="4c5ff-138">Type Forwarding in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/type-forwarding-in-the-common-language-runtime.md)  
 <span data-ttu-id="4c5ff-139">형식 전달을 사용하여 기존 애플리케이션을 손상하지 않고 형식을 다른 어셈블리로 이동하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-139">Describes how to use type forwarding to move a type into a different assembly without breaking existing applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4c5ff-140">참조</span><span class="sxs-lookup"><span data-stu-id="4c5ff-140">Reference</span></span>  
 <xref:System.Reflection.Assembly>  
 <span data-ttu-id="4c5ff-141">어셈블리를 나타내는 .NET Framework 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-141">The .NET Framework class that represents an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4c5ff-142">관련 단원</span><span class="sxs-lookup"><span data-stu-id="4c5ff-142">Related Sections</span></span>  
 [<span data-ttu-id="4c5ff-143">방법: 어셈블리에서 형식 및 멤버 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="4c5ff-143">How to: Obtain Type and Member Information from an Assembly</span></span>](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 <span data-ttu-id="4c5ff-144">프로그래밍 방식으로 어셈블리에서 형식 및 기타 정보를 가져오는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-144">Describes how to programmatically obtain type and other information from an assembly.</span></span>  
  
 [<span data-ttu-id="4c5ff-145">공용 언어 런타임의 어셈블리</span><span class="sxs-lookup"><span data-stu-id="4c5ff-145">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="4c5ff-146">공용 언어 런타임 어셈블리의 개념을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-146">Provides a conceptual overview of common language runtime assemblies.</span></span>  
  
 [<span data-ttu-id="4c5ff-147">어셈블리 버전 관리</span><span class="sxs-lookup"><span data-stu-id="4c5ff-147">Assembly Versioning</span></span>](../../../docs/framework/app-domains/assembly-versioning.md)  
 <span data-ttu-id="4c5ff-148">어셈블리 바인딩과 <xref:System.Reflection.AssemblyVersionAttribute> 및 <xref:System.Reflection.AssemblyInformationalVersionAttribute> 특성에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-148">Provides an overview of assembly binding and of the <xref:System.Reflection.AssemblyVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes.</span></span>  
  
 [<span data-ttu-id="4c5ff-149">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="4c5ff-149">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 <span data-ttu-id="4c5ff-150">런타임에서 바인딩 요청을 충족하는 데 사용할 어셈블리를 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-150">Describes how the runtime determines which assembly to use to fulfill a binding request.</span></span>  
  
 [<span data-ttu-id="4c5ff-151">리플렉션</span><span class="sxs-lookup"><span data-stu-id="4c5ff-151">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="4c5ff-152">**Reflection** 클래스를 사용하여 어셈블리에 대한 정보를 얻는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5ff-152">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
